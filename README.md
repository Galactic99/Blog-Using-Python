# Blog-Using-Python
The Blog Management System is a web application developed using Python and Flask. It provides a platform for users to manage their blog posts, with features such as user authentication, creating, editing, and deleting posts. This application ensures user privacy through secure password encryption and offers a rich text editor for creating blog content.

Features
User Authentication:

Register and log in securely.
Passwords are encrypted and stored securely.
Blog Post Management:

Create new blog posts with a title, subtitle, body content, and image URL.
Edit blog posts that you have authored.
Delete blog posts you have created.
View all blog posts and individual posts with comments.
Comments:

Authenticated users can leave comments on blog posts.
User Interface:

Built with Flask, Flask-Bootstrap for styling, and Flask-CKEditor for rich text editing.
Gravatar integration for user avatars.
Technologies Used
Flask: Web framework for Python.
SQLAlchemy: ORM for database interactions.
Flask-Login: Session management for user authentication.
Flask-CKEditor: Rich text editor for blog content.
Flask-Bootstrap: Styling framework.
Flask-Gravatar: Avatar display integration.
Installation
To set up the project locally, follow these steps:

Clone the Repository

bash

git clone https://github.com/yourusername/blog-management-system.git
cd blog-management-system
Create a Virtual Environment (optional but recommended)

bash

python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install Dependencies

bash

pip install -r requirements.txt
Set Up the Database

Initialize the database with:

bash

flask db upgrade
Run the Application

bash

flask run
By default, the application will run on http://127.0.0.1:5000/.

Usage
Register: Visit /register to create a new account.
Login: Visit /login to access your account.
Create a Post: Visit /new-post to create a new blog post.
Edit a Post: Visit /edit-post/<post_id> to modify an existing post.
Delete a Post: Visit /delete/<post_id> to remove a blog post.
View Posts: Visit / to see all blog posts or /post/<post_id> to view a specific post.
User Posts: Visit /user_posts to view posts authored by the logged-in user.
Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes.
Commit your changes (git commit -am 'Add new feature').
Push to the branch (git push origin feature-branch).
Create a new Pull Request.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Contact
For any questions or issues, please open an issue on GitHub or contact the repository owner.

