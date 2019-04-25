# Travaux Pratiques : Docker

## Objectifs

L'objectif de ce TP est de créer des conteneurs et d'automatiser la phase de construction et de déploiement des conteneurs dans un contexte Ops. Pour réaliser ce TP, il vous faudra respecter scrupuleusement les conventions de nommage et de configuration demandées, afin que le bot de correction soit en mesure de vérifier que tout fonctionne comme attendu. Cela passe également par le respect des formats de données utilisés. Il vous sera demandé de construire deux conteneurs communiquant entre eux. Ces deux conteneurs présentent des APIs simple permettant de renvoyer des données au format JSON via le protocole HTTP. Ces deux applicatifs sont fournis et doivent uniquement être déployés, il ne s'agit donc pas de développement mais de mise en production, orienté système et services.

## Les applicatifs

Les applicatifs sont publiés sur un dépôt Github, dans les sous dossiers de ce dépôts :

- API Frontend : api-frontend
- API Backend : api-backend

L'API Frontend est un script écrit en python et utilisant le framework Flask. Elle présente 2 endpoints qui sont :

 - / (GET) : Cette uri est censé renvoyer une réponse HTTP au format JSON avec un code 200. Un call est fait sur l'API Backend qui renvoi une réponse au format JSON.

 - /traceback (GET) : Cette uri permet de générer une erreur mettant fin au processus en cours d'éxécution dans le container. Cela permet de vérifier, lors de la correction, que l'ID du processus est bien le 1 et que l'applicatif se recharge  automatiquement en cas d'arrêt inopiné.


 L'API Backend est sensiblement similaire à l'API frontend. Elle présente 2 endpoints qui sont :

 - / (GET) : Cette uri renvoi est censé renvoyé une réponse avec un code HTTP 200.

 - /traceback (GET) : Cette uri permet de générer une erreur mettant fin au processus en cours d'éxécution dans le container. Cela permet de vérifier, lors de la correction, que l'ID du processus est bien le 1 et que l'applicatif se recharge  automatiquement en cas d'arrêt inopiné.

Chaque applicatif propose un fichier README.md indiquant les pré-requis de fonctionnement du programme (langage utilisé, version de langage et bibliothèques nécessaires).

## Rendu

Vous devrez faire un fork du dépôt Github afin de récupérer les deux applicatifs et de pouvoir envoyer vos modifications sur votre dépôt.
Vous devrez mettre à disposition deux `Dockerfile` (un par applicatif) ainsi qu'un fichier `docker-compose.yaml` pour le déploiement automatique des deux applicatifs. Vous devriez avoir une arborescence telle que :

```
.
├── LICENSE
├── README.md
├── api-backend
│   ├── Dockerfile
│   └── api.py
│   └── Readme.md
├── api-frontend
│   ├── Dockerfile
│   └── api.py
│   └── Readme.md
└── docker-compose.yaml
```

Vous devrez également publier vos images sur un compte Dockerhub que vous aurez préalablement crée. La version fonctionnelle doit être taggué en `latest`. L'adresse des images sur le Dockerhub devra figurer dans un champs `LABEL` de chaque Dockerfile, ayant pour valeur `hub_url`.

Voici comment devrait se lancer les deux applicatifs après avoir rempli votre fichier `docker-compose.yaml` :

[![asciicast](https://asciinema.org/a/mzbhERZTHnBuf6lEZJ9iMNGEH.svg)](https://asciinema.org/a/mzbhERZTHnBuf6lEZJ9iMNGEH)
