# Guida al Raspberry Pi 4 per l'esecuzione di Zebra

![Raspberry pi4](assets/41cDz-BqefL._AC_UF894,1000_QL80_.png)

L'esecuzione del software del nodo Zebra su un Raspberry Pi 4 consente di partecipare alla rete Zcash come nodo indipendente e compatibile con il consenso. Questa guida vi guiderà attraverso i passaggi per configurare ed eseguire Zebra sul vostro Raspberry Pi 4.

## Prerequisiti

1. Raspberry Pi 4 (si consigliano 2 GB di RAM o superiore).

2. Scheda MicroSD (si consiglia 16 GB o superiore) con Raspberry Pi OS (Raspbian) installato.

3. Connessione Internet stabile.

4. Tastiera, mouse e monitor (per la configurazione iniziale).

5. Client SSH (opzionale, per l'accesso remoto).

## Installazione

1. Aggiornare il sistema
   Aprite un terminale o SSH nel vostro Raspberry Pi e assicuratevi che il sistema sia aggiornato eseguendo:

   __sudo apt update__

   __sudo apt upgrade__

2. __Installazione delle dipendenze__
   È necessario installare alcune dipendenze necessarie per costruire ed eseguire Zebra:

   __sudo apt install build-essential cmake git clang libssl-dev pkg-config__

3. __Clonare il repository di Zebra__
   Aprire un terminale e clonare il repository Zebra sul Raspberry Pi:

   __git clone https://github.com/ZcashFoundation/zebra.git__

   __cd zebra__

4. __Costruire Zebra__
   Per compilare Zebra, utilizzare i seguenti comandi:

   __cargo build --release__

   Questo processo potrebbe richiedere un po' di tempo. Assicuratevi che il vostro Raspberry Pi sia adeguatamente raffreddato, poiché la compilazione può generare calore.

5. __Configurazione__
   Creare un file di configurazione per Zebra. È possibile utilizzare la configurazione predefinita come punto di partenza:

   __cp zcash.conf.example zcash.conf__

   Modificare il file zcash.conf per personalizzare le impostazioni del nodo. È possibile specificare la rete, abilitare il mining, impostare le connessioni peer e altro ancora.

6. __Avvio di Zebra__
   Ora è possibile avviare Zebra con la configurazione personalizzata:

   __./target/release/zebrad -c zcash.conf__

   __git comment__ 

   Questo comando avvierà il nodo Zebra, che inizierà a sincronizzarsi con la blockchain Zcash.

7. __Monitoraggio__
   Potete monitorare i progressi e lo stato del vostro nodo Zebra aprendo un browser web e navigando su http://127.0.0.1:8233/status__.

![Zebra logo](assets/daeacb227c9b3a9e448d6e0e61f9641e9b233b80.png)

## Risoluzione dei problemi

Se si riscontrano problemi con la creazione o l'esecuzione di Zebra, consultare la [documentazione Zebra](https://doc.zebra.zfnd.org/docs/intro.html) per suggerimenti sulla risoluzione dei problemi e ulteriori informazioni.

Assicuratevi di mantenere aggiornato il vostro Raspberry Pi, poiché l'esecuzione di un nodo può generare calore. Si consiglia di utilizzare una soluzione di raffreddamento, come una ventola o un dissipatore di calore.

## Conclusione

Seguendo questa guida, dovreste essere riusciti a configurare ed eseguire Zebra sul vostro Raspberry Pi 4. Ora state contribuendo alla creazione del nodo. Ora state contribuendo a mantenere la rete Zcash sicura e distribuita.
