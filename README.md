# DIC1 Shop — Django E-commerce Platform

<div align="center">

![Django](https://img.shields.io/badge/Django-5.2-092E20?style=flat-square&logo=django&logoColor=white)
![DRF](https://img.shields.io/badge/Django%20REST%20Framework-3.16-red?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

**Full-stack e-commerce platform for tech products — custom user authentication with email verification, session-based cart, product catalog with category filtering, and a REST API layer.**

</div>

## Overview

DIC1 Shop is a Django e-commerce application covering the full shopping lifecycle: account creation with email activation, product browsing by category, full-text search, session-based cart management, and a user dashboard. It also exposes a REST API for programmatic access to user data.

## Features

- **Custom user model** — `AbstractBaseUser` with email as the login field, `MyAccountManager` for user/superuser creation, REST framework token generated on signup via `post_save` signal
- **Email verification** — account activation link sent on registration (`uidb64` + token), with a separate password reset flow
- **Product catalog** — browsing by category (slug-based URLs), product detail pages, stock and availability flags, brand field
- **Full-text search** — `Q` objects querying `product_name` and `description`
- **Session-based cart** — anonymous cart keyed by `session_key`, add/remove/decrement items, per-item subtotal (`price × quantity`)
- **User dashboard** — profile view and settings page
- **REST API** — `UserViewSet` (token auth) + `UserLogIn` endpoint, DRF browsable API at `/accounts/api/v1/`
- **Django Admin** — full CRUD on all models

## Project Structure

```
dic1-shop/
├── myboutique/               # Django project config
│   ├── settings.py
│   ├── urls.py               # Root router
│   └── views.py              # Home, validation, profil, parametres
├── accounts/                 # Custom user authentication + REST API
│   ├── models.py             # Account (AbstractBaseUser), token signal
│   ├── views.py              # register, login, activate, forgotPassword, resetPassword, UserViewSet
│   ├── forms.py              # RegistrationForm
│   ├── serializers.py        # UserSerializer
│   └── urls.py               # Auth routes + /api/v1/
├── store/                    # Product catalog
│   ├── models.py             # Product (name, slug, price, stock, brand, category FK)
│   ├── views.py              # store, product_detail, search
│   └── urls.py
├── carts/                    # Shopping cart
│   ├── models.py             # Cart (session_key), CartItem (product FK, quantity)
│   ├── views.py              # cart, add_cart, remove_cart, remove_cart_item
│   └── context_processors.py
├── category/                 # Product categories
│   ├── models.py             # category (name, slug, image)
│   └── context_processors.py
├── templates/
│   ├── base.html / navbar.html / footer.html
│   ├── home.html / dashboard.html
│   ├── accounts/             # login, register, forgotPassword, resetPassword, emails
│   └── store/                # store, product_detail, cart
├── media/                    # Uploaded product/category images
├── manage.py
└── requirements.txt
```

## URL Routes

| URL | View | Description |
|---|---|---|
| `/` | `home` | Landing page |
| `/store/` | `store` | All products |
| `/store/category/<slug>/` | `store` | Products filtered by category |
| `/store/category/<cat>/<slug>/` | `product_detail` | Product detail |
| `/store/search/` | `search` | Full-text search |
| `/cart/` | `cart` | Cart overview |
| `/cart/add_cart/<id>/` | `add_cart` | Add item to cart |
| `/cart/remove_cart/<id>/` | `remove_cart` | Decrement item |
| `/cart/remove_cart_item/<id>/` | `remove_cart_item` | Remove item entirely |
| `/accounts/register` | `register` | User registration |
| `/accounts/login` | `login` | Login |
| `/accounts/activate/<uidb64>/<token>/` | `activate` | Email activation |
| `/accounts/forgotpassword/` | `forgotPassword` | Password reset request |
| `/accounts/resetPassword/` | `resetPassword` | Set new password |
| `/accounts/dashboard/` | `dashboard` | User dashboard |
| `/accounts/api/v1/users/` | `UserViewSet` | REST — list/retrieve users |
| `/accounts/api-user-login/` | `UserLogIn` | REST — obtain auth token |

## Setup & Usage

```bash
# Clone the repository
git clone https://github.com/thiernodaoudaly/dic1-shop.git
cd dic1-shop

# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate       # Linux / macOS
# venv\Scripts\activate        # Windows

# Install dependencies
pip install -r requirements.txt

# Apply migrations
python manage.py migrate

# Create a superuser
python manage.py createsuperuser

# Start the development server
python manage.py runserver
# → http://127.0.0.1:8000
```

**Email setup (required for account activation and password reset):**

Add to `settings.py` or a `.env` file:
```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'
```

## Roadmap

- [ ] Move `SECRET_KEY` to environment variable (currently hardcoded)
- [ ] Add order model and checkout flow
- [ ] Implement product ratings and reviews
- [ ] Add pagination to product listing
- [ ] Deploy on Railway or Render

## License

MIT License — see [LICENSE](LICENSE) for details.
