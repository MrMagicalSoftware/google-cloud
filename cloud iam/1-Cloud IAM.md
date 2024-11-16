# Cloud IAM



**Cloud IAM (Identity and Access Management)** è il sistema di gestione delle identità e dei permessi di **Google Cloud Platform (GCP)**.
Consente di controllare chi (utenti, gruppi o service account) può eseguire determinate azioni sulle risorse del tuo progetto GCP. 
È uno strumento fondamentale per gestire la sicurezza e l'accesso nei progetti cloud.

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




