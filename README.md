
### README

# Flask Blog Application

This is a Flask-based web application where users can register, log in, create blog posts, comment on them, and perform other blog-related activities. The application is built with a focus on user authentication, password security, and a clean interface using Flask-Bootstrap and Flask-CKEditor.

## Features
1. **User Authentication**:
   - Register and Login functionalities.
   - Passwords are securely hashed using `werkzeug.security`.
   - Logged-in users can create, edit, and delete their blog posts.
   
2. **Blog Functionality**:
   - Users can create, view, and comment on blog posts.
   - Only authenticated users can create posts and add comments.
   - Posts can have a title, subtitle, body, and image.
   - Users can only edit or delete their own posts.

3. **Comments**:
   - Authenticated users can comment on posts.
   - The comments are linked to both the blog post and the user who made the comment.

## Project Setup

### Prerequisites
- Python 3.x
- Flask
- SQLite (default database)
- Python packages listed in the `requirements.txt` file.

### Installing Dependencies
To install all the required dependencies, run the following command:
```bash
pip install -r requirements.txt
```

### Folder Structure
The project has the following folder structure:

```
├── app.py              # Main Flask application file
├── forms.py            # Contains Flask-WTF form classes for registration, login, etc.
├── templates/          # HTML templates for various pages
│   ├── index.html      # Home page
│   ├── register.html   # User registration page
│   ├── login.html      # User login page
│   ├── post.html       # Individual blog post page
│   ├── make-post.html  # Page for creating/editing blog posts
│   ├── user_post.html  # Page to display user's own blog posts
├── static/             # Static files (CSS, JS, images)
│   ├── css/
│   ├── js/
├── posts.db            # SQLite database file (created automatically)
├── README.md           # Project documentation
└── requirements.txt    # Python dependencies file
```

### Running the Application
1. **Set Up the Database**:
   - The database is automatically created when the application runs for the first time. 
   - It uses SQLite as the default database, defined in the `app.config['SQLALCHEMY_DATABASE_URI']`.

2. **Running the App**:
   Use the following command to start the Flask development server:
   ```bash
   python app.py
   ```

   By default, the app will run on `http://localhost:5001/`. You can visit this URL to see the app in action.


### Functionality Overview

#### User Authentication
- **Registration**: Users can register with a name, email, and password. Passwords are hashed before being stored in the database.
- **Login**: Existing users can log in with their email and password. Passwords are verified using `werkzeug.security.check_password_hash`.

#### Blog Posts
- **View Posts**: The homepage displays all blog posts.
- **Create Posts**: Logged-in users can create blog posts with a title, subtitle, body, and an image URL.
- **Edit Posts**: Users can edit their own blog posts.
- **Delete Posts**: Users can delete their own blog posts.

#### Comments
- **View Comments**: Comments are displayed on each blog post.
- **Add Comments**: Logged-in users can comment on blog posts.
- **Delete Comments**: Users can delete their own comments.


### Forms

#### `forms.py`:
- **CreatePostForm**: Form for creating/editing blog posts.
- **RegisterForm**: Form for user registration.
- **LoginForm**: Form for user login.
- **CommentForm**: Form for adding comments to a blog post.

### Gravatar Integration
User avatars are displayed using Gravatar based on their email. The Gravatar service is integrated using the `flask-gravatar` library.

### Database Models

#### `BlogPost`
- Represents each blog post in the database.
- Linked to a user (author) via `author_id`.

#### `User`
- Represents users registered in the system.
- Contains hashed passwords for security.
- Linked to blog posts and comments.

#### `Comment`
- Represents user comments on blog posts.
- Linked to a user and a blog post.

### Templates
The templates directory contains all the HTML files required for rendering different parts of the application. They use Jinja2 templating syntax to dynamically display content from the Flask app.

### Debug Mode
The app is run with `debug=True`, which provides better error messages and auto-reloading during development.

## Future Improvements
- Add support for post categories/tags.
- Enable rich text editing in the blog body (currently supported with CKEditor but can be improved).
- Add pagination to the list of blog posts.
- Implement email verification during user registration.
- Adding admin privileges to users

## Contributing
Pull requests are welcome. For significant changes, please open an issue first to discuss what you would like to change.

### License
This project is licensed under the MIT License.
