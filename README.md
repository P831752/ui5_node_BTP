### How to Run
npm install
ui5 serve

### 01_localjson_databinding
local data.json file
controller binding in init method with JSON
Data binding in View (List & StandardListItem)
Introduced Component.js file

### 02_remotesource_approuter
Remote Data Source instead of local Data
Define Data Source & Model in Manifest file
Define Manifest ref in Component JS file
Update databinding in View based on Manifest models.
If you aviod CROS error for accessing External API (here youtube API) introdue App Router (xs-app.json)

### App Router
Entry poing of App
Handles External API/Source requests
Define Routes with Source (point to destination-Define in Manifest)
Setup proxy for all other requests
Define UI5 middleware as Destination
- run 'npm install ui5-middleware-cfdestination'
- Mocks CF destination locally
- add UI5 section in package.json define middleware as dependency
- ui5.yaml, configure custom middleware point to xs-app.json & destination

### Deploy to BTP Cloud Foundry
create package.json file in approuter folder
Approuter, node JS base application to run on CloudFoundry
create destination.json file with BTP subaccount this information should be pushed to BTP CF after deploy
Define build script in main package.json file (mbt build) & run 'npm install -g mbt'
create 'mta.yaml', deployment target of Multitarget application
. Define Modules like approuter, ui5 
. Define resources 

npm run build, creates mta_archives file
cf login to CF
cf deploy mta_archives/ui5_approuter_1.0.0.mtar

### 03_Authorization_BTP
Not working as expected






