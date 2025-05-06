**Autore: Prof. Gabriel Rovesti**
## 1. SISTEMI DI ELABORAZIONE

### 1.1 Definizione di Sistema

Un sistema è un insieme di elementi interconnessi che interagiscono tra loro per raggiungere uno scopo comune. Nei sistemi informatici, questi elementi includono componenti hardware e software che lavorano insieme per elaborare informazioni.

### 1.2 Classificazione dei Sistemi

I sistemi informatici possono essere classificati in base a diversi criteri:

- **Per architettura**: CPU/BUS/cache
- **Per dimensione**: microcomputer, minicomputer, mainframe, supercomputer
- **Per scopo**: general-purpose, special-purpose
- **Per tipologia**: embedded, real-time, distribuiti, centralizzati

### 1.3 Il Computer

Il computer è un sistema elettronico programmabile in grado di eseguire elaborazioni automatiche su dati. È costituito da:

- Unità di elaborazione (CPU)
- Unità di memoria (RAM, ROM, cache)
- Unità di input/output
- Bus di interconnessione

### 1.4 Hardware, Software e Firmware

- **Hardware**: componenti fisiche del sistema (circuiti elettronici, dispositivi meccanici)
- **Software**: insieme dei programmi che permettono al sistema di funzionare (sistema operativo, applicazioni)
- **Firmware**: software integrato nell'hardware che ne controlla le funzionalità di base (BIOS, UEFI)

### 1.5 Memorie e Gerarchie

La gerarchia delle memorie è organizzata in livelli con diverse caratteristiche di velocità, capacità e costo:

1. **Registri**: all'interno della CPU, velocissimi ma di capacità minima
2. **Cache**: memoria ad alta velocità che fa da intermediario tra CPU e RAM
3. **Memoria principale (RAM)**: memoria volatile ad accesso rapido
4. **Memoria secondaria**: dischi, SSD, ecc., non volatile ma più lenta
5. **Memoria terziaria**: backup, archivi, ecc., accesso molto lento

### 1.6 Periferiche di I/O

Dispositivi che permettono la comunicazione tra il computer e l'esterno:

- **Input**: tastiera, mouse, scanner, microfono, webcam
- **Output**: monitor, stampante, altoparlanti
- **I/O**: touchscreen, dispositivi di rete, dispositivi di memorizzazione esterni

## 2. CPU E ARCHITETTURA

### 2.1 La Macchina di Von Neumann

Architettura fondamentale dei computer moderni, caratterizzata da:

- Unità di elaborazione (CPU)
- Memoria principale
- Unità di controllo
- Dispositivi di I/O
- Bus di sistema unico per dati e istruzioni

### 2.2 Confronto Von Neumann e Harvard

|Von Neumann|Harvard|
|---|---|
|Memoria unica per dati e programmi|Memorie separate per dati e programmi|
|Un solo bus|Bus separati per dati e istruzioni|
|Flessibile ma potenziale bottleneck|Migliori prestazioni ma meno flessibile|
|Usata nella maggior parte dei computer general-purpose|Usata in sistemi embedded e DSP|

### 2.3 La CPU e la Sua Architettura Interna

La CPU (Central Processing Unit) è il cervello del computer e contiene:

- Unità di controllo (CU)
- Unità aritmetico-logica (ALU)
- Registri
- Cache interna (L1, L2)
- Interfacce per il collegamento con il resto del sistema

### 2.4 I Registri

Piccole memorie ad altissima velocità interne alla CPU:

- **Registri di uso speciale**:
    - PC (Program Counter): indirizzo della prossima istruzione
    - SR (Status Register): contiene i flag di stato (zero, overflow, carry, ecc.)
    - SP (Stack Pointer): punta al top dello stack
    - IR (Instruction Register): contiene l'istruzione corrente
    - MAR (Memory Address Register): indirizzo di memoria da accedere
    - MDR (Memory Data Register): dati da/per la memoria
- **Registri di uso generale**:
    - Accumulatore: usato per operazioni aritmetiche
    - Registri generici: R0, R1, ..., Rn

### 2.5 L'Unità di Controllo (CU)

Coordina il funzionamento della CPU:

- Preleva le istruzioni dalla memoria
- Le decodifica
- Genera i segnali di controllo per gli altri componenti
- Può essere implementata tramite circuiti logici (hardwired) o microprogrammazione

### 2.6 L'Unità Aritmetico-Logica (ALU)

Esegue operazioni matematiche e logiche:

- Operazioni aritmetiche: addizione, sottrazione, moltiplicazione, divisione
- Operazioni logiche: AND, OR, NOT, XOR
- Operazioni di confronto
- Operazioni di shift e rotazione

### 2.7 Bus di Sistema

Canali di comunicazione tra i vari componenti del sistema:

- **Bus dati**: trasporta i dati tra i componenti (ampiezza in bit: 8, 16, 32, 64...)
- **Bus indirizzi**: trasporta gli indirizzi di memoria
- **Bus di controllo**: trasporta i segnali di controllo (lettura, scrittura, ecc.)

### 2.8 Banda Passante (Bandwidth) del FSB

Il Front Side Bus collega la CPU alla memoria e al chipset:

- Misurata in bit per secondo (bps) o multipli (Mbps, Gbps)
- Influenza significativamente le prestazioni del sistema
- Dipende da frequenza del bus e ampiezza (numero di linee parallele)

### 2.9 Il Clock

Segnale che sincronizza le operazioni della CPU:

- Frequenza misurata in Hertz (Hz, MHz, GHz)
- Determina la velocità di esecuzione delle istruzioni
- Legato al consumo energetico e alla generazione di calore

### 2.10 Il Ciclo Macchina

Sequenza di operazioni elementari che la CPU esegue per ogni istruzione:

1. **Fetch**: preleva l'istruzione dalla memoria
2. **Decode**: decodifica l'istruzione
3. **Execute**: esegue l'istruzione
4. **Eventuale aggiornamento dei registri e memoria**

### 2.11 Prestazioni di un Microprocessore

Metriche per misurare le prestazioni:

- **MIPS** (Millions of Instructions Per Second): numero di istruzioni eseguite al secondo
- **FLOPS** (Floating Point Operations Per Second): operazioni in virgola mobile al secondo
- **Benchmark**: test standardizzati che misurano le prestazioni in scenari reali (SPEC, Cinebench, Geekbench)

