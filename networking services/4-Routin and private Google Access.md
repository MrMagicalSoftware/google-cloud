# Routing and Private Google Access





_______________________________________________________________


### **Routing e Private Google Access**

Il **routing** e il **Private Google Access** sono due elementi fondamentali per gestire il traffico di rete all'interno di una VPC e consentire l'accesso sicuro ai servizi Google Cloud senza utilizzare Internet.

---

### **1. Routing nella VPC**

Il routing in una VPC definisce come il traffico viene instradato tra subnet, risorse, o verso destinazioni esterne. Ogni rete VPC ha una tabella di routing associata, che contiene regole per indirizzare i pacchetti.

#### **Tipologie di routing**

1. **Routing predefinito**
   - Quando si crea una VPC, viene configurata automaticamente una regola di routing predefinita per il traffico interno (tra subnet) e una regola per il traffico in uscita verso Internet (se abilitata).

2. **Routing statico**
   - Le rotte sono definite manualmente dall'utente e rimangono fisse.

   **Esempio di creazione di una rotta statica:**
   ```bash
   gcloud compute routes create my-static-route \
       --network=my-vpc \
       --destination-range=10.1.2.0/24 \
       --next-hop-ip=192.168.1.1
   ```

3. **Routing dinamico**
   - Si può utilizzare un **Cloud Router** per gestire rotte dinamiche. Questo approccio è utile per connettere reti on-premise a Google Cloud utilizzando protocolli come BGP (Border Gateway Protocol).

   **Esempio di creazione di un router dinamico:**
   ```bash
   gcloud compute routers create my-router \
       --network=my-vpc \
       --region=us-central1
   ```

#### **Componenti principali del routing**

- **Tabella di routing**: Contiene tutte le regole di routing associate alla VPC.
- **Next hop**: Specifica la destinazione successiva per il traffico. Può essere:
  - Un indirizzo IP di una VM.
  - Una VPN Gateway.
  - Un'interfaccia interna (ILB - Internal Load Balancer).

---

### **2. Private Google Access**

Il **Private Google Access** consente alle risorse all'interno di una subnet VPC di accedere ai servizi Google Cloud (come BigQuery, Cloud Storage, Pub/Sub) utilizzando solo indirizzi IP interni.
Questo elimina la necessità di un indirizzo IP pubblico o di un gateway Internet.

#### **Funzionamento**
- Quando si abilita il Private Google Access su una subnet, le risorse nella subnet possono accedere ai servizi Google mantenendo la comunicazione all'interno della rete privata.

#### **Configurazione**

**Abilitazione del Private Google Access tramite gcloud CLI:**
```bash
gcloud compute networks subnets update my-subnet \
    --region=us-central1 \
    --enable-private-ip-google-access
```

**Abilitazione tramite Console:**
1. Vai a **VPC Network** > **Subnets**.
2. Seleziona la subnet desiderata.
3. Abilita l'opzione **Private Google Access**.

#### **Quando usarlo**
- Per motivi di sicurezza, si utilizza il Private Google Access per evitare che i dati viaggino su Internet pubblico.
- È utile per ambienti sensibili, come quelli in ambito finanziario o sanitario.

---

### **3. Routing e Private Google Access combinati**

Quando si utilizza il Private Google Access, è importante configurare correttamente le tabelle di routing. La subnet che utilizza il Private Google Access deve avere una rotta per indirizzare il traffico verso i servizi Google.

#### **Rotte predefinite per il Private Google Access**
Google configura automaticamente una rotta per il traffico verso gli indirizzi IP specifici dei servizi Google. Non è necessario aggiungere rotte personalizzate per il traffico destinato ai servizi Google, purché il Private Google Access sia abilitato.

---

### **4. Best Practices**

1. **Isolamento del traffico**
   - Configurare regole del firewall per consentire solo il traffico necessario tra subnet e verso Internet.
   
2. **Cloud NAT (Network Address Translation)**
   - Utilizzare **Cloud NAT** per abilitare il traffico in uscita verso Internet per risorse che non hanno un IP pubblico, mantenendo il Private Google Access attivo.

3. **Monitoraggio e audit**
   - Abilitare i VPC Flow Logs per monitorare il traffico di rete e verificare che il Private Google Access sia utilizzato correttamente.

4. **Routing dinamico per connessioni ibride**
   - Usare il routing dinamico con un Cloud Router per mantenere una connettività efficiente tra reti on-premise e Google Cloud.

---


_______________________________________________________________




°°°°°°°°Routing°°°°°°°°°°°°°°°°°°°°°



<img width="1033" alt="Screenshot 2024-11-17 alle 13 24 08" src="https://github.com/user-attachments/assets/aa99a98f-e6ec-4096-9af8-3af996d74645">


In google cloud sono presenti 2 diversi tipi di routing :


<img width="516" alt="Screenshot 2024-11-17 alle 13 25 02" src="https://github.com/user-attachments/assets/f5a7321f-17b7-4cae-97c3-78ce549575ee">


°°°°°°°°°°°°°°° Default Route °°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°


<img width="970" alt="Screenshot 2024-11-17 alle 13 26 35" src="https://github.com/user-attachments/assets/3b3e2e2d-75de-4b02-b692-3ccca3ff26d5">



°°°°°°°°°°°°° Subnet Route °°°°°°°°°°°°°°°°°°°°°°°°°°


 <img width="1053" alt="Screenshot 2024-11-17 alle 13 28 57" src="https://github.com/user-attachments/assets/64a02c40-fd6b-4c76-ac6f-be791a9d758d">




_______________ CUSTOM ROUTES _______________________


1) STATIC ROUTE 

<img width="1064" alt="Screenshot 2024-11-17 alle 13 30 32" src="https://github.com/user-attachments/assets/c660baa1-a478-4578-9d2c-781a8beb3787">

<img width="1308" alt="Screenshot 2024-11-17 alle 13 32 55" src="https://github.com/user-attachments/assets/40e05011-12dd-45a7-800b-ac0b5b1ed191">




2) Dynamic Route


<img width="1397" alt="Screenshot 2024-11-17 alle 13 34 39" src="https://github.com/user-attachments/assets/119558de-300a-401c-9953-c0cce548b4f5">





<img width="1114" alt="Screenshot 2024-11-17 alle 14 05 23" src="https://github.com/user-attachments/assets/4af83cdc-cd71-47fe-a5be-19682850fb70">



















