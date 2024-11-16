


# Cloud Shell


<img width="975" alt="Screenshot 2024-11-16 alle 14 01 58" src="https://github.com/user-attachments/assets/78a7c25f-4ef8-4994-814e-99aded921c8b">





**Cloud Shell and Editor** è un ambiente interattivo fornito da Google Cloud che permette di accedere a strumenti e risorse direttamente dal browser senza dover configurare nulla sul tuo sistema locale. 

### **Caratteristiche principali**

1. **Cloud Shell**:
   - **Ambiente preconfigurato**: Include strumenti come `gcloud`, `kubectl`, Git, Python, Node.js, Go, Docker, e molti altri.
   - **Accesso sicuro**: Consente di lavorare direttamente sulle risorse di Google Cloud senza configurare credenziali locali.
   - **Storage persistente**: Ogni utente dispone di uno spazio di archiviazione di 5 GB su `/home`, che rimane salvato tra le sessioni.
   - **Supporto per SSH**: Puoi connetterti a macchine virtuali tramite SSH con un solo clic.

2. **Cloud Shell Editor**:
   - Basato su **Visual Studio Code** (VS Code).
   - **Accesso diretto al progetto**: Modifica e sviluppa codice direttamente sui tuoi progetti Google Cloud.
   - **Integrazione con strumenti Google Cloud**: Ad esempio, puoi eseguire comandi `gcloud` direttamente dal terminale incorporato.
   - **Anteprima web integrata**: Visualizza le tue applicazioni web ospitate nel Cloud Shell in una scheda del browser.

---

### **Come accedere a Cloud Shell**
1. Vai alla [console di Google Cloud](https://console.cloud.google.com).
2. Fai clic sull'icona di **Cloud Shell** in alto a destra della pagina (un terminale con una `>_`).
3. In pochi secondi, si aprirà un terminale interattivo pronto all'uso.

---

### **Utilizzi tipici**
- **Amministrazione del progetto**: Gestisci risorse GCP (VM, cluster Kubernetes, bucket) senza configurazioni locali.
- **Sviluppo e debug**: Scrivi, esegui e testa codice direttamente nel Cloud.
- **Installazione di strumenti personalizzati**: Puoi installare librerie e strumenti aggiuntivi per esigenze specifiche, che rimangono salvati nella tua directory `/home`.

---

### **Comandi utili in Cloud Shell**
- **Avviare il Cloud Shell Editor**:
  ```bash
  cloudshell edit
  ```
- **Esportare credenziali gcloud**:
  ```bash
  gcloud auth login
  ```
- **Gestire VM Compute Engine**:
  ```bash
  gcloud compute instances list
  ```

---

### **Vantaggi principali**
- **Pronto all'uso**: Nessuna necessità di configurazioni locali.
- **Sempre aggiornato**: Gli strumenti sono sempre aggiornati alla versione più recente.
- **Sicurezza**: L'accesso è autenticato e sicuro tramite l'account Google Cloud.


Una volta loggato posso usare il comando : df -h per vedere lo spazio nel disco


Il comando 

```bash
curl "http://metadata/computeMetadata/v1/instance/zone" -H "Metadata-Flavor: Google"
```

è usato per recuperare la **zona di Compute Engine** in cui si trova un'istanza Google Cloud. Questo comando accede ai **metadata server** forniti da Google Cloud, che permettono alle istanze di ottenere informazioni su sé stesse e sull'ambiente in cui operano.

---

### **Dettagli del comando**

1. **URL**:  
   `http://metadata/computeMetadata/v1/instance/zone`  
   - Questo è il percorso del server metadata per ottenere informazioni sulla zona della VM.
   - Ogni VM in Google Cloud ha accesso a un server metadata disponibile all'interno della rete locale.

2. **Header richiesto**:  
   `Metadata-Flavor: Google`  
   - Questo header è obbligatorio per autenticare la richiesta e dimostrare che è legittima. Senza di esso, il server restituirà un errore.

3. **Struttura della risposta**:
   La risposta è una stringa che indica la risorsa completa della zona dell'istanza, ad esempio:
   ```
   projects/123456789012/zones/us-central1-a
   ```
   - **projects/123456789012**: L'ID del progetto.
   - **zones/us-central1-a**: La zona in cui si trova la VM.

---

### **Estrarre solo il nome della zona**
Se vuoi ottenere solo il nome della zona (es. `us-central1-a`), puoi usare un comando come questo:
```bash
curl "http://metadata/computeMetadata/v1/instance/zone" -H "Metadata-Flavor: Google" | awk -F'/' '{print $NF}'
```
- Qui `awk` divide la stringa usando `/` come separatore e prende l'ultima parte.

---

### **Casi d'uso comuni**
1. **Identificare l'ambiente in cui opera una VM**:  
   Utile in script o applicazioni che devono adattarsi alla zona della VM.

2. **Bilanciamento del carico o failover**:  
   Puoi configurare script per distribuire il carico tra diverse zone o spostare operazioni su altre zone in caso di problemi.

3. **Automatizzare configurazioni regionali**:  
   Conoscere la zona aiuta a configurare servizi collegati (es. bucket di Cloud Storage o altre risorse regionali).

---

### **Nota sulla sicurezza**
- Il metadata server è accessibile solo dalle VM e non è disponibile dall'esterno.
- Non è richiesta un'autenticazione aggiuntiva, ma i metadati sensibili (es. chiavi API) devono essere usati con cautela.






