---
id: customAuth
title: customAuth app
sidebar_label: customAuth
---

this app handles users, customers and Authentication.

## Sign up workflow 
![](/img/auth_workflow.png)

the app uses the Twilio API to verify the user's phone number. the sign up process start by fillling in the form on the front end and send it to get validated at `/signup/validateForm` once the API respond with OK, the frontend send a phone verfication request to `signup/phoneVerification' that tells the twilio API to initiate a phone verification. once the user receive his code by SMS he can then enters it on the frontend and add it to the final sign up form in the field _code_ . Once the final request with the SMS code reach the API it checks if the code is correct then sends back the token to log user in.



