# Subtle Seconds - Watch E-commerce Website

A Flask-based e-commerce website for selling watches, built with Bootstrap for responsive design and MySQL for data storage.

## Features

- **Product Catalog**: Browse watches with detailed product pages
- **Categories**: New arrivals and popular items sections
- **Shopping Cart**: Add products to cart functionality
- **Admin Dashboard**: Manage products (add, edit, delete)
- **Responsive Design**: Bootstrap-powered mobile-friendly interface

## Tech Stack

- **Backend**: Flask (Python)
- **Database**: MySQL with SQLAlchemy ORM
- **Frontend**: HTML, CSS, JavaScript, Bootstrap
- **Authentication**: Session-based admin login

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Watch-Site-Flask-Bootstrap-main
   ```

2. **Install dependencies**
   ```bash
   pip install flask flask-sqlalchemy pymysql
   ```

3. **Database Setup**
   - Create MySQL database named `ecom`
   - Update database credentials in `config.json`

4. **Configure Settings**
   - Edit `config.json` with your database URI and admin credentials
   - Set upload location for product images

5. **Run the application**
   ```bash
   python main.py
   ```

## Configuration

Update `config.json` with your settings:
```json
{
  "parameters": {
    "local_uri": "mysql+pymysql://username:password@localhost/ecom",
    "admin_username": "your_username",
    "admin_password": "your_password",
    "upload_location": "path/to/upload/folder"
  }
}
```

## Database Models

- **Products**: Store watch information (name, price, company, description, images)
- **Cart**: Manage shopping cart items

## Routes

- `/` - Home page with product catalog
- `/product/<slug>` - Individual product page
- `/newarrivals` - New arrival products
- `/popularitems` - Popular products
- `/cart` - Shopping cart
- `/dashboard` - Admin panel (login required)

## Admin Features

- Product management (CRUD operations)
- Image upload for products
- Mark products as new arrivals or popular items

## License

This project is open source and available under the MIT License.