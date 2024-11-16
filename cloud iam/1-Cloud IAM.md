# Cloud IAM



**Cloud IAM (Identity and Access Management)** è il sistema di gestione delle identità e dei permessi di **Google Cloud Platform (GCP)**.
Consente di controllare chi (utenti, gruppi o service account) può eseguire determinate azioni sulle risorse del tuo progetto GCP. 
È uno strumento fondamentale per gestire la sicurezza e l'accesso nei progetti cloud.


REGOLA AUREA:

°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°

A user, program , or process should have oly the bare minimum privileges necessary to perform its function

<img width="760" alt="Screenshot 2024-11-16 alle 14 58 05" src="https://github.com/user-attachments/assets/1877c1de-4631-49c4-90de-64df8316ebf4">

## POLICY ARCHITECTURE 


<img width="659" alt="Screenshot 2024-11-16 alle 15 02 23" src="https://github.com/user-attachments/assets/93fe82cd-1dd1-4e2d-a3fd-3757d5bee51f">


**the who**

<img width="1346" alt="Screenshot 2024-11-16 alle 15 04 43" src="https://github.com/user-attachments/assets/bca21992-6a0c-4513-aad9-5e2a54102b1a">



**Permissions**

<img width="884" alt="Screenshot 2024-11-16 alle 15 06 25" src="https://github.com/user-attachments/assets/96ef60d7-b80f-4147-812a-f4f4ef345108">


**Roles**

<img width="892" alt="Screenshot 2024-11-16 alle 15 07 38" src="https://github.com/user-attachments/assets/485c5498-e915-431d-916c-5707beb64b93">



I roles possono essere :


<img width="949" alt="Screenshot 2024-11-16 alle 15 09 59" src="https://github.com/user-attachments/assets/3214c94d-e5ae-4e76-be45-0a2c7d58328b">



**Conditions**


<img width="737" alt="Screenshot 2024-11-16 alle 15 11 50" src="https://github.com/user-attachments/assets/db0fe1ca-ceee-4cd7-b714-5dc58d021b59">




**METADATA**




<img width="1152" alt="Screenshot 2024-11-16 alle 16 07 24" src="https://github.com/user-attachments/assets/01d4217e-8dc7-4b9d-a98a-1996e72caa41">



**Audit config**


<img width="1015" alt="Screenshot 2024-11-16 alle 16 08 27" src="https://github.com/user-attachments/assets/1592e2bc-e625-4b6d-94ca-d3b43fa57744">



 

°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°



<img width="1422" alt="Screenshot 2024-11-16 alle 14 59 55" src="https://github.com/user-attachments/assets/a7afe5a9-7c72-4f8e-8927-3bd2e4558321">





---

### **Concetti principali**

1. **Policy IAM**:
   - Una policy è un insieme di regole che associa **ruoli** a **principali** (entità che possono accedere alle risorse).
   - Le policy sono definite a livello di progetto, cartella o organizzazione.

2. **Principali**:
   - Gli utenti o entità che richiedono accesso alle risorse.
   - Esempi:
     - **Utenti**: Un account Google (es. `utente@gmail.com`).
     - **Gruppi**: Un gruppo Google (es. `gruppo@azienda.com`).
     - **Service account**: Un account utilizzato dalle applicazioni per accedere alle risorse.
     - **Domini**: Accesso concesso a tutti gli utenti di un dominio (es. `@azienda.com`).

3. **Ruoli**:
   - Specificano un insieme di permessi.
   - Tipi di ruoli:
     - **Predefiniti (built-in)**: Ruoli standard forniti da Google (es. `roles/viewer`, `roles/editor`, `roles/owner`).
     - **Personalizzati**: Definiti dall'utente per esigenze specifiche.
     - **Ruoli primitivi**: Ruoli legacy (`Viewer`, `Editor`, `Owner`).
   - Esempi di ruoli predefiniti:
     - `roles/storage.objectViewer`: Permette di leggere oggetti in Cloud Storage.
     - `roles/compute.instanceAdmin`: Permette di gestire le istanze di Compute Engine.

