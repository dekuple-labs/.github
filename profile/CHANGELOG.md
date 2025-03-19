# Changelog v0.2512.2  

## 📊 Nouvelles fonctionnalités  

### Frontend  
- **Data Editor** :  
  - Activation du support des zones de chalandise en production. (`9cc622ea`)  
  - Ajout du support des zones de chalandise :  
    - Flux d'importation  
    - Visualisation des zones  
    - Détails des POI (`cc2c7da2`)  
- **Bibliothèques externes** :  
  - Remplacement de `ngx-max-timepicker` par `@dmc/ngx-mat-timepicker`.  
  - Ajout d'une gestion améliorée des dépendances et correction des styles. (`a1d8d091`)  
- **Import de données** : Mise à jour de l'URL pour les imports batch. (`b83c8b5c`)  

### Backend  
- **Recherche dans les ressources** :  
  - Ajout automatique de wildcard dans les requêtes de recherche. (`05452ac`)  
  - Simplification de la recherche `bleve`, en utilisant l'analyseur `simple` et une requête `query string`. (`5959496`)  
- **Profils utilisateurs** : Ajout de l'ID dans le filtre de comptage des coordonnées. (`077990e`)  

## 🛠 Corrections de bugs  

### Frontend  
- **Partage** : Affichage des `incomeGroups` même lorsque `housings` est manquant. (`f4de2787`)  
- **Vue partagée** : Extraction correcte des valeurs des objets. (`5ea111a4`)  

### Backend  
- **Profils utilisateurs** : Suppression des valeurs des labels `incomeGroup`. (`9d10528`)  

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