## 3. MEMORIE E COMPONENTI

### 3.1 Case, Alimentatore, Scheda Madre

- **Case**: struttura che contiene e protegge i componenti
- **Alimentatore**: fornisce energia elettrica ai componenti
- **Scheda Madre** (Motherboard): circuito principale su cui sono montati o collegati gli altri componenti
- **CPU Socket**: connettore specifico per tipo di CPU

### 3.2 Il Chipset

Insieme di circuiti integrati che controllano il flusso di dati tra processore, memoria e periferiche:

- **Northbridge** (Memory Controller Hub):
    - Gestisce comunicazioni ad alta velocità
    - Controlla accesso a RAM
    - Si interfaccia con GPU (attraverso PCIe o AGP)
    - Nei sistemi moderni è spesso integrato nella CPU
- **Southbridge** (I/O Controller Hub):
    - Gestisce periferiche più lente
    - Controlla SATA, USB, audio, rete
    - Si interfaccia con dispositivi di I/O

### 3.3 Memorie Primarie, Secondarie e Periferiche

- **Memorie primarie**:
    - RAM (Random Access Memory): volatile, ad accesso rapido
    - ROM (Read-Only Memory): non volatile, sola lettura
    - Cache: memoria veloce tra CPU e RAM
- **Memorie secondarie**:
    - HDD (Hard Disk Drive): magnetico, non volatile
    - SSD (Solid State Drive): elettronico, non volatile, più veloce degli HDD
    - Unità ottiche (CD, DVD, Blu-ray)
- **Memorie periferiche**:
    - USB flash drive
    - Schede di memoria (SD, microSD)
    - Unità di backup esterne

### 3.4 Memorie Ottiche

Tecnologie per la memorizzazione ottica dei dati:

- **CD** (Compact Disc): capacità ~700 MB
- **DVD** (Digital Versatile Disc): capacità 4.7-17 GB
- **Blu-ray**: capacità 25-128 GB
- Differiscono per lunghezza d'onda del laser e densità di memorizzazione

### 3.5 Pipeline

Tecnica di elaborazione che consente di sovrapporre fasi diverse dell'esecuzione di istruzioni consecutive:

- Aumenta il throughput (istruzioni completate per unità di tempo)
- Non riduce la latenza della singola istruzione
- Fasi tipiche: fetch, decode, execute, memory access, write-back
- Problemi: hazard strutturali, dipendenze dai dati, branch prediction

## 4. ARCHITETTURE AVANZATE

### 4.1 Architettura a Virgola Mobile

Sistema specializzato per calcoli con numeri in virgola mobile:

- Unità FPU (Floating Point Unit): integrata nella CPU moderna
- Standard IEEE 754 per rappresentazione numeri
- Formati: precisione singola (32 bit), doppia (64 bit), quadrupla (128 bit)
- Operazioni specializzate per calcoli scientifici e grafica

### 4.2 Architetture CISC e RISC

Due filosofie di progettazione dei set di istruzioni:

|CISC (Complex Instruction Set Computer)|RISC (Reduced Instruction Set Computer)|
|---|---|
|Molte istruzioni complesse|Set di istruzioni ridotto e semplice|
|Istruzioni di lunghezza variabile|Istruzioni di lunghezza fissa|
|Modalità di indirizzamento multiple|Pochi modi di indirizzamento|
|Codice più compatto|Codice più esteso|
|Più complesso da implementare|Più semplice da implementare|
|Es: x86, x86-64|Es: ARM, MIPS, RISC-V|

### 4.3 Assembly e Tipi di Instruction Set

- **Assembly**: linguaggio di programmazione a basso livello specifico per una CPU
- **Instruction Set Architecture (ISA)**: insieme delle istruzioni che la CPU può eseguire
- **Tipi di istruzioni**:
    - Trasferimento dati (MOV, LOAD, STORE)
    - Aritmetiche (ADD, SUB, MUL, DIV)
    - Logiche (AND, OR, NOT, XOR)
    - Controllo di flusso (JMP, CALL, RET)
    - Gestione I/O

## 5. RAPPRESENTAZIONE DELLE INFORMAZIONI

### 5.1 Tipi di Memoria: ROM, RAM, Cache

- **ROM e tipi**:
    - ROM tradizionale: programmata in fabbrica
    - PROM (Programmable ROM): programmabile una sola volta
    - EPROM (Erasable PROM): cancellabile con UV
    - EEPROM (Electrically EPROM): cancellabile elettricamente
    - Flash: evoluzione dell'EEPROM, base di SSD e memorie USB
- **RAM e tipi**:
    - SRAM (Static RAM): veloce, costosa, usata per cache
    - DRAM (Dynamic RAM): più economica, richiede refresh
    - SDRAM (Synchronous DRAM): sincronizzata col clock
    - DDR SDRAM (Double Data Rate): trasferisce dati su entrambi i fronti del clock
- **Cache e località**:
    - Località temporale: dati usati recentemente probabilmente riusati presto
    - Località spaziale: dati vicini a quelli acceduti probabilmente acceduti presto
    - Livelli: L1 (nella CPU), L2, L3 (condivisa tra core)

### 5.2 Tipi di Indirizzamento

Modi in cui un processore può identificare gli operandi:

- **Immediato**: il valore è parte dell'istruzione (es: ADD R1, #5)
- **Diretto**: l'istruzione contiene l'indirizzo del dato (es: ADD R1, [100])
- **Indiretto**: l'istruzione contiene l'indirizzo dell'indirizzo del dato (es: ADD R1, [[100]])
- **Indicizzato**: l'indirizzo effettivo è somma di un registro indice e un offset (es: ADD R1, [R2+10])
- **Basato su registro**: l'operando è in un registro (es: ADD R1, R2)
- **Relativo al PC**: indirizzamento relativo al Program Counter (usato nei salti)

### 5.3 Rappresentazione delle Informazioni e Codifiche