4. **Permessi**:
   - Ogni ruolo è composto da permessi specifici.
   - Esempio: Il ruolo `roles/storage.admin` include permessi come `storage.buckets.create` e `storage.objects.delete`.

---

### **Comandi principali con `gcloud iam`**

1. **Visualizzare i ruoli assegnati a un progetto**:
   ```bash
   gcloud projects get-iam-policy <PROJECT_ID>
   ```

2. **Aggiungere un ruolo a un utente**:
   ```bash
   gcloud projects add-iam-policy-binding <PROJECT_ID> \
       --member="user:utente@example.com" \
       --role="roles/viewer"
   ```

3. **Rimuovere un ruolo da un utente**:
   ```bash
   gcloud projects remove-iam-policy-binding <PROJECT_ID> \
       --member="user:utente@example.com" \
       --role="roles/viewer"
   ```

4. **Elencare tutti i ruoli disponibili**:
   ```bash
   gcloud iam roles list
   ```

5. **Creare un ruolo personalizzato**:
   ```bash
   gcloud iam roles create <ROLE_ID> \
       --project=<PROJECT_ID> \
       --title="Titolo del ruolo" \
       --description="Descrizione del ruolo" \
       --permissions="permesso1,permesso2" \
       --stage="ALPHA"
   ```

6. **Elencare gli account di servizio**:
   ```bash
   gcloud iam service-accounts list
   ```

---

### **Best Practices per Cloud IAM**

1. **Segui il principio del privilegio minimo**:
   - Assegna solo i permessi strettamente necessari per una specifica attività.

2. **Usa ruoli predefiniti o personalizzati**:
   - Evita i ruoli primitivi (`Owner`, `Editor`) che sono troppo permissivi.

3. **Monitora l'accesso**:
   - Usa **Cloud Audit Logs** per registrare chi accede alle risorse e cosa fa.

4. **Usa gruppi e service account**:
   - Gestire l'accesso tramite gruppi semplifica la gestione dei permessi.
   - Usa service account per le applicazioni anziché account utente.

5. **Periodicamente revisiona le policy**:
   - Controlla regolarmente i ruoli assegnati e rimuovi quelli non necessari.

---

