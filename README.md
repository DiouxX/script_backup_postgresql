# script_backup_postgresql

## Description
Ce script permet de sauvegarder une base de donnée PostgreSQL et de spécifié si l'on
désire transférer le DUMP en local ou sur un serveur distant

## Utilisation

Utilisation du script :

	
-u Nom de l'utilisateur de la database

-m Mot de passe de l'utilisateur de la database

-h Hote contenant la database a backuper

-p Port d'ecoute de la database (default: 5432)

-d Nom de la database

-n Nom du Backup (default: Nom de la database)

-f Dossier du backup si l'on ne désire pas un DUMP distant

-t Chemin de sauvegarde de l hote distant

-v Mode verbeux

*******
Example
*******

Si l'on veut un DUMP distant

script_backup_postgresql -u sogo_user -h localhost -d sogodb -n SOGo -t root@192.168.1.1:/mnt/backup_server/backup_postgresql/sogo/


Si l'on veut un DUMP local

script_backup_postgresql -u sogo_user -h localhost -d sogodb -n sogo-backup -f /opt/backup/sogo/"


*********
IMPORTANT
*********

Pensez à copier la clef public sur le serveur que vous desirer envoyer le backup ( Pour automatiser la tache de backup)

[user@ordi ~]$ ssh-copy-id -i ~/.ssh/id_dsa.pub root@serveur-distant
