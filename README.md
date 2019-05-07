# Postgres & pgadmin4 docker per Base Dati 2 
## Introduzione
Le seguenti istruzioni ti permetteranno di istanziare un Docker contenente il DBMS PostgreSQL e  pgadmin4, una interfaccia grafica che consente di amministrare in modo semplificato database di PostgreSQL. Tramite cui è possibile eseguire query tramite il query editor.

## Come iniziare
Queste istruzioni permetteranno di installare Docker, e il container e di creare una shared folder fra l'host e il docker.

### Prerequisiti
1. Una macchina con sistema operativo Linux o MacOS. Attualmente Windows non è supportato.
2. Bisogna avere i permessi di ***root*** e avere disponibile la porta 5000 e 5432.
3. Docker, docker-compose e git installati. Per la procedura di installazione seguire le istruzioni in base al tuo sistema operativo per installarlo  [docker.com](https://www.docker.com/).

### Installazione tramite docker-compose
4. Effettuare un git clone dal repository

5. Eseguire il seguente comando per iniziare il processo di installazione:
```sh
$ docker-compose up -d 
``` 
6. Eseguire l'accesso tramite il browser all'indirizzo localhost:5000
7. Nella dashboard cliccare su 'Add new server'
8. Nella tab 'General' nel campo Name scrivere 'postgres' 
9. Cambiare tab e scegliere 'Connection'
10. Nel campo Host name / address' scrivere 'postgres'
11. Nel campo port se non presente scrivere 5432
12. Nel campo Maintenance database scrivere 'postgres'
13. Nel campo password scrivere 'postgres'

NB: tutti i campi sono da completare senza apici

## Esecuzione dei test

Per controllare che tutto sia andato a buon fine, caricate nel browser la pagina localhost:5000.

## Credenziali

#### Credenziali PGADMIN4:
Per eseguire l'accesso a PGADMIN4 utilizzate le seguenti credenziali:
> id: base@didati2.it
> password: admin
> port: 5000

#### Credenziali PostgreSQL:
Per eseguire tramite linea di comando utilizzate le seguenti credenziali:

> id: postgres
> password: postgres
> port: 5432

## Condividiere file tra il Docker e il File System host
Per condividere file sql, file di configurazione e dump della base di dati è possibile utilizzare la cartella  ./postgresFOLDER 

## Eseguire query tramite pgadmin4
È possibile eseguire query o file sql tramite l'interfaccia grafica di pgadmin4 con l'utilizzo del suo query editor.


## Utilizzare PostgreSQL da linea di comando:
Eseguire il seguente comando per accedere alla shell del container.
```sh
$ docker exec -it postgres_container bash
$ psql -U postgres
``` 

## Nota bene:
Si è liberi di modificare il docker-compose.yml come meglio si preferisce.
Le seguenti cartelle postgresFOLDER e pgadminFOLDER devono essere vuote e presenti durante l'installazione.
## Authors

* **Andrea Bacciu**  [Github profile](https://github.com/andreabac3)
* **Valerio Neri**   [Github profile](https://github.com/selektion)

## Riferimenti
* **Docker:** [docker.com](https://www.docker.com/)
* **PostgreSQL:**  [postgresql.org](https://www.postgresql.org/)
* **pgadmin4:**  [pgadmin.org](https://www.pgadmin.org/)
