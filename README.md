# NAS-SERVER
Configuration d'un serveur NAS sur raspberry pi 4

## Configuration de l'espace de stockage avec un disque externe de 2 To avec allimentation externe

### Gestion des partitions

pour voir toutes les **partitions** du système

```
sudo fdisk -l
```
la commande **fdisk** va permettre de connaître l'emplacement physique de chacune des partitions **/dev/***

pour créer des partitions sur un espace de stockage 

```
sudo cfdisk /dev/<emplacement de la partition>
```
puis **new** sur **espace libre** et sélection de la taille puis **type** sur la partiton pour spécifier son type (server data, linux file,swap...)
.
Une fois fait il faut écrire sur les partitions et confirmer avec la commande **write** et confirmer par **yes**

### Formatage des partitions

```sudo mkfs.ext3 /dev/*``` ou ext4 pour des fichiers linux 

```sudo mkswap /dev/*``` pour la partition swap

#### monter les partitions

pour monter la partition de stockage pour le serveur nas je créé un repertoire **nas-storage** dans le repertoire racine puis

```sudo mount -t ext4 /dev/* /home/pi/nas-storage``` la partition est montée

cependant pour pouvoir écrire dessus il faut changer le propriétaire qui est en root par **sudo chown** et **sudo chgrp**
