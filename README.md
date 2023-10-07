# TP3_DEVOPS
TP 3 Mise en place pour une application en Python d’une chaine d’intégration continue  permettant de valider l’application  avant de la packager dans une  image de conteneur

## Pré-requis

* Avoir sur sa machine git, docker et docker-compose installé
* Créer un fork dans votre compte github du dépôt : https://github.com/xavnono/TP3_DEVOPS.git 
* Cloner le dépôt : `git clone https://github.com/xavnono/TP3_DEVOPS` 

## Installation de jenkins

* A partir du dossier cloné, se mettre à la racine et lancer la commande :
```
docker-compose up -d --build
```
* Cela permet d'avoir une image de jenkins qui contient Docker (qui nous sera utile pour les actions d'intégration et de déploiement continue) et de lancer un conteneur
* Une fois le conteneur lancé (vérifier qu'il est au statut up), se rendre à l'url : http://localhost:8888 pour accéder à l'interface de Jenkins

## Configurer le jenkins

* La première chose que vous demande Jenkins est le mot de passe pour dévérouiller jenkins
![](https://drive.google.com/uc?id=1jI9hziiVXGWSEHSaTxEuhrxS2QXIvvLA)

* Pour afficher ce mot de passe, effectuer les 2 commandes suivantes puis `copier/coller`
```
docker exec -it  jenkins-custom /bin/bash
```
```
cat /var/jenkins_home/secrets/initialAdminPassword
```

* Ensuite Jenkins vous propose d'installer les plugins suggérés ou de choisir les plugins à installé, laissez l'option par défaut d'installer les plugins suggérés :
![](https://drive.google.com/uc?id=1-SsvUPj8p2s5Zl6Pil2xXGQmSZWV94dU)

* Puis Jenkins vous demande de créer un compte administrateur, remplir le formulaire et cliquer sur  `Save and continue`
![](https://drive.google.com/uc?id1wkO1-XPj0SYHAm3rkttvXEKIFD1W4k4w)
* Votre Jenkins est maintenant prêt à être utilisé
