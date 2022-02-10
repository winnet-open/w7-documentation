# GRANTS

| CODICE (NOME)                                                | APPSHELL                                                     | W7-MICROSERVICE-API                                          |
| :----------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **GIS_VIEW** (MODULO GIS - visualizza)                       |                                                              | **login**, GET/QUERY: retrieve alert, alertzone, snapshot, collection, profile, GETDATI, stationiInfo, stationMemo, alarm-limit, history rain, battery Level, alarm-limit STSCONF, GET/**<u>DELETE</u>** user |
| **GIS_ADMIN** (Modulo GIS - admin)                           |                                                              | INSERT allerte                                               |
| **GIS_OPERATOR** (Modulo GIS - operator)                     |                                                              | INSERT/DELETE: graphProfiles, layers, profile, alarm-limit   |
| **GRAPH_VIEW** (Modulo Grafici - visualizza)                 |                                                              | **login**, GET/QUERY: retrieve alert, alertzone, camera, img, collection, profile, GETDATI, stationiInfo, stationMemo, alarm-limit, battery Level, alarm-limit STSCONF, GET/**<u>DELETE</u>** user |
| **GRAPH_OPERATOR** (Modulo Grafici - operatore)              |                                                              | EDIT scale_graph                                             |
| **GRAPH_ADMIN** (Modulo Grafici - admin)                     |                                                              | EDIT scale_graph                                             |
| **SCADA_ADMIN** (Modulo Scada - admin)                       | modulo scada                                                 |                                                              |
| **SCADA_VIEW** (Modulo Scada - view)                         | modulo scada                                                 |                                                              |
| **SCADA_OPERATOR** (Modulo Scada - operator)                 | modulo scada                                                 |                                                              |
| **CAMERA_VIEW** (Modulo Camera - view)                       | modulo csm                                                   | GET camera list                                              |
| **CAMERA_ADMIN** (Modulo Camera - admin)                     | modulo csm                                                   | EDIT camera list                                             |
| **CAMERA_OPERATOR** (Modulo Camera - operator)               | modulo csm                                                   | EDIT camera list                                             |
| **ALERT_VIEW** (Modulo Alert - view)                         | modulo alertOpertaion                                        |                                                              |
| **ADMIN** (admin)                                            | modulo ADMIN e ricarica references                           | GET/INSERT user                                              |
| **RIEPILOGHI_VIEW** (Modulo RIEPILOGHI - visualizza)         | modulo riepiloghi                                            |                                                              |
| **RIEPILOGHI_ADMIN** (Modulo RIEPILOGHI - admin)             | modulo riepiloghi                                            |                                                              |
| **RIEPILOGHI_OPERATOR** (Modulo RIEPILOGHI - operator)       | modulo riepiloghi                                            |                                                              |
| **ANNALI_ACCESS** (Accesso modulo Annali)                    |                                                              |                                                              |
| **ANNALI_PRINT_MANAGE** (Stampe modulo Annali)               |                                                              |                                                              |
| **VALIDATION_VIEW** (Modulo validazione)                     | modulo validazioni                                           |                                                              |
| **MODE3D_VIEW** (Modulo 3d - visualizza)                     | GIS mode 3D                                                  |                                                              |
| **PLANT_OPERATOR** (Operatore pagina impianto)               | modulo stazioni ( DELETE/INSERT photo) - EDIT info station -monografia - VIEW input status - IP | EDIT station-info                                            |
| **PLANT_VIEW** (Visualizza pagina impianto)                  | modulo Stazioni Generali                                     | **login**, GET station-info, alarm-limit                     |
| **PLANT_ADMIN** (Admin pagina impianto)                      | modulo Stazioni Avanzate                                     | INSERTconfiguration                                          |
| **SUPER_ADMIN** (super admin)                                | lista user grants                                            | GET/ INSERT user **<u>but not delete</u>**                   |
| **ALARMS_VIEW** (Modulo Alarms - view)                       | modulo allarmi, icone allarmi raggruppati, timeslider        | GET alarms                                                   |
| **ALARMS_OPERATOR** (Modulo Alarms - operator)               | soglie alarm hydro, soglie alarm intensive, tacitare allarmi, **<u>NO MODULO ALLARMI</u>** | INSERT/DELETE silence-alarm, alarm-limit                     |
| **ALARMS_ADMIN** (Modulo Alarms - admin)                     | modifica soglie allarmi GIS, visualizza differenze allarmi stazioni con soglie allarmi | INSERT/DELETE silence-alarm, alarm-limit                     |
| **DAS_ADMIN** (Modulo DAS - admin)                           | modulo das                                                   |                                                              |
| **DAS_VIEW** (Modulo DAS - view)                             | modulo das                                                   |                                                              |
| **ISOLINE_ADMIN** (Modulo isoline - admin)                   | tematismo isoline                                            |                                                              |
| **ISOLINE_VIEW** (Modulo isoline - view)                     | mostra button isoline sidebar                                |                                                              |
| **ISOLINE_OPERATOR** (Modulo isoline - operator)             | tematismo isoline                                            |                                                              |
| **KPI_VIEW** (Modulo KPI - view)                             | modulo RMO pagina KPI                                        |                                                              |
| **KPI_ADMIN** (Modulo KPI - admin)                           |                                                              |                                                              |
| **RMO_VIEW** (Modulo RMO - view)                             | Modulo RMO                                                   |                                                              |
| **RMO_ADMIN** (Modulo RMO - admin)                           | Sensor Card - Link a Validazioni                             |                                                              |
| **RMO_OPERATOR** (Modulo RMO - operator)                     | modulo RMO pagina errori                                     |                                                              |
| **FER_OPERATOR** (Modulo FER)                                | modulo fer                                                   |                                                              |
| **ALERT_ADMIN** (Alert - admin)                              | modulo alertOperation                                        |                                                              |
| **ALERT_SUPERADMIN** (Alert - superadmin)                    | modulo alertOperation                                        |                                                              |
| **ALARMS_SOUND** (Modulo alarms - sirena)                    | audio allarme gis                                            |                                                              |
| **STATION_GET_DATI** (Permesso Station Get-Dati)             | bottone getDati GIS e Stazioni                               |                                                              |
| **DATAEXCHANGE_ADMIN** (Permesso Modulo DataExchange Admin)  | modulo dataExchange                                          | ricarica procedure                                           |
| **DATAEXCHANGE_VIEW** (Permesso Modulo DataExchange View)    | modulo dataExchange                                          | vede logs **<u>configurazione può far tutto</u>**            |
| **DATAEXCHANGE_OPERATOR** (Permesso Modulo DataExchange Operator) |                                                              |                                                              |
| **AREALRAIN_VIEW** (Modulo Piogge areali - View)             | modulo piogge areali                                         | GET arealrain                                                |
| **AREALRAIN_ADMIN** (Modulo Piogge areali - Admin)           | modulo piogge areali                                         | INSERT Param, update/delete insert soglie,basin              |
| **CONFIGURATION_VIEW** (Modulo Configuration - view)         | modulo configurazione                                        | view tables <u>**(station.query è solo gis view, graph view)**</u> |
| **CONFIGURATION_OPERATOR** (Modulo Configuration - operator) | import csv, EDIT table                                       | EDIT table, load storic data csv                             |
| **CONFIGURATION_ADMIN** (Modulo Configuration - admin)       | modulo configurazioni pagna LOGS                             | EDIT table, load storic data csv                             |
| **STATION_MEMO_VIEW** (Modulo Eventi - view)                 | Stazioni pagina eventi, Grafici simbolo eventi               | GET event                                                    |
| **STATION_MEMO_OPERATOR** (Modulo Eventi - operator)         | EDIT eventi                                                  | EDIT event                                                   |
| **GRAFANA_ADMIN** (Modulo Grafana - Admin)                   | vede monitoraggio                                            |                                                              |
| **EXTERNAL_SERVICES_VIEW** (Servizio API esterne - VIEW)     |                                                              | station/list, correnti, history-rain, alarm-limit            |
| **MIDES_ADMIN** (Modulo Mides - Admin)                       | vede config mides                                            | stoppa,avvia e cambia sensori                                |
| **MIDES_VIEW** (Modulo Mides - View)                         | vede modulo mides                                            | vede lista dati                                              |
| **EXTERNAL_SERVICES_EXPORT** (Servizio API esterne - EXPORT) |                                                              | station-list, get data by time range                         |
| **SNAPSHOTS_GRAPH_VIEW** (Permesso Snapshots Grafici - View) | foto nei grafici                                             |                                                              |
| **PLANT_INTERVENTION** (Visualizzazione Interventi Stazione) | Stazioni e interventi                                        | **login**                                                    |
| **LIMIT_DATABASE** (Visualizzazione solo dati grezzi)        | mostra solo dataSet Grezzi e filtra anche le stazioni da mostrare |                                                              |