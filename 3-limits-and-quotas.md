# 


In **Google Cloud**, i **limiti e le quote** regolano l'uso delle risorse per garantire che i clienti utilizzino il servizio in modo equo e per proteggere il sistema da sovraccarichi. 
Questi limiti possono essere globali, per progetto, o specifici per una regione o una zona.



---

### **Tipologie di limiti**
1. **Limiti di risorse**:
   - Massima quantità di risorse disponibili (ad esempio, numero massimo di CPU o dischi).
   - Questi limiti sono fissi, ma in alcuni casi possono essere aumentati su richiesta.

2. **Quote di utilizzo**:
   - Controllano il consumo di risorse in un determinato periodo di tempo (giornaliero o orario).
   - Ad esempio, richieste API, operazioni di rete o spazio di archiviazione utilizzato.

---

### **Visualizzare i limiti e le quote**
Puoi verificare i limiti e le quote direttamente dalla **Google Cloud Console** o tramite la CLI `gcloud`.

#### Da Console:
1. Vai a **IAM e amministrazione > Quote** nella [Google Cloud Console](https://console.cloud.google.com/iam-admin/quotas).
2. Usa i filtri per selezionare il servizio o la risorsa.
3. Visualizza i limiti correnti e l'utilizzo.


<img width="923" alt="Screenshot 2024-11-16 alle 14 37 03" src="https://github.com/user-attachments/assets/1b136ce9-6b36-4131-9bca-b95d734f4b8e">

<img width="629" alt="Screenshot 2024-11-16 alle 14 37 32" src="https://github.com/user-attachments/assets/b0a2598f-6c6c-4631-984f-e6ddabb17981">

<img width="925" alt="Screenshot 2024-11-16 alle 14 40 17" src="https://github.com/user-attachments/assets/2662b22c-4665-4b1a-b4e2-3268da08089e">
<img width="920" alt="Screenshot 2024-11-16 alle 14 40 04" src="https://github.com/user-attachments/assets/0bd3ec5a-b7b3-4c55-bc1b-f845547c737d">
<img width="934" alt="Screenshot 2024-11-16 alle 14 39 50" src="https://github.com/user-attachments/assets/84e4668d-39e6-47e0-85ac-7da5e6ac0188">


#### Da `gcloud`:


```bash
gcloud compute project-info describe --project=<PROJECT_ID>
```
Oppure, per visualizzare le quote di un'area specifica:
```bash
gcloud compute regions describe <REGION>
```

---

### **Quote comuni**
quote tipiche nei progetti Google Cloud:

1. **Compute Engine**:
   - CPU totali per regione.
   - Numero massimo di dischi permanenti.
   - IP esterni statici.

2. **Cloud Storage**:
   - Numero massimo di bucket.
   - Operazioni API per minuto.

3. **BigQuery**:
   - Query simultanee.
   - Dati elaborati al giorno.

4. **Cloud Functions**:
   - Limite di distribuzioni.
   - Memoria e tempo massimo di esecuzione.

5. **Cloud Pub/Sub**:
   - Numero massimo di messaggi inviati al secondo.
   - Dimensione totale del messaggio.

---

### **Aumentare i limiti**
Se un limite non è sufficiente per l' utilizzo, pi può richiedere un aumento. 

1. Vai alla pagina **IAM e amministrazione > Quote**.
2. Filtra la risorsa interessata.
3. Fai clic su **Richiedi aumento**.
4. Compila il modulo e attendi una risposta da Google Cloud.

---

### **Monitorare le quote**
Puoi configurare avvisi per sapere quando ti stai avvicinando a un limite:
1. Si usa **Cloud Monitoring** per creare una policy di avviso.
2. Si Configura un avviso basato sul superamento di una percentuale della quota (es. 80%).

---

### **Errori comuni relativi alle quote**
- **Quota exceeded**: Si verifica quando si supera  il limite assegnato.
- **Rate Limit Exceeded**: Troppi accessi in un breve periodo.

In questi casi, si può ottimizzare le risorse o richiedere un aumento delle quote.

