# Installation Guide

This guide provides detailed instructions on how to set up and run the Biz2Factory application.

## System Requirements

- Python 3.10 or higher
- pip (Python package installer)
- Git

## Step-by-Step Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Biz2Factory.git
cd Biz2Factory
```

### 2. Set Up Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS/Linux

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project root directory by copying the example file:

```bash
cp env.example .env
```

Then, edit the `.env` file and update the values according to your environment:

- `SECRET_KEY`: Generate a secure secret key
- `EMAIL_HOST_USER` and `EMAIL_HOST_PASSWORD`: Your email service credentials

### 5. Database Setup

Apply database migrations:

```bash
python manage.py migrate
```

### 6. Create Superuser

Create an admin user to access the Django admin interface:

```bash
python manage.py createsuperuser
```

Follow the prompts to create your admin username, email, and password.

### 7. Run the Development Server

```bash
python manage.py runserver
```

The application will be available at http://127.0.0.1:8000/

### 8. Access the Admin Interface

Navigate to http://127.0.0.1:8000/admin/ and log in with your superuser credentials.

## Troubleshooting

### Common Issues

1. **Database Migration Errors**
   - Check if your database file exists and has correct permissions
   - Try running `python manage.py makemigrations` before `migrate`

2. **Module Import Errors**
   - Verify all dependencies are installed with `pip list`
   - Ensure your virtual environment is activated

3. **Email Configuration Issues**
   - Verify your email service credentials
   - Check if your email service allows less secure apps (if applicable)

For additional help, please create an issue on the GitHub repository. 