- **Sistema binario**: base 2 (0,1), usato internamente dai computer
- **Sistema ottale**: base 8 (0-7), poco usato oggi
- **Sistema esadecimale**: base 16 (0-9, A-F), usato per rappresentare dati binari in modo compatto
- **Conversioni**:
    - Binario a esadecimale: raggruppare 4 bit
    - Binario a ottale: raggruppare 3 bit
- **Codifiche caratteri**:
    - ASCII: 7 bit, 128 caratteri
    - Extended ASCII: 8 bit, 256 caratteri
    - Unicode: standard universale (UTF-8, UTF-16, UTF-32)

### 5.4 Digitalizzazione

Processo di conversione di segnali analogici in digitali:

- **Campionamento**: misurazione del segnale ad intervalli regolari
- **Quantizzazione**: arrotondamento dei valori campionati a livelli discreti
- **Codifica**: rappresentazione dei valori quantizzati in bit
- **Compressione**:
    - Lossless: senza perdita di informazioni (ZIP, PNG)
    - Lossy: con perdita accettabile di informazioni (JPEG, MP3)
    - Tecniche: codifica entropia, compressione predittiva, trasformate

## 6. SISTEMI OPERATIVI

### 6.1 Introduzione ai Sistemi Operativi

Il sistema operativo è un software che gestisce l'hardware del computer e fornisce servizi ai programmi applicativi:

- Intermediario tra utente e hardware
- Gestore delle risorse di sistema
- Fornisce un'interfaccia per i programmi applicativi (API)
- Garantisce sicurezza e isolamento

### 6.2 Tipi di OS e Processi

- **Tipi di OS**:
    - Monolitici: kernel unico (Linux, Unix tradizionali)
    - A microkernel: funzioni minime nel kernel (MINIX)
    - Ibridi: combinano aspetti monolitici e microkernel (Windows, macOS)
    - Real-time: garantiscono tempi di risposta deterministici
    - Embedded: per dispositivi dedicati
    - Distribuiti: su più macchine fisiche
- **Processi e stati**:
    - Processo: programma in esecuzione con risorse associate
    - Stati principali: nuovo, pronto, in esecuzione, in attesa, terminato
    - Transizioni tra stati gestite dallo scheduler

### 6.3 Politiche di Gestione dei Processi

- **FCFS/FIFO** (First Come First Served):
    - I processi vengono eseguiti nell'ordine di arrivo
    - Semplice ma inefficiente, può causare convoy effect
- **SJF** (Shortest Job First):
    - Si esegue prima il processo più breve
    - Ottimale per il tempo medio di completamento
    - Difficile prevedere la durata dei processi
- **Round Robin**:
    - A ciascun processo è assegnato un quanto di tempo
    - Allo scadere del tempo, il processo torna in coda
    - Buon compromesso tra responsività e equità
- **Priorità**:
    - Processi con priorità più alta vengono eseguiti prima
    - Rischio di starvation per processi a bassa priorità

### 6.4 Gestione della Memoria

- **Paginazione**:
    - Memoria fisica divisa in frame di dimensione fissa
    - Memoria logica divisa in pagine della stessa dimensione
    - Tabella delle pagine per mappare pagine logiche su frame fisici
    - Vantaggi: riduce frammentazione esterna, supporta memoria virtuale
- **Segmentazione**:
    - Divisione in segmenti logici di dimensione variabile
    - Ogni segmento ha un nome e una lunghezza
    - Supporta naturalmente la protezione e la condivisione
    - Svantaggi: può causare frammentazione esterna

### 6.5 Permessi ed Errori

- **Permessi di accesso**:
    - Lettura (R)
    - Scrittura (W)
    - Esecuzione (X)
    - Controllati per garantire protezione
- **Memory Faults**:
    - Segmentation Fault: accesso a memoria non allocata
    - Page Fault: accesso a pagina non in memoria principale
    - Protection Fault: violazione dei permessi di accesso
    - Bus Error: accesso a indirizzo fisicamente invalido

## 7. LIVELLO FISICO

### 7.1 Introduzione allo Strato Fisico

Lo strato fisico (livello 1 del modello ISO/OSI) si occupa della trasmissione di bit grezzi attraverso il canale di comunicazione:

- Definisce caratteristiche elettriche, meccaniche e funzionali
- Si occupa della modulazione e codifica del segnale
- Gestisce il mezzo trasmissivo

### 7.2 Teoria dei Segnali

- **Tipi di segnali**:
    - Analogici: variano con continuità nel tempo
    - Digitali: discreti, rappresentati da sequenze di 0 e 1
- **Caratteristiche**:
    - Ampiezza: intensità del segnale
    - Frequenza: cicli per secondo (Hertz)
    - Fase: posizione relativa nell'onda
    - Larghezza di banda: intervallo di frequenze utilizzate

### 7.3 Tipologie di Cavo e Trasmissione

- **Cavi in rame**:
    - Doppino intrecciato (UTP, STP): economico, sensibile a interferenze
    - Cavo coassiale: migliore schermatura, maggiore larghezza di banda
- **Fibra ottica**:
    - Monomodale: distanze maggiori, più costosa
    - Multimodale: distanze minori, più economica
    - Vantaggi: immunità alle interferenze, alta velocità, sicurezza
- **Trasmissione wireless**:
    - Radio: WiFi, Bluetooth, cellulare
    - Infrarossi: line-of-sight, limitata distanza
    - Microonde: collegamenti punto-punto
- **Problemi di trasmissione**:
    - Attenuazione: perdita di energia del segnale
    - Distorsione: alterazione della forma del segnale
    - Rumore: interferenze elettriche
    - Jitter: variazioni nel tempo di arrivo

### 7.4 Gestione Errori, Framing e Flusso

- **Gestione errori**:
    - Rilevazione: parità, CRC, checksum
    - Correzione: codici a correzione d'errore (Hamming, Reed-Solomon)
- **Framing**:
    - Delimitazione dei frame: flag, conteggio caratteri, violazioni di codifica
    - Sincronizzazione
- **Controllo di flusso**:
    - Stop-and-wait: attesa di ACK prima di inviare il frame successivo
    - Sliding window: invio di più frame prima di ricevere ACK

### 7.5 Modulazioni

Tecniche per adattare il segnale digitale al mezzo trasmissivo:

