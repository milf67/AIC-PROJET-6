# AIC-PROJET-6

Script to Save wordpress site to AWS S3

Le script permet de sauvegarder le dossier d'installation de wordpress en entier ainsi que le dump de la base de donnée Wordpress sur MariaDB
Les fichiers sont compresser en Bz2
Il copie d'abord les fichiers en local sur la machine puis upload les fichiers sur le bucket AWS S3 choisis
Une vérification des fichiers sur AWS S3 est faites, ensuite les fichiers en local sont supprimé !!

Il y'a une fonction pour chaque élément, si un élément ne vous intéresse pas n'utilisé pas la fonction.
Il y'a une fonction REgex qui permet de lancer le script sans rentrer d'identifiant ROOT pour le dump MYSQL.
(Important l'user de la base de donnée doit avoir les droits nécessaire pour faire le dump).

Script to Save wordpress site to AWS S3

The script saves the all files in Wordpress installation folder and the Wordpress database dump to MariaDB.
Files are compressed in Bz2
It first copies the files locally to the machine and then uploads the files to the selected AWS S3 bucket.
A file check on AWS S3 is done, then local files are deleted !

There is a function for each item, if you are not interested for all item don't use the function.
There is a REgex function that allows you to launch the script without entering a ROOT ID for the MYSQL dump.
(Important the user of the database must have the necessary rights to do the dump).

