# Changelog v0.2512.2  

## ✨ New Features

### Data
*   **New Geo JSON Data Source:** Added a new geo JSON data source with arrondissements.
*   **Enhanced Profile Enrichment:** Added a category for CSP (socio-professional category) dimension to enriched profiles, including income group and housing properties.
*   **With Children Targeting Criteria:** Added a `with_children` dimension to aggregated profiles.
*   **Potentials Global Iris Details:** Added `with_iris` and `is_geocoding_approximated` fields to `potentials_global`.
*   **Incremental Load Modes in Data Loader:** The data loader now supports overwrite, append, and incremental modes.
*   **Email Notifications for Data Exporter:** The data exporter now sends email notifications.
*   **Custom Schema for Firestore Sync:**  Implemented the ability to use custom schemas for syncing specific collections in Firestore.

### Frontend
*   **Trading Area in Data Editor:** Enabled the trading area feature in the data editor for production, including trading area visualization and POI details.
*   **Timepicker Component:** Replaced `dhutaryan/ngx-max-timepicker` with `@dmc/ngx-mat-timepicker` for time input.
*   **Batch Import URL Update:** Updated the batch import URL in the data editor.
*   **Auto Append Wildcard in Search Query:** Implemented automatic appending of wildcards in search queries.

## 🐛 Bug Corrections

### Infra
*   **Bleve Index with Simple Analyzer:** Fixed the backend to use a bleve index built with a simple analyzer.
*   **BigQuery Permissions:** Corrected the service account used for BigQuery permissions.
*   **Cons Exports Authorized Datasets:** Fixed the authorized datasets for consumer exports.

### Data
*   **Geometry Removal from Prioritized Profiles:** Removed geometry from prioritized profiles and fixed the city type filter.
*   **Join Key Issue:** Fixed an issue where the `col_type` was being removed from the join key, causing incorrect join conditions. Also, improved filtering on blacklist and removed unnecessary columns from selects.

### Frontend
*   **Income Groups Display:** Fixed an issue in the sharing component where income groups were not displayed when housing data was missing.
*   **Shared View Object Values:** Corrected the extraction of object values in the shared view.

### Backend
*   **Simplified Bleve Search:** Simplified bleve search using a 'simple' analyzer and 'query string' query.
*   **Coordinate Counting Filter:** Added ID to the coordinate counting filter in profiles.
*   **Income Group Labels:** Removed values from income group labels.

### Dev
*   **Collection Name Extraction:** Fixed the regular expression to include digits when extracting the collection name from the path in `dmc-firestore-event-pipe`.
*   **Cloud Build Issue:** Fixed a cloud build issue in `dmc-firestore-event-pipe`.
# Changelog v0.2511.0  

## 📊 Nouvelles fonctionnalités  

### Frontend  
- **Media Planning** :  
  - Ajout d'un segment d'audience `withChildren`. (`533`)  
  - Ajout de la propriété `incomeGroups`. (`532`)  
- **SMS Content** : Sanitation du contenu pour supprimer les caractères non compatibles GMS7. (`530`)  
- **Data Editor** :  
  - Ajout d'un bouton pour réinitialiser les colonnes. (`496`)  
  - Ajout du choix du type de zones de chalandise. (`493`)  
- **UI** : Ajout d'un composant de dialogue de base. (`511`)  
- **Clipboard** : Ajout d'un feedback lorsque l'utilisateur désactive la permission de copier/coller. (`423`)  
- **Tableau de bord** : Ajout d'une directive permettant de cliquer sur une ligne de tableau `ag-Grid`. (`502`)  

### Backend  
- **Firestore** :  
  - Ajout d'une option pour surcharger les collections Firestore.  
  - Ajout de la méthode `CollectionGroup` pour le client Firestore. (`#137`)  
  - Ajout d'un mécanisme de surcharge de la collection `config`. (`#139`)  
- **Géodonnées** : Migration vers `geo_json_v2` pour la gestion des ressources.  
- **Zones de chalandise** :  
  - Support de l'upload par morceaux (`chunk upload`).  
  - Ajout des endpoints `get page` et `get all`.  
  - Ajout du schéma `trading_area` avec validation améliorée (`allOf`, `oneOf`).  
  - Amélioration du schéma des dépendances (`schema dependencies`).  
- **Profils utilisateurs** :  
  - Ajout des propriétés `houses`, `apartments`, `owners`, `leasers`, `withChildren` et `incomeGroups`.  
  - Ajout de nouveaux filtres de propriétés : `houses`, `apartments`, `owners`, `leasers`, `with_children`, `income_group`. (`#136`)  
- **Export de données** : Ajout d'un nouvel endpoint `data-exports`.  
- **Datafield** : Ajout du schéma `trading_area` et amélioration de la validation (`allOf`, `oneOf`). (`#51bee5c`)  
- **Dataloader & SFTPGo** : Ajout de nouveaux clients pour `dataloader` et `sftpgo`. (`#121`)  

## 🛠 Corrections de bugs  

### Frontend  
- **Data Editor** :  
  - Ajustement des appels au schéma JSON. (`516`)  
  - Correction de l'événement `checkbox select` pour éviter la propagation. (`505`)  
  - Modification des labels pour le mapping et l'affichage en liste. (`499`)  
- **Gestion des comptes** : Correction de la redirection avec les paramètres de requête par défaut. (`434`)  
- **Dépendances circulaires** : Correction des imports pour éviter les erreurs de dépendances circulaires.  
- **Géocodage** : Révision des abonnements et amélioration des performances. (`513`)  

### Backend  
- **OpenAPI** : Correction des chemins des zones de chalandise.  
- **Validation des données** : Correction des erreurs liées aux dépendances (`dependentRequired`).  
- **POI** : Correction du champ `partitionID`.  
- **Divers** : Corrections de typographies et améliorations de la validation des schémas.  
- **Gomod** : Correction des dépendances Go Modules. (`#0d0b7d8`)  
