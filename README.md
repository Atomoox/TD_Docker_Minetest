# TP Docker: Compose - Networks - Build - Volume

## Selection des images

|Service         |Image                                            
|----------------|-------------------------------
|Apache|`php:8.2-apache`            |
|MySQL       |`mysql`            
|PhpMyAdmin          |`dpage/pgadmin4`


## Compose file

Le compose file `docker-compose.yaml` contiens tout le processus pour créer les containers avec la commande `docker compose up -d` grace a ce fichier et a quelques un que nous verons plus tard, il est possible de setup tous les containers en quelques secondes.

Nous utilisons la version: 3.8

 **SAE**
 Nous utilisons pour ce container pour faire tourner le serveur web de la SAE.
 Pour ce faire, il a besoin d'un volume pour charger tous les fichiers versionné a l'aide de github vers le dossier root du serveur. Nous réalisons ceci avec 
 
`- ./storage/sae:/var/www/html`

Nous redirigeons ensuite le port de base du serveur vers le port 8185 pour eviter tout conflits avec la machine 'host'

**MYSQL**

Nous avons installé mysql et lui avons donné un storage a /storage/mysql pour sauvegarder les données de la BDD. Nous n'avons pas redirigé le port de base vers un port spécial cette fois ci.

**PhpMyAdmin**

Nous avons installé PhpMyAdmin pour gérer la BDD avec les utilisateur et mots de passe défini par défault. 
Nous avons redirigé le port par défault 80 vers le port 8185 afin que l'on puisse utiliser PhpMyadmin sans se priver du serveur Apache qui sert pour la SAE.

## Storage

Nous avons crée le dossier storage afin d'y stocker les fichiers contenant les données de nos container. Il contient les fichiers de la SAE et les base de données.

### Par Anais ANDRE et Clément TRENS Q5.
