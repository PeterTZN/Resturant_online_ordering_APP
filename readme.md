# 🍽️ Restaurant Online Ordering App

A Django-based web application that allows restaurants to display their menu online, organised by category, with item availability status and pricing. Built with Python, Django, and Bootstrap 5.

---

## 📋 Features

- Browse full restaurant menu organised by category (Starters, Salads, Main Dishes, Desserts)
- View individual menu item details
- Item availability status (Available / Unavailable) with visual indicators
- Price display per menu item
- Django Admin panel for full menu management
- QR code generation for quick menu access
- Responsive frontend built with Bootstrap 5

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.13, Django 6.0.5 |
| Database | SQLite |
| Frontend | HTML5, Bootstrap 5 |
| Auth | Django built-in authentication |
| Environment | python-dotenv |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.13+
- pip

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/PeterTZN/Resturant_online_ordering_APP.git
cd Resturant_online_ordering_APP
```

2. **Create and activate a virtual environment**

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

4. **Set up environment variables**

Create a `.env` file in the project root:

```env
SECRET_KEY=your-secret-key-here
```

5. **Run database migrations**

```bash
python manage.py makemigrations
python manage.py migrate
```

6. **Create a superuser (for admin access)**

```bash
python manage.py createsuperuser
```

7. **Start the development server**

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000` to view the app, or `http://127.0.0.1:8000/admin` to manage the menu.

---

## 📁 Project Structure

```
Resturant_online_ordering_APP/
│
├── mysite/                  # Django project configuration
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── restaurant_menu/         # Main application
│   ├── models.py            # Item model, MEAL_TYPE & STATUS choices
│   ├── views.py             # MenuList and MenuItemDetail views
│   ├── urls.py
│   ├── admin.py
│   └── templates/           # HTML templates
│
├── manage.py
├── qr.py                    # QR code generator
└── .gitignore
```

---

## 🗃️ Menu Item Model

Each menu item contains the following fields:

| Field | Type | Description |
|---|---|---|
| `meal` | CharField | Name of the dish |
| `description` | CharField | Description of the dish |
| `price` | DecimalField | Price of the dish |
| `meal_type` | CharField | Category (Starters, Salads, Main Dishes, Desserts) |
| `author` | ForeignKey | Linked Django user |
| `status` | IntegerField | 0 = Unavailable, 1 = Available |
| `date_created` | DateTimeField | Auto-set on creation |
| `date_modified` | DateTimeField | Auto-updated on save |

---

## ⚙️ Admin Panel

The Django admin panel at `/admin` allows restaurant staff to:

- Add, edit, and delete menu items
- Set item availability
- Manage user accounts

---

## 📌 Roadmap

- [ ] Online ordering and cart functionality
- [ ] Customer accounts and order history
- [ ] Payment integration
- [ ] Order notifications
- [ ] Mobile app version

---

## 🙏 Acknowledgements

- [Django](https://www.djangoproject.com/)
- [Bootstrap 5](https://getbootstrap.com/)

---

## 📄 Licence

This project is open source and available under the [MIT License](LICENSE).