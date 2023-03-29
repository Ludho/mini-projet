# Projet Docker/containerization 

Projet de fin de module Containerization/Cloud

## Membre de l'équipe

* Youssef KHEMIRI
* Yassine EL HIRACH
* Mohamed Amine TRIGUI
* Ludwig HO

## Utilisation

Pré-requis:
Installation de docker

Cloner le projet:
 
    git clone https://github.com/Ludho/mini-projet.git

Se rendre dans le dossier postgresql et construire l'image:

    sudo docker build . -t postgresql
    

 Puis se rendre dans le dossier odoo et construire l'image:
 
    sudo docker build . -t odoo
    
## Les difficultés rencontrées

Problème de connection entre odoo et psql
Difficulté pour deployer avec kubernetes

## Dockerfile odoo


Utilisation debian:buster-slim pour commencer avec une image légère <br>
A partir de l'image nous avons installé les dépendances utiles <br>
Puis généré les clés pour l'utilisation de odoo <br>
Copie du fichier config dans le containeur de odoo<br>
Pour lancer l'application avec les config<br>

 

## Dockerfile psql



Utilisation d'une image à partir d'une image dispobible sur le Docker Hub<br>
Création de l'utilisateur odoo

  
