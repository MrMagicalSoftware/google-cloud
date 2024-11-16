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


