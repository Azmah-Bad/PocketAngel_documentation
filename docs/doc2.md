---
id: doc2
title: Backend
sidebar_label: Introduction
---

## Introduction
The backend purpose is to query the database for data and provide a `REST API` for the frontend. It is coded in Python and we used Django as the backend framework.

## Installation
to run the project you will need Python3.8 installed, or a later version.
then run the following command to install the dependencies.
```
$ pip3 install -r requirements.txt
```

then to run the server 
```
$ python manage.py runserver
```

## Constants.py
All the project constants are in this centralized in `PocketAngel_backend/constants.py`
here is the default file
```python
NEW_USER_SCORE = 0  # user score when creating an account
SCORE_PER_SIGNALIZATION = 5  # score that the user will win when signaling a danger
SCORE_PER_VOTE = 1  # score that the user will win when voting on signalization
VOTES_TO_DISMISS = -6  # number of votes to automatically delete signalization
SIGNALIZATION_LIFESPAN = 6  # hours before the signalization no longer shows on the map
RESOLUTION = 20  # in Km raduis of a circle around the user where we will send him signalization
```
## Apps
in a Django a single application can host multiple apps. Pocket Angel's backend has multiple apps each provides a feature for of the app.

- [signalisation]()
- [customAuth]() 
- [feedback]()


