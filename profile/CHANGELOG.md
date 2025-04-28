# Changelog v0.2518.0

## ✨ New Features

### Data

*   **Improved Point of Interest (POI) Data:** Simplified POI identifiers and added more comprehensive information about POIs in various datasets, including campaign statistics, trading areas, and SMS data. This makes it easier to analyze and target specific locations.
*   **Enhanced Trading Area Analysis:** Added new views and functions to better analyze trading areas, including municipality and iris data, along with key organizational information.

### Backend & Infrastructure

*   **Multi-POI Functionality:** Implemented several features to support multi-POI campaigns and reporting, including new API endpoints, data export options, and validation processes.
*   **Improved API and Reporting:** Enhanced campaign reporting with paginated data and dedicated endpoints for POIs.
*   **Modernized Technology Stack:** Upgraded to Go 1.24.2 and enabled HTTP/2 for improved performance.
*   **Media Planning improvements:** Added poi filters

### Frontend

*   **Media Planning Enhancements:** Improved media planning capabilities with POI count for tags, POI network visualization, and the ability to export maximum potential reach.
*   **Reporting Improvements:** Added support for multi-POI reporting.
*   **Data Editor Activation:** The data editor is now live in the production environment.
*   **Core UI Improvements:** Added a splash screen and maintenance mode.
*   **Campaign Management:** Added support for multi-store campaigns.

## 🐛 Bug Fixes

### Data

*   **Blacklist Fix:** Corrected an issue with mobile phone blacklists.
*   **Data Accuracy:** Fixed issues with data collection and trading area calculations.

### Backend & Infrastructure

*   **Technical Fixes:** Addressed issues related to configuration, data accuracy, and template rendering.

### Frontend

*   **UI Fixes:** Resolved various UI issues, including scaling problems, button functionality, and layout issues in media planning and reporting.


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

## ✨ New Features

### Frontend
*   **Media Planning**:
    *   Added an audience segment `withChildren`. (`533`)
    *   Added the `incomeGroups` property. (`532`)
*   **SMS Content**: Sanitized content to remove GMS7 incompatible characters. (`530`)
*   **Data Editor**:
    *   Added a button to reset columns. (`496`)
    *   Added the choice of trading area type. (`493`)
*   **UI**: Added a basic dialog component. (`511`)
*   **Clipboard**: Added feedback when the user disables copy/paste permission. (`423`)
*   **Dashboard**: Added a directive to click on a row of an `ag-Grid` table. (`502`)

### Backend
*   **Firestore**:
    *   Added an option to overwrite Firestore collections.
    *   Added the `CollectionGroup` method for the Firestore client. (`#137`)
    *   Added a mechanism to override the `config` collection. (`#139`)
*   **Geodata**: Migration to `geo_json_v2` for resource management.
*   **Trading Areas**:
    *   Support for chunked uploads (`chunk upload`).
    *   Added `get page` and `get all` endpoints.
    *   Added the `trading_area` schema with improved validation (`allOf`, `oneOf`).
    *   Improved schema dependencies (`schema dependencies`).
*   **User Profiles**:
    *   Added the properties `houses`, `apartments`, `owners`, `leasers`, `withChildren` and `incomeGroups`.
    *   Added new property filters: `houses`, `apartments`, `owners`, `leasers`, `with_children`, `income_group`. (`#136`)
*   **Data Export**: Added a new `data-exports` endpoint.
*   **Datafield**: Added the `trading_area` schema and improved validation (`allOf`, `oneOf`). (`#51bee5c`)
*   **Dataloader & SFTPGo**: Added new clients for `dataloader` and `sftpgo`. (`#121`)

## 🐛 Bug Fixes

### Frontend
*   **Data Editor**:
    *   Adjusted calls to the JSON schema. (`516`)
    *   Fixed the `checkbox select` event to prevent propagation. (`505`)
    *   Modified labels for mapping and list display. (`499`)
*   **Account Management**: Fixed redirection with default query parameters. (`434`)
*   **Circular Dependencies**: Fixed imports to avoid circular dependency errors.
*   **Geocoding**: Revised subscriptions and improved performance. (`513`)

### Backend
*   **OpenAPI**: Fixed trading area paths.
*   **Data Validation**: Fixed errors related to dependencies (`dependentRequired`).
*   **POI**: Fixed the `partitionID` field.
*   **Miscellaneous**: Fixed typos and improved schema validation.
*   **Gomod**: Fixed Go Modules dependencies. (`#0d0b7d8`)