- **Modulazione di ampiezza (AM)**: varia l'ampiezza dell'onda portante
- **Modulazione di frequenza (FM)**: varia la frequenza
- **Modulazione di fase (PM)**: varia la fase
- **Modulazioni digitali**:
    - ASK (Amplitude Shift Keying)
    - FSK (Frequency Shift Keying)
    - PSK (Phase Shift Keying)
    - QAM (Quadrature Amplitude Modulation): combina ampiezza e fase

### 7.6 Architetture di Rete

- **Problemi**:
    - Scalabilità: capacità di crescere senza degradazione
    - Distribuzione: gestione efficiente di risorse distribuite
- **Quality of Service (QoS)**:
    - Parametri: larghezza di banda, ritardo, jitter, perdita di pacchetti
    - Tecniche: prioritizzazione, prenotazione di risorse, shaping del traffico
- **Tipi di reti per dimensione**:
    - PAN (Personal Area Network): pochi metri
    - LAN (Local Area Network): edificio o campus
    - MAN (Metropolitan Area Network): città
    - WAN (Wide Area Network): paesi o continenti
- **Architetture client/server vs peer-to-peer**

### 7.7 Ridondanza e Tolleranza all'Errore

- **Ridondanza**: duplicazione di componenti critici
- **Tecniche di fault tolerance**:
    - Replicazione
    - Standby systems
    - Fail-over automatico
    - RAID per lo storage

### 7.8 Dispositivi di Rete

- **Hub**: ripete il segnale su tutte le porte (livello 1)
- **Switch**: inoltra i frame in base all'indirizzo MAC (livello 2)
- **Bridge**: collega segmenti di rete (livello 2)
- **Router**: instrada pacchetti tra reti diverse (livello 3)
- **Gateway**: traduce tra protocolli diversi (livelli superiori)

### 7.9 Topologie di Rete

- **A stella**: dispositivi collegati a un nodo centrale
    - Vantaggi: facile implementazione, isolamento guasti
    - Svantaggi: single point of failure
- **Ad anello**: ogni nodo collegato a due vicini
    - Vantaggi: accesso deterministico, nessuna collisione
    - Svantaggi: un guasto può interrompere l'anello
- **A bus**: tutti i nodi collegati a un unico canale
    - Vantaggi: semplice, economico
    - Svantaggi: limitata scalabilità, vulnerabile a guasti
- **A maglia (mesh)**:
    - Completa: ogni nodo collegato a tutti gli altri
    - Parziale: collegamenti selettivi
    - Vantaggi: alta affidabilità, percorsi alternativi
    - Svantaggi: costo elevato, complessità
- **Ad albero**: gerarchia di nodi
    - Vantaggi: scalabilità, gestione semplificata
    - Svantaggi: dipendenza dai nodi superiori

### 7.10 Ethernet e Tecnologie

- **Ethernet**: standard dominante per LAN (IEEE 802.3)
- **Struttura pacchetto Ethernet**:
    - Preambolo (7 byte)
    - SFD - Start Frame Delimiter (1 byte)
    - Indirizzo MAC destinazione (6 byte)
    - Indirizzo MAC sorgente (6 byte)
    - EtherType/Length (2 byte)
    - Payload (46-1500 byte)
    - FCS - Frame Check Sequence (4 byte, CRC-32)
- **Token Ring**: tecnica di accesso con passaggio di token
    - Accesso deterministico
    - Poco usato oggi, sostituito da Ethernet

## 8. ALGORITMI DI CONTESA

### 8.1 Algoritmi di Contesa a Livello Fisico

- **ALOHA**:
    - Trasmissione immediata
    - In caso di collisione, ritrasmissione dopo tempo casuale
    - Efficienza massima teorica: 18%
- **Slotted ALOHA**:
    - Tempo diviso in slot
    - Trasmissione solo all'inizio di uno slot
    - Efficienza massima teorica: 37%
- **CSMA** (Carrier Sense Multiple Access):
    - Ascolta prima di trasmettere
    - Varianti:
        - 1-persistente: trasmette subito se canale libero
        - Non-persistente: attende tempo casuale se canale occupato
        - p-persistente: trasmette con probabilità p se canale libero
- **CSMA/CD** (CSMA with Collision Detection):
    - Rileva collisioni durante la trasmissione
    - In caso di collisione, interrompe e ritrasmette dopo tempo casuale
    - Usato in Ethernet tradizionale

### 8.2 Problemi MAC (Medium Access Control)

- **Collisioni**: due o più stazioni trasmettono contemporaneamente
- **Hidden terminal**: stazioni che non possono sentirsi a vicenda
- **Exposed terminal**: inibizione non necessaria di trasmissioni
- **Fairness**: equità nell'accesso al mezzo
- **Overhead**: costo di gestione del protocollo

### 8.3 Frequenze Wireless e Spettro

- **Bande di frequenza**:
    - 2.4 GHz: WiFi, Bluetooth, microonde
    - 5 GHz: WiFi più recente
    - 60 GHz: WiGig, comunicazioni ad alta velocità
    - Licenziate vs non licenziate
- **Regolamentazione**: ITU, autorità nazionali
- **Allocazione dello spettro**: statica vs dinamica

### 8.4 Reti Infrarossi, Telefoniche e Satellitari

- **Reti infrarossi**:
    - Line-of-sight, corto raggio
    - IrDA, telecomandi
- **Reti telefoniche cellulari**:
    - Celle e riuso delle frequenze
    - Handoff: trasferimento di connessione tra celle
    - Soft handoff vs hard handoff
- **Reti satellitari**:
    - LEO (Low Earth Orbit): 500-2000 km, bassa latenza, vita breve
    - MEO (Medium Earth Orbit): 8000-20000 km
    - GEO (Geostationary Earth Orbit): 36000 km, alta latenza, copertura ampia

### 8.5 Generazioni Reti Cellulari e Modulazioni

- **1G**: analogico (AMPS)
- **2G**: digitale (GSM, CDMA)
- **3G**: dati a banda larga (UMTS, CDMA2000)
- **4G/LTE**: IP-based, alta velocità
- **5G**: latenza ultra-bassa, IoT, slicing di rete
- **Modulazioni telefoniche**:
    - AMPS (Advanced Mobile Phone System): analogico
    - CDMA (Code Division Multiple Access): codici unici per utente
    - TDMA (Time Division Multiple Access): slot temporali
    - FDMA (Frequency Division Multiple Access): canali in frequenza

