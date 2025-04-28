# CHANGELOG v0.2518.0

## ✨ New Features

### Frontend
*   **Media Planning:** You can now see the number of Points of Interest (POI) for each tag in media planning.
*   **Reporting:** Enhanced reporting to support multiple Points of Interest (POI).
*   **Data Editor:** The data editor is now activated for production use.
*   **Core:** A splash screen has been added to the application.
*   **Campaigns:** You can now add multiple stores to campaigns.
*   **Media Planning:** Introduced POI network functionality, including targeted zones, saving counts, a new component, and map cluster markers.
*   **Media Planning:** Added the ability to export the maximum potential reach.
### Backend
*   **POI:** Added an endpoint to retrieve tags with Point of Interest (POI) counts.
*   **POI:** Implemented functionality to retrieve all POI data information for a multi-POI counting version.
*   **Campaign Reporting:** Moved the `/poi` endpoint to `/pois`.
*   **Campaign Reporting:** Added paginated reporting data for campaign POIs, including a single POI endpoint.
*   **Campaigns:** Added multi-POI merge tags validation.
*   **Profiles:** Automatically export `poi_id` when a POI filter is applied.
*   **Profiles:** Implemented multi-POI export (with `poi_id`).
*   **Core:** Implemented maintenance mode API.
*   **Core:** Enabled HTTP/2 support.
*   **Campaigns:** Campaigns are now adapted to support multi-POI functionality, including TestSMS and SeedList.
*   **Media Planning:** Added POI filters.
*   **POI Data:** Moved POI data Data Access Object (DAO) to `dmc-domain`.
*   **Reservations:** Implemented acquisition of multi-POI reservations, including adding `poi_id` to beta tester reservation profiles.
### Data
*   **POI:** Standardized and simplified POI identification by renaming `poi_external_id` fields to `poi_id`.
*   **SMS Reporting:** Added `poi_id` columns for enhanced SMS reporting.
*   **Media Planning:** Introduced a new `trading_area_item` view for media planning purposes, including geographic point data and POI tags.
*   **Campaign Stats:** Added POI column to campaign statistics.
*   Enhanced multi-POI counting capabilities.
*   **Data Layer:** Added sharing project and analytics hub to data layer module.
### Infrastructure
*   **Backend:** Added POI data table configuration.
*   **Backend:** Added POI CSV template.

##  🐛 Bug Fixes

###  Frontend
*   **Reporting:** Fixed scaling issues in the URL view details.
*   **Campaigns:** Resolved issues with the POI list.
*   **Media Planning:** Fixed an issue that disabled the "save version" button while loading.
*   **Media Planning:** Fixed layout issues by adding margin and fixed width.
*   **Media Planning:** Fixed multiple issues.
*   **Media Planning:** Automatically dispatch potential calculations.
*   **Media Planning:** Corrected the upload text.
### Backend
*   **Campaign Reporting:** Fixed the `AccountKPI Stopped` JSON tag.
*   **Profiles:** Added a label for the POI dimension.
*   **Counting:** Fixed the count SQL template.
*   **POI:** Fixed `viper` gomod version.
### Data
*   Correct profiles deletion job to remove profiles collected more then 3 years ago
*   Corrects mobile phone number cleaning by fixing the nohash blacklists
*   Fixed inconsistencies in `collect_date_expired` to include null values.
*   **Trading Areas:** Improved ranking of trading areas by type and distance.
### Infrastructure
*   Fixed auth routines.
*   Fixed missing IAM for FS sync on Console Dataflow.
*   Fixed default null in schema struct.
*   Fixed partition ID field case.
*   Fix terraform changes detection.
### Cleaning
*   Updated the maximum municipalities count to 35074.

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
