#Utiliser 'Composer' sur un MAC avec MAMP

'Composer' est un outil de gestion des dépendances - développé en PHP.

'Composer' permet de déclarer les différentes bibiothèques liées à un projet.

'Composer' va installer et mettre à jour les différentes bibliothèques liées au projet (les dépendances)

MAMP est un environnement de développement / Serveur local sur MAC

##Introduction
- Environnement de développement : MAMP
- Version PHP pour ce tutorial : 5.6.10
- 'Commposer' est installé globalement sur le MAC
- 'Composer' pourra être utilisé depuis n'importe quel projet (dossier) situé dans le dossier MAMP/htdocs

##Comment installer 'Composer'
- Lancer le terminal (Console de saisie)
- à l'aide de nano, à la racine de votre dossier user, créer un fichier .bash_alias
- pour cela, saisir dans le terminal -> nano ~/.bash_alias
- ensuite, dans le fichier nano créer un alias vers la version mamp de php - ici la 5.6.10
- pour cela saisir -> alias phpmamp='/Applications/MAMP/bin/php/php5.6.10/bin/php'
- enregistrer le fichier (ctrl O puis return)
- fermer nano (ctrl X)
- télécharger composer.phar
- pour cela saisir dans le terminal : curl -sS https://getcomposer.org/installer | phpmamp
- la commande ci-dessus utilise la version php de mamp grâce à phpmamp - utilisation de l'alias
- le fichier doit être normalement téléchargé dans /Users/votre_nom_user/
- le message suivant doit apparaitre :

    `All settings correct for using Composer`
    
    `Downloading...`
    
    `Composer successfully installed to: /Users/nom_de_user/composer.phar`

    `Use it: php composer.phar`

- pour utiliser 'Composer' globalement sur l'ensemble de votre ordinateur, il faut le déplacer dans le dossier /usr/local/bin/composer
- créer et déplacer le fichier dans le dossier
- pour cela, saisir dans le terminal -> sudo mv composer.phar /usr/local/bin/composer
- le terminal demande votre mot de passe
- saisir votre mot de passe
- le dossier est automatiquement crée, le fichier est déplacé et près à être utilisé
- pour tester l'installation, saisir dans le terminal -> composer
- la version et les commandes disponibles doivent apparaitre
- l'installation a réussi

##Rappel des commandes pour l'installation :
nano ~/.bash_alias

alias phpmamp='/Applications/MAMP/bin/php/php5.6.10/bin/php'


curl -sS https://getcomposer.org/installer | phpmamp

sudo mv composer.phar /usr/local/bin/composer

mot de passe

composer

##Comment utiliser 'Composer'
