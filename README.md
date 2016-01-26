#Utiliser 'Composer' sur un MAC avec MAMP

**Composer** est un outil de gestion des dépendances - développé en PHP.

**Composer** permet de déclarer les différentes bibliothèques liées à un projet (ex : symfony)

**Composer** va installer les différentes bibliothèques liées au projet (les dépendances) et permettre leur mise à jour facilement

**MAMP** est un environnement de développement / Serveur local sur MAC

##Introduction
- Environnement de développement : MAMP
- Version PHP pour ce tutorial : 5.6.10
- **Composer** peut être installé globalement sur le MAC ou bien localement dnas le dossier du projet
- J'ai choisi de l'installer globalement
- **Composer** pourra ainsi être utilisé depuis n'importe quel projet (dossier) situé dans le dossier MAMP/htdocs
- Quelques connaissances sur l'utilisation du terminal sont nécessaires

##Comment installer Composer
- Lancer le terminal (Console de saisie)
- À l'aide de nano, à la racine de votre dossier user, créer un fichier .bash_alias
- pour cela, saisir dans le terminal -> nano ~/.bash_alias (ou tout autre nom : .bash_[nom-quelconque] - attention : .bash_history est déjà utilisé
- nano ouvre le fichier
- créer alors dans le fichier ouvert un alias vers la version (mamp) de php - ici la 5.6.10 (attention : vérifier la version de php utilisée par votre version de MAMP)
- pour cela saisir -> alias phpmamp='/Applications/MAMP/bin/php/php5.6.10/bin/php'
- enregistrer le fichier (ctrl O puis return)
- fermer nano (ctrl X)
- télécharger composer.phar
- pour cela saisir dans le terminal -> curl -sS https://getcomposer.org/installer | phpmamp
- la commande ci-dessus utilise la version php de mamp grâce à phpmamp - utilisation de l'alias
- le fichier doit être normalement téléchargé dans /Users/votre_nom_user/
- le message suivant doit apparaitre :

    `All settings correct for using Composer`
    
    `Downloading...`
    
    `Composer successfully installed to: /Users/nom_de_user/composer.phar`

    `Use it: php composer.phar`

- pour utiliser **Composer** globalement sur l'ensemble de votre ordinateur, il faut le déplacer dans le dossier /usr/local/bin/composer
- créer et déplacer le fichier dans le dossier
- pour cela, saisir dans le terminal -> sudo mv composer.phar /usr/local/bin/composer
- le terminal demande votre mot de passe
- saisir votre mot de passe
- le dossier est automatiquement créé, le fichier est déplacé et prêt à être utilisé
- pour tester l'installation, saisir dans le terminal -> composer
- la version et les commandes disponibles doivent apparaitre
- l'installation a réussi

##Rappel des commandes pour l'installation :
Listing des commandes d'installation de **Composer**

`nano ~/.bash_alias`

`alias phpmamp='/Applications/MAMP/bin/php/php5.6.10/bin/php'`

`curl -sS https://getcomposer.org/installer | phpmamp`

`sudo mv composer.phar /usr/local/bin/composer`

`mot de passe`

`composer`

##Comment utiliser Composer - installer une dépendance
Utilisation de l'exemple officiel du site http://composer.org
- dans le terminal se rendre dans le dossier htdocs
- pour cela, saisir -> cd /Applications/MAMP/htdocs (Ici MAMP est insatallé dans le dossier Applications - Installation classique)
- créer un dossier
- pour cela, saisir dans le terminal -> mkdir [nom_du_repertoire]
- dans le dossier, créer un fichier **composer.json** (avec nano ou tout autre editeur)
- avec nano, dans le terminal, saisir -> nano composer.json
- nano s'ouvre
- dans le fichier composer.json, saisir les lignes basiques suivantes - les dépendances du projet, exemple ici monolog :

```
{
    "require": {
        "monolog/monolog": "1.0.*"
    }
}
```

- d'autres renseignements peuvent être saisis, ceux ci-dessus sont le strict minimum (à savoir, nom et version du package)
- lancer l'installation des dépendances
- pour cela, dans le dossier contenant le fichier composer.json, dasn le terminal, saisir -> composer install
- le message suivant doit apparaitre dans le terminal :
```
    Loading composer repositories with package information
    Installing dependencies (including require-dev)
        - Installing monolog/monolog (1.0.2)
    Loading from cache
    Writing lock file
    Generating autoload files
```
- dans le dossier racine, un dossier vendor est créé avec la bibliothèque (téléchargée automatiquement)
- d'autres fichiers sont créés automatiquement (fichiers d'autoload, lock etc.)
- à présent, gràce à ##composer##, il est facile de mettre à jour le projet et ses dépendances
- pour cela, saisir -> composer update

**Rappel :** si vous avez suivi mes instructions et installé **composer** selon la méthode **'globale'** vous ne devez pas utiliser la commande -> php composer.phar install (utilisation locale) mais bien la commande -> composer install 

##liens utiles
- Le site de **Composer** : https://getcomposer.org
- L'utilisation basique de **Composer** : https://getcomposer.org/doc/01-basic-usage.md
- Le site officiel hébergeant les bibliothèques compatibles ##Composer## : https://packagist.org
