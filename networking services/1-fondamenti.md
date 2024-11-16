# Fondamenti di Networking



**Internet protocol**

<img width="922" alt="Screenshot 2024-11-16 alle 17 45 52" src="https://github.com/user-attachments/assets/5b82115d-a3e6-4bb2-9636-f81b0f58d22c">


L'**Internet Protocol (IP)** è un protocollo di comunicazione fondamentale che consente lo scambio di dati tra dispositivi collegati in rete, come computer, server e smartphone. Fa parte del modello di rete TCP/IP, utilizzato per Internet e altre reti.

### Caratteristiche principali dell'IP:
1. **Indirizzamento**: Ogni dispositivo in rete ha un indirizzo IP univoco, che funge da identificatore. Esistono due versioni principali:
   - **IPv4**: Utilizza indirizzi a 32 bit (esempio: `192.168.1.1`), con un limite di circa 4,3 miliardi di indirizzi unici.
   - **IPv6**: Utilizza indirizzi a 128 bit (esempio: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`), progettato per risolvere la carenza di indirizzi IP e offrire migliori funzionalità di sicurezza e gestione.

2. **Connessione senza stato**: L'IP non mantiene uno stato tra due dispositivi; ogni pacchetto viene trattato indipendentemente.

3. **Suddivisione dei dati in pacchetti**: L'IP frammenta i dati in pacchetti, ciascuno con intestazione e payload. L'intestazione contiene informazioni come:
   - Indirizzo IP del mittente
   - Indirizzo IP del destinatario
   - Informazioni per l'instradamento

4. **Instradamento**: I pacchetti vengono inoltrati da un router all'altro fino a raggiungere la destinazione.

### Funzionamento:
- **Livello di rete**: L'IP opera al livello di rete del modello OSI o al livello Internet nel modello TCP/IP.
- **Non affidabilità intrinseca**: L'IP non garantisce la consegna, l'ordine o l'integrità dei pacchetti. Questi aspetti sono gestiti da protocolli di livello superiore, come **TCP** (Transmission Control Protocol).

### Utilizzo:
- **Reti locali (LAN)**: Dispositivi nella stessa rete condividono indirizzi IP privati.
- **Reti globali (WAN/Internet)**: I dispositivi usano indirizzi IP pubblici per comunicare oltre la rete locale.
