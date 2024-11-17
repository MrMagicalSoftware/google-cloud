
# VPC NETWORK SUBNETS



Le **VPC Subnets** (sottoreti di una Virtual Private Cloud) sono segmenti logici di rete definiti all'interno di una VPC. 
Ogni subnet è associata a una regione specifica e rappresenta un intervallo di indirizzi IP utilizzato per organizzare e gestire le risorse della rete come VM, container e database.

---

### **1. Caratteristiche delle Subnet**

#### **Regionalità**
- Ogni subnet è **regionale**, il che significa che si estende a tutte le zone di una regione.
- Ad esempio, una subnet definita nella regione `us-central1` coprirà tutte le zone in `us-central1-a`, `us-central1-b`, ecc.
  
#### **Intervallo di IP**
- Ogni subnet ha un **range IP CIDR** (es. `10.0.0.0/24`) che definisce gli indirizzi disponibili per le risorse.
- si può specificare un intervallo personalizzato o utilizzare valori predefiniti nelle VPC automatiche.

#### **Connessione tra subnet**
- Le subnet all'interno della stessa VPC possono comunicare tra loro tramite **routing interno**, senza bisogno di ulteriori configurazioni.

#### **Subnet predefinite**
- Nelle VPC **automatiche**, le subnet vengono create automaticamente in tutte le regioni con intervalli IP preconfigurati.

#### **Subnet personalizzate**
- Nelle VPC **personalizzate**, siamo responsabile della creazione delle subnet e della definizione degli intervalli di indirizzi IP.

---

### **2. Creazione di Subnet**

#### **Utilizzando Google Cloud Console**
1. Sezione  **VPC network** > **Subnets**.
2. Clicca su **Create subnet**.
3. Seleziona la rete VPC a cui associare la subnet.
4. Specifica:
   - Nome della subnet.
   - Regione.
   - Intervallo CIDR (es. `10.0.1.0/24`).

#### **Utilizzando gcloud CLI**

**Comando per creare una subnet:**
```bash
gcloud compute networks subnets create my-subnet \
    --network=my-vpc \
    --region=us-central1 \
    --range=10.0.1.0/24
```

- `--network`: Specifica il nome della rete VPC.
- `--region`: Regione in cui creare la subnet.
- `--range`: Intervallo IP della subnet in formato CIDR.

#### **Modifica di una subnet**
Alcuni attributi (come il range IP) non possono essere modificati dopo la creazione. Tuttavia, puoi aggiornare altre proprietà come etichette o regole di accesso privato.

---

### **3. Accesso Privato ai Servizi Google**

Le subnet possono essere configurate per consentire l'accesso privato ai servizi Google (come Cloud Storage, BigQuery) senza passare per Internet.

**Abilitazione di Private Google Access:**
```bash
gcloud compute networks subnets update my-subnet \
    --region=us-central1 \
    --enable-private-ip-google-access
```

---

### **4. Subnet Modes**

Quando si crea una VPC, si può scegliere tra due modalità per la gestione delle subnet:

#### **1. Modalità Automatica**
- Le subnet vengono create automaticamente in tutte le regioni con intervalli IP predefiniti.
- Utile per configurazioni semplici e rapide.
- Non puoi eliminare le subnet create automaticamente, ma puoi modificarle.

#### **2. Modalità Personalizzata**
- Bisogna creare manualmente ogni subnet e definire gli intervalli IP.
- Offre maggiore controllo sulla configurazione della rete.

**Cambio di modalità:**
Una VPC in modalità automatica può essere convertita in modalità personalizzata, ma non viceversa.

---

### **5. Best Practices nella Configurazione delle Subnet**

1. **Pianifica il range di indirizzi IP**
   - Usa CIDR sufficientemente grandi da supportare la crescita futura.
   - Evita sovrapposizioni con reti on-premise o altre VPC.

2. **Isolamento logico**
   - Crea subnet separate per ambienti diversi (es. produzione, sviluppo, test).
   - Usa subnet diverse per tipi di risorse (es. backend, database, frontend).

3. **Accesso privato**
   - Abilita Private Google Access per le subnet che richiedono accesso ai servizi Google senza usare Internet.

4. **Etichettatura**
   - Applica etichette significative alle subnet per facilitarne la gestione e il monitoraggio.

5. **Audit delle regole firewall**
   - Monitora le regole del firewall per garantire che le subnet siano protette da accessi non autorizzati.

---

### **6. Connettività tra Subnet**

#### **Tra subnet nella stessa VPC**
- Il traffico è permesso di default tramite routing interno.
- SI può controllare l'accesso con regole del firewall.

#### **Tra subnet in VPC diverse**
- Richiede il **VPC Peering** o una connessione tramite **Cloud VPN** o **Interconnessione**.

**Configurazione di VPC Peering:**
```bash
gcloud compute networks peerings create my-peering \
    --network=my-vpc-1 \
    --peer-network=my-vpc-2
```

---

### **7. Limitazioni delle Subnet**

- **Numero massimo di subnet**: C'è un limite al numero di subnet per progetto e VPC, configurabile tramite le **quote**.
- **Range IP fisso**: Una volta creato, il range IP non può essere modificato.
- **Conflitti IP**: Evita sovrapposizioni IP tra subnet o con reti on-premise.

---

### **8. Monitoraggio delle Subnet**

Google Cloud offre strumenti integrati per monitorare le subnet:
- **Cloud Monitoring**: Per visualizzare metriche di utilizzo delle subnet.
- **VPC Flow Logs**: Per registrare e analizzare il traffico di rete nelle subnet.

**Abilitazione dei Flow Logs:**
```bash
gcloud compute networks subnets update my-subnet \
    --region=us-central1 \
    --enable-flow-logs
```

---

°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°


<img width="1035" alt="Screenshot 2024-11-17 alle 13 07 25" src="https://github.com/user-attachments/assets/e34b7595-b59b-4370-80ce-8500ad456322">



**increasung subnet Ip space**


<img width="1052" alt="Screenshot 2024-11-17 alle 13 16 18" src="https://github.com/user-attachments/assets/7521e7c7-4bef-46f7-bddb-cadc884c1354">



**RESERVED IP ADDRESSES**

<img width="965" alt="Screenshot 2024-11-17 alle 13 17 53" src="https://github.com/user-attachments/assets/235d7b23-8951-48b8-b9a5-0906072e5788">







°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°