### **Risorse correlate**
- **Cloud Console**: Configura IAM graficamente [da qui](https://console.cloud.google.com/iam-admin/iam).
- **Cloud Audit Logs**: Monitora tutte le attività IAM.
- **Documentazione ufficiale**: [IAM di Google Cloud](https://cloud.google.com/iam/docs).


<img width="1460" alt="Screenshot 2024-11-16 alle 16 10 00" src="https://github.com/user-attachments/assets/3bfe72fb-a57a-48e8-8e8f-cee46b9a65dd">




In **Google Cloud IAM (Identity and Access Management)**, le **policy di accesso** sono **ereditarie** in base alla gerarchia delle risorse: **Organizzazione** > **Cartella** > **Progetto** > **Risorse**. La gestione delle policy ereditarie significa che le policy assegnate a un livello superiore (ad esempio, un'Organizzazione o una Cartella) possono influenzare le risorse a livelli inferiori (come i progetti o le singole risorse come le istanze di Compute Engine).

### **Ereditarietà delle Policy IAM**

1. **Gerarchia delle risorse**:
   - **Organizzazione**: Il livello più alto, che rappresenta l'intera struttura della tua organizzazione.
   - **Cartelle**: Possono essere utilizzate per raggruppare progetti e risorse. Le policy IAM possono essere assegnate a livello di cartella.
   - **Progetti**: Un progetto è l'unità di base per la gestione delle risorse in Google Cloud. Le policy IAM possono essere assegnate a livello di progetto.
   - **Risorse**: Ogni risorsa (come le istanze di VM, i bucket di storage, ecc.) ha la propria policy IAM, ma può ereditare quella del progetto o della cartella in cui si trova.

2. **Ereditarietà**:
   - Le **policy IAM** assegnate a un livello superiore (ad esempio, a livello di **organizzazione** o **cartella**) vengono **ereditate** dai livelli inferiori (ad esempio, **progetti** o **risorse individuali**). 
   - Tuttavia, se una policy IAM viene assegnata a un livello inferiore (ad esempio, direttamente a un progetto), questa sostituirà la policy del livello superiore (a meno che non venga esplicitamente negata).

3. **Overrides (Sovrascritture)**:
   - Se assegni una policy a un livello inferiore, ad esempio a un **progetto**, essa può sovrascrivere o **modificare** le policy ereditate dal livello superiore. Ad esempio, un progetto può avere un ruolo IAM che differisce da quello ereditato dalla cartella o dall'organizzazione.
   - Le modifiche dirette a livello di risorsa (ad esempio, assegnando un ruolo a una VM specifica) **sovrascriveranno** le policy a livello di progetto o cartella, ma continueranno a rispettare le regole di accesso generali a meno che non siano esplicitamente modificate.

4. **Implicazioni di Ereditarietà**:
   - **Vantaggio**: L'eredità delle policy facilita la gestione centralizzata dell'accesso. Si può configurare policy globali per tutta l'organizzazione, riducendo il bisogno di configurazioni ripetitive.
   - **Problema**: Se non gestito correttamente, potrebbe portare a **accessi non intenzionali** o **a una sicurezza indebolita**. Ad esempio, un membro che ha accesso a un progetto potrebbe, involontariamente, acquisire permessi per tutte le risorse all'interno di una cartella o organizzazione se non vengono impostate policy più restrittive.

---

### **Comportamento dell'Ereditarietà**
- **Cartella a Progetto**: Una **cartella** che contiene più progetti può avere policy IAM che si applicano automaticamente a tutti i progetti al suo interno. Le policy IAM definite a livello di progetto possono sovrascrivere quelle ereditate dalla cartella.
  
- **Progetto a Risorsa**: Le policy assegnate a un **progetto** si applicano a tutte le risorse del progetto, ma le risorse singole (ad esempio, una VM o un bucket di Storage) possono avere policy personalizzate.

- **Organizzazione a Cartella/Progetto**: Le **policy assegnate a livello di organizzazione** si propagano a tutte le cartelle e i progetti che vi appartengono. Tuttavia, se una cartella o un progetto ha policy IAM assegnate direttamente, queste possono sovrascrivere le policy a livello di organizzazione.

---

### **Come vedere le policy ereditarie**
Puoi visualizzare e verificare le policy IAM in un progetto (e in altri livelli della gerarchia) tramite il comando `gcloud`:

#### Visualizzare le policy a livello di progetto:
```bash
gcloud projects get-iam-policy <PROJECT_ID>
```

#### Visualizzare le policy a livello di organizzazione:
```bash
gcloud organizations get-iam-policy <ORGANIZATION_ID>
```

#### Visualizzare le policy a livello di cartella:
```bash
gcloud resource-manager folders get-iam-policy <FOLDER_ID>
```

Se ad esempio applico una policy al project x , i figli avranno la stessa policy.

<img width="945" alt="Screenshot 2024-11-16 alle 16 16 22" src="https://github.com/user-attachments/assets/cf5744e8-9d4f-48b8-b833-15d8e73d2f95">



---

### **Gestire e bloccare l'ereditarietà**
In alcuni casi, potresti voler bloccare l'ereditarietà delle policy a livello di cartella o progetto per evitare che permessi non desiderati si propaghino. Puoi fare ciò utilizzando il blocco dell'ereditarietà delle policy. Questo è utile per garantire che le risorse non ricevano accidentalmente permessi da livelli superiori che non desideri.

1. **Bloccare l'ereditarietà**:
   - Puoi impedire che una cartella o un progetto erediti le policy impostate a livello superiore utilizzando il comando:
     ```bash
     gcloud resource-manager folders set-iam-policy <FOLDER_ID> --no-iam-policy-binding
     ```
   
2. **Rimuovere l'ereditarietà**:
   - Se desideri ripristinare l'ereditarietà delle policy, puoi annullare il blocco e permettere alle policy di propagarsi.

---









