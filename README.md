Installation de services réseau

Ce projet vise à mettre en place une infrastructure réseau complète en déployant OwnCloud pour la gestion de fichiers en ligne. Il comprend également la sécurisation des connexions, la gestion des utilisateurs et l'automatisation de la configuration du serveur.
Fonctionnalités

    Déploiement d'OwnCloud : Installation et configuration d'OwnCloud pour le partage et la synchronisation de fichiers.
    Sécurisation des connexions :
        Mise en place de certificats SSL/TLS pour les connexions HTTPS sécurisées.
        Configuration de SSH pour un accès sécurisé au serveur.
    Gestion des utilisateurs : Création et administration des comptes utilisateurs avec des permissions d'accès spécifiques.
    Automatisation : Scripts pour automatiser la configuration initiale du serveur et le déploiement des services.

Structure du projet

Le projet est organisé comme suit :

    Oral_sae_2.03.pptx : Présentation détaillant le processus d'installation, les configurations effectuées et les résultats obtenus.

Note : Le dépôt actuel contient principalement la présentation du projet. Les scripts et fichiers de configuration associés peuvent être ajoutés ultérieurement.
Prérequis

    Un serveur fonctionnant sous une distribution Linux (par exemple, Ubuntu 20.04).
    Accès root ou des privilèges sudo sur le serveur.
    Nom de domaine pointant vers l'adresse IP du serveur pour la configuration HTTPS.

Installation

    Mise à jour du système :

sudo apt update && sudo apt upgrade -y

Installation des dépendances requises :

sudo apt install apache2 mariadb-server libapache2-mod-php php-mysql openssl -y

Téléchargement et configuration d'OwnCloud :

# Télécharger la dernière version d'OwnCloud
wget https://download.owncloud.org/community/owncloud-x.y.z.tar.bz2
# Extraire les fichiers
tar -xjf owncloud-x.y.z.tar.bz2
# Déplacer vers le répertoire web
sudo mv owncloud /var/www/html/

Configuration d'Apache :

sudo nano /etc/apache2/sites-available/owncloud.conf

Ajouter la configuration virtuelle pour OwnCloud et activer le site :

    sudo a2ensite owncloud.conf
    sudo systemctl reload apache2

    Sécurisation des connexions HTTPS :

    Générer et installer des certificats SSL/TLS pour le domaine. Cela peut être fait en utilisant Let's Encrypt ou en générant des certificats auto-signés pour des environnements de test.

    Configuration de SSH :

    Assurer que le service SSH est installé et configuré pour n'autoriser que les connexions sécurisées. Il est recommandé de désactiver l'accès root direct et d'utiliser l'authentification par clé publique.

    Automatisation :

    Des scripts peuvent être créés pour automatiser les étapes ci-dessus, en particulier pour la configuration initiale du serveur et le déploiement d'OwnCloud.

Utilisation

    Accès à OwnCloud :

    Ouvrez un navigateur web et accédez à https://votre-domaine.com/owncloud.

    Connexion :

    Connectez-vous avec les identifiants administrateur créés lors de l'installation.

    Gestion des fichiers :

    Téléchargez, partagez et synchronisez vos fichiers en toute sécurité via l'interface web ou les clients OwnCloud disponibles pour diverses plateformes.
