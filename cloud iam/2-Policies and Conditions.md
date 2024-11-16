# Policies and Conditions


In **Google Cloud IAM**, oltre a definire **ruoli** e **permessi**, puoi anche specificare **condizioni** per determinare **quando** un ruolo è valido. Le **condizioni IAM** 
permettono di applicare controlli di accesso più granuli, in base a fattori come l'ora del giorno, l'indirizzo IP, o altre caratteristiche contestuali.



Le **condizioni IAM** ti permettono di applicare controlli più granuli per la gestione dell'accesso alle risorse Google Cloud, introducendo una gestione del **"quando"** un ruolo è valido. Questo è utile in scenari complessi, come quando si vuole limitare l'accesso in base a orari specifici, indirizzi IP o altre caratteristiche contestuali. Le policy con condizioni  offrono maggiore flessibilità e controllo sulla sicurezza.

---

### **1. Cos'è una Policy IAM?**

Una **policy IAM** è una combinazione di **principali**, **ruoli** e **condizioni** applicate a risorse specifiche.

- **Principali**: Gli utenti o le entità (es. account, gruppi, service account).
- **Ruoli**: I permessi assegnati a un principale, come `roles/viewer`, `roles/editor`, o ruoli personalizzati.
- **Condizioni**: Restrizioni contestuali che permettono di applicare un ruolo solo in determinati scenari.

La policy IAM definisce *chi può fare cosa* su *quali risorse*. Le **condizioni IAM** estendono questa logica, permettendo di **limitare l'accesso** in base a criteri specifici.

---

### **2. Condizioni IAM**

Le **condizioni IAM** aggiungono un ulteriore livello di controllo per l'accesso. Queste condizioni sono **filtri** che devono essere soddisfatti affinché un ruolo venga applicato a un'entità. 

#### **Sintassi delle Condizioni IAM**:
Una condizione IAM ha la seguente sintassi:
- **Condizione**: Una serie di **chiavi** (attributi), **operatori** (come `=`, `!=`, `>`, `<`) e **valori**.
- **Esempio**:
   - Chiave: `request.time`
   - Operatore: `>=`
   - Valore: `2024-01-01T00:00:00Z`

### **Esempi di Condizioni IAM**

1. **Restrizione in base al tempo**:
   Si può limitare l'accesso a determinate risorse solo in specifici intervalli temporali:
   ```yaml
   - title: "Accesso a risorse solo dopo una certa data"
     description: "Permette l'accesso solo dopo il 1° gennaio 2024"
     condition:
       title: "Accesso limitato a tempo"
       expression: "request.time >= timestamp('2024-01-01T00:00:00Z')"
   ```

2. **Restrizione in base all'indirizzo IP**:
   Limita l'accesso a una risorsa solo se la richiesta proviene da una determinata rete o indirizzo IP:
   ```yaml
   - title: "Accesso da IP specifici"
     description: "Permette l'accesso solo dall'indirizzo IP specifico"
     condition:
       title: "Accesso da rete aziendale"
       expression: "origin.ip == '192.168.1.100'"
   ```

3. **Restrizione in base a un attributo di una risorsa**:
   Si può limitare l'accesso in base a un'etichetta o un altro attributo associato a una risorsa. Ad esempio, si può permettere l'accesso solo alle risorse contrassegnate con un'etichetta specifica:
   ```yaml
   - title: "Accesso solo a risorse etichettate"
     description: "Permette l'accesso solo se la risorsa è etichettata con 'env=production'"
     condition:
       title: "Accesso limitato a risorse di produzione"
       expression: "resource.labels.env == 'production'"
   ```

---

### **3. Come Creare una Policy IAM con Condizioni**

Possiamo definire una policy IAM con condizioni tramite la **Console Google Cloud**, la **gcloud CLI** o tramite l'**API**.

#### **Aggiungere una Condizione tramite `gcloud`**

Per assegnare un ruolo con una condizione a un principale (utente, gruppo, service account) tramite `gcloud`, possiamo usare il comando `add-iam-policy-binding` con l'opzione `--condition`.

Esempio: Assegnare il ruolo `roles/storage.objectViewer` con una condizione che consente l'accesso solo se la richiesta proviene dall'indirizzo IP specificato:

