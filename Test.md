# Batch-update-sw-vehicles

### Batch per l'aggiornamento del software dell'OBU

---

###### Il flusso del batch mostrato nell'immagine qui sotto:

![Alt text](BatchUpdate.jpg?raw=true "Sequance Diagram")

###### Datasources del batch:

![Alt text](ORMDiagram1.jpg?raw=true "Orm Diagram")

---

###### Prerequisiti del batch:

1. Installare o Scarica il [SqlServer PowerShell-Module](https://www.powershellgallery.com/packages/SqlServer/21.1.18245) per eseguire tutte le attività del database.
   1. Per installare il modulo manualmente Da Opzioni di installazione Selezionare Download manuale.
   2. [Installare il Module] (https://sqlserverunlimited.com/2019/08/01/powershell-install-sqlserver-module-offline/)
      1. Aprire PowerShell sul server in cui verrà installato il batchAprire PowerShell sul server di destinazion per ottenere la posizione dei percorsi di Psmodule eseguendo il codice seguente:
         `$env:PSModulePath`
      2. copia il modulo scaricato dal passaggio 1, in tutti i percorsi del comando precedente
2. Scarica il [scrcpy](https://github.com/Genymobile/scrcpy#get-the-app) che include adb.exe "per eseguire tutti i comandi necessari relativi al dispositivo".
   1. Per Linux: `apt install scrcpy`.
   2. Per Windows: [download](https://github.com/Genymobile/scrcpy/releases/download/v1.22/scrcpy-win64-v1.22.zip).
   3. Per macOS: `brew install scrcpy`.

---

###### Configurazione del batch:

Configurazione del batch definito nel file [BatchConfig.xml](config/BatchConfig.xml)

Dove definito i seguenti parametri:

1. Logging Config (log folder location, log file name, ecc.).
2. Database Config (db Address, username, password, ecc.).
3. Update Device Config (kit source location, partial update location, final update location, adb.exe location, ecc.).

---

###### Esecuzione del batch:

eseguire il comando seguente:

`PS> batch_update_sw_vehicles.ps1`
