---
id: doc3
title: Introduction 
---

## Technologies 

the Pocket Angel was made with Angular and Ionic to create a cross platform PWA. it uses the Twilio API to verify the phone numbers. And uses Leaflet to display the Map. 


## Configuration 

the app was designed with the ability of being highly configurable. you can find all the configurable parameters in `/config.json`. you can configure the backend URLs and some other constants parameters.

## Organisation 

### Interfaces 

in the `/interfaces` directory, you can find the interfaces used by the app, that represent the data structure of:
- user 
- customer 
- signalization

### Services 
services are where the logic happened, it logs user in sign them up, fetch data from API and post comments.

### Pages 
each page represent ... a page in the app, since they are pretty simple component and don't need to be broke down into seperate component. 
except map popup that is component and get injected with the signalisation info once fetched.





