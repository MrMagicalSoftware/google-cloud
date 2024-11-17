
# Virtual Private Cloud 



Una **Virtual Private Cloud (VPC)** è una rete virtuale all'interno di Google Cloud che consente di gestire risorse cloud in un ambiente isolato e sicuro. 
Una VPC offre **connettività, isolamento** e **controllo** sulle risorse di rete, come VM, container, e database, consentendo di configurare routing, firewall, e subnet per adattarsi ai requisiti di rete specifici dell' organizzazione.

---

### **1. Cos'è una VPC?**

- Una **VPC** è una rete logica e privata all'interno del cloud di Google. 
- Supporta il traffico interno tra le risorse della rete senza esporle direttamente a Internet.
- È scalabile, globale, e altamente configurabile, consentendo alle organizzazioni di creare reti personalizzate in base alle proprie esigenze.

---

### **2. Caratteristiche principali di una VPC**

#### **Globalità**
Le VPC in Google Cloud sono **globali**, il che significa che si possono creare una singola rete che copre più regioni. Questo è utile per semplificare la gestione delle risorse e migliorare la connettività tra regioni.

#### **Subnet regionali**
Anche se la VPC è globale, le **subnet** (sottoreti) sono regionali. Si possono configurare subnet diverse in regioni diverse all'interno della stessa VPC.

#### **Routing personalizzato**
Le VPC supportano:
- **Routing statico**: Adatto a scenari semplici con percorsi predefiniti.
- **Routing dinamico**: Utilizza il protocollo BGP (Border Gateway Protocol) per adattarsi ai cambiamenti della rete in tempo reale.

#### **Controllo tramite firewall**
Le regole del firewall consentono di:
- Permettere o negare il traffico basato su criteri specifici (indirizzi IP, protocolli, porte, ecc.).
- Definire regole per il traffico interno (tra risorse VPC) e per il traffico esterno (da e verso Internet).

#### **Interconnessione e Peering**
- **Interconnessione dedicata**: Permette di collegare reti on-premise a Google Cloud con connessioni ad alte prestazioni.
- **Peering di rete VPC**: Connettività diretta tra due VPC diverse, anche in progetti o organizzazioni separate.

#### **Condivisione della rete (Shared VPC)**
Si possono condividere una VPC tra più progetti Google Cloud nella stessa organizzazione, semplificando la gestione di risorse multi-progetto.

#### **Accesso privato ai servizi**
Le risorse in una VPC possono accedere ai servizi Google (es. Cloud Storage, BigQuery) senza passare attraverso Internet, usando **Private Google Access**.

#### **Scalabilità e resilienza**
Le VPC sono progettate per scalare automaticamente con il carico e garantire alta disponibilità.

---

### **3. Elementi di una VPC**

1. **Progetto**: Ogni VPC appartiene a un progetto Google Cloud.
2. **Subnet**: Una suddivisione della VPC in blocchi IP regionali.
3. **Regole del firewall**: Permettono di gestire il traffico in entrata e in uscita.
4. **Router**: Gestisce il traffico tra subnet, verso altre VPC o verso reti on-premise.
5. **Endpoint privati**: Consentono l'accesso privato a servizi gestiti da Google Cloud.

---

### **4. Creazione di una VPC**

Si può creare una VPC tramite:
- **Google Cloud Console**.
- **gcloud CLI**.
- **API di Google Cloud**.

#### **Creazione con gcloud CLI**

```bash
# Crea una nuova VPC personalizzata
gcloud compute networks create my-vpc \
    --subnet-mode=custom \
    --bgp-routing-mode=regional

# Crea una subnet all'interno della VPC
gcloud compute networks subnets create my-subnet \
    --network=my-vpc \
    --region=us-central1 \
    --range=10.0.0.0/24
```

---

### **5. Configurazione delle Regole del Firewall**

Le regole del firewall consentono di controllare il traffico tra risorse nella VPC o con Internet.

#### **Esempio di regola firewall**
Per permettere il traffico SSH verso le VM in una VPC:

```bash
gcloud compute firewall-rules create allow-ssh \
    --network=my-vpc \
    --allow=tcp:22 \
    --source-ranges=0.0.0.0/0 \
    --direction=INGRESS
```

