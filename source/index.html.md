---
title: Runit API documentation

language_tabs:
  - shell
  - ruby

toc_footers:
  - <a>Si vous avez des questions,</a>
  - <a>Veuillez contacter les administrateurs.</a>
  - <a>Powered by Runit</a>

search: true
---

# Introduction

Bienvenue dans la documentation d'API du projet Runit. Vous allez retrouver dans ce document tous les modèles du projet Runit ainsi tous les informations nécessaires pour chaque fonctionnalité de l'API.


# Authentification

## Connexion

>le json de la requête doit ressembler à l'exemple suivant:

```json
[
  {
    "email": "toto@gmail.com",
    "password": "totoliketoto",
  }
]
```

### HTTP Request
`POST http://www.runit.com/api/v1/users/sign_in`


# User


## Modèle

<aside class="success">
Le système d'utilisateur se base sur le Gem Device, pour tous les paramètres qui ne sont pas mentionnés ci-dessous, veuillez référer à la documentation du Gem Device ou regarder directement dans le projet.
</aside>

Paramètre | Type | Défaut | Nullable | Unique | Déscription
--------- | ---- | ----------------- | -------- | ------ | -----------
email | string | "" | false | true |
firstname | string | "" | false | false |
lastname | string | "" | false | false |
password | string | "" | false | false | le mot de passe doit avoir au moins 8 caractères.
phone | string | "" | true | true |
address | string | "" | true | false |
enable | boolean | false | false |  |

## Création

### Requête HTTP

`POST http://runit.com/api/v1/users`

### Type du data

`JSON`

```shell

  >> rails c
  >> User.create('email':'toto@gmail.com', 'firstname':'jean', 'lastname': 'pierre', password:"totoliketoto")

```


```ruby

#le json de la requête doit ressembler à l'exemple suivant:

[
  {
    "email": "toto@gmail.com",
    "firstname": "jean",
    "lastname": "pierre",
    "password": "totoliketoto",
    "phone": "0601010101" (optionnel),
    "address": "chez toto" (optionnel),
  }
]
```

### Les paramètres de la requête

Paramètre | Défaut | Déscription
--------- | ------- | -----------
email | "" |
firstname | "" |
lastname | "" |
password | "" | le mot de passe doit avoir au moins 8 caractères.
phone | "" | Ce paramètre n'est pas nécessaire
address | "" | Ce paramètre n'est pas nécessaire

## Modification

```ruby
#le json de la requête doit ressembler à l'exemple suivant:

[
  {
    "firstname": "jean"(optionnel),
    "lastname": "pierre"(optionnel),
    "password": "totoliketoto"(optionnel),
    "phone": "0601010101" (optionnel),
    "address": "chez toto" (optionnel),
  }
]
```

```shell
  >> rails c
  >> user1 = User.find(user.id)
  >> user1.update_attributes('firstname':'billy')
```

### HTTP Request

`PUT http://www.runit.com/api/v1/users`

### Les paramètres qui sont modifiables

Paramètre | Défaut | Déscription
--------- | ------- | -----------
firstname | "" |
lastname | "" |
password | "" | le mot de passe doit avoir au moins 8 caractères.
phone | "" | Ce paramètre n'est pas nécessaire
address | "" | Ce paramètre n'est pas nécessaire

## Confirmation

### HTTP Request
`GET http://www.runit.com/api/v1/users/confirmation?confirmation_token=SqZ84MHykSPMvLdR1nDY`

<aside class="warning">
Vous devez remplacer le confirmation_token par le token fourni dans le mail de confirmation.
</aside>


# Run

## Création

# Friends

## Création
