# Flask Blog

A full-featured blog application built with Flask, featuring user authentication, post management, and a clean, responsive design.

## Features

- **User Authentication**
  - User registration with email validation
  - Secure login/logout system
  - Password hashing for security
- **Blog Post Management**
  - Create, read, and delete blog posts
  - Only authenticated users can create posts
  - Users can only delete their own posts
  - Posts display author information and timestamps
- **User Interface**
  - Clean, responsive design
  - Flash messages for user feedback
  - Separated CSS for maintainability
  - Professional styling with custom color scheme

## Technologies Used

- **Flask 3.0.0** - Web framework
- **Flask-SQLAlchemy 3.1.1** - Database ORM
- **Flask-Login 0.6.3** - User session management
- **SQLite** - Database (development)
- **Jinja2** - Template engine
- **Gunicorn 21.2.0** - WSGI server (production)

## Project Structure

```
flask_blog/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── Procfile              # Deployment configuration
├── static/
│   └── style.css         # Stylesheet
└── templates/
    ├── base.html         # Base template
    ├── index.html        # Home page
    ├── post.html         # Individual post view
    ├── create.html       # Create post form
    ├── login.html        # Login page
    └── register.html     # Registration page
```

## Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Setup

1. **Clone the repository:**

```bash
git clone https://github.com/yukiseno/flask_blog.git
cd flask_blog
```

2. **Create and activate virtual environment:**

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies:**

```bash
pip install -r requirements.txt
```

4. **Run the application:**

```bash
python app.py
```

5. **Open your browser:**
   Navigate to `http://localhost:8001`

## Usage

### First Time Setup

1. Register a new account at `/register`
2. Log in with your credentials
3. Create your first blog post
4. Only you can delete your own posts

### Creating Posts

- Click "Create Post" in the navigation (only visible when logged in)
- Fill in the title and content
- Submit to publish

### Managing Posts

- View all posts on the home page
- Click "Read More" to see full post content
- Delete button only appears on your own posts

## Database

The application uses SQLite for development. The database file (`blog.db`) is automatically created on first run.

### Models

**User**

- id (Primary Key)
- username (Unique)
- email (Unique)
- password_hash
- posts (Relationship)

**Post**

- id (Primary Key)
- title
- content
- created_at
- user_id (Foreign Key)

## Deployment

This application is deployed on Railway. To deploy your own instance:

1. **Push to GitHub:**

```bash
git add .
git commit -m "Your commit message"
git push
```

2. **Deploy to Railway:**

- Connect your GitHub repository
- Railway will automatically detect and deploy
- Set environment variables if needed

### Environment Variables

- `SECRET_KEY` - Secret key for Flask sessions (set in production)
- `PORT` - Port number (automatically set by Railway)

## Development

### Running Locally

```bash
# Activate virtual environment
source venv/bin/activate

# Run development server
python app.py
```

### Making Changes

1. Edit files in `templates/` for HTML changes
2. Edit `static/style.css` for styling changes
3. Edit `app.py` for backend logic
4. Database changes require deleting `blog.db` and restarting

## Security Features

- Password hashing using Werkzeug
- CSRF protection via Flask's secret key
- SQL injection protection via SQLAlchemy ORM
- User session management with Flask-Login
- Protected routes with `@login_required` decorator

## Future Improvements

- [ ] Add post editing functionality
- [ ] Implement pagination for posts
- [ ] Add search feature
- [ ] Add categories/tags
- [ ] Add comment system
- [ ] Rich text editor for posts
- [ ] User profile pages
- [ ] Post images/media upload
- [ ] Email verification for registration
- [ ] Password reset functionality

## Learning Resources

This project was built while learning Flask. Key concepts covered:

- Flask routing and views
- SQLAlchemy ORM
- User authentication with Flask-Login
- Template inheritance with Jinja2
- Form handling and validation
- CSS separation and styling
- Git version control
- Deployment to production

## License

This project is open source and available for educational purposes.

## Author

Built by Yuki as part of learning Python web development with Flask.

## Acknowledgments

- Flask documentation
- Flask-Login documentation
- Railway deployment platform
