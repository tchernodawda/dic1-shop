# DIC1 Shop - Boutique E-commerce Django

Une plateforme de commerce électronique moderne développée avec Django, offrant une expérience d'achat complète pour les produits électroniques et technologiques.

## Description

DIC1 Shop est une boutique en ligne spécialisée dans la vente de produits électroniques et technologiques. La plateforme permet aux utilisateurs de parcourir un large catalogue de produits, gérer leur panier d'achat, passer des commandes et suivre leurs livraisons.

## Fonctionnalités

### Interface Utilisateur
- **Inscription et Connexion** : Système d'authentification complet
- **Catalogue de Produits** : Navigation par catégories avec recherche avancée
- **Panier d'Achat** : Gestion des produits avec calcul automatique des totaux
- **Profil Utilisateur** : Gestion des informations personnelles et historique des commandes
- **Suivi de Commande** : Système de tracking des colis

### Catégories de Produits
- Ordinateurs et ordinateurs portables
- Téléphones intelligents
- Casques de musique et accessoires audio
- Accessoires informatiques et mobiles
- Appareils photo et équipements photo
- Télévisions et électroménager
- Consoles de jeu
- Montres et accessoires
- GPS et navigation
- Technologies portables

### Fonctionnalités Avancées
- **Système de Paiement Sécurisé** : Traitement sécurisé des transactions
- **Gestion des Livraisons** : Plusieurs options de livraison disponibles
- **Liste de Souhaits** : Sauvegarde des produits favoris
- **Comparateur de Produits** : Comparaison côte à côte des caractéristiques
- **Support Client** : Service d'assistance intégré
- **Application Mobile** : Disponible sur Google Play Store et App Store

## Technologies Utilisées

- **Backend** : Django (Python)
- **Frontend** : HTML5, CSS3, JavaScript
- **Base de Données** : SQLite
- **Authentification** : Django Auth System
- **Gestion des Médias** : Django Media Files
- **Interface Admin** : Django Admin

## Installation

### Prérequis
- Python 3.8+
- pip
- virtualenv (recommandé)

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/thiernodaoudaly/boutique-dic1.git
cd dic1-shop
```

2. **Créer et activer un environnement virtuel**
```bash
python -m venv venv
source venv/bin/activate  
```

3. **Installer les dépendances**
```bash
pip install -r requirements.txt
```

4. **Configuration de la base de données**
```bash
python manage.py makemigrations
python manage.py migrate
```

5. **Créer un superutilisateur**
```bash
python manage.py createsuperuser
```

6. **Lancer le serveur de développement**
```bash
python manage.py runserver
```

## Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Fork le projet
2. Créez une branche pour votre fonctionnalité (`git checkout -b feature/nouvelle-fonctionnalite`)
3. Committez vos changements (`git commit -am 'Ajout d'une nouvelle fonctionnalité'`)
4. Push vers la branche (`git push origin feature/nouvelle-fonctionnalite`)
5. Créez une Pull Request


