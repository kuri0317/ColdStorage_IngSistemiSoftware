Progetto per l'esame di Ingegneria dei Sistemi Software M - UNIBO (sviluppato in solitaria)

- scaricare o clonare la repository
- unzippare il file
- consultare le cartelle 'Presentazione' e 'User_Docs_finali' per informazioni più approfondite su come far partire ogni step e test del progetto

Il progetto gestisce il carico e lo scarico di merce all'interno di un sistema frigorifero, gestendo le prenotazioni di spazio e le richieste di tickets.

# ColdStorage Service — Ingegneria dei Sistemi Software

- **Progetto per l'esame di Ingegneria dei Sistemi Software M — UNIBO Magistrale**  
- Sviluppato in solitaria

Sistema distribuito per la **gestione automatizzata di un magazzino frigorifero**, con robot DDR per il trasporto merce, sistema di allarmi e interfaccia web per gli utenti.


## Scenario

Una azienda commissiona un sistema per gestire un **ColdStorage** composto da:
- **Service Area**: area rettangolare con porta INDOOR e container ColdRoom
- **DDR Robot**: transport trolley per carico/scarico merce
- **ServiceAccessGUI**: interfaccia per richiedere ticket e validarli
- **ServiceStatusGUI**: dashboard per il service manager
- **Sistema di allarmi**: Sonar e Led per sicurezza

## Tecnologie

| Tecnologia | Utilizzo |
|------------|----------|
| **QAK / QActor** | Core applicativo, comunicazioni COAP/TCP |
| **Java** | Connessioni COAP/TCP, classi di supporto |
| **SpringBoot + Thymeleaf** | Server Web, frontend HTML/JS |
| **Apache Tomcat** | Container web embedded |
| **Docker** | BasicRobot virtualizzato |
| **WebGL** | Simulazione scena 3D |

## Come eseguire

### Prerequisiti
- Java JDK
- Docker & Docker Compose
- Eclipse IDE (per i progetti QAK)
- Gradle

### 1. Avvia il BasicRobot (Docker)
cd unibo.basicrobot23
docker compose -f basicrobot23.yaml up

### 2. Avvia l'applicazione ColdStorage 
cd Progetto/Sprint3-2/codici/coldStorageService
./gradlew run

### 3. Avvia il sistema allarmi (Led)
cd Progetto/Sprint3-2/codici/allarmi
./gradlew run

### 4. Avvia il simulatore Sonar
./gradlew runSonar

### 5. Avvia il Server Web SpringBoot
cd Progetto/Sprint3-2/codici/spring
./gradlew bootrun

### 6. Accedi all'interfaccia
Apri il browser su http://localhost:8080 per la GUI utente
e su http://localhost:8090 per la scena WebGL.
