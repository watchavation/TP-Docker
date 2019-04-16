# Travaux Pratiques : Docker

## Objectifs

L'objectif de ce TP est de créer des conteneurs et d'automatiser la phase de construction et de déploiement des conteneurs dans un contexte Ops. Pour réaliser ce TP, il vous faudra respecter scrupuleusement les conventions de nommage et de configuration demandées, afin que le bot de correction soit en mesure de vérifier que tout fonctionne comme attendu. Cela passe également par le respect des formats de données utilisés, ainsi que la publication et la nomenclature. Il vous sera demandé de construire deux conteneurs communiquant entre eux. Ces deux conteneurs présentent des APIs simple permettant de renvoyer des données au format JSON via le protocole HTTP. Ces deux applicatifs sont fournis et doivent uniquement être déployés, il ne s'agit donc pas de développement mais de mise en production, orienté système et services.

## Les applicatifs

Les applicatifs sont publiés sur un dépôt Github, aux addresses suivantes :

- API Frontend :
- API Backend :

L'API Frontend est un script écrit en python et utilisant le framework Flask. Il présente 3 endpoints qui sont :

 - / (GET) : Cette uri renvoi est censé renvoyer une réponse HTTP au format JSON avec un code 200. Un call est fait sur l'API Backend
 - /healthcheck (GET) : Cette uri renvoi un code HTTP 200. Elle doit être utilisée afin de vérifier le bon fonctionnement de l'applicatif par Docker
 - /traceback (GET) : Cette uri permet de générer une erreur mettant fin au processus en cours d'éxécution dans le container. Cela permet de vérifier, lors de la correction, que l'ID du processus est bien le 1 et que l'applicatif se recharge  automatiquement en cas d'arrêt inopiné.

 L'API Backend est sensiblement similaire à l'API frontend. Elle présente également trois endpoints qui sont :

 - / (GET) : Cette uri renvoi est censé renvoyé une réponse avec un code HTTP 200.
 - /healthcheck (GET) : Cette uri renvoi un code HTTP 200. Elle doit être utilisée afin de vérifier le bon fonctionnement de l'applicatif par Docker
 - /traceback (GET) : Cette uri permet de générer une erreur mettant fin au processus en cours d'éxécution dans le container. Cela permet de vérifier, lors de la correction, que l'ID du processus est bien le 1 et que l'applicatif se recharge  automatiquement en cas d'arrêt inopiné.
