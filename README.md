__________________________________________________________________
# Projet 6 : Participez à la vie de la communauté Open Source    #
__________________________________________________________________

## Script de Sauvegarde de votre serveur Wordpress et sa base de Donnée vers AWS S3 #

Le script permet de sauvegarder le dossier d'installation de wordpress en entier ainsi que le dump de la base de donnée Wordpress sur MariaDB
Les fichiers sont compresser en Bz2
Il copie d'abord les fichiers en local sur la machine puis upload les fichiers sur le bucket AWS S3 choisis
Une vérification des fichiers sur AWS S3 est faites, ensuite les fichiers en local sont supprimé !!

Il y'a une fonction pour chaque élément, si un élément ne vous intéresse pas n'utilisé pas la fonction.
Il y'a une fonction REgex qui permet de lancer le script sans rentrer d'identifiant ROOT pour le dump MYSQL.

__________________________________________________________________
# Prérequis                                                      #
__________________________________________________________________

## Python   
Version recommandée : 3.7.7   https://www.python.org/downloads/release/python-377/

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
Installation du module AWS CLI version 2 __https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html__

###### aws configure
AWS Access Key ID [None]: XXXXX
AWS Secret Access Key [None]:XXXXXXXX
Default region name [None]: XXXXXX
Default output format [None]: XXXXX





Script to Save wordpress site and a MYSQL DUMP to AWS S3

The script saves the all files in Wordpress installation folder and the Wordpress database dump to MariaDB.
Files are compressed in Bz2
It first copies the files locally to the machine and then uploads the files to the selected AWS S3 bucket.
A file check on AWS S3 is done, then local files are deleted !

There is a function for each item, if you are not interested for all item don't use the function.
There is a REgex function that allows you to launch the script without entering a ROOT ID for the MYSQL dump.
(Important the user of the database must have the necessary rights to do the dump).