### 8.6 Standard ISO/IEEE

- **ISO** (International Organization for Standardization):
    - Modello OSI
    - Standard per formati di documenti, sicurezza, ecc.
- **IEEE** (Institute of Electrical and Electronics Engineers):
    - 802.3: Ethernet
    - 802.11: WiFi
    - 802.15: Bluetooth, ZigBee
    - 802.16: WiMAX

### 8.7 Commutazione e Switching

- **Commutazione di circuito**:
    - Connessione dedicata per tutta la durata
    - Risorse riservate, QoS garantita
    - Inefficiente per traffico a burst
    - Es: rete telefonica tradizionale
- **Commutazione di pacchetto**:
    - I dati divisi in pacchetti indipendenti
    - Condivisione delle risorse
    - Più efficiente, ma senza garanzie di QoS
    - Es: Internet

### 8.8 Protocolli per LAN Wireless

- **Problemi specifici**:
    - Stazione esposta: inibizione non necessaria
    - Stazione nascosta: impossibilità di rilevare collisioni
- **MACA** (Multiple Access with Collision Avoidance):
    - Usa RTS (Request To Send) e CTS (Clear To Send)
    - Risolve il problema della stazione nascosta
- **MACAW** (MACA for Wireless):
    - Evoluzione di MACA
    - Aggiunge ACK e backoff adattivo

### 8.9 Ethernet: Codifica e Backoff

- **Codifica Manchester**:
    - Transizione a metà bit
    - Alto-basso per 0, basso-alto per 1
    - Autosincronia, rilevamento errori
- **Algoritmo di backoff esponenziale**:
    - Dopo una collisione, attesa casuale
    - Finestra di contesa raddoppia ad ogni collisione consecutiva
    - Limitato a un massimo (10 in Ethernet)

### 8.10 Tipi di Trasmissione

- **Unicast**: da uno a uno
- **Broadcast**: da uno a tutti
- **Multicast**: da uno a molti
- **Anycast**: da uno a uno qualsiasi di un gruppo

## 9. MODELLI DI RIFERIMENTO

### 9.1 Modello ISO/OSI

Modello a 7 livelli per standardizzare le comunicazioni di rete:

1. **Livello fisico**: trasmissione di bit grezzi
2. **Livello data link**: framing e controllo errori
3. **Livello rete**: routing e indirizzamento
4. **Livello trasporto**: connessione end-to-end affidabile
5. **Livello sessione**: gestione delle sessioni
6. **Livello presentazione**: rappresentazione dati
7. **Livello applicazione**: servizi di rete all'utente

### 9.2 Modello TCP/IP

Modello a 4 livelli usato in Internet:

1. **Livello di accesso alla rete**: corrisponde ai livelli 1 e 2 di OSI
2. **Livello internet**: corrisponde al livello 3 di OSI (protocollo IP)
3. **Livello di trasporto**: corrisponde al livello 4 di OSI (TCP, UDP)
4. **Livello applicazione**: corrisponde ai livelli 5, 6 e 7 di OSI

### 9.3 Confronto tra ISO/OSI e TCP/IP

|Caratteristica|ISO/OSI|TCP/IP|
|---|---|---|
|Numero di livelli|7|4|
|Orientamento|Teorico|Pratico|
|Sviluppo|Prima il modello, poi i protocolli|Prima i protocolli, poi il modello|
|Adozione|Limitata|Universale|
|Complessità|Maggiore|Minore|
|Flessibilità|Rigido|Flessibile|

### 9.4 Livello 2: LLC/MAC

Il livello data link è suddiviso in due sottolivelli:

- **LLC** (Logical Link Control):
    - Fornisce un'interfaccia verso il livello superiore (rete)
    - Indipendente dal mezzo fisico
    - Controllo di flusso e gestione errori
- **MAC** (Media Access Control):
    - Gestisce l'accesso al mezzo condiviso
    - Indirizzamento MAC (48 bit)
    - Specifico per il tipo di rete (Ethernet, WiFi, ecc.)

## 10. LIVELLO DI RETE

### 10.1 Introduzione al Livello 3

Il livello di rete si occupa di:

- Routing dei pacchetti tra reti diverse
- Indirizzamento logico (IP)
- Frammentazione e riassemblaggio dei pacchetti
- Controllo della congestione
- Qualità del servizio

### 10.2 Tipi di Routing

- **Routing statico**:
    - Percorsi configurati manualmente dall'amministratore
    - Non si adatta ai cambiamenti topologici
    - Basso overhead, ma poca flessibilità
    - Adatto a reti piccole e stabili
- **Routing dinamico**:
    - I router scambiano informazioni sulla topologia
    - Si adatta automaticamente ai cambiamenti
    - Maggiore overhead, ma più flessibile
    - Protocolli: RIP, OSPF, BGP, ecc.

### 10.3 Algoritmi di Routing: Link State e Distance Vector

- **Distance Vector**:
    - Basato sull'algoritmo di Bellman-Ford
    - Ogni router condivide con i vicini la propria visione della rete
    - Problemi: slow convergence, count-to-infinity
    - Esempi: RIP, RIPv2
- **Link State**:
    - Basato sull'algoritmo di Dijkstra
    - Ogni router costruisce una mappa completa della rete
    - Convergenza più rapida, ma maggior consumo di risorse
    - Esempi: OSPF, IS-IS

### 10.4 Routing Table

Tabella contenente le informazioni per l'inoltro dei pacchetti:

- Prefisso di destinazione (indirizzo di rete)
- Maschera di sottorete
- Next hop (indirizzo del router successivo)
- Interfaccia di uscita
- Metrica (costo del percorso)
- Flag e timer

### 10.5 Algoritmo di Bellman-Ford

Utilizzato nei protocolli distance vector:

- Calcola il percorso più breve tra nodi in un grafo
- Funziona anche in presenza di pesi negativi
- Complessità: O(V×E) dove V è il numero di vertici e E il numero di archi
- Problemi in reti con cicli

### 10.6 Algoritmo di Dijkstra

Utilizzato nei protocolli link state:

