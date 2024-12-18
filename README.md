# google-cloud




## Introduzione al Cloude di Google






Google Cloud, o Google Cloud Platform (GCP), è una suite di servizi cloud offerti da Google, progettati per supportare aziende, sviluppatori e utenti singoli nella gestione di infrastrutture, dati e applicazioni in un ambiente sicuro e scalabile. GCP offre una vasta gamma di servizi che spaziano dall'elaborazione dei dati alla gestione di macchine virtuali, database, strumenti di machine learning e molto altro.

Panoramica dei servizi principali di GCP:

### 1. **Compute Engine**
   È il servizio di infrastruttura come servizio (IaaS) di Google, che permette di creare e gestire macchine virtuali in esecuzione su hardware dedicato. Compute Engine offre flessibilità e scalabilità, supportando ambienti di sviluppo, test e produzione.

### 2. **App Engine**
   È una piattaforma come servizio (PaaS) che consente di eseguire applicazioni su una piattaforma completamente gestita. È ideale per sviluppatori che vogliono concentrarsi sul codice senza preoccuparsi della gestione dell'infrastruttura, poiché Google si occupa di scalabilità e manutenzione.

### 3. **Kubernetes Engine (GKE)**
   GKE è una piattaforma gestita per l'esecuzione di applicazioni containerizzate basata su Kubernetes, un sistema open-source per l'automazione della gestione, del deployment e della scalabilità dei container.

### 4. **Cloud Storage**
   Un servizio di storage scalabile e sicuro per archiviare e accedere a grandi volumi di dati. Google Cloud Storage supporta vari tipi di archiviazione (Standard, Nearline, Coldline, e Archive) per diversi livelli di accesso e costi.

### 5. **BigQuery**
   È un data warehouse serverless e scalabile per eseguire query SQL su grandi set di dati. BigQuery è particolarmente utile per l'analisi di big data e per generare insights utili in tempo reale.

### 6. **Cloud SQL e Firestore**
   Google Cloud offre diversi servizi di database come **Cloud SQL**, che gestisce database relazionali (come MySQL, PostgreSQL e SQL Server), e **Firestore**, un database NoSQL completamente gestito per applicazioni mobili e web.

### 7. **AI e Machine Learning**
   Google Cloud offre strumenti come **Vertex AI** per sviluppare e implementare modelli di machine learning su larga scala, e le **API AI** per integrare funzioni come traduzione, analisi di testo e riconoscimento immagini nelle applicazioni.

### 8. **Networking e sicurezza**
   Con servizi come **Cloud Load Balancing**, **Cloud CDN**, e **Cloud Armor**, Google Cloud consente di distribuire e proteggere le applicazioni a livello globale. Include anche strumenti di gestione della rete e sicurezza avanzati per proteggere i dati e le applicazioni.

### Vantaggi del Google Cloud
   - **Scalabilità**: permette di crescere senza preoccuparsi di limiti infrastrutturali.
   - **Affidabilità**: GCP è costruito sulla stessa infrastruttura che supporta i servizi di Google.
   - **Sicurezza**: fornisce robusti protocolli di sicurezza e conformità alle normative.
   - **Innovazione**: offre accesso agli strumenti AI/ML e alle ultime tecnologie sviluppate da Google.



_______________


IaaS, o **Infrastructure as a Service**, è un modello di cloud computing in cui un provider cloud fornisce ai clienti risorse di infrastruttura IT di base come **server, storage, e networking**. In questo modello, i clienti possono gestire e configurare queste risorse come meglio credono, ma senza preoccuparsi dell'hardware fisico sottostante o della sua manutenzione.

### Caratteristiche principali di IaaS
- **Virtualizzazione**: IaaS utilizza tecniche di virtualizzazione per offrire accesso a server virtuali (macchine virtuali) che si comportano come server fisici. Gli utenti possono configurare questi server con le proprie specifiche, installando il sistema operativo e le applicazioni desiderate.
  
- **Gestione flessibile**: gli utenti possono gestire e configurare direttamente le risorse, controllando l'ambiente virtuale in modo simile a come farebbero in un data center on-premises.
  
- **Flessibilità e scalabilità**: IaaS consente di aumentare o diminuire le risorse in base alle esigenze. Gli utenti possono aggiungere server, aumentare lo spazio di archiviazione o la capacità di rete senza dover acquistare nuovo hardware fisico.
  
- **Pagamento basato sull'uso**: i servizi IaaS sono solitamente fatturati in base all'uso (pay-as-you-go). Si paga solo per le risorse effettivamente utilizzate, eliminando i costi associati alla manutenzione dell'hardware fisico.

### Vantaggi di IaaS

IaaS è l'opzione ideale per chi ha bisogno di controllo e flessibilità a livello di infrastruttura senza preoccuparsi dell’hardware fisico.


- **Risparmio sui costi**: permette di evitare investimenti iniziali in hardware e infrastruttura.
- **Maggior controllo**: offre agli utenti pieno controllo su macchine virtuali, reti e storage.
- **Scalabilità**: si può scalare rapidamente in risposta ai cambiamenti nelle necessità di elaborazione o archiviazione.
- **Accessibilità globale**: le risorse IaaS sono accessibili da qualsiasi parte del mondo, consentendo collaborazione e accesso remoto.

### Esempi di fornitori di IaaS
I principali fornitori di servizi IaaS includono:
- **Google Cloud Compute Engine** (in Google Cloud Platform)
- **Amazon Web Services (AWS)** con Amazon EC2
- **Microsoft Azure** con le sue Virtual Machines

### Differenza tra IaaS, PaaS e SaaS
- **IaaS**: fornisce l'infrastruttura di base (macchine virtuali, storage, rete), mentre l'utente gestisce il sistema operativo e le applicazioni.
- **PaaS (Platform as a Service)**: fornisce un ambiente già pronto per sviluppare, testare e distribuire applicazioni, senza bisogno di gestire l'infrastruttura sottostante.
- **SaaS (Software as a Service)**: fornisce applicazioni completamente gestite e pronte per l'uso (es. Google Workspace o Microsoft 365).



![Screenshot 2024-11-10 alle 17 06 43](https://github.com/user-attachments/assets/3f23961e-f0c3-4496-8ec8-bcda52acf281)


**Definizione di cloud**

l'erogazione di un pool di servizi informatici on demand su Internet, che possono essere rapidamente forniti e rilasciati con un minimo sforzo di gestione o di interazione con il fornitore di servizi.


>Server
>Storage
>Networking
>Databases


**Le 5 caratteristiche del cloud**

1) On-demand Self Service
   (Provision reseources automatically without requiring human interaction)

2) Broad Network Access
   (Available over the network)

3) Resource Pooling
   (Pooled resources to support a multi-tenant model allowing multiple customers to share the same applications or the same physical infrastructure)

4) Rapid Elasticity
   (Rapidly provision and de-provision any of the cloud computing resources)

5) Measured Service
   (Resources usage can be monitored, controlled and reported using metering capabilities)



