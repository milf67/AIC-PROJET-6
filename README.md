__________________________________________________________________
# Projet 6 : Participez à la vie de la communauté Open Source    #
__________________________________________________________________

## Script de Sauvegarde de votre serveur Wordpress et sa base de Donnée vers AWS S3 #

Le script permet de sauvegarder le dossier d'installation de wordpress en entier ainsi que le dump de la base de donnée Wordpress sur MariaDB

__________________________________________________________________
# Prérequis                                                      #
__________________________________________________________________

## Python ; Debian ; MariaDB
Version Python recommandée : 3.7.7   https://www.python.org/downloads/release/python-377/
Version Debian Utilisé     : 10.4.0  https://www.debian.org/distrib/netinst
Version MariaDB Utilisé    :

## Modules utilisés    
 os
 sys
 re
 subprocess
 tarfile
 datetime
 boto3
 time 
 
## Configuration AWS S3
Installation du module AWS CLI version 2 https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html

###### aws configure
Modifier le fichier de configuration AWS avec la commande suivante dans une distribution Linux
> $ aws configure 

- AWS Access Key ID [None]: VOTRE ID
- AWS Secret Access Key [None]:VOTRE KEY
- Default region name [None]: 
- Default output format [None]: 

## MariaDB
- Création d'un utilisateur avec les droits pour effectuer le dump de la base de donnée du site wordpress
- Pas de chiffrement des credentials __ATTENTION AUX DROITS__ donnés

###### Création d'un bucket sur AWS S3

Suivre la documentation AWS https://docs.aws.amazon.com/fr_fr/AmazonS3/latest/user-guide/create-bucket.html 

__________________________________________________________________
# Exécution du script                                                  #
__________________________________________________________________
## Variable à modifier 

- HOMEPATH = 'Dossier de votre site Wordpress'
- BACKUP_PATH = 'chemin de votre dossier de sauvegarde'
- bucket = "le nom de votre bucket"

Le script exécute toute les fonctions  présente dans le code principal


Script to Save wordpress site and a MYSQL DUMP to AWS S3

The script saves the all files in Wordpress installation folder and the Wordpress database dump to MariaDB.
Files are compressed in Bz2
It first copies the files locally to the machine and then uploads the files to the selected AWS S3 bucket.
A file check on AWS S3 is done, then local files are deleted !

There is a function for each item, if you are not interested for all item don't use the function.
There is a REgex function that allows you to launch the script without entering a ROOT ID for the MYSQL dump.
(Important the user of the database must have the necessary rights to do the dump).

