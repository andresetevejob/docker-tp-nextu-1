# TP Docker

```
Dans ce tp nous allons créer notre propre image pour un site web

Pré-réquis : 

 - Avoir docker installé
```


## I - Installation de l’environnement

1 - Installer Visual Studio Code

2 - Installer git

3 - Installer l’extension live server de visual studio code


## II - Cloner le site web

Via cette commande : 

- Ouvrir votre terminal
- Tapez la commande suivante :  git clone https://github.com/andresetevejob/docker-tp-nextu-1

## III - Les commandes

1 - Création de votre compte sur docker hub

https://hub.docker.com/

2 - Création du fichier Dockerfile
```
 - Dans le dossier de votre application créer un fichier Dockerfile

 - Ajouter les instructions ci-dessous

FROM ubuntu

RUN apt-get update

RUN apt-get install nginx -y

COPY . /var/www/html/

EXPOSE 80

CMD ["nginx","-g","daemon off;"]

```
3 - Création de votre image avec un tag
```
 Positionnez vous dans le dossier de votre site web contenant le Docker file et exécuter la commande ci-dessous:

   build -t [docker_hub_name]/[nom_application]:[version] .

   * [docker_hub_name] : votre username docker
   * [nom_application]: nom de votre application
   * [version]: version de votre application 

```

4 - Démarrage de votre conteneur
```
  docker run -d -p 8000:80 [docker_hub_name]/[nom_application]:[version]

```

5 - Vérifier que notre conteneur est démarré
```
 docker container ls

```