# IP Addressing



### **IP Addressing in Google Cloud**

La gestione degli indirizzi IP è fondamentale in Google Cloud per configurare la rete di una **Virtual Private Cloud (VPC)**, le sue subnet e le risorse come VM o servizi gestiti. Google Cloud supporta indirizzi IP privati e pubblici per fornire flessibilità e sicurezza.

---

### **1. Tipi di Indirizzi IP**

#### **1.1 Indirizzi IP Privati**
- Vengono utilizzati per la comunicazione interna tra le risorse all'interno della stessa rete VPC.
- Non sono accessibili direttamente da Internet.
- Sono assegnati automaticamente alle risorse in una subnet o possono essere specificati manualmente.

**Range IP privati supportati** (RFC 1918):
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

#### **1.2 Indirizzi IP Pubblici**
- Consentono alle risorse di comunicare direttamente con Internet.
- Sono associati alle risorse tramite un indirizzo IP esterno (statico o temporaneo).
- Gli indirizzi IP pubblici possono essere rilasciati e riutilizzati.

#### **1.3 Indirizzi IP Alias**
- Consentono a una VM di avere più indirizzi IP privati, utili per configurare più servizi sulla stessa macchina.
- Gli alias IP possono essere assegnati manualmente o automaticamente.

#### **1.4 Indirizzi IP Statici**
- Indirizzi IP (pubblici o privati) che rimangono associati a una risorsa specifica fino a quando non vengono rilasciati manualmente.

**Creazione di un indirizzo IP statico:**
```bash
gcloud compute addresses create my-static-ip \
    --region=us-central1 \
    --addresses=203.0.113.1 \
    --network-tier=STANDARD
```

---

### **2. Assegnazione degli Indirizzi IP**

#### **2.1 Indirizzi IP Privati**
Quando si crea una risorsa in una subnet VPC, un indirizzo IP privato viene assegnato automaticamente, a meno che non si specifichi un indirizzo manualmente.

**Esempio di assegnazione di un indirizzo IP privato:**
```bash
gcloud compute instances create my-instance \
    --subnet=my-subnet \
    --private-network-ip=10.0.1.10
```

#### **2.2 Indirizzi IP Pubblici**
Gli indirizzi IP pubblici possono essere:
- **Temporanei**: Assegnati automaticamente quando una risorsa viene creata con accesso a Internet.
- **Statici**: Riservati manualmente e associati alla risorsa.

**Esempio di assegnazione di un IP pubblico statico:**
```bash
gcloud compute instances create my-instance \
    --network-interface=network-tier=PREMIUM,subnet=my-subnet,address=my-static-ip
```

#### **2.3 Alias IP**
Si può assegnare un alias IP a una VM per consentire la comunicazione tra più servizi sulla stessa macchina.

**Esempio di configurazione di un alias IP:**
```bash
gcloud compute instances create my-instance \
    --subnet=my-subnet \
    --aliases=10.0.1.10/24
```

---

### **3. Regole di Firewall per Indirizzi IP**

Per abilitare o limitare il traffico basato sugli indirizzi IP, si possono configurare regole del firewall. Ad esempio:

**Permettere il traffico HTTP (porta 80):**
```bash
gcloud compute firewall-rules create allow-http \
    --network=my-vpc \
    --allow=tcp:80 \
    --source-ranges=0.0.0.0/0
```

**Limitare il traffico a un range IP specifico:**
```bash
gcloud compute firewall-rules create allow-internal \
    --network=my-vpc \
    --allow=all \
    --source-ranges=10.0.0.0/16
```

---

### **4. Best Practices per la Gestione degli IP**

1. **Pianificazione degli indirizzi IP**
   - Pianificare intervalli IP sufficientemente ampi per supportare la crescita futura.
   - Evitare sovrapposizioni IP tra subnet o con reti on-premise.

2. **Usare IP Alias per microservizi**
   - Configurare alias IP per VM che ospitano più servizi.

3. **Evitare l'uso di IP pubblici quando non necessario**
   - Utilizzare **Cloud NAT** per consentire l'accesso in uscita a Internet senza esporre risorse interne.

4. **Monitoraggio degli IP**
   - Abilitare i **VPC Flow Logs** per monitorare e analizzare l'utilizzo degli indirizzi IP.

---

### **5. Limitazioni**

- **Quota degli IP**: C'è un limite al numero di indirizzi IP pubblici e privati per progetto. Si può aumentare la quota tramite una richiesta a Google Cloud.
- **Sovrapposizioni IP**: Gli intervalli IP delle subnet devono essere univoci all'interno di una rete VPC.

---

### **6. Accesso Privato con Cloud NAT**

In alcuni casi, si desidera che le risorse senza IP pubblico accedano a Internet. **Cloud NAT (Network Address Translation)** consente il traffico in uscita verso Internet utilizzando indirizzi IP NAT condivisi.

**Configurazione di Cloud NAT:**
```bash
gcloud compute routers create my-router \
    --region=us-central1 \
    --network=my-vpc

gcloud compute routers nats create my-nat \
    --router=my-router \
    --nat-external-ip-pool=my-static-ip \
    --region=us-central1
```

---


![Screenshot 2024-11-17 alle 17 10 28](https://github.com/user-attachments/assets/11bf4b00-fa16-466d-a493-09b99c606788)



°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°° INTERNAL IP ADDRESSING °°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°


![Screenshot 2024-11-17 alle 17 18 13](https://github.com/user-attachments/assets/94fc6cde-0c1a-48ba-abd0-41f334f7c0ea)



![Screenshot 2024-11-17 alle 17 19 49](https://github.com/user-attachments/assets/4cb54836-6431-41e0-934e-bc0581a0620b)


![Screenshot 2024-11-17 alle 17 21 00](https://github.com/user-attachments/assets/d209900d-9cf2-4bf5-89b6-839c3b358917)


![Screenshot 2024-11-17 alle 17 21 56](https://github.com/user-attachments/assets/a591b8cf-0183-468e-94ad-3ede0c1656b2)

![Screenshot 2024-11-17 alle 17 22 53](https://github.com/user-attachments/assets/afd25fb4-76cf-4f13-8890-28cd55041bab)


°°°°°°°°°°°° External IP ADDRESSING °°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°

![Screenshot 2024-11-17 alle 17 23 56](https://github.com/user-attachments/assets/f758972e-7bd0-44c3-843b-5672935bb3e0)

![Screenshot 2024-11-17 alle 17 25 06](https://github.com/user-attachments/assets/17aa2d77-5f09-4409-9b9a-22b4a11875be)

![Screenshot 2024-11-17 alle 17 26 03](https://github.com/user-attachments/assets/05daa5d4-a7be-48d6-9cc0-c7ad73e3e0ad)


**INTERNAL IP ADDRESS RESERVATION**

![Screenshot 2024-11-17 alle 17 28 13](https://github.com/user-attachments/assets/760edd86-88d5-40a3-940b-2975b15e39d5)