```bash
gcloud projects add-iam-policy-binding <PROJECT_ID> \
  --member="user:utente@example.com" \
  --role="roles/storage.objectViewer" \
  --condition="title='Accesso limitato a IP aziendale'\
  expression='origin.ip == \"192.168.1.100\"'"
```

#### **Esempio di policy con condizione**:
```yaml
bindings:
- members:
  - user:utente@example.com
  role: roles/storage.objectViewer
  condition:
    title: "Accesso limitato a IP aziendale"
    description: "Permette l'accesso solo da indirizzo IP specifico"
    expression: "origin.ip == '192.168.1.100'"
etag: BwWUxxlF+hg=
version: 1
```

---

### **4. Limiti delle Condizioni IAM**

Le condizioni IAM possono essere molto potenti, ma ci sono alcune limitazioni:
- **Semplicità**: Le condizioni sono limitate a un linguaggio di espressione semplice e non possono supportare operazioni complesse come calcoli matematici avanzati.
- **Supporto**: Non tutti i ruoli supportano l'uso delle condizioni. I ruoli di sistema o alcuni ruoli ad alta responsabilità potrebbero non supportare le condizioni.
- **Ambito delle condizioni**: Le condizioni possono essere applicate solo a livello di ruoli, non a singoli permessi all'interno di un ruolo.

---

### **5. Best Practices per l'uso delle Condizioni IAM**

- **Principio del privilegio minimo**: Assicurati che le condizioni siano il più restrittive possibile per garantire l'accesso solo quando è strettamente necessario.
- **Audit e monitoraggio**: Usa **Cloud Audit Logs** per monitorare l'applicazione delle policy IAM con condizioni.
- **Test accurato**: Verifica accuratamente le condizioni, per evitare di bloccare l'accesso inaspettatamente o di consentirlo erroneamente.

---



ULTERIORI ESEMPI :


### **Esempio di Policy Statement Completo**

```yaml
bindings:
  - members:
      - user:utente@example.com  # L'utente a cui assegnare il ruolo
    role: roles/storage.objectViewer  # Ruolo assegnato
    condition:
      title: "Accesso limitato a IP aziendale"
      description: "Permette l'accesso solo se la richiesta proviene dall'indirizzo IP aziendale"
      expression: "origin.ip == '192.168.1.100'"  # Condizione: solo IP specifico
  - members:
      - serviceAccount:service-account@example.com  # Service account a cui assegnare il ruolo
    role: roles/storage.objectAdmin  # Ruolo con permessi amministrativi sugli oggetti di Storage
    condition:
      title: "Accesso solo durante l'orario lavorativo"
      description: "Permette l'accesso solo dalle 9:00 alle 18:00"
      expression: "request.time >= timestamp('2024-01-01T09:00:00Z') && request.time <= timestamp('2024-01-01T18:00:00Z')"  # Condizione: solo durante l'orario di lavoro
etag: BwWUxxlF+hg=  # Identificatore univoco della policy, utilizzato per la gestione della versione
version: 1  # Versione della policy
```

### **Spiegazione dell'Esempio**

1. **`members`**: Qui vengono definiti gli utenti o gli account a cui viene assegnato un ruolo. In questo esempio:
   - Un **utente** (`utente@example.com`).
   - Un **service account** (`service-account@example.com`).
   
2. **`role`**: Il ruolo che viene assegnato a ciascun membro. In questo caso:
   - `roles/storage.objectViewer`: Permette l'accesso in sola lettura agli oggetti in un bucket di Cloud Storage.
   - `roles/storage.objectAdmin`: Consente la gestione completa degli oggetti nel bucket di Cloud Storage.

3. **`condition`**: Le condizioni sono applicate per limitare l'accesso in base a determinati criteri:
   - La prima condizione limita l'accesso al ruolo di lettore solo se la richiesta proviene da un indirizzo IP specifico (`192.168.1.100`).
   - La seconda condizione limita l'accesso al service account solo durante l'orario lavorativo (dalle 9:00 alle 18:00).

4. **`etag`**: Questo è un identificatore univoco per la versione della policy. Viene utilizzato per il controllo delle versioni e per evitare conflitti quando si aggiorna la policy.

