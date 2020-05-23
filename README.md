__________________________________________________________________
# Projet 6 : Participez à la vie de la communauté Open Source    #
__________________________________________________________________

## Script de Sauvegarde de votre serveur Wordpress et sa base de Donnée vers AWS S3 #

Le script permet de sauvegarder le dossier d'installation de wordpress en entier ainsi que le dump de la base de donnée Wordpress sur MariaDB

__________________________________________________________________
# Prérequis                                                      #
__________________________________________________________________

## Python ; Debian ; MariaDB
- Version Python  Utilisé    : 3.7.7   https://www.python.org/downloads/release/python-377/
- Version Debian  Utilisé    : 10.4.0  https://www.debian.org/distrib/netinst
- Version MariaDB Utilisé    : 10.4    https://go.mariadb.com/

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

## Exécution
- Le script exécute vérifie la présense du dossier Wordpress puis éxécute toute les fonctions dans le code principal.(Fontion supprimable à souhait)
> /.../.\data.py

## Particularité du script


  - Expréssion Regulière pour extraire les idenfiants permettant le dump de la BDD
    > def WPregex(HOMEPATH):
  - Compréssion des fichiers à sauvegarder en tar.Bz2
    > def WPBackupTar
  - Temps d'attente entre l'éxécution de la fonction de suppréssion des fichiers local et l'upload sur S3 (*L125*)
    - Cela permet d'assurer que l'upload est bien fini avant de le tester ( *temps modifiable a souhait en fonction de la taille         des fichiers*)
      