- Calcola il percorso più breve da un nodo a tutti gli altri
- Funziona solo con pesi positivi o nulli
- Complessità: O(V²) o O(E log V) con coda di priorità
- Più efficiente in reti dense

### 10.7 Routing Mobile

Gestione di nodi che cambiano posizione:

- **Home Agent**: gestisce la posizione corrente del nodo mobile
- **Foreign Agent**: fornisce servizi al nodo in roaming
- **Tunneling**: incapsulamento dei pacchetti per il forwarding
- Protocolli: Mobile IP, NEMO

### 10.8 Algoritmi di Congestione

- **Leaky Bucket**:
    - Regola il flusso di pacchetti come un secchio che perde
    - Rata di uscita costante
    - Traffico in eccesso viene scartato
- **Token Bucket**:
    - Genera token a velocità costante
    - Un pacchetto può essere trasmesso solo se c'è un token disponibile
    - Consente burst controllati di traffico

### 10.9 Algoritmi di Routing Avanzati

- **BGP** (Border Gateway Protocol):
    - Protocollo di routing esterno (EGP)
    - Utilizzato tra Autonomous System (AS)
    - Path vector, policy-based
    - Considera fattori politici, economici oltre ai tecnici
- **OSPF** (Open Shortest Path First):
    - Protocollo di routing interno (IGP)
    - Link state
    - Supporta aree gerarchiche
    - Convergenza rapida

### 10.10 Algoritmi di Controllo

- **ICMP** (Internet Control Message Protocol):
    - Segnalazione di errori
    - Echo request/reply (ping)
    - Redirect
    - Time exceeded
- **RIP** (Routing Information Protocol):
    - Distance vector
    - Metrica: numero di hop (max 15)
    - Aggiornamenti periodici ogni 30 secondi
    - Limitato per reti grandi

### 10.11 Struttura Pacchetto IPv4

- **Versione** (4 bit): IPv4 = 4
- **IHL** (4 bit): lunghezza dell'header in parole da 32 bit
- **ToS/DSCP** (8 bit): tipo di servizio / punto di codice per servizi differenziati
- **Lunghezza totale** (16 bit): lunghezza totale in byte
- **Identificazione** (16 bit): identifica i frammenti di un pacchetto
- **Flag** (3 bit): controllo frammentazione
- **Offset frammentazione** (13 bit): posizione del frammento
- **TTL** (8 bit): time to live, decrementato ad ogni hop
- **Protocollo** (8 bit): protocollo di livello superiore (TCP=6, UDP=17, ICMP=1)
- **Checksum header** (16 bit): verifica integrità header
- **Indirizzo sorgente** (32 bit)
- **Indirizzo destinazione** (32 bit)
- **Opzioni** (variabile): opzioni aggiuntive
- **Dati** (variabile): payload

### 10.12 Differenze tra IPv4 e IPv6

|Caratteristica|IPv4|IPv6|
|---|---|---|
|Lunghezza indirizzo|32 bit (4 byte)|128 bit (16 byte)|
|Notazione|Decimale puntata|Esadecimale con :|
|Numero di indirizzi|~4,3 miliardi|~3,4×10^38|
|Header|Variabile, complesso|Fisso, semplificato|
|Frammentazione|Router e host|Solo host|
|Checksum|Presente|Assente (delegato ai livelli superiori)|
|Configurazione|Manuale o DHCP|Autoconfigurazione o DHCPv6|
|NAT|Comune|Non necessario|
|Sicurezza|Opzionale (IPsec)|Integrata|
|QoS|Basata su ToS|Flow Label|
|Multicast|Limitato|Integrato e migliorato|
|Broadcast|Supportato|Sostituito da multicast|

### 10.13 Internetworking e Topologie di Rete

- **Internetworking**: connessione di reti eterogenee
- **Dispositivi di interconnessione**:
    - Bridge: livello 2, collega segmenti LAN
    - Router: livello 3, collega reti diverse
    - Gateway: livelli superiori, traduce protocolli
- **Topologie di internetworking**:
    - Backbone: rete principale ad alta velocità
    - Star-based: reti satelliti collegate a hub centrali
    - Mesh: connessioni ridondanti tra reti
    - Gerarchica: reti organizzate a livelli

### 10.14 Algoritmi di Congestione Avanzati

- **Choke Packet**:
    - Il router congestionato invia pacchetti di "strozzamento" alla sorgente
    - La sorgente riduce la velocità di trasmissione
- **Leaky Bucket**:
    - Limita il traffico a una velocità costante
    - I pacchetti in eccesso vengono bufferizzati o scartati
- **Token Bucket**:
    - Limita il traffico medio ma permette burst
    - Tokens generati a velocità costante, consumati dai pacchetti

## 11. LIVELLO DI TRASPORTO

### 11.1 TCP e UDP: Caratteristiche e Confronto

- **TCP** (Transmission Control Protocol):
    - Orientato alla connessione
    - Affidabile: garantisce consegna in ordine e senza duplicati
    - Controllo di flusso e congestione
    - Overhead maggiore
    - Applicazioni: web, email, file transfer
- **UDP** (User Datagram Protocol):
    - Senza connessione
    - Non affidabile: possibili perdite, duplicati, disordine
    - Nessun controllo di flusso o congestione
    - Overhead minimo
    - Applicazioni: streaming, VoIP, DNS

|Caratteristica|TCP|UDP|
|---|---|---|
|Affidabilità|Alta|Bassa|
|Ordine pacchetti|Garantito|Non garantito|
|Velocità|Più lenta|Più veloce|
|Overhead|Alto|Basso|
|Handshake|3-way|Nessuno|
|Controllo congestione|Sì|No|
|Dimensione header|20-60 byte|8 byte|

### 11.2 Algoritmi di Controllo Flusso

- **Stop-and-wait**:
    - Il mittente invia un pacchetto e attende ACK
    - Semplice ma inefficiente
    - Utilizzabile per collegamenti ad alta velocità e bassa latenza
- **Go-back-N**:
    - Finestra scorrevole di N pacchetti
    - Se timeout, ritrasmette tutti i pacchetti dalla posizione N
    - Efficiente ma può ritrasmettere pacchetti già ricevuti