5. **`version`**: Indica la versione della policy. Google Cloud attualmente supporta `version: 1`.

---

### **Applicazione della Policy**

Puoi applicare questa policy nel tuo progetto utilizzando il comando `gcloud`, specificando la policy tramite un file YAML. Ecco un esempio di come applicare questa policy a livello di progetto:

1. Crea un file YAML (ad esempio, `iam-policy.yaml`) con il contenuto sopra.

2. Esegui il comando per applicare la policy:

```bash
gcloud projects set-iam-policy <PROJECT_ID> iam-policy.yaml
```

### **Dettagli Importanti**

- **Condizioni IAM**: Le condizioni ci permettono di specificare **quando** un ruolo può essere assegnato, per esempio in base a **orari**, **indirizzi IP**, **etichettature delle risorse** e altro.
- **Versione della Policy**: Ogni modifica alla policy (aggiunta di membri, ruoli o condizioni) crea una nuova versione della policy.
- **Uso di etag**: È utile quando stai aggiornando o gestendo la policy e vuoi evitare conflitti di concorrenza.

---

### **Altri Esempi di Condizioni IAM**

- **Controllo basato su etichette di risorsa**:
  ```yaml
  expression: "resource.labels.env == 'production'"
  ```

- **Controllo basato su tipo di risorsa**:
  ```yaml
  expression: "resource.type == 'compute.googleapis.com/Instance'"
  ```



°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°Policy Limitations°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°



---

### **1. Limiti di Complessità delle Condizioni IAM**

Le **condizioni IAM** consentono di applicare restrizioni basate su vari attributi, ma hanno una sintassi e una logica relativamente semplici. Le principali limitazioni sono:

- **Espressioni limitate**: Le condizioni possono essere espresse solo con operatori e funzioni semplici. Non è possibile eseguire operazioni complesse o calcoli matematici avanzati.
  
  - **Esempio di espressione semplice**:
    ```yaml
    expression: "request.time >= timestamp('2024-01-01T09:00:00Z')"
    ```

- **No funzioni avanzate**: Non si può utilizzare funzioni di aggregazione o calcoli complessi nelle espressioni delle condizioni. Ad esempio, non si può sommare o sottrarre date in modo dinamico all'interno di una condizione IAM.

- **Limitata interazione con altri sistemi**: Le condizioni IAM possono fare riferimento solo ad alcune informazioni specifiche come `request.time`, `origin.ip`, e altre variabili limitate a contesti Google Cloud, ma non possono interagire direttamente con dati esterni o API di terze parti.

---

### **2. Limiti di Ruoli e Permessi**

Google Cloud IAM supporta l'assegnazione di **ruoli predefiniti** (come `roles/viewer`, `roles/editor`, ecc.) o **ruoli personalizzati**, ma ci sono alcune limitazioni:

- **Ruoli predefiniti vs. Ruoli personalizzati**:
  - I **ruoli predefiniti** sono generalmente ampi e assegnano una serie di permessi per intere categorie di risorse.
  - I **ruoli personalizzati** sono più granulari, ma c'è un limite al numero di permessi che possono essere inclusi in un singolo ruolo personalizzato. Questo può diventare un problema se si ha bisogno di controlli di accesso molto specifici.
  
- **Limitazioni dei permessi granulari**: In alcuni casi, Google Cloud non fornisce permessi granulari per risorse specifiche, il che significa che le operazioni su una risorsa potrebbero essere troppo generali. Ad esempio, potremmo non riuscire a concedere il permesso di **visualizzare** una risorsa senza anche consentire l'accesso per **modificarla**.

---

### **3. Limitazioni nell'Ereditarietà delle Policy**

Le policy IAM sono **ereditarie** nella gerarchia delle risorse (Organizzazione > Cartella > Progetto > Risorsa), ma l'eredità ha delle **limitazioni**:

- **Overriding delle policy**: Se si assegna un ruolo a livello di progetto o risorsa, questo può sovrascrivere le policy ereditarie dalla cartella o dall'organizzazione. Tuttavia, non si può applicare **esclusioni** dirette o **combinazioni complesse** di policy su un singolo livello.
  
