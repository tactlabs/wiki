/ [Home](index.md) / [NuvoMl](nuvoml.md)


## NuvoML vs MLFlow

#### MLFlow:
- open source python library
- can track any number of models
- Can easily create api link for the models
- Deployment and model version tracking
- app/UI needs to be created by user. Just the API link will be provided by MLFlow
- Server cost/maintanance should be taken care by the user
- No user anayltics

#### NuvoML:
- Free and subscription based service
- Can track limited number of models based on subscription
- No seperate API link
- No Version tracking
- app/UI is created by NuvoML and various themes can be used for deployment
- Server cost/maintainance is taken care by featurepreneur
- No user analytics(as of right now)

#### Future plans/ ideas:
- Automatic theme converter - get the html/css/javascript from frontend developer and convert it to our required format
- User analytics(prediction parameters given by end-user, ip of end-users)
- seperate API link for postman/curl
- deployment version tracking and changing version on the fly (v1 to v2 with just the click of a button)
    
- (Maybe) python library for local model tracking(can track any number of models in the local) with UI similar to MLFlow and integration with NuvoML (deploy/change version, etc. on the local UI itself)

    * featureprenuer login creds should be specified to deploy, otherwise can be just used for model tracking.
    * Can track several models in the local. When they need to deploy it, just a click in local will deploy in NuvoML and give the deployment link
    * Can switch the current production model in the local UI itself.

