---
id: API
title: API
sidebar_label: API
---


## Auth

### sign up 
url: `/signup`
---
`POST`
```json
{
    "user" : {
        "first_name" : "Alfred",
        "last_name" : "Stan",
        "username" : "Alf",
        "email" : "alfred@stan.com",
        "password" : "reallyHardPassword1"
    },
    "phone" : "+41524204242",
    "age" : 18,
    "code": "TWILIO CODE RECEIVED BY SMS"
}
```
to create a new user, send a POST request like the example shown above. `NOTE THAT THE PHONE NUMBER MUST BE VALIDATED BY THE TWILIO API BY USING THE /phoneVerification ROUTE`

### verify phone with the twilio API
url: `/signup/phoneVerification`
---
`POST`
```json
{
  "To": "PHONE NUMBER IN INTERNTIONAL FORMAT"
}
```
to verify a phone number using twilio use this route to initiate phone verification. the user will then receive an SMS with the a code

### validate form
url: `/signup/validateForm`
---
`POST`
```json
{
    "user" : {
        "first_name" : "Alfred",
        "last_name" : "Stan",
        "username" : "Alf",
        "email" : "alfred@stan.com",
        "password" : "reallyHardPassword1"
    },
    "phone" : "+41524204242",
    "age" : 18
}
```
in order to not submit to the twilio API a phone verification request if the form is not valid, you can use this endpoint to check if the form is valid before checking if the phone number is valid. this cuts the uses of unnecessary twilio phone verifications 



## Signalization
url: `/signalization`
---
`GET` 
Query parameters: 
- `lat` : latitude as float 
- `lon` : longitude as a float
returns a list of signalization within `RESOLUTION` Km.
  
`POST`
body 
```json
{
  "type": SIGNALISATION CODE,
  longitude" : 10,
  "latitude" : 10
}
```
to add new signalisation to the database use the POST http request. Note that the user must be logged in to be able to dod this. 
The type field should be a the 2 letters in all caps of the signalisation code like 'VO' for 'Vol'
  
`PUT`
body
```json
{
  "pk": number,
  "isPositive" : boolean
}
```
to vote on signalisation send a PUT request with the primary key of the signalisation and indicate if the vote is positive in the `isPostive` field. 


## Feedback
url: `/feedback`
---
`POST`
```json
{
  "comment": string,
}
```
to add a new feedback send a post request with the the feedback in the field `comment` like shown above. the API identify the user and display it in the admin interface.




