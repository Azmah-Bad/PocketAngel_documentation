---
id: signalisation
title: signalization app
sidebar_label: signalization
---

first of all `signalization` isn't a typo but written in French.
This app is registered in the admin dashboard.

## model
this app has a single model : `Signalisation`

this model has the following fields :

- type : which indicates the type of the signalization, however it can only be one of code words of the preset signalisation types.
```python
    SIGNALISATION_TYPE = (
        ('AG', 'Aggression'),
        ('HA', 'Harcellement de rue '),
        ('ID', 'Individus dangereux'),
        ('MA', 'Manifestation en cours'),
        ('ES', 'Escroquerie'),
        ('VO', 'Vol'),
        ('DE', 'Degradation'),
        ('NS', 'Nuisance sonores'),
        ('AU', 'Autres'),
    )
```
in the left there are the code words for the signalisation on the right there meaning. note that the code words are the one stored in the database.

- time: time of signalisation and is auto set at it's creation
- longitude and latitude: coordinates of the signalisation
- vote: Int indicating the number of votes a signalisation have, if enough people down votes the signalization it can have a negative score, since down vote decrement this value by 1. Please use the vote methode to change this value.

### methods
```python
def vote(self, isPositive=False) --> None:
```
the vote methode increment the votes a signalization has, if isPositive is set to True it decrements it. 
After computing the vote, if it reaches `- SIGNALIZATION_LIFESPAN` which is the number of down votes to dismiss the signalization, it gets deleted
