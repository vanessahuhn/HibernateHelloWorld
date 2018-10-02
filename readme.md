# HibernateHelloWorld

[TOC]

## Introduction

Cette application sert à ajouter des informations à une base de données sur des maîtres de conférence d'une université.

## Création de la base de données

En amont, il faut créer une base de données *Universite* et une table *Lecturer*. Le script pour le faire est disponible [ici](https://github.com/vanessahuhn/HibernateHelloWorld/blob/master/SQL/createDB%20%2B%20table.sql). Il est possible de ne pas spécifier les champs *FName* et *LName* qui seront automatiquement créés au lancement de l'application.

## Création du projet Java

### La classe persistante 'Lecturer.java'

Le fichier pour cette classe est disponible [ici](https://github.com/vanessahuhn/HibernateHelloWorld/blob/master/src/model/Lecturer.java). Cette classe est notre classe modèle. Elle est aussi appelée classe persistante. Elle correspond à la table *Lecturer* de notre base de données. Elle est placée dans le package *model*.

### Fichier de mappage 'Lecturer.hbm.xml'

Ce fichier est disponible [ici](https://github.com/vanessahuhn/HibernateHelloWorld/blob/master/src/Lecturer.hbm.xml). Il permet d'indiquer à Hibernate quelle classe représente quelle table et quelle variable instantanée correspond à quelle colonne. 

Dans le tag <class>, l'attribut name correspond au nom de la classe persistante et table spécifie au nom de la table de la base de données.

Dans le tag <property>, l'attribut name correspond à l'attribut de la classe persistante et column spécifie le nom du champ dans la base de données. L'attribut type permet de définir le type de données (ici, string).

/!\ **Attention**, avec le nom de la classe il faut penser à ajouter le nom du package. Ici, le nom de la classe est *model.Lecturer*.

### Le fichier de configuration 'hibernate.cfg.xml'

Ce fichier est disponible [ici](https://github.com/vanessahuhn/HibernateHelloWorld/blob/master/src/hibernate.cfg.xml). Il permet de définir les configurations Hibernate.

/!\ **Attention**, il faut modifier :

- le nom de la base de données dans la propriété *connection.url*
- le nom de l'utilisateur du serveur MySQL dans la propriété *connection.username* car il est *root* par défaut
- le mot de passe du serveur MySQL dans la propriété *connection.password*



### La classe de test 'SimpleTest.java'

Le fichier pour cette classe est disponible [ici](https://github.com/vanessahuhn/HibernateHelloWorld/blob/master/src/application/SimpleTest.java). Il s'agit de la classe qui contient la méthode main. Elle est placée dans le package *application*.

/!\ **Attention**, il faut importer la classe persistante.