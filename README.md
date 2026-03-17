# DIC1 Shop - Django E-commerce Platform

A modern e-commerce platform built with Django, providing a complete shopping experience for electronic and tech products.

## Description

DIC1 Shop is an online store specializing in electronic and technology products.
The platform allows users to browse a wide product catalog, manage their shopping cart, place orders, and track deliveries.

## Features

### User Interface

* **Authentication System**: User registration and login
* **Product Catalog**: Category-based browsing with advanced search
* **Shopping Cart**: Add/remove items with automatic total calculation
* **User Profile**: Manage personal information and order history
* **Order Tracking**: Track delivery status

### Product Categories

* Computers and laptops
* Smartphones
* Headphones and audio accessories
* Computer and mobile accessories
* Cameras and photography equipment
* TVs and home appliances
* Gaming consoles
* Watches and accessories
* GPS and navigation devices
* Wearable technologies

### Advanced Features

* **Secure Payment System**: Safe transaction processing
* **Delivery Management**: Multiple shipping options
* **Wishlist**: Save favorite products
* **Product Comparison**: Side-by-side feature comparison
* **Customer Support**: Integrated help system
* **Mobile App**: Available on Google Play Store and App Store

## Tech Stack

* **Backend**: Django (Python)
* **Frontend**: HTML5, CSS3, JavaScript
* **Database**: SQLite
* **Authentication**: Django Auth System
* **Media Management**: Django Media Files
* **Admin Interface**: Django Admin

## Prerequisites

* Python 3.8+
* pip
* virtualenv (recommended)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/thiernodaoudaly/dic1-django-ecommerce-platform.git
cd dic1-django-ecommerce-platform
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up the database

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Create a superuser

```bash
python manage.py createsuperuser
```

### 6. Run the development server

```bash
python manage.py runserver
```

## Learning Outcomes

* Backend web development with Django
* Database design and management
* Building scalable web applications
* Structuring full-stack projects

## Contribution

Contributions are welcome!

1. Fork the project
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m "Add new feature"`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License.