---

### **6. Modelli di VPC**

1. **VPC Automatico**
   - Le subnet vengono create automaticamente per ogni regione con un intervallo di IP predefinito.
   - Meno configurabile ma più semplice da usare.

2. **VPC Personalizzato**
   - Bisonga creare manualmente le subnet e configurare gli intervalli di IP.
   - Offre maggiore controllo sulla configurazione della rete.

---

### **7. Connettività Avanzata**

#### **1. VPN**
Permette di creare tunnel sicuri tra reti on-premise e la VPC utilizzando IPsec.

```bash
gcloud compute vpn-tunnels create my-tunnel \
    --peer-address=192.168.1.1 \
    --shared-secret=my-shared-secret \
    --ike-version=2 \
    --region=us-central1
```

#### **2. Interconnessione diretta**
Collega il tuo datacenter on-premise direttamente a Google Cloud tramite un link fisico ad alte prestazioni.

#### **3. Peering**
Connetti due VPC per consentire il traffico diretto senza passare per Internet.

#### **4. Cloud Router**
Gestisce il routing dinamico per le connessioni VPN o interconnessioni dirette.

```bash
gcloud compute routers create my-router \
    --network=my-vpc \
    --region=us-central1
```

---

### **8. Best Practices**

- **Progetta subnet con margine sufficiente**: bisogna prevedere espansioni future scegliendo blocchi IP più ampi.
- **Usa regole firewall minimali**: Applica il **principio del privilegio minimo** per evitare esposizioni accidentali.
- **Abilita il logging del firewall**: Per monitorare e auditare il traffico della rete.
- **Usa Shared VPC per organizzazioni grandi**: Condividi una VPC con più progetti per semplificare la gestione.
- **Abilita l'accesso privato ai servizi Google**: Minimizza la necessità di connettività Internet per risorse interne.

---

### **9. Vantaggi di una VPC**

- **Sicurezza avanzata**: Regole del firewall granulari e isolamento delle risorse.
- **Flessibilità**: Supporta una varietà di topologie di rete.
- **Connettività globale**: Una singola VPC può estendersi a più regioni, riducendo la complessità.
- **Scalabilità automatica**: Adatta la rete automaticamente al carico.

---

### **10. Limitazioni di una VPC**

- **Quota per VPC e subnet**: Ogni progetto ha un limite sul numero di VPC, subnet e regole del firewall.
- **Non cross-cloud**: Una VPC è specifica per Google Cloud; non può essere utilizzata direttamente con altre piattaforme cloud (ad esempio AWS o Azure) senza configurazioni aggiuntive.

---


°°°°°°°°°°°°° Recapp Virtual Private Cloud (VPC) °°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°


<img width="1019" alt="Screenshot 2024-11-17 alle 11 48 58" src="https://github.com/user-attachments/assets/84f7f16c-c3ef-45e4-996c-822db5378dbb">

<img width="998" alt="Screenshot 2024-11-17 alle 11 50 17" src="https://github.com/user-attachments/assets/cd6c2e32-2488-4739-bae6-df8b0add45c5">

<img width="1454" alt="Screenshot 2024-11-17 alle 11 52 21" src="https://github.com/user-attachments/assets/27225129-6c00-4345-a19c-9591d7d03dcd">



°°°°°°°°°°°°°°°°°°°°DEMO °°°°°°°°°°°°°°°°°°°°°°°°°°



<img width="1431" alt="Screenshot 2024-11-17 alle 11 55 51" src="https://github.com/user-attachments/assets/c6af5c56-905d-4c74-b0c4-f58f8fd1b120">
<img width="970" alt="Screenshot 2024-11-17 alle 12 37 40" src="https://github.com/user-attachments/assets/e05b1161-bf02-457c-9e08-3b7f8c16dcd8">
<img width="1440" alt="Screenshot 2024-11-17 alle 12 41 06" src="https://github.com/user-attachments/assets/bb9bf3e6-bf7e-42ce-b26c-d314ba724d84">


Con cloud shell possono espandere la rete usando :

```
gcloud compute networks subnets expand-ip-range default --region=us-west1 --prefix-length=16

```


```
gcloud compute networks subnets describe default --region=us-west1
```











