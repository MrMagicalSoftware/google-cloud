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




**Modello iso/osi**


<img width="723" alt="Screenshot 2024-11-16 alle 17 49 01" src="https://github.com/user-attachments/assets/03dbdb3f-74b9-4796-8684-1cf12d2a8db0">


<img width="972" alt="Screenshot 2024-11-16 alle 17 52 36" src="https://github.com/user-attachments/assets/6151a3b9-1d92-423e-9f66-edb242a44839">


Le **classi di indirizzi IP** sono una categorizzazione utilizzata principalmente nell'indirizzamento IPv4 per suddividere lo spazio degli indirizzi in base alla grandezza della rete e al numero di host che possono essere supportati. Questa suddivisione era utile prima dell'introduzione del **CIDR (Classless Inter-Domain Routing)**, che ha reso più flessibile l'assegnazione degli indirizzi.

### Classi di IP
Gli indirizzi IPv4 sono rappresentati da 32 bit (quattro ottetti), 
e la classe di un indirizzo si basa sui primi bit più significativi (MSB, Most Significant Bits).

#### **Classe A**
- **Range**: da `0.0.0.0` a `127.255.255.255`
- **Primi bit**: 0 (il primo ottetto varia da 0 a 127)
- **Numero massimo di reti**: 128 (2⁷, considerando 0 e 127 riservati)
- **Numero massimo di host per rete**: 16.777.214 (2²⁴ - 2, esclusi indirizzo di rete e broadcast)
- **Destinazione**: Grandi reti, ad esempio grandi aziende o organizzazioni globali.
- **Esempio**: `10.0.0.1`

#### **Classe B**
- **Range**: da `128.0.0.0` a `191.255.255.255`
- **Primi bit**: 10 (il primo ottetto varia da 128 a 191)
- **Numero massimo di reti**: 16.384 (2¹⁴)
- **Numero massimo di host per rete**: 65.534 (2¹⁶ - 2)
- **Destinazione**: Medie reti, ad esempio università o aziende di media grandezza.
- **Esempio**: `172.16.0.1`

#### **Classe C**
- **Range**: da `192.0.0.0` a `223.255.255.255`
- **Primi bit**: 110 (il primo ottetto varia da 192 a 223)
- **Numero massimo di reti**: 2.097.152 (2²¹)
- **Numero massimo di host per rete**: 254 (2⁸ - 2)
- **Destinazione**: Piccole reti, ad esempio uffici o reti domestiche.
- **Esempio**: `192.168.1.1`

#### **Classe D** (Multicast)
- **Range**: da `224.0.0.0` a `239.255.255.255`
- **Primi bit**: 1110
- **Destinazione**: Utilizzata per inviare pacchetti a gruppi di dispositivi (multicast). Non supporta host o subnetting.
- **Esempio**: `224.0.0.1` (usato per i protocolli di routing come OSPF).

#### **Classe E** (Riservata)
- **Range**: da `240.0.0.0` a `255.255.255.255`
- **Primi bit**: 1111
- **Destinazione**: Riservata per scopi sperimentali e non utilizzata nella rete pubblica.
- **Esempio**: Nessun esempio di uso pratico comune.

---

### Indirizzi riservati
- **Privati**:
  - Classe A: `10.0.0.0` - `10.255.255.255`
  - Classe B: `172.16.0.0` - `172.31.255.255`
  - Classe C: `192.168.0.0` - `192.168.255.255`
  
- **Loopback**: `127.0.0.0` - `127.255.255.255` (usato per comunicare con se stessi, ad esempio `127.0.0.1`).

---
Con l'introduzione del CIDR, le classi tradizionali sono state superate, consentendo una maggiore flessibilità con il formato **notazione CIDR** (es. `192.168.1.0/24`), dove il suffisso indica il numero di bit utilizzati per la parte di rete.


°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°

Private IP Addresss

<img width="1086" alt="Screenshot 2024-11-17 alle 11 15 12" src="https://github.com/user-attachments/assets/da49215a-3b64-483f-8785-aaf586b4c188">






Più è grande il prefix , più piccola è l'ampiezza della rete

192.168.0.0/16 
°°°°°°°°°°°
Network Address Prefix (16)


Questa rete ha un'ampiezza di 192.168.0.0 - 192.168.255.255


<img width="999" alt="Screenshot 2024-11-17 alle 11 30 02" src="https://github.com/user-attachments/assets/c7561d60-9d00-4120-9135-436eb0053485">

<img width="992" alt="Screenshot 2024-11-17 alle 11 31 30" src="https://github.com/user-attachments/assets/a520ee61-1561-45e5-a365-dadc67e82a8d">