- **Incoerenza tra livelli**: Le policy assegnate a un livello (ad esempio, un progetto) possono entrare in conflitto con quelle assegnate a un altro livello (ad esempio, l'organizzazione). Ciò può creare confusione nella gestione dei permessi.

---

### **4. Limitazioni con il Supporto di Condizioni in Alcuni Ruoli**

Non tutti i **ruoli IAM** supportano l'uso delle **condizioni**. Alcuni ruoli, in particolare quelli **sistemici** o **ad alta responsabilità**, come `roles/owner`, non supportano l'uso delle condizioni IAM. Questo potrebbe limitare la capacità di applicare restrizioni basate su condizioni specifiche per questi ruoli.

- **Ruoli ad alta responsabilità**: Ruoli come `roles/owner` e `roles/editor` tendono ad avere permessi molto ampi, e non è possibile aggiungere condizioni per limitare questi permessi in modo fine.

---

### **5. Limiti di Identificazione dei Principali**

Quando si assegna una policy IAM, bisogna identificare il **principale** (ad esempio, utente, gruppo, service account), ma ci sono delle limitazioni nella gestione dei principali:

- **Identificazioni complesse**: La gestione di **gruppi** di utenti (ad esempio, gruppi di Google) può risultare meno flessibile rispetto all'uso di singoli account o service account. A volte, l'assegnazione di permessi a un gruppo di persone può risultare più difficile rispetto all'assegnazione a singoli membri.
  
- **Service accounts**: L'uso dei **service accounts** per l'accesso alle risorse è potente, ma in alcuni casi può essere difficile da gestire, specialmente se sono coinvolti più service account o ruoli diversi per ciascuno.

---

### **6. Limiti del Numero di Membri e Ruoli per Policy IAM**

Ci sono delle **limitazioni numeriche** nella configurazione delle policy IAM, come:

- **Numero di membri per ruolo**: C'è un limite al numero di **membri** che puoi aggiungere a una policy per un determinato ruolo.
- **Numero di ruoli per membro**: Un membro (utente o service account) può essere associato a un numero massimo di **ruoli** in una policy.

---

### **7. Limitazioni per le API di IAM**

- **Lentezza nelle modifiche**: Le modifiche alle **policy IAM** potrebbero richiedere del tempo per propagarsi attraverso tutte le risorse, il che può comportare un certo ritardo nell'applicazione delle nuove regole.
- **Limitazioni nelle operazioni tramite API**: Le API di IAM, che vengono utilizzate per configurare e gestire le policy, hanno dei limiti in termini di **numero di richieste** o di **complessità** delle query (ad esempio, l'uso di espressioni condizionali molto complesse).

---

### **8. Limiti di Auditing e Tracciamento delle Policy**

Anche se Google Cloud fornisce strumenti per il **monitoraggio** delle attività e per l'audit delle policy, ci sono alcune limitazioni:

- **Non tutte le azioni sono tracciate**: Alcuni cambiamenti a livello di risorse o configurazioni potrebbero non essere completamente tracciati da Google Cloud Audit Logs.
- **Accesso ai log**: I log di audit possono essere difficili da analizzare se non vengono configurati correttamente, specialmente quando le policy IAM sono complesse.

---

### **9. Limitazioni nella Creazione di Ruoli Personalizzati**

- **Numero massimo di ruoli personalizzati**: C'è un numero massimo di **ruoli personalizzati** che puoi creare in un progetto o in un'organizzazione.
- **Limite di permessi per ruolo personalizzato**: I ruoli personalizzati possono contenere solo un numero limitato di permessi. Se hai bisogno di un set più ampio di permessi, potresti dover ricorrere alla creazione di più ruoli.

---

### **Conclusioni**

Le **policy IAM** di Google Cloud sono estremamente potenti per gestire la sicurezza e l'accesso alle risorse, ma hanno alcune limitazioni che devono essere comprese. Queste limitazioni riguardano la complessità delle condizioni, la gestione dei ruoli, l'eredità delle policy, e la gestione dei membri. È importante progettare le politiche di accesso tenendo conto di queste limitazioni per garantire la sicurezza e la semplicità nella gestione delle risorse.