![Screenshot 2024-11-10 alle 17 26 26](https://github.com/user-attachments/assets/28066781-b580-459b-9ae7-cf60ed3e1ff2)



**Cloud DEPLOYMENT Models**



![Screenshot 2024-11-10 alle 17 11 28](https://github.com/user-attachments/assets/3aa91650-0f2e-4525-81db-f262b06053de)



![Screenshot 2024-11-10 alle 17 11 40](https://github.com/user-attachments/assets/5264e080-b4bc-4f3c-82c7-a8f3a919fbd5)



I modelli di cloud deployment definiscono il modo in cui un’infrastruttura cloud è implementata e utilizzata.

la scelta del modello di cloud deployment dipende dalle esigenze dell’organizzazione in termini di sicurezza, controllo, flessibilità e costo. Molte aziende adottano approcci ibridi o multi-cloud per ottenere un bilanciamento ottimale tra sicurezza e scalabilità.



I principali modelli di deployment nel cloud sono:
1. Cloud Pubblico

Il cloud pubblico è gestito da un provider di servizi esterno (come Google Cloud, AWS, o Microsoft Azure) che mette a disposizione le risorse cloud (server, storage, rete) su un’infrastruttura condivisa e accessibile via Internet. In questo modello, le risorse sono condivise tra diversi utenti (multi-tenant), mantenendo comunque la separazione dei dati tra i clienti.

    Vantaggi:
        Bassi costi iniziali e manutenzione ridotta, poiché l’infrastruttura è gestita dal provider.
        Alta scalabilità per gestire le esigenze in crescita o stagionali.
        Accesso a una vasta gamma di servizi e tecnologie innovative.

    Svantaggi:
        Maggiore dipendenza dal provider per la sicurezza e la privacy.
        Possibili problemi di latenza, specialmente se i server sono lontani dall’utente.

2. Cloud Privato

![Screenshot 2024-11-10 alle 17 37 55](https://github.com/user-attachments/assets/dd447915-60d6-4ed8-a5f4-73b6cc064746)


Il cloud privato è dedicato a una singola organizzazione e può essere gestito internamente o da un provider esterno. In questo modello, l’infrastruttura cloud è progettata per offrire maggiore controllo e sicurezza, spesso su hardware dedicato che garantisce un ambiente isolato.

    Vantaggi:
        Maggiore sicurezza e controllo sui dati e sull’infrastruttura.
        Ideale per le organizzazioni con requisiti di conformità e regolamentazione elevati.
        Minore rischio di latenza, poiché il cloud è spesso ospitato presso la sede dell’organizzazione.

    Svantaggi:
        Costi elevati per l’acquisto e la manutenzione dell’infrastruttura.
        Scalabilità limitata rispetto al cloud pubblico.

3. Cloud Ibrido

![Screenshot 2024-11-10 alle 17 39 32](https://github.com/user-attachments/assets/294ed75f-8ca1-4233-9500-625684aee982)


Il cloud ibrido combina elementi del cloud pubblico e del cloud privato, permettendo alle organizzazioni di sfruttare i vantaggi di entrambi i modelli. Le aziende possono mantenere i dati sensibili o i carichi di lavoro critici nel cloud privato, utilizzando invece il cloud pubblico per carichi di lavoro meno critici o per gestire picchi di utilizzo.

    Vantaggi:
        Maggiore flessibilità: consente di adattare i carichi di lavoro tra cloud pubblico e privato in base alle esigenze.
        Maggiore efficienza sui costi: le aziende possono utilizzare il cloud pubblico per esigenze temporanee o inaspettate.
        Bilanciamento della sicurezza e della scalabilità.

    Svantaggi:
        Complessità di gestione e integrazione tra cloud pubblico e privato.
        Maggiore necessità di coordinamento tra i due ambienti per garantire la compatibilità.

4. Multi-Cloud

Il multi-cloud implica l'uso di più provider di cloud pubblico (ad esempio, AWS, Google Cloud e Azure) all'interno della stessa organizzazione. È utile per evitare la dipendenza da un singolo fornitore (vendor lock-in), distribuendo il rischio e sfruttando i punti di forza di ciascun provider.

![Screenshot 2024-11-10 alle 17 34 05](https://github.com/user-attachments/assets/59eda000-96fe-43e9-8034-be3e2b3f4737)


    Vantaggi:
        Maggiore flessibilità: si possono scegliere i servizi migliori tra diversi provider.
        Riduzione del rischio di dipendenza da un singolo provider.
        Ottimizzazione dei costi: possibilità di scegliere il fornitore più economico per ciascun servizio.

    Svantaggi:
        Maggiore complessità nella gestione e nel monitoraggio delle risorse.
        Possibili problemi di compatibilità e integrazione tra i servizi dei diversi provider.

![Screenshot 2024-11-10 alle 17 41 24](https://github.com/user-attachments/assets/902e9984-6d0a-44e7-a26a-ff71c1423bfc)




________________________

## Cloud service Models 

![Screenshot 2024-11-10 alle 17 44 04](https://github.com/user-attachments/assets/2c3d5198-a418-473e-a263-c2c9516a4d94)


Con X che varia :

![Screenshot 2024-11-10 alle 17 47 20](https://github.com/user-attachments/assets/15476a99-333f-4c62-8ca8-f6bbeb9527ef)





I **modelli di servizio del cloud** (o **cloud service models**) definiscono il livello di controllo, gestione e automazione delle risorse IT fornito da un provider cloud. Esistono tre principali modelli di servizio:

### 1. **IaaS (Infrastructure as a Service)**
   **Infrastructure as a Service** è il modello di servizio più "basso" nella gerarchia del cloud, fornendo le risorse di infrastruttura di base come **server virtuali, storage, rete e sistemi operativi**. L’utente ha il controllo su queste risorse e può installare e gestire applicazioni e sistemi operativi come meglio preferisce.

   - **Esempi**: Amazon EC2 (AWS), Google Compute Engine (GCP), Microsoft Azure Virtual Machines.
   
   - **Vantaggi**:
     - **Flessibilità e controllo**: offre controllo completo sulle risorse di computing.
     - **Scalabilità**: le risorse possono essere scalate in base alle necessità.
     - **Pagamento a consumo**: si paga solo per le risorse utilizzate.
   
   - **Tipico utilizzo**: Ideale per chi ha bisogno di un controllo profondo dell'infrastruttura, come ambienti di test e sviluppo, data center virtuali, e applicazioni con configurazioni specifiche.

### 2. **PaaS (Platform as a Service)**
   **Platform as a Service** è un livello sopra IaaS e fornisce un ambiente completamente gestito per sviluppare, testare, distribuire e gestire applicazioni senza doversi preoccupare dell’infrastruttura sottostante. In un ambiente PaaS, il provider cloud gestisce hardware, sistemi operativi, storage e database, lasciando agli sviluppatori il solo compito di concentrarsi sullo sviluppo dell’applicazione.

   - **Esempi**: Google App Engine (GCP), Microsoft Azure App Services, Heroku.
   
   - **Vantaggi**:
     - **Riduzione dei costi di gestione**: non è necessario occuparsi della manutenzione dell'infrastruttura.
     - **Ambiente di sviluppo ottimizzato**: offre strumenti preconfigurati per il coding, il test e il deployment.
     - **Velocità di sviluppo**: consente agli sviluppatori di concentrarsi solo sul codice, accelerando il ciclo di sviluppo.
   
   - **Tipico utilizzo**: Adatto per sviluppare applicazioni web e mobile, progetti di prototipazione e sviluppo di applicazioni di e-commerce, CRM, o sistemi di gestione aziendale.

### 3. **SaaS (Software as a Service)**
   **Software as a Service** è il modello di cloud più completo, in cui il provider offre applicazioni pronte all'uso accessibili via Internet. Gli utenti utilizzano il software direttamente senza doversi preoccupare dell'infrastruttura, della piattaforma o della gestione dell’applicazione stessa. SaaS è ideale per software standardizzati, utilizzati da una vasta gamma di utenti.

   - **Esempi**: Google Workspace (ex G Suite), Microsoft 365, Salesforce, Dropbox.
   
   - **Vantaggi**:
     - **Accessibilità**: applicazioni disponibili via Internet da qualsiasi dispositivo.
     - **Manutenzione e aggiornamenti**: tutto è gestito dal provider, inclusi aggiornamenti e sicurezza.
     - **Costi prevedibili**: spesso offerto con piani di abbonamento a costo fisso.

   - **Tipico utilizzo**: Ideale per software aziendali come CRM, sistemi di gestione dei progetti, strumenti di collaborazione, applicazioni di posta elettronica e gestione documentale.

### Differenze principali tra IaaS, PaaS e SaaS

| **Modello**  | **Responsabilità Utente**                       | **Responsabilità Provider**                  |
|--------------|-------------------------------------------------|----------------------------------------------|
| **IaaS**     | Sistema operativo, middleware, runtime, app     | Infrastruttura fisica (server, storage)      |
| **PaaS**     | Applicazioni, configurazioni specifiche         | Infrastruttura, sistema operativo, runtime   |
| **SaaS**     | Utilizzo del software                           | Tutto (infrastruttura, OS, app, manutenzione)|




![Screenshot 2024-11-10 alle 17 50 04](https://github.com/user-attachments/assets/072ca144-6100-42b4-ad88-b264b0ea604e)



____________________________



# Google Cloud Global Infrastructure



La **Google Cloud Global Infrastructure** è l’infrastruttura globale di data center e risorse di rete che Google utilizza per offrire i suoi servizi cloud, fornendo una piattaforma scalabile, sicura e ad alta disponibilità per le aziende di tutto il mondo. Google ha costruito questa infrastruttura per sostenere i suoi prodotti (come Google Search e YouTube) e oggi rende disponibili queste risorse anche agli utenti di **Google Cloud Platform (GCP)**.

### Principali Componenti dell'Infrastruttura Globale di Google Cloud

#### 1. **Regioni e Zone**
   - **Regioni**: Google Cloud è organizzato in regioni distribuite geograficamente in tutto il mondo. Ogni regione è un’area geografica distinta e autonoma, come l'Europa occidentale (europe-west1) o l'Asia orientale (asia-east1).
   - **Zone**: Ogni regione contiene più zone, che rappresentano data center fisicamente isolati tra loro. Le zone all'interno di una regione permettono alle applicazioni di ridondanza e alta disponibilità, poiché i servizi possono essere replicati tra diverse zone della stessa regione per garantire continuità operativa anche in caso di problemi.

#### 2. **Rete Privata Globale**
   - Google Cloud possiede e gestisce una delle reti private più vaste al mondo, che include **cavi sottomarini privati** e collegamenti di rete ad alta velocità. Questo assicura una bassa latenza, elevata velocità di trasferimento dati e sicurezza.


![Screenshot 2024-11-10 alle 18 04 46](https://github.com/user-attachments/assets/4120cc6d-6f68-434d-bdc1-86ffdd3ac1b4)



![Screenshot 2024-11-10 alle 18 08 26](https://github.com/user-attachments/assets/84336410-a47b-42b0-844e-a9d4a4dbfc45)









   - La rete globale di Google permette anche il **peering** diretto con altre reti, ottimizzando ulteriormente la connettività tra i suoi data center e offrendo una connettività diretta e sicura verso altre piattaforme cloud o on-premises.

#### 3. **Punti di Presenza (PoP) e Caching**
   - I **Punti di Presenza (PoP)** sono hub di rete distribuiti in tutto il mondo che garantiscono un accesso rapido ai servizi Google Cloud. Google utilizza questi punti di accesso per instradare efficacemente il traffico e ridurre la latenza.
   - Google implementa inoltre sistemi di **caching** per ottimizzare la distribuzione dei contenuti, migliorando le performance per utenti globali, particolarmente per contenuti statici e file multimediali.


![Screenshot 2024-11-10 alle 18 09 57](https://github.com/user-attachments/assets/3ac6d093-9e52-4679-8aed-d65b6be37e9a)





#### 4. **Sicurezza dell’Infrastruttura**
   - Google adotta una serie di misure di sicurezza all’avanguardia per proteggere la sua infrastruttura, che comprendono **crittografia dei dati in transito e a riposo**, sistemi avanzati di rilevamento delle minacce e gestione delle identità e degli accessi.
   - L'infrastruttura di Google Cloud aderisce a numerose certificazioni di conformità, come **ISO/IEC 27001, SOC 1/2/3** e **GDPR**, rispettando rigorosi standard di sicurezza e privacy.

#### 5. **Availability e Redundancy**
   - Google Cloud è progettato per garantire alta disponibilità e ridondanza. I servizi sono replicati tra zone e regioni, permettendo agli utenti di creare applicazioni resilienti che possono continuare a funzionare anche in caso di guasti a livello di zona o di data center.
   - Google fornisce inoltre strumenti come il **Cloud Load Balancing**, che distribuisce automaticamente il traffico tra le risorse globali per migliorare la disponibilità e ridurre i tempi di inattività.

### Vantaggi della Google Cloud Global Infrastructure

- **Bassa latenza e alte prestazioni** grazie alla rete privata globale e ai data center distribuiti.
- **Sicurezza avanzata** e compliance con gli standard internazionali per la protezione dei dati e la privacy.
- **Scalabilità globale**, che permette di espandere le applicazioni rapidamente e senza interruzioni.
- **Flessibilità e ridondanza**: i servizi possono essere distribuiti su più zone e regioni per garantire la continuità operativa.
  





![Screenshot 2024-11-10 alle 18 02 39](https://github.com/user-attachments/assets/41fb7e6f-c908-4b88-b0ac-2448a018d58f)



![Screenshot 2024-11-10 alle 18 02 51](https://github.com/user-attachments/assets/ae0c36c7-d5ec-4722-988c-298fad031c5e)


**Zone**


![Screenshot 2024-11-10 alle 18 13 07](https://github.com/user-attachments/assets/293b5038-5a08-4211-9ed3-c9151deced70)




**Regione**

Una regione è una collections di Zone


![Screenshot 2024-11-10 alle 18 15 29](https://github.com/user-attachments/assets/f73b7b5e-2995-4746-b814-60e54f64ae84)



**Multi-region**

![Screenshot 2024-11-10 alle 18 17 18](https://github.com/user-attachments/assets/cfb7ba78-38f6-4a99-926f-d7ffb1ca867d)


Recap :

![Screenshot 2024-11-10 alle 18 18 12](https://github.com/user-attachments/assets/97c3d877-2bc8-43f1-8609-96be4f875724)

___________________________________________



# Compute Service Options



I servizi di **Compute** di Google Cloud offrono diverse opzioni per eseguire carichi di lavoro computazionali, con livelli di controllo, scalabilità e automazione diversi. Ogni servizio è progettato per supportare varie esigenze di sviluppo, dall'esecuzione di macchine virtuali personalizzate all'orchestrazione di container e all'hosting di applicazioni serverless.


![Screenshot 2024-11-10 alle 18 29 52](https://github.com/user-attachments/assets/0469600e-6e00-4d03-9ccd-2bccda1657a9)



principali opzioni di servizi di calcolo (Compute) in Google Cloud:

### 1. **Compute Engine**
   **Compute Engine** è il servizio di **Infrastructure as a Service (IaaS)** di Google Cloud che consente di eseguire **macchine virtuali** (VM) personalizzate in ambiente cloud. Con Compute Engine, gli utenti hanno il controllo completo delle VM, inclusa la scelta del sistema operativo, delle risorse di memoria e di CPU, delle configurazioni di rete e delle opzioni di storage.

   - **Ideale per**: carichi di lavoro tradizionali, applicazioni legacy, ambienti di sviluppo personalizzati e applicazioni che richiedono un controllo approfondito dell'infrastruttura.
   - **Vantaggi**:
     - Flessibilità nella scelta delle risorse e nelle configurazioni di rete.
     - Ampio supporto per sistemi operativi, inclusi Linux e Windows.
     - Opzioni di scalabilità automatica per adattare le risorse alle esigenze dei carichi di lavoro.

![Screenshot 2024-11-10 alle 18 31 56](https://github.com/user-attachments/assets/03b825de-1b2a-4a88-bb06-67bd8adcff96)

![Screenshot 2024-11-10 alle 18 33 12](https://github.com/user-attachments/assets/ef6552c7-6663-463e-a206-86d4e4e747e6)





### 2. **Google Kubernetes Engine (GKE)**
   **Google Kubernetes Engine** è un servizio di **container orchestration** che utilizza Kubernetes per gestire i **container** su larga scala. GKE offre un ambiente completamente gestito per eseguire e orchestrare applicazioni containerizzate, riducendo la complessità della gestione manuale dei cluster Kubernetes.

   - **Ideale per**: applicazioni basate su microservizi, workload containerizzati e ambienti DevOps.
   - **Vantaggi**:
     - Kubernetes gestito da Google, che si occupa di aggiornamenti, scaling e sicurezza.
     - Integrazione nativa con i servizi di rete, bilanciamento del carico e sicurezza di Google Cloud.
     - Supporto per cluster ibridi e multi-cloud tramite **Anthos**, che consente di gestire container su ambienti diversi.


![Screenshot 2024-11-10 alle 18 35 16](https://github.com/user-attachments/assets/8f333001-c318-4abe-9fcd-9965749e51b5)



   
### 3. **App Engine**
   **Google App Engine** è una piattaforma **Platform as a Service (PaaS)** che consente agli sviluppatori di eseguire applicazioni senza dover gestire l'infrastruttura. Con App Engine, è possibile distribuire applicazioni in vari linguaggi di programmazione (come Python, Java, Go, PHP) in un ambiente scalabile e completamente gestito.

   - **Ideale per**: applicazioni web e mobile, prototipazione rapida, e startup che cercano di evitare la gestione dell’infrastruttura.
   - **Vantaggi**:
     - Completamente gestito, con scalabilità automatica in base al traffico.
     - Nessuna configurazione del server: gli sviluppatori si concentrano solo sul codice.
     - Integrato con numerosi servizi di Google Cloud per semplificare la creazione di applicazioni complete.
    
![Screenshot 2024-11-10 alle 18 37 14](https://github.com/user-attachments/assets/e80da5d5-58c5-41a8-b62f-f965606a980a)








   
### 4. **Cloud Functions**
   **Cloud Functions** è il servizio **serverless di Function as a Service (FaaS)** di Google Cloud che permette di eseguire codice in risposta a eventi, senza dover gestire server o infrastruttura. Cloud Functions è ideale per task singoli, come rispondere a richieste HTTP, attivarsi in base a eventi di altri servizi (ad esempio, caricamento di file in Cloud Storage) o gestire eventi di integrazione.

   - **Ideale per**: automazione, task singoli, API semplici e integrazioni di microservizi.
   - **Vantaggi**:
     - Esecuzione serverless: Google gestisce completamente le risorse di calcolo.
     - Scatta ed esegue il codice solo quando si verificano eventi specifici, riducendo i costi.
     - Facile da integrare con altri servizi di Google Cloud, come Pub/Sub e Cloud Storage.
    

![Screenshot 2024-11-10 alle 18 38 27](https://github.com/user-attachments/assets/e3095262-e833-448d-86e8-6275322ab3ca)

![Screenshot 2024-11-10 alle 18 39 38](https://github.com/user-attachments/assets/5715afbf-59e0-48ef-80f0-19b57b468a28)





   
### 5. **Cloud Run**
   **Cloud Run** è una piattaforma serverless per eseguire **container** in risposta a richieste HTTP o eventi, senza gestire direttamente server o infrastruttura. Con Cloud Run, gli sviluppatori possono distribuire qualsiasi applicazione containerizzata senza dover gestire Kubernetes o macchine virtuali.

   - **Ideale per**: API, applicazioni web containerizzate, e carichi di lavoro stateless.
   - **Vantaggi**:
     - Esecuzione serverless di container: scala automaticamente in base al traffico.
     - Basato su standard open-source (Knative), quindi supporta facilmente anche ambienti multi-cloud.
     - Opzione per configurare Cloud Run in modalità **Cloud Run for Anthos**, che consente di eseguire i carichi di lavoro su cluster Kubernetes esistenti.
    


 ![Screenshot 2024-11-10 alle 18 41 01](https://github.com/user-attachments/assets/7b12bf1d-7c69-4920-9875-f2a1d5b53963)







### Schema delle opzioni di Compute Service su Google Cloud

| **Servizio**            | **Tipo**       | **Controllo**            | **Gestione dell’infrastruttura** | **Ideale per**                            |
|-------------------------|----------------|---------------------------|-----------------------------------|-------------------------------------------|
| **Compute Engine**      | IaaS           | Alto                      | Utente                            | Applicazioni legacy, VM personalizzate    |
| **Kubernetes Engine**   | Container      | Moderato                  | Google (Kubernetes gestito)       | Applicazioni containerizzate, microservizi|
| **App Engine**          | PaaS           | Basso                     | Google                            | Applicazioni web e mobile                 |
| **Cloud Functions**     | FaaS           | Molto basso               | Google                            | Task singoli, automazione                |
| **Cloud Run**           | Serverless     | Moderato                  | Google                            | Applicazioni containerizzate stateless    |




![Screenshot 2024-11-10 alle 18 26 41](https://github.com/user-attachments/assets/420196e7-df5a-44ff-bf17-a9782a33dcfd)




_________________________________________________




# Storage and Database Options



Google Cloud offre una vasta gamma di opzioni di **storage** e **database** per gestire dati di ogni tipo, da file e oggetti a database relazionali e non relazionali, ognuno progettato per scopi diversi e ottimizzato per esigenze specifiche di prestazioni, disponibilità e scalabilità. 




### Storage Options

1. **Cloud Storage**
   - **Tipo**: Storage di oggetti.
   - **Descrizione**: Un servizio di archiviazione di oggetti per memorizzare file di ogni tipo (video, immagini, backup) su larga scala, accessibili via HTTP o HTTPS. Supporta varie classi di storage in base alla frequenza di accesso ai dati (Standard, Nearline, Coldline, Archive).
   - **Ideale per**: Archiviazione di dati non strutturati, backup e recupero di emergenza, archivi a lungo termine, content delivery.
   - **Vantaggi**:
     - Sicurezza avanzata e ridondanza globale.
     - Semplice integrazione con altri servizi Google Cloud.
     - Costo variabile a seconda della frequenza di accesso.

![Screenshot 2024-11-10 alle 21 42 04](https://github.com/user-attachments/assets/3175a706-ba2e-4ae3-9f81-832670f1b501)

**Cloude Storage Classes :**


![Screenshot 2024-11-10 alle 21 44 17](https://github.com/user-attachments/assets/4e3398b2-588d-4b62-b82e-3774fb91c673)


**Google Cloud Storage** offre diverse **classi di archiviazione** (Storage Classes) per ottimizzare i costi in base alla frequenza di accesso e alla durata della conservazione dei dati. Ogni classe è progettata per un tipo specifico di utilizzo e varia nei costi di memorizzazione e nelle tariffe di accesso ai dati. Tutte le classi di archiviazione condividono la stessa API, consentendo una gestione semplice dei dati e una migrazione tra le classi senza dover trasferire fisicamente i dati.

### Classi di Archiviazione di Google Cloud Storage

1. **Standard Storage**
   - **Descrizione**: La classe più adatta per i dati ad accesso frequente e con elevata disponibilità. Perfetta per carichi di lavoro attivi, come siti web, applicazioni web o data analysis.
   - **Ideale per**: Archiviazione di dati a cui si accede frequentemente, applicazioni di produzione, dati transazionali.
   - **Costo di memorizzazione**: Più elevato rispetto ad altre classi, ma con tariffe di accesso basse.
   - **Disponibilità**: 99.9% a livello di singola regione e 99.99% a livello multi-regione.

2. **Nearline Storage**
   - **Descrizione**: Pensata per dati a cui si accede meno frequentemente (circa una volta al mese). Ha un costo di memorizzazione più basso rispetto allo Standard Storage, ma tariffe di accesso ai dati più alte.
   - **Ideale per**: Backup periodici, storage per dati di disaster recovery, e archivi di dati che necessitano di accesso occasionale.
   - **Costo di memorizzazione**: Inferiore rispetto alla classe Standard.
   - **Tariffa di recupero dati**: Applicata per ogni accesso ai dati.
   - **Disponibilità**: 99.9% a livello di singola regione e 99.99% a livello multi-regione.

3. **Coldline Storage**
   - **Descrizione**: Ideale per dati a cui si accede raramente, circa una volta all'anno. Ha un costo di memorizzazione basso e tariffe di accesso più elevate, pensata per dati che devono essere conservati a lungo termine e sono usati solo in caso di necessità.
   - **Ideale per**: Backup a lungo termine, disaster recovery, archiviazione di dati legali o finanziari.
   - **Costo di memorizzazione**: Inferiore rispetto a Nearline Storage.
   - **Tariffa di recupero dati**: Più elevata, applicata per ogni accesso ai dati.
   - **Disponibilità**: 99.9% a livello di singola regione e 99.99% a livello multi-regione.

4. **Archive Storage**
   - **Descrizione**: La classe di archiviazione con i costi più bassi, adatta per dati che devono essere conservati per molti anni e a cui si accede raramente. Sebbene i costi di recupero siano più elevati, è ottimale per archivi di lunga durata.
   - **Ideale per**: Dati da conservare a lungo termine, archiviazione di dati storici, backup di documenti che potrebbero essere richiesti solo in casi eccezionali.
   - **Costo di memorizzazione**: Il più basso di tutte le classi.
   - **Tariffa di recupero dati**: La più elevata, applicata per ogni accesso.
   - **Disponibilità**: 99.9% a livello di singola regione e 99.99% a livello multi-regione.

### Confronto delle Classi di Archiviazione

| **Classe**        | **Frequenza di Accesso**  | **Costo di Memorizzazione** | **Tariffa di Recupero Dati** | **Ideale per**                                  |
|-------------------|---------------------------|-----------------------------|------------------------------|-------------------------------------------------|
| **Standard**      | Frequentemente            | Più elevato                 | Basso                        | Dati ad accesso frequente, app in produzione    |
| **Nearline**      | Occasionalmente (1/mese)  | Medio                       | Medio                        | Backup periodici, archivi a accesso occasionale |
| **Coldline**      | Raramente (1/anno)        | Basso                       | Alto                         | Backup a lungo termine, disaster recovery       |
| **Archive**       | Molto raramente           | Molto basso                 | Molto alto                   | Archivi di lunga durata, dati storici           |

Google Cloud consente anche di cambiare classe di archiviazione dei dati in modo dinamico e programmabile tramite policy di **lifecycle management**, così che i dati possano essere automaticamente trasferiti a classi meno costose man mano che invecchiano o cambiano requisiti di accesso.


![Screenshot 2024-11-10 alle 21 45 49](https://github.com/user-attachments/assets/e8372918-cde4-41d5-88c7-bc8d7be12830)




La **disponibilità** di **Google Cloud Storage** indica la probabilità che i dati siano accessibili e disponibili quando richiesto. La disponibilità varia leggermente a seconda della classe di archiviazione e della configurazione geografica (multi-regione, dual-regione o singola regione). Più la configurazione è distribuita (ad esempio multi-regione), maggiore sarà la disponibilità.

### Livelli di Disponibilità delle Classi di Google Cloud Storage

1. **Standard Storage**
   - **Disponibilità Multi-regione**: 99.95%
   - **Disponibilità Regione Singola**: 99.9%
   - È progettato per carichi di lavoro che richiedono accesso continuo ai dati e che non possono tollerare interruzioni, adatto per applicazioni critiche.

2. **Nearline Storage**
   - **Disponibilità Multi-regione**: 99.95%
   - **Disponibilità Regione Singola**: 99.9%
   - Offre un buon equilibrio tra costi e disponibilità, ideale per backup o dati a cui si accede periodicamente.

3. **Coldline Storage**
   - **Disponibilità Multi-regione**: 99.95%
   - **Disponibilità Regione Singola**: 99.9%
   - Destinato ai dati ad accesso infrequente ma che devono essere altamente disponibili se richiesti, come nel caso di dati di ripristino d'emergenza.

4. **Archive Storage**
   - **Disponibilità Multi-regione**: 99.95%
   - **Disponibilità Regione Singola**: 99.9%
   - Pur avendo il costo più basso, mantiene un'alta disponibilità per dati di lungo termine e accesso raro, come archivi storici.

### Differenze tra Multi-regione, Dual-regione e Regione Singola

- **Multi-regione**: i dati sono replicati in più regioni all'interno di una determinata area geografica (come Stati Uniti, Europa o Asia), garantendo una disponibilità molto alta. È ideale per dati con requisiti di accesso globale e per ridurre al minimo i tempi di latenza.
  
- **Dual-regione**: i dati vengono replicati in due regioni specifiche all'interno di un'area geografica. Offre un buon compromesso tra disponibilità elevata e localizzazione geografica mirata, riducendo la latenza per aree specifiche.

- **Regione Singola**: i dati sono memorizzati in una sola regione, con un livello di disponibilità leggermente inferiore rispetto a configurazioni multi-regione, ma a un costo inferiore. È adatto per applicazioni che non necessitano di disponibilità globale o accesso rapido a livello internazionale.

### Riepilogo della Disponibilità di Google Cloud Storage

| **Classe**           | **Multi-regione** | **Dual-regione** | **Regione Singola** |
|----------------------|-------------------|-------------------|----------------------|
| **Standard**         | 99.95%            | 99.95%           | 99.9%               |
| **Nearline**         | 99.95%            | 99.95%           | 99.9%               |
| **Coldline**         | 99.95%            | 99.95%           | 99.9%               |
| **Archive**          | 99.95%            | 99.95%           | 99.9%               |

### Considerazioni

- Per applicazioni mission-critical che richiedono un'alta disponibilità e ridondanza, le configurazioni multi-regione e dual-regione sono più appropriate.
- Le policy di disponibilità di Google Cloud Storage garantiscono che anche per le classi a costo inferiore sia disponibile un elevato livello di accesso, anche in caso di guasti infrastrutturali.












2. **Persistent Disk**
   - **Tipo**: Block storage.
   - **Descrizione**: Storage persistente per macchine virtuali su **Compute Engine** e **Google Kubernetes Engine**. Offre dischi standard, SSD e bilanciamento delle prestazioni e dei costi.
   - **Ideale per**: Applicazioni che richiedono elevate IOPS, database su VM, storage per container su GKE.
   - **Vantaggi**:
     - Prestazioni prevedibili e bassa latenza.
     - Ridimensionamento dinamico e backup incrementali.

3. **Filestore**
   - **Tipo**: File storage.
   - **Descrizione**: Soluzione di storage di file completamente gestita compatibile con il protocollo NFS, per supportare applicazioni che richiedono una struttura di file system.
   - **Ideale per**: Applicazioni che richiedono accesso diretto ai file, backup e restore di database, workload di machine learning e rendering.
   - **Vantaggi**:
     - Facile integrazione con VM e container.
     - Performance configurabili in base al carico di lavoro.
    


![Screenshot 2024-11-10 alle 21 51 48](https://github.com/user-attachments/assets/72849885-4b92-4209-b95e-da25fdaa4a5a)



4. **Local SSD**
   - **Tipo**: Storage su disco locale.
   - **Descrizione**: Storage su SSD locale a bassa latenza, collegato direttamente alle VM su Compute Engine, per carichi di lavoro con alti requisiti di IOPS e bassa latenza.
   - **Ideale per**: Applicazioni ad alte prestazioni che richiedono un accesso rapido ai dati, come database ad alta velocità.
   - **Vantaggi**:
     - Prestazioni molto elevate e tempi di accesso rapidi.
     - Progettato per supportare carichi intensivi in lettura e scrittura.

### Database Options




![Screenshot 2024-11-10 alle 21 55 26](https://github.com/user-attachments/assets/89bad949-1b2e-4c22-a9a9-c22c6c61ac4f)










1. **Cloud SQL**
   - **Tipo**: Database relazionale (SQL).
   - **Descrizione**: Database completamente gestito per MySQL, PostgreSQL e SQL Server. Consente di configurare, mantenere e scalare database relazionali nel cloud.
   - **Ideale per**: Applicazioni che richiedono la struttura relazionale di SQL, come CRM, ERP e applicazioni web.
   - **Vantaggi**:
     - Gestione automatizzata di backup, patch e scaling.
     - Sicurezza integrata con crittografia, autenticazione e conformità.
     - Alta disponibilità con failover automatico.

2. **Cloud Spanner**
   - **Tipo**: Database distribuito relazionale (SQL).
   - **Descrizione**: Database relazionale globale scalabile e distribuito, progettato per applicazioni di livello enterprise che richiedono scalabilità e transazioni multi-regione.
   - **Ideale per**: Applicazioni globali e mission-critical che richiedono alta coerenza e scalabilità orizzontale.
   - **Vantaggi**:
     - Scalabilità globale e forte coerenza dei dati.
     - Compatibilità con SQL e gestione automatica dei dati.
    

![Screenshot 2024-11-10 alle 21 56 38](https://github.com/user-attachments/assets/f9f9886a-4465-4a7e-a660-a6484e6273db)





3. **Bigtable**
   - **Tipo**: Database NoSQL a colonne.
   - **Descrizione**: Database NoSQL scalabile progettato per gestire grandi volumi di dati (fino a petabyte), con una struttura a colonne per applicazioni che richiedono bassa latenza e throughput elevato.
   - **Ideale per**: Dati temporali, analisi IoT, motori di raccomandazione e analytics in tempo reale.
   - **Vantaggi**:
     - Alta disponibilità e bassa latenza.
     - Perfetto per dataset molto grandi, strutturati e scalabili.

4. **Firestore**
   - **Tipo**: Database NoSQL documentale.
   - **Descrizione**: Database NoSQL gestito, progettato per memorizzare e sincronizzare dati strutturati e semi-strutturati su larga scala, compatibile con l’ambiente serverless di Google.
   - **Ideale per**: Applicazioni mobile, web e IoT che richiedono sincronizzazione e aggiornamenti in tempo reale.
   - **Vantaggi**:
     - Sincronizzazione in tempo reale tra client e server.
     - Architettura serverless, che riduce i costi di gestione.

![Screenshot 2024-11-10 alle 21 58 45](https://github.com/user-attachments/assets/fa8ed4d1-e606-441d-83ca-c8726d2ba529)





5. **BigQuery**
   - **Tipo**: Data warehouse analitico.
   - **Descrizione**: Data warehouse serverless per l'analisi di grandi volumi di dati. Progettato per eseguire query SQL in tempo reale su grandi dataset.
   - **Ideale per**: Analisi di big data, generazione di report, machine learning e analisi predittiva.
   - **Vantaggi**:
     - Query rapide su dataset enormi e pagamenti in base all’utilizzo.
     - Integrazione con strumenti di machine learning (BigQuery ML) e strumenti di visualizzazione dati.







### Tabella Riepilogativa

| **Servizio**       | **Tipo**                 | **Descrizione**                             | **Ideale per**                          |
|--------------------|--------------------------|---------------------------------------------|-----------------------------------------|
| **Cloud Storage**  | Object storage           | Archiviazione di oggetti non strutturati    | Backup, archiviazione, content delivery |
| **Persistent Disk**| Block storage            | Storage per VM e container                  | VM e applicazioni ad alte prestazioni   |
| **Filestore**      | File storage             | Storage file-based per NFS                  | Applicazioni che richiedono file system |
| **Local SSD**      | Local storage            | SSD locale con bassa latenza                | Database ad alta velocità               |
| **Cloud SQL**      | Relational database (SQL)| Database SQL gestito                        | Applicazioni web e aziendali            |
| **Cloud Spanner**  | Distributed SQL database | Database SQL globale e scalabile            | Applicazioni mission-critical globali   |
| **Bigtable**       | NoSQL (Columnar)         | Database per dati scalabili e analitici     | IoT, dati temporali, analytics          |
| **Firestore**      | NoSQL (Document)         | Database documentale in tempo reale         | App mobile/web, dati sincronizzati      |
| **BigQuery**       | Data warehouse           | Data warehouse per analisi dei big data     | Business intelligence, machine learning |



_________________________________________________________________________________________________________________________________________



# Networking Services 




Google Cloud offre vari servizi di **networking** che permettono di configurare, gestire e ottimizzare la connettività delle risorse cloud in modo sicuro, veloce e scalabile. Questi servizi coprono aspetti come la connettività di rete globale, il bilanciamento del carico, la sicurezza di rete e l'interconnessione con ambienti on-premise.

L'interconnessione con ambienti on-premise da possibilità di collegare in modo sicuro e diretto la rete locale dell'azienda (ovvero le risorse on-premise, che si trovano fisicamente presso la sede dell'organizzazione o in data center privati) con la rete di un provider di cloud pubblico, come Google Cloud.

Questa connessione consente di creare un ambiente ibrido, in cui le risorse locali e quelle cloud possono funzionare insieme come se fossero parte di un'unica rete. L'interconnessione offre vantaggi in termini di flessibilità e scalabilità: le aziende possono mantenere parte delle loro risorse critiche o regolamentate on-premise, utilizzando il cloud per altre attività o per espandere rapidamente la capacità.


### Principali Servizi di Networking su Google Cloud

1. **Virtual Private Cloud (VPC)**
   - **Descrizione**: VPC è una rete privata virtuale che consente di collegare, isolare e gestire risorse cloud su una rete globale scalabile. Ogni VPC è definita dall'utente e può essere configurata per gestire il routing, firewall e subnet specifiche.
   - **Funzionalità principali**:
     - **Subnet IP personalizzabili**: Configurazione di range IP personalizzati per isolare e controllare il traffico.
     - **Peering VPC**: Collega VPC diversi in modo privato senza necessità di IP pubblici.
     - **Firewall e routing**: Firewall personalizzati per autorizzare o limitare il traffico, con opzioni di routing avanzate.
   - **Ideale per**: Isolare le risorse di rete, creare reti ibride e gestire le comunicazioni tra progetti e regioni.

![Screenshot 2024-11-10 alle 22 06 17](https://github.com/user-attachments/assets/8f23e7a0-73c0-4fff-9cdc-769530285edd)

![Screenshot 2024-11-10 alle 22 08 41](https://github.com/user-attachments/assets/bc169f99-5beb-40d2-a4ff-1c76d052d860)




2. **Cloud Load Balancing**
   - **Descrizione**: Un sistema di bilanciamento del carico completamente gestito, progettato per distribuire il traffico in modo efficace su diverse risorse di backend a livello globale. Supporta vari tipi di bilanciamento per differenti casi d'uso, come bilanciamento HTTP(S), TCP, UDP e bilanciamento del carico interno.
   - **Tipi**:
     - **Global HTTP(S) Load Balancer**: Bilanciamento a livello globale per app e servizi web.
     - **TCP/UDP Load Balancer**: Bilanciamento per applicazioni TCP o UDP.
     - **Internal Load Balancer**: Per distribuire traffico tra risorse interne alla rete privata.
   - **Ideale per**: Applicazioni ad alta disponibilità, ridistribuzione del traffico e miglioramento delle prestazioni a livello globale.


![Screenshot 2024-11-10 alle 22 10 10](https://github.com/user-attachments/assets/6448577b-6c61-485c-9c04-b0826c2f1911)




3. **Cloud CDN (Content Delivery Network)**
   - **Descrizione**: CDN completamente gestito che riduce la latenza e migliora le prestazioni per contenuti web statici. Distribuisce i contenuti agli utenti da nodi globali vicini, riducendo i tempi di risposta.
   - **Funzionalità principali**:
     - **Caching**: Riduce la latenza memorizzando in cache i contenuti richiesti di frequente.
     - **Integrazione con Load Balancer**: Funziona con Cloud Load Balancing per fornire contenuti in modo scalabile e ottimizzato.
     - **Gestione del traffico**: Dirige il traffico al nodo più vicino all'utente.
   - **Ideale per**: Distribuire contenuti web statici, migliorare la latenza e ottimizzare l’esperienza utente globale.





4. **Cloud Interconnect**
   - **Descrizione**: Servizio per stabilire una connessione fisica diretta tra la rete on-premise e Google Cloud, riducendo latenza e costi di banda rispetto a connessioni internet standard.
   - **Tipi**:
     - **Dedicated Interconnect**: Connessione diretta con Google tramite porte dedicate (da 10 o 100 Gbps).
     - **Partner Interconnect**: Connessione tramite partner di Google per velocità minori o regioni non supportate.
   - **Ideale per**: Applicazioni con bassi requisiti di latenza e grandi volumi di trasferimento dati, collegamenti sicuri con ambienti on-premise.

5. **Cloud VPN**
   - **Descrizione**: Connessione sicura tra Google Cloud e un ambiente on-premise o altra cloud tramite VPN, crittografando il traffico tra le reti.
   - **Tipi**:
     - **IPsec VPN**: Connessione VPN basata su IPsec per alta sicurezza e crittografia del traffico.
     - **HA VPN**: Fornisce un'alta disponibilità per le connessioni VPN.
   - **Ideale per**: Collegare ambienti on-premise e Google Cloud in modo sicuro, creando una rete ibrida.

![Screenshot 2024-11-10 alle 22 13 05](https://github.com/user-attachments/assets/098a000d-dc73-48dc-91df-ad0ac38eff92)




6. **Cloud DNS**
   - **Descrizione**: Servizio di gestione DNS (Domain Name System) che offre DNS globale, scalabile e ad alta disponibilità, per risolvere i nomi di dominio di risorse in Google Cloud.
   - **Funzionalità principali**:
     - **DNS gestito**: Risoluzione DNS veloce e sicura con configurazione semplice.
     - **DNS pubblico e privato**: Supporta sia la risoluzione pubblica che quella interna alla rete.
   - **Ideale per**: Applicazioni distribuite, configurazione DNS sicura e ad alte prestazioni.

![Screenshot 2024-11-10 alle 22 12 21](https://github.com/user-attachments/assets/25e2b1c2-2653-4253-9c6f-ddcd0b847a07)





7. **Traffic Director**
   - **Descrizione**: Servizio di gestione del traffico per configurare e controllare il traffico tra i servizi su Google Cloud, progettato per scenari di service mesh. Consente un controllo avanzato con funzionalità come il bilanciamento del carico lato client, il failover automatico e il routing basato su criteri.
   - **Funzionalità principali**:
     - **Service mesh**: Ottimizzazione delle comunicazioni tra microservizi.
     - **Failover e bilanciamento avanzato**: Gestione avanzata del traffico per garantire la resilienza dei servizi.
   - **Ideale per**: Applicazioni basate su microservizi, gestione del traffico tra servizi su larga scala.

8. **Network Intelligence Center**
   - **Descrizione**: Una suite di strumenti per monitorare, risolvere problemi e ottimizzare le reti in Google Cloud. Include funzionalità di analisi della topologia, diagnostica del percorso e monitoraggio del traffico.
   - **Funzionalità principali**:
     - **Topology Viewer**: Visualizza la struttura della rete per una gestione più intuitiva.
     - **Performance Dashboard**: Monitoraggio e analisi delle prestazioni.
     - **Network Troubleshooter**: Diagnostica e risolve i problemi di connettività.
   - **Ideale per**: Monitoraggio continuo della rete, ottimizzazione delle prestazioni e gestione delle configurazioni.

### Tabella Riepilogativa

| **Servizio**                   | **Descrizione**                                                          | **Ideale per**                                                |
|--------------------------------|--------------------------------------------------------------------------|---------------------------------------------------------------|
| **VPC**                        | Rete privata virtuale scalabile e configurabile                          | Isolamento delle risorse, reti ibride                         |
| **Cloud Load Balancing**       | Bilanciamento del carico globale per app ad alta disponibilità           | Ridistribuzione del traffico, alta disponibilità              |
| **Cloud CDN**                  | CDN per distribuire contenuti statici in modo veloce                     | Ottimizzazione delle prestazioni e della latenza              |
| **Cloud Interconnect**         | Connessione diretta tra Google Cloud e rete on-premise                   | Collegamento a bassa latenza per ambienti ibridi              |
| **Cloud VPN**                  | VPN sicura per reti ibride                                               | Connessione sicura on-premise/Google Cloud                    |
| **Cloud DNS**                  | Gestione DNS ad alte prestazioni e scalabile                             | Configurazione DNS per applicazioni cloud e distribuite       |
| **Traffic Director**           | Gestione avanzata del traffico per architetture basate su microservizi   | Service mesh e ottimizzazione del traffico                    |
| **Network Intelligence Center**| Monitoraggio e risoluzione di problemi di rete                          | Diagnostica e ottimizzazione della rete cloud                 |




___________________________________________________________________________________________



# RESOURCE HIERARCHY


RISORSE :

Esempi di Risorse in Google Cloud

Alcuni tipi comuni di risorse in Google Cloud includono:
1.Compute Engine (Macchine Virtuali): Rappresentano istanze di macchine virtuali che eseguono applicazioni, simili ai server fisici, ma scalabili e configurabili nel cloud.<br><br>
2.Cloud Storage Bucket: Spazi di archiviazione utilizzati per conservare file, immagini, video e altri dati non strutturati. Sono adatti per archiviare e recuperare file di grandi dimensioni.<br>
3.Cloud SQL e BigQuery: Servizi di database. Cloud SQL è per database relazionali, mentre BigQuery è un data warehouse scalabile e adatto per analisi di big data.<br>
4.App Engine: Piattaforma serverless per distribuire e scalare automaticamente applicazioni web e mobile senza dover gestire l'infrastruttura.<br>
5.Cloud Pub/Sub: Sistema di messaggistica per inviare e ricevere messaggi in tempo reale, utilizzato per costruire sistemi di comunicazione tra componenti distribuiti.<br>
Kubernetes Engine: Un servizio gestito per eseguire e scalare applicazioni containerizzate tramite Kubernetes.<br><br>


![Screenshot 2024-11-10 alle 22 29 00](https://github.com/user-attachments/assets/248447a4-1f0d-4f49-955f-0ef9151cf295)



In Google Cloud, la **Resource Hierarchy** è la struttura gerarchica utilizzata per organizzare, gestire e assegnare autorizzazioni alle risorse nel cloud. Questa gerarchia è pensata per facilitare la gestione di progetti e risorse in modo scalabile, sicuro e facilmente configurabile, specialmente per aziende con più team o ambienti di sviluppo. La struttura consente di gestire autorizzazioni e configurazioni su vari livelli, che vengono poi applicate automaticamente ai livelli inferiori.
### Livelli della Resource Hierarchy di Google Cloud

![Screenshot 2024-11-10 alle 22 33 55](https://github.com/user-attachments/assets/71456a16-baba-4548-a1a5-b796864e1226)

![Screenshot 2024-11-10 alle 22 35 11](https://github.com/user-attachments/assets/b8169484-9574-4197-ab52-32832a743e75)


![Screenshot 2024-11-10 alle 22 39 29](https://github.com/user-attachments/assets/a6476295-1eda-4ae7-900b-ccfacb20b79f)



La gerarchia delle risorse di Google Cloud è composta da quattro livelli principali, disposti dall’alto verso il basso:

1. **Organizzazione**
   - **Descrizione**: Rappresenta l'entità di livello più alto nella gerarchia. Di solito corrisponde a una singola azienda o organizzazione e permette di centralizzare la gestione delle risorse aziendali.
   - **Gestione**: L'account super amministratore dell'organizzazione può impostare policy e controllare le risorse a livello globale.
   - **Funzionalità principali**:
     - Controllo centralizzato su tutte le risorse dell’organizzazione.
     - Applicazione di policy di sicurezza e conformità a tutte le risorse sottostanti.
   - **Esempio d'uso**: Un'azienda che vuole avere una governance unificata su tutte le sue risorse Google Cloud.

2. **Folder (Cartella)**
   - **Descrizione**: Le cartelle aiutano a organizzare i progetti in modo logico all'interno dell'organizzazione. Possono essere utilizzate per rappresentare dipartimenti aziendali, team o ambienti (ad esempio, produzione, sviluppo).
   - **Gestione**: Ogni cartella può avere policy di sicurezza e autorizzazioni specifiche che vengono applicate automaticamente alle risorse al suo interno.
   - **Funzionalità principali**:
     - Struttura logica per organizzare e gestire progetti multipli.
     - Eredità delle policy: le policy impostate su una cartella vengono ereditate da tutte le risorse figlie.
   - **Esempio d'uso**: Una cartella "Produzione" con autorizzazioni limitate per il team operativo e una cartella "Sviluppo" con più accesso per i team di sviluppo e testing.

3. **Progetto (Project)**
   - **Descrizione**: È il livello base per la gestione e l’organizzazione delle risorse in Google Cloud. Ogni risorsa (macchine virtuali, database, bucket di storage, ecc.) deve appartenere a un progetto. È su questo livello che vengono impostati i budget, la fatturazione e le configurazioni di rete.
   - **Gestione**: Ogni progetto ha un proprio ID univoco e può essere associato a un budget di fatturazione, oltre che a specifiche impostazioni di sicurezza.
   - **Funzionalità principali**:
     - Controllo dettagliato delle risorse e dei permessi di accesso.
     - Configurazione separata per rete, fatturazione e monitoraggio per progetto.
   - **Esempio d'uso**: Un progetto chiamato "App Mobile" per contenere tutte le risorse necessarie a un’applicazione mobile aziendale.

4. **Risorse (Resources)**
   - **Descrizione**: Sono le entità più specifiche e rappresentano i servizi di Google Cloud, come le istanze di macchine virtuali (Compute Engine), i bucket di Cloud Storage, i database, le funzioni serverless, ecc.
   - **Gestione**: Ogni risorsa eredità le policy impostate a livello di progetto, cartella o organizzazione.
   - **Esempio di Risorse**:
     - Istanza di **Compute Engine**: una macchina virtuale per l’esecuzione di applicazioni.
     - **Cloud Storage Bucket**: spazio di archiviazione per i dati.
     - **Cloud SQL Instance**: database relazionale gestito.

### Eredità delle Policy di Sicurezza e Accesso

Le autorizzazioni e le policy impostate a livello di organizzazione vengono automaticamente applicate a tutti i livelli inferiori, dalle cartelle fino alle singole risorse. Questo sistema permette di gestire le policy in modo centralizzato:

- **Policy a Livello di Organizzazione**: Applicate a tutte le risorse aziendali.
- **Policy a Livello di Cartella**: Possono essere personalizzate per settori o team, sovrascrivendo le impostazioni di livello organizzativo quando necessario.
- **Policy a Livello di Progetto**: Permettono il controllo specifico sulle risorse di uno specifico progetto.
- **Policy a Livello di Risorsa**: Per regolare permessi dettagliati sulle singole risorse, come accesso specifico a una singola macchina virtuale.

### Esempio di Resource Hierarchy

un'azienda con diversi team e progetti, come segue:

- **Organizzazione**: "XYZ Corp"
  - **Cartella "Produzione"**
    - **Progetto "App E-commerce"**
      - Compute Engine per il server backend
      - Cloud Storage per i dati dei clienti
    - **Progetto "ERP"**
      - Cloud SQL per database aziendale
  - **Cartella "Sviluppo"**
    - **Progetto "Sito Web"**
      - Compute Engine per ambiente di test
    - **Progetto "Analytics"**
      - BigQuery per analisi dei dati di produzione

Ogni livello della Resource Hierarchy consente di impostare policy e autorizzazioni appropriate, mantenendo le risorse organizzate e sicure.




_________________________________________________________________________________________



# Create a Free Tier Account

 

![Screenshot 2024-11-10 alle 22 44 32](https://github.com/user-attachments/assets/01f20925-1ceb-4591-8756-00f381ca2daa)


![Screenshot 2024-11-10 alle 22 45 25](https://github.com/user-attachments/assets/fd699993-2a4b-4a06-a868-d6f0bfee828b)



Accesso a tutti i prodotti Google Cloud

Ottieni tutto il necessario per creare e gestire applicazioni, siti web e servizi, tra cui Firebase e l'API di Google Maps.
300 $ di credito gratis

Google Cloud al tuo servizio con 300 $ di credito da spendere nei prossimi 90 giorni.
Nessun addebito automatico alla fine della prova gratuita

Ti chiediamo i dati della carta di credito per essere certi che tu non sia un robot. Se utilizzi una carta di credito o di debito, non ti verrà addebitato alcun costo, a meno che non attivi manualmente l'account completo



https://cloud.google.com/free?hl=it


____________________________



# GCP CONSOLE OVERVIEW


![Screenshot 2024-11-11 alle 13 55 28](https://github.com/user-attachments/assets/2ba751ca-95c7-44ab-bed9-6addfe9aa48d)



___________________________

°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°

# CLOUD APIS

Le **Cloud APIs** di Google Cloud sono interfacce di programmazione (API) che consentono agli sviluppatori di interagire con i vari servizi e risorse disponibili su Google Cloud. Queste API permettono di automatizzare, gestire e integrare i servizi cloud nelle applicazioni, offrendo un modo semplice per accedere e controllare le funzionalità di Google Cloud tramite codice.

Le Cloud APIs di Google sono  strumenti fondamentali per sfruttare al meglio l’infrastruttura e i servizi cloud in modo programmabile e automatizzato.


### Principali Tipi di Cloud APIs in Google Cloud

1. **Compute APIs**: Consentono di creare e gestire risorse di calcolo come macchine virtuali, cluster Kubernetes, app serverless e molto altro.
   - **Esempio**: Compute Engine API, Kubernetes Engine API, App Engine Admin API.

2. **Storage APIs**: Forniscono accesso ai servizi di archiviazione per memorizzare e gestire dati strutturati e non strutturati.
   - **Esempio**: Cloud Storage API, Cloud Bigtable API, Cloud SQL Admin API, Firestore API.

3. **Database e Big Data APIs**: Consentono di eseguire operazioni avanzate sui database e analizzare grandi quantità di dati.
   - **Esempio**: BigQuery API, Cloud Spanner API, Dataflow API.

4. **Machine Learning APIs**: Offrono modelli di intelligenza artificiale preaddestrati o strumenti per creare modelli di machine learning personalizzati.
   - **Esempio**: Vision API, Natural Language API, Translation API, AutoML API.

5. **Networking APIs**: Consentono di gestire e configurare le reti, bilanciare il carico, impostare firewall e VPN.
   - **Esempio**: VPC Access API, Cloud DNS API, Cloud Load Balancing API.

6. **Operations APIs**: Forniscono strumenti per monitorare, analizzare e gestire le risorse e le applicazioni su Google Cloud.
   - **Esempio**: Cloud Monitoring API, Cloud Logging API, Error Reporting API.

7. **Security APIs**: Permettono di gestire la sicurezza delle risorse, autenticare gli utenti e configurare le policy di accesso.
   - **Esempio**: Identity and Access Management (IAM) API, Cloud KMS (Key Management Service) API, Security Command Center API.

### Come Usare le Cloud APIs

Devo prima abilitarle


Le Cloud APIs possono essere utilizzate tramite:

- **REST API**: Gli endpoint delle API sono accessibili tramite richieste HTTP. È possibile fare chiamate REST con vari metodi come `GET`, `POST`, `PUT`, e `DELETE`.
- **Client Libraries**: Google offre librerie client ufficiali in vari linguaggi (Python, Java, Node.js, Go, ecc.) per semplificare l’integrazione delle API nelle applicazioni.
- **Google Cloud SDK**: Uno strumento da riga di comando per interagire direttamente con le Cloud APIs, utile per gli sviluppatori che preferiscono l'accesso tramite CLI.

Per vedere le API ABILITATE VADO (menù)  APIs & Services.




### Autenticazione

Per utilizzare le Cloud APIs, è necessaria l’autenticazione tramite **Google Cloud IAM** (Identity and Access Management). Gli sviluppatori possono autenticarsi tramite credenziali di servizio o account utente. L’autenticazione garantisce che solo gli utenti e le applicazioni autorizzati possano accedere alle risorse Google Cloud.

### Esempio Pratico di Utilizzo

Immagina di voler **creare un’istanza di Compute Engine** per eseguire un’applicazione. Puoi farlo in questo modo:

1. **Abilita Compute Engine API** nel progetto Google Cloud.
2. **Configura le credenziali di autenticazione** per l’API.
3. **Scrivi uno script** (in Python, ad esempio) per fare una chiamata API e creare un’istanza con le specifiche desiderate (ad esempio, numero di CPU, memoria, e posizione geografica).

### Vantaggi delle Cloud APIs

- **Automazione**: Permettono di automatizzare operazioni ripetitive, come la gestione delle risorse o la scalabilità delle applicazioni.
- **Scalabilità**: Rendono possibile adattare le risorse cloud in modo dinamico, rispondendo alle esigenze dell’applicazione.
- **Flessibilità**: Consentono di personalizzare il comportamento dei servizi Google Cloud secondo le necessità del progetto.
- **Sicurezza**: Offrono controllo granulare sui permessi grazie all’integrazione con IAM.


________________________________________________________________________________________________________________________


# Cloud SDK AND CLI 

Il **Cloud SDK** e la **Google Cloud CLI** sono strumenti essenziali per interagire con Google Cloud tramite la riga di comando. Il Cloud SDK include una serie di strumenti, comandi e librerie che permettono di configurare e gestire risorse, automatizzare attività e integrare Google Cloud nelle proprie applicazioni.

### Google Cloud SDK

Il **Google Cloud SDK** (Software Development Kit) è un insieme di strumenti che fornisce agli sviluppatori tutti gli strumenti necessari per gestire i servizi di Google Cloud da locale. Include la **Google Cloud CLI** (strumento da riga di comando), librerie client, e altri strumenti per l’interazione con il cloud.

- **Installazione**: Il Cloud SDK può essere installato su sistemi operativi diversi (Windows, macOS, e Linux) e richiede Python per essere eseguito.
- **Google Cloud CLI**: La CLI (comando `gcloud`) è parte integrante del Cloud SDK e consente di eseguire tutte le operazioni disponibili nelle Cloud APIs direttamente dalla riga di comando.

### Componenti Principali del Cloud SDK

1. **gcloud**: Lo strumento da riga di comando principale per Google Cloud. Permette di gestire risorse e servizi, come Compute Engine, Cloud Storage, IAM, e molto altro. Supporta vari comandi e flag per configurare, creare, aggiornare e cancellare risorse.

2. **gsutil**: Uno strumento specifico per interagire con Cloud Storage. È usato per caricare e scaricare file, gestire i bucket e configurare permessi sui dati archiviati.

3. **bq**: Lo strumento a riga di comando per BigQuery, utilizzato per eseguire query SQL, gestire dataset e configurare opzioni di elaborazione dei dati.

4. **kubectl**: Per gestire i cluster Kubernetes. Questo strumento, incluso come parte del Cloud SDK, è utile per chi utilizza Google Kubernetes Engine (GKE) per orchestrare i container.

### Funzionalità e Utilizzo della Google Cloud CLI

La **Google Cloud CLI** consente di interagire con Google Cloud in modo programmatico e da locale. È utile sia per chi gestisce risorse occasionalmente che per sviluppatori che vogliono automatizzare flussi di lavoro. Di seguito sono riportati alcuni esempi di utilizzo della CLI:

1. **Autenticazione**:
   - `gcloud auth login`: Autentica l'utente per accedere alle risorse Google Cloud.
   - `gcloud auth application-default login`: Configura le credenziali predefinite per le applicazioni.

2. **Configurazione del Progetto**:
   - `gcloud config set project [PROJECT_ID]`: Imposta il progetto attivo in Google Cloud.
   - `gcloud config list`: Visualizza la configurazione corrente della CLI.

3. **Gestione delle Risorse**:
   - Creazione di una VM Compute Engine:
     ```bash
     gcloud compute instances create example-instance --zone=us-central1-a
     ```
   - Caricamento di un file su Cloud Storage:
     ```bash
     gsutil cp my-file.txt gs://my-bucket
     ```

4. **IAM e Sicurezza**:
   - Gestione dei ruoli di accesso per utenti e account di servizio:
     ```bash
     gcloud projects add-iam-policy-binding [PROJECT_ID] --member=user:[USER_EMAIL] --role=roles/viewer
     ```

5. **Automazione con Script**:
   - È possibile scrivere script per automatizzare la creazione, configurazione e monitoraggio delle risorse Google Cloud. I comandi `gcloud`, `gsutil`, e `bq` possono essere concatenati in script shell per gestire flussi di lavoro complessi.

### Vantaggi del Cloud SDK e della Google Cloud CLI

- **Accesso Diretto**: Permette di accedere alle funzionalità cloud da locale, senza dover entrare nella console web.
- **Automazione**: Consente di automatizzare task ripetitivi e flussi di lavoro tramite script.
- **Supporto a Più Ambienti**: Può essere usato in ambienti di sviluppo, test e produzione con facilità, grazie al controllo delle configurazioni.
- **Debug e Monitoraggio**: Utile per monitorare risorse e risolvere problemi tramite log e output della CLI.
- **Integrazione con CI/CD**: Spesso integrato nelle pipeline CI/CD per automatizzare il deploy delle applicazioni e il provisioning delle risorse.

### Esempio di Flusso di Lavoro con la Google Cloud CLI

1. Autentica il tuo account Google Cloud:
   ```bash
   gcloud auth login
   ```

2. Configura il progetto e la zona:
   ```bash
   gcloud config set project my-project
   gcloud config set compute/zone us-central1-a
   ```

3. Crea un’istanza di Compute Engine:
   ```bash
   gcloud compute instances create my-instance --machine-type=e2-medium --image-family=debian-10 --image-project=debian-cloud
   ```

4. Carica dati su Cloud Storage:
   ```bash
   gsutil cp local-file.txt gs://my-bucket
   ```

5. Esegui una query BigQuery:
   ```bash
   bq query --use_legacy_sql=false 'SELECT * FROM my-dataset.my-table LIMIT 10'
   ```


<img width="1334" alt="Screenshot 2024-11-14 alle 13 51 39" src="https://github.com/user-attachments/assets/87c6f4bf-6ee6-4027-846e-cefa6a9deb92">


## Come installare :

https://cloud.google.com/sdk/docs/quickstarts

<img width="1037" alt="Screenshot 2024-11-14 alle 14 36 58" src="https://github.com/user-attachments/assets/4743f223-123e-4d6c-8b53-d201f3f6ef69">


Per verificare il corretto funzionamento

```
gcloud --help
```
```
gcloud config list 
```


```
 gcloud init 
```

Il comando gcloud init è utilizzato per configurare l'ambiente della Google Cloud CLI (gcloud) e associarlo a un progetto Google Cloud. 
Questo comando serve per la configurazione delle seguenti opzioni:

Autenticazione dell'utente: si effettua il login utilizzando il tuo account Google.
Progetto predefinito: Selezioniamo il progetto Google Cloud con cui lavorare.
Regione e zona predefinita: Configuriamo l'area geografica e la zona per le risorse.



```
gcloud init --console-only
```



comando `gcloud auth list` mostra un elenco degli account Google autenticati nell'ambiente della CLI di Google Cloud. 
Si può usare per verificare quale account è attualmente attivo e disponibile.

### Utilizzo del comando:
```bash
gcloud auth list
```

### Output tipico:
Esempio di risultato:

```
Credentialed Accounts:
 - user1@gmail.com               ACTIVE
   user2@example.com
```

- **ACTIVE** indica l'account attualmente attivo nella sessione di `gcloud`.
- Gli altri account elencati sono quelli che hai precedentemente autenticato, ma non sono attualmente attivi.

### Cambiare l'account attivo:
Per impostare un altro account come attivo, usa:
```bash
gcloud config set account <EMAIL_ACCOUNT>
```

Ad esempio:
```bash
gcloud config set account user2@example.com
```

### Rimuovere un account:
Se desideri rimuovere un account dall'elenco, puoi usare:
```bash
gcloud auth revoke <EMAIL_ACCOUNT>
```

### Comando gcloud components list


Il comando `gcloud components list` ti permette di vedere un elenco dei componenti disponibili, installati o aggiornabili per la Google Cloud CLI. 
I componenti includono strumenti opzionali come SDK specifici per alcuni servizi, emulatori o librerie aggiuntive.

### Utilizzo del comando:
```bash
gcloud components list

```



### Tipi di componenti visualizzati:
L'output mostra tre sezioni principali:
- **Installed**: Componenti già installati sul tuo sistema.
- **Not Installed**: Componenti disponibili ma non ancora installati.
- **Updates Available**: Componenti installati per cui esistono aggiornamenti.

### Output tipico:


<img width="969" alt="Screenshot 2024-11-16 alle 13 49 45" src="https://github.com/user-attachments/assets/0e02dadf-28e8-4a30-9578-e840a101a59c">


Esempio:
```
Your current Cloud SDK version is: 123.0.0
The latest available version is: 124.0.0

Installed components:
 - core                  202.0.0
 - gcloud-deploy         0.2.1

Available components:
 - app-engine-python     1.9.91
 - kubectl               1.19.6

Upgradable components:
 - beta                  202.0.0    -> 202.1.0
```

### Operazioni sui componenti:
- **Aggiornare i componenti installati:**
  ```bash
  gcloud components update
  ```

- **Installare un nuovo componente:**
  ```bash
  gcloud components install <nome_componente>
  ```
  Ad esempio:
  ```bash
  gcloud components install kubectl
  ```

- **Rimuovere un componente installato:**
  ```bash
  gcloud components remove <nome_componente>
  ```



°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°


Il comando `gcloud beta interactive` apre un'interfaccia interattiva per la Google Cloud CLI. Questo strumento, attualmente nella fase **beta**, consente di esplorare i comandi di `gcloud` in un ambiente con **autocompletamento avanzato** e **suggerimenti in tempo reale**.



### Utilizzo del comando:
```bash
gcloud beta interactive
```


<img width="961" alt="Screenshot 2024-11-16 alle 13 54 46" src="https://github.com/user-attachments/assets/07b4ae03-06a4-464f-91a4-832f1d9f8341">





### Funzionalità principali:
1. **Autocompletamento**: Mentre digiti un comando, ti vengono suggerite opzioni valide, inclusi flag e valori.
2. **Suggerimenti inline**: Mostra descrizioni utili e informazioni sui comandi e sui flag selezionati.
3. **Storia dei comandi**: Ti consente di scorrere rapidamente tra i comandi già utilizzati.
4. **Highlighting della sintassi**: I comandi vengono evidenziati per facilitarne la lettura.

### Esempio:
Supponiamo tu stia esplorando i progetti GCP:
1. Digita:
   ```bash
   gcloud projects
   ```
2. Verranno suggeriti i comandi correlati, come `list` o `create`.

3. Se selezioni `list`:
   ```bash
   gcloud projects list
   ```
   L'interfaccia fornirà opzioni come `--filter`, `--format`, ecc., con descrizioni.

### Uscire dalla modalità interattiva:
Premi `Ctrl + D` oppure digita `exit`.

### Configurazione consigliata:
Se vuoi rendere l'interfaccia interattiva più efficace:
- **Abilita il completamento della shell**:
  ```bash
  gcloud beta interactive --setup
  ```
con questo comando installo anche il supporto interattivo nella  shell predefinita.











________________________________________________











































