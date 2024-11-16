Ecco un elenco dei principali comandi `gcloud`, organizzati per categoria, con una breve descrizione delle loro funzionalità:

---

### **Configurazione**
- **`gcloud init`**: Configura la CLI e associa il progetto e l'account.
- **`gcloud auth login`**: Effettua il login con il tuo account Google.
- **`gcloud config set <PROPERTY> <VALUE>`**: Imposta una proprietà di configurazione (es., `project`, `region`).
- **`gcloud config list`**: Mostra le configurazioni attuali.
- **`gcloud auth list`**: Elenca gli account autenticati.

---

### **Progetti**
- **`gcloud projects list`**: Elenca i progetti disponibili.
- **`gcloud projects create <PROJECT_ID>`**: Crea un nuovo progetto.
- **`gcloud projects delete <PROJECT_ID>`**: Elimina un progetto.

---

### **Compute Engine**
- **`gcloud compute instances list`**: Elenca le VM.
- **`gcloud compute instances create <NAME>`**: Crea una nuova VM.
- **`gcloud compute instances delete <NAME>`**: Elimina una VM.
- **`gcloud compute ssh <INSTANCE_NAME>`**: Effettua il login SSH in una VM.

---

### **Cloud Storage**
- **`gcloud storage buckets list`**: Elenca i bucket di storage.
- **`gcloud storage buckets create <BUCKET_NAME>`**: Crea un bucket di storage.
- **`gcloud storage buckets delete <BUCKET_NAME>`**: Elimina un bucket.
- **`gcloud storage cp <SOURCE> <DESTINATION>`**: Copia file da/a un bucket.

---

### **Kubernetes Engine (GKE)**
- **`gcloud container clusters list`**: Elenca i cluster Kubernetes.
- **`gcloud container clusters create <CLUSTER_NAME>`**: Crea un cluster Kubernetes.
- **`gcloud container clusters delete <CLUSTER_NAME>`**: Elimina un cluster.
- **`gcloud container clusters get-credentials <CLUSTER_NAME>`**: Configura `kubectl` per un cluster.

---

### **Cloud Functions**
- **`gcloud functions deploy <NAME>`**: Distribuisce una funzione Cloud.
- **`gcloud functions list`**: Elenca le funzioni distribuite.
- **`gcloud functions delete <NAME>`**: Elimina una funzione.

---

### **Cloud Run**
- **`gcloud run deploy`**: Distribuisce un'app su Cloud Run.
- **`gcloud run services list`**: Elenca i servizi di Cloud Run.
- **`gcloud run services delete <SERVICE_NAME>`**: Elimina un servizio.

---

### **IAM (Identity and Access Management)**
- **`gcloud iam roles list`**: Elenca i ruoli IAM disponibili.
- **`gcloud iam service-accounts list`**: Elenca i service account.
- **`gcloud projects add-iam-policy-binding`**: Aggiunge un ruolo IAM a un utente o gruppo.

---

### **Database**
- **`gcloud sql instances list`**: Elenca le istanze di Cloud SQL.
- **`gcloud sql instances create <INSTANCE_NAME>`**: Crea un'istanza Cloud SQL.
- **`gcloud sql instances delete <INSTANCE_NAME>`**: Elimina un'istanza Cloud SQL.

---

### **Monitoraggio e Log**
- **`gcloud logging logs list`**: Elenca i log disponibili.
- **`gcloud logging read <QUERY>`**: Legge i log con una query specifica.
- **`gcloud monitoring dashboards list`**: Elenca le dashboard di monitoraggio.

---

### **Beta e Alpha**
- **`gcloud beta <COMMAND>`**: Accesso a funzionalità in fase beta.
- **`gcloud alpha <COMMAND>`**: Accesso a funzionalità in fase alpha (più sperimentali).

---