- **Selective Repeat**:
    - Finestra scorrevole con ACK selettivi
    - Ritrasmette solo i pacchetti persi
    - Più efficiente ma più complesso

### 11.3 Port e Socket

- **Port**:
    - Identificatore numerico (16 bit) per processi/servizi
    - Tipi: well-known (0-1023), registered (1024-49151), dynamic (49152-65535)
    - Esempi: HTTP=80, HTTPS=443, FTP=21, SSH=22
- **Socket**:
    - Endpoint di comunicazione
    - Identificato da IP:porta
    - API per la comunicazione di rete
    - Tipi: stream (TCP), datagram (UDP), raw

### 11.4 Connessione e Disconnessione

- **TCP Three-way Handshake**:
    1. SYN: client → server (inizializza sequenza)
    2. SYN+ACK: server → client (conferma e inizializza sequenza)
    3. ACK: client → server (conferma)
- **TCP Four-way Termination**:
    1. FIN: client → server (chiusura in un senso)
    2. ACK: server → client (conferma)
    3. FIN: server → client (chiusura nell'altro senso)
    4. ACK: client → server (conferma)

### 11.5 Gestione Problemi di Rete

- **Perdita di pacchetti**:
    - Rilevamento: timeout, ACK duplicati
    - Mitigazione: ritrasmissione
- **Congestione**:
    - Rilevamento: aumento RTT, perdita pacchetti
    - Algoritmi: slow start, congestion avoidance, fast retransmit, fast recovery
- **Latenza**:
    - Monitoraggio RTT (Round Trip Time)
    - Adaptive timeout
- **Jitter**:
    - Buffer di playout (per applicazioni multimediali)
    - Prioritizzazione del traffico

## 12. PRINCIPI FONDAMENTALI DI SICUREZZA

### 12.1 Triade CIA

Tre principi fondamentali della sicurezza informatica:

- **Confidenzialità** (Confidentiality):
    - Protezione da accessi non autorizzati
    - Tecniche: crittografia, controllo accessi, autenticazione
- **Integrità** (Integrity):
    - Garanzia che i dati non siano alterati
    - Tecniche: hash, firme digitali, controlli di integrità
- **Disponibilità** (Availability):
    - Garanzia che i servizi siano accessibili quando necessario
    - Tecniche: ridondanza, backup, disaster recovery

### 12.2 Autenticazione, Autorizzazione, Accounting (AAA)

- **Autenticazione**: verifica dell'identità
    - Fattori: qualcosa che sai, hai, sei
    - Tecniche: password, token, biometria
- **Autorizzazione**: concessione di privilegi
    - RBAC (Role-Based Access Control)
    - ACL (Access Control List)
    - Principio del privilegio minimo
- **Accounting**: tracciamento delle attività
    - Logging
    - Auditing
    - Non ripudio

### 12.3 Minacce, Vulnerabilità e Rischi

- **Minaccia**: potenziale causa di un incidente
    - Naturale: disastri naturali
    - Involontaria: errori umani
    - Intenzionale: attacchi
- **Vulnerabilità**: debolezza che può essere sfruttata
    - Software: bug, configurazioni errate
    - Hardware: difetti di progettazione
    - Organizzativa: procedure inadeguate
- **Rischio**: probabilità che una minaccia sfrutti una vulnerabilità
    - Risk = Threat × Vulnerability × Asset Value
    - Gestione del rischio: identificazione, analisi, mitigazione

## 13. VULNERABILITÀ A LIVELLO DI RETE E TRASPORTO

### 13.1 Vulnerabilità a Livello 2 (Data Link)

- **ARP Spoofing/Poisoning**:
    - Falsificazione di risposte ARP
    - Permette man-in-the-middle su LAN
    - Contromisure: DHCP snooping, DAI, static ARP
- **MAC Flooding**:
    - Saturazione della tabella CAM dello switch
    - Forza lo switch in modalità hub
    - Contromisure: port security, MAC limit
- **Rogue DHCP**:
    - Server DHCP non autorizzato
    - Può reindirizzare traffico o negare servizio
    - Contromisure: DHCP snooping, autenticazione 802.1X

### 13.2 Vulnerabilità a Livello 3 (Network)

- **IP Spoofing**:
    - Falsificazione dell'indirizzo IP sorgente
    - Usato per attacchi DoS o bypass di filtri
    - Contromisure: ingress/egress filtering, RPF
- **ICMP Attacks**:
    - Ping flood
    - Smurf attack (amplificazione broadcast)
    - ICMP redirect illegittimo
    - Contromisure: filtraggio ICMP, rate limiting
- **Routing Attacks**:
    - Route poisoning
    - Black hole routing
    - Contromisure: autenticazione routing, filtri

### 13.3 Vulnerabilità a Livello 4 (Transport)

- **TCP SYN Flood**:
    - Invio massivo di SYN senza completare handshake
    - Esaurisce le risorse del server
    - Contromisure: SYN cookies, firewall
- **Session Hijacking**:
    - Intercettazione e furto di sessione attiva
    - Possibile con sniffing e sequenza prevedibile
    - Contromisure: crittografia, random sequence numbers
- **UDP Flood**:
    - Invio massivo di pacchetti UDP
    - Possibili attacchi di amplificazione
    - Contromisure: rate limiting, filtri

## 14. SOCIAL ENGINEERING E ATTACCHI A LIVELLO UMANO

### 14.1 Definizione e Tecniche Principali

Il social engineering sfrutta la psicologia umana anziché vulnerabilità tecniche:

- **Principi psicologici sfruttati**:
    - Autorità
    - Scarsità
    - Simpatia
    - Reciprocità
    - Impegno e coerenza
    - Prova sociale
    - Urgenza

### 14.2 Phishing e Varianti

- **Phishing generico**:
    - Email o messaggi che sembrano da fonti legittime
    - Induce l'utente a rivelare credenziali o dati personali
- **Spear Phishing**:
    - Phishing mirato a specifici individui o organizzazioni
    - Personalizzato con informazioni su target
- **Vishing** (Voice Phishing):
    - Phishing tramite telefono
    - Sfrutta social engineering vocale

### 14.3 Pretexting e Baiting

- **Pretexting**:
    - Creazione di scenario fittizio per ottenere informazioni
    - L'attaccante si finge un'altra persona (HR, IT, ecc.)
- **Baiting**:
    - Usa curiosità o avidità come esca
    - Es: chiavette USB infette lasciate in luoghi pubblici

### 14.4 Contromisure e Prevenzione

- **Formazione e sensibilizzazione**:
    - Training regolare degli utenti
    - Simulazioni di phishing
- **Politiche e procedure**:
    - Verifica multi-canale per richieste sensibili
    - Principio del "need to know"
- **Tecnologie**:
    - Filtri anti-phishing
    - Autenticazione multi-fattore
    - Analisi comportamentale

## 15. ACCENNI AI LIVELLI SUCCESSIVI ISO/OSI

### 15.1 Livello 5 – Sessione

- **Funzioni principali**:
    - Stabilimento, gestione e chiusura delle sessioni
    - Sincronizzazione del dialogo
    - Controllo del token
    - Ripristino della sessione
- **Protocolli**:
    - NetBIOS
    - RPC
    - SSL/TLS (aspetti di sessione)

### 15.2 Livello 6 – Presentazione

- **Funzioni principali**:
    - Traduzione, compressione e crittografia dei dati
    - Conversione di formato
    - Negoziazione della sintassi
- **Standard e formati**:
    - ASCII, Unicode
    - JPEG, MPEG, GIF
    - XDR (External Data Representation)

### 15.3 Livello 7 – Applicazione

- **Funzioni principali**:
    - Interfaccia per le applicazioni utente
    - Servizi di rete
    - Identificazione dei partner comunicanti
- **Protocolli comuni**:
    - HTTP/HTTPS (web)
    - SMTP, POP3, IMAP (email)
    - FTP, SFTP (file transfer)
    - DNS (risoluzione nomi)
    - DHCP (configurazione IP)
    - Telnet, SSH (terminal)

---

# GLOSSARIO TERMINI CHIAVE

- **ALU** (Arithmetic Logic Unit): componente della CPU che esegue operazioni aritmetiche e logiche
- **ALOHA**: protocollo di accesso al mezzo trasmissivo ad alto rischio di collisione
- **ARP** (Address Resolution Protocol): protocollo per mappare indirizzi IP in indirizzi MAC
- **ASK** (Amplitude Shift Keying): modulazione che varia l'ampiezza del segnale
- **BGP** (Border Gateway Protocol): protocollo di routing tra Autonomous System
- **CISC** (Complex Instruction Set Computer): architettura con set di istruzioni complesso
- **CRC** (Cyclic Redundancy Check): tecnica di rilevamento errori
- **CSMA/CD** (Carrier Sense Multiple Access with Collision Detection): protocollo di accesso al mezzo con rilevamento collisioni
- **CU** (Control Unit): componente della CPU che coordina le operazioni
- **DHCP** (Dynamic Host Configuration Protocol): protocollo per assegnazione automatica indirizzi IP
- **Dijkstra**: algoritmo per trovare il percorso minimo in un grafo
- **DNS** (Domain Name System): sistema per tradurre nomi di dominio in indirizzi IP
- **EEPROM** (Electrically Erasable Programmable ROM): memoria cancellabile elettricamente
- **Ethernet**: tecnologia per LAN standardizzata IEEE 802.3
- **FIFO** (First In First Out): politica di scheduling che processa richieste nell'ordine di arrivo
- **FPU** (Floating Point Unit): unità specializzata per calcoli in virgola mobile
- **FSB** (Front Side Bus): bus che collega CPU e northbridge
- **FTP** (File Transfer Protocol): protocollo per trasferimento file
- **GEO** (Geostationary Earth Orbit): orbita satellitare a 36000 km
- **HTTP** (Hypertext Transfer Protocol): protocollo applicativo per il web
- **ICMP** (Internet Control Message Protocol): protocollo per messaggi di controllo IP
- **IEEE** (Institute of Electrical and Electronics Engineers): organizzazione per standardizzazione
- **IP** (Internet Protocol): protocollo di rete fondamentale di Internet
- **ISA** (Instruction Set Architecture): insieme delle istruzioni eseguibili da una CPU
- **ISO** (International Organization for Standardization): organizzazione per standardizzazione
- **LLC** (Logical Link Control): sottolivello superiore del livello data link
- **MAC** (Media Access Control): sottolivello inferiore del livello data link
- **MACA** (Multiple Access with Collision Avoidance): protocollo di accesso wireless
- **MIPS** (Million Instructions Per Second): misura di performance CPU
- **NAT** (Network Address Translation): traduzione indirizzi di rete
- **OSPF** (Open Shortest Path First): protocollo di routing link state
- **PCIe** (Peripheral Component Interconnect Express): bus per periferiche ad alta velocità
- **QAM** (Quadrature Amplitude Modulation): modulazione che combina ampiezza e fase
- **QoS** (Quality of Service): gestione priorità traffico di rete
- **RAID** (Redundant Array of Independent Disks): tecnologia di ridondanza dati
- **RAM** (Random Access Memory): memoria volatile ad accesso casuale
- **RIP** (Routing Information Protocol): protocollo di routing distance vector
- **RISC** (Reduced Instruction Set Computer): architettura con set di istruzioni ridotto
- **ROM** (Read-Only Memory): memoria non volatile di sola lettura
- **RTS/CTS** (Request To Send/Clear To Send): meccanismo di controllo accesso in reti wireless
- **RTT** (Round Trip Time): tempo di andata e ritorno di un pacchetto
- **SJF** (Shortest Job First): politica di scheduling che prioritizza processi più brevi
- **SMTP** (Simple Mail Transfer Protocol): protocollo per invio email
- **SSD** (Solid State Drive): dispositivo di memoria non volatile basato su flash
- **TCP** (Transmission Control Protocol): protocollo di trasporto affidabile
- **TTL** (Time To Live): campo IP che limita la vita del pacchetto
- **UDP** (User Datagram Protocol): protocollo di trasporto non affidabile
- **UTP** (Unshielded Twisted Pair): cavo a coppie intrecciate non schermato
- **VoIP** (Voice over IP): tecnologia per trasmissione voce su IP
- **WAN** (Wide Area Network): rete geografica estesa