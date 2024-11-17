
# Firewall and Firewall Rules



### **Regole del firewall nella VPC**

Le **regole del firewall** in una rete **VPC** controllano il traffico in entrata e in uscita dalle risorse all'interno della rete. Queste regole consentono di definire policy di sicurezza per proteggere le risorse, specificando quali connessioni sono consentite o bloccate.

---

### **1. Caratteristiche principali delle regole del firewall**

1. **Livello VPC**
   - Le regole del firewall sono applicate a livello di rete VPC e non a singole risorse.
   
2. **Regole implicite**
   - Ogni VPC ha alcune regole di firewall predefinite:
     - **Consenti il traffico interno**: Permette la comunicazione tra le risorse della stessa rete VPC.
     - **Nega il traffico in entrata**: Blocca tutto il traffico in entrata da origini esterne, eccetto le connessioni esplicitamente permesse.
     - **Consenti il traffico in uscita**: Consente tutto il traffico in uscita, a meno che non sia bloccato esplicitamente.

3. **Direzione del traffico**
   - **Ingress**: Controlla il traffico **in entrata** verso le risorse.
   - **Egress**: Controlla il traffico **in uscita** dalle risorse.

4. **Priorità**
   - Ogni regola del firewall ha una priorità (valore numerico da `0` a `65535`, dove `0` è la priorità più alta). Le regole con priorità più alta vengono applicate prima.

5. **Target**
   - Le regole del firewall possono essere applicate a tutte le risorse della VPC o solo a risorse specifiche, identificate tramite **tag** o **account di servizio**.

---

### **2. Creazione di regole del firewall**

#### **Con Google Cloud Console**
1. Vai a **VPC network** > **Firewall**.
2. Clicca su **Create Firewall Rule**.
3. Specifica i dettagli, inclusi nome, rete VPC, priorità, direzione e criteri di applicazione.
4. Definisci **IP source/destination**, protocolli e porte.

#### **Con gcloud CLI**

**Esempio: creare una regola per consentire il traffico SSH (porta 22):**
```bash
gcloud compute firewall-rules create allow-ssh \
    --network=my-vpc \
    --priority=1000 \
    --direction=INGRESS \
    --action=ALLOW \
    --rules=tcp:22 \
    --source-ranges=0.0.0.0/0
```

**Parametri principali:**
- `--network`: Specifica la rete VPC.
- `--priority`: Imposta la priorità della regola.
- `--direction`: Direzione del traffico (`INGRESS` o `EGRESS`).
- `--action`: Azione da applicare (`ALLOW` o `DENY`).
- `--rules`: Protocolli e porte (es. `tcp:22` o `icmp`).
- `--source-ranges`: Intervalli IP di origine per il traffico in ingresso.
- `--target-tags`: Applica la regola solo alle risorse con tag specifici.

---

### **3. Modifica di una regola del firewall**

Le regole del firewall possono essere aggiornate per modificare parametri come priorità, target, e protocolli.

**Comando per aggiornare una regola:**
```bash
gcloud compute firewall-rules update allow-ssh \
    --priority=500
```

---

### **4. Monitoraggio delle regole del firewall**

Si può utilizzare **VPC Flow Logs** per monitorare e analizzare il traffico filtrato o consentito dalle regole del firewall.

**Abilitazione dei VPC Flow Logs su una subnet:**
```bash
gcloud compute networks subnets update my-subnet \
    --region=us-central1 \
    --enable-flow-logs
```

---

### **5. Esempi di regole comuni**

#### **a. Consentire il traffico HTTP/HTTPS**
```bash
gcloud compute firewall-rules create allow-http-https \
    --network=my-vpc \
    --direction=INGRESS \
    --action=ALLOW \
    --rules=tcp:80,tcp:443 \
    --source-ranges=0.0.0.0/0
```

#### **b. Consentire il traffico interno nella subnet**
```bash
gcloud compute firewall-rules create allow-internal \
    --network=my-vpc \
    --direction=INGRESS \
    --action=ALLOW \
    --rules=all \
    --source-ranges=10.0.0.0/8
```

#### **c. Bloccare tutto il traffico in uscita**
```bash
gcloud compute firewall-rules create deny-all-egress \
    --network=my-vpc \
    --direction=EGRESS \
    --action=DENY \
    --rules=all \
    --destination-ranges=0.0.0.0/0
```

#### **d. Consentire il traffico solo a risorse con tag specifici**
```bash
gcloud compute firewall-rules create allow-web-traffic \
    --network=my-vpc \
    --direction=INGRESS \
    --action=ALLOW \
    --rules=tcp:80,tcp:443 \
    --source-ranges=0.0.0.0/0 \
    --target-tags=web-server
```

---

### **6. Best Practices per le regole del firewall**

1. **Principio del privilegio minimo**
   - Configurare regole per consentire solo il traffico strettamente necessario.

2. **Usare tag o account di servizio**
   - Applicare regole basate su **target-tags** o **target-service-accounts** per limitare il traffico a risorse specifiche.

3. **Priorità delle regole**
   - Assegnare priorità appropriate per garantire che le regole critiche siano applicate prima.

4. **Abilitare il logging**
   - Utilizzare il logging delle regole per monitorare e diagnosticare problemi di rete.

5. **Audit regolare**
   - Verificare periodicamente le regole per identificare e rimuovere quelle obsolete o superflue.

---




