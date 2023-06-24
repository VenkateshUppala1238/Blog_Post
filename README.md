# Blog_Post Application

### Project Overview
  "Build a Blog application with Django that allows users to create, edit, and delete posts. 
The homepage will list all blog posts, and there will be a dedicated detail page for each individual post"
#### Features Required:-
1. Apis to create, read, update and delete the BlogPosts.
2. Register/Login System for users visiting the Blog Site.
3. Authentication for Users. (JWT based)
#### Web pages :-
1. Homepage, where all posts should be listed.
2. Details page, where all details of an individual blog should be displayed.
3. Users should only be able to delete/update their own BlogPost.
4. Logout functionality for users already logged in.
### Installation
  Instructions on how to install, set up, and run the project.
  #### 1.Prerequisites:-
  Ensure that Python is installed on your system. You can install Django using
     
     pip install Django
  Need API development tools like Postman (https://www.postman.com/downloads/) to test and interact with your APIs during development.
  
  The djangorestframework-simplejwt package is commonly used for JWT authentication in Django. You can install it by using

    pip install djangorestframework-simplejwt
    
  #### 2.Clone the Project:-
  Set up a new Django project django-admin startproject blog_project.
  
  Create a new Django app within the project cs blog_project.
  
	python manage.py startapp blog

 Open the blog/models.py file and define your BlogPost model with the necessary fields like title, content, author, created_at, etc.

   ```
     from django.db import models
	 from django.contrib.auth.models import User
	 class BlogPost(models.Model):
    	title = models.CharField(max_length=255)
    	content = models.TextField()
    	author = models.ForeignKey(User, on_delete=models.CASCADE)
    	created_at = models.DateTimeField(auto_now_add=True)

    	def __str__(self):
                 return self.title
   ```

  Configure your database settings in the blog_project/settings.py file, including the database engine, name, user, password, etc.
   ```
	 python manage.py makemigrations
	 python manage.py migrate
   ```
  Create views in the blog/views.py file to handle the different functionalities like creating, reading, updating, and deleting blog posts.

  Define URL patterns in the blog_project/urls.py file to map the URLs to the corresponding view functions or classes.
  ```
 from django.contrib import admin
 from django.urls import include, path
 urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('blog_app.urls')),
 ]
 ```
 Implement the necessary authentication logic(registration, login, and logout) using Django's built-in authentication system or a JWT-based authentication library 
 like djangorestframework-simplejwt.
 
 Migrate Database by using
 ```
 python manage.py makemigrations
 python manage.py migrate
 ```
 Start the Django development server for test and run the application by using
 ```
 python manage.py runserver
 ```
							
Test the application by accessing it in a web browser or using API testing tools like Postman.

Visit http://localhost:8000 in your web browser to access the blog application and see the listed posts on the homepage.
### Usage
Examples and guidelines on how to use the project, including command-line instructions or API documentation.
1. Command-Line Instructions
   ```
   python manage.py runserver
   ```
3. API Documentation:
   
   Create a Blog Post (POST)
       
   Get All Blog Posts (GET)
       
   Get a Single Blog Post (GET)
       
   Update a Blog Post (PUT)
       
   Delete a Blog Post (DELETE)
       
   User Registration (POST)
       
   User Login (POST)
       
   User Logout (POST)
### Road Map
This project's roadmap outlines the planned and potential future enhancements and features that could be implemented. It provides an overview of the project's direction and upcoming milestones. Please note that this roadmap is subject to change and updates based on the project's needs and priorities.

The initial version of the project will focus on implementing the core functionalities. The following features will be included:

 + Apis to create, read, update, and delete BlogPosts.
 + Register/Login System for users visiting the Blog Site.
 + Authentication for Users (JWT based).
 + Homepage to list all blog posts.
 + Details page to display individual blog post details.
 + Users can only delete/update their own BlogPost.
 + Logout functionality for logged-in users.

Some of the future enhancements are:
 + User profile page to manage user-specific information.
 + Comments section for blog posts to allow user engagement.
 + Search functionality to find specific blog posts.
 + Social media sharing options for blog posts.
  
### Contributing
Guidelines for developers who want to contribute to the project, including information on how to submit bug reports, feature requests, or pull requests.
	
 1. Fork the Repository
 2. Set Up the Development Environment
 3. Explore the Codebase
 4. Check for Existing Issues
 5. Create a New Issue (Bug Report/Feature Request)
 6. Work on Your Contribution
 7. Commit and Push Changes
 8. Submitting a Pull Request
 9. Engage in Code Review
 10. Merge and Close the Pull Request
### Contact
Feel free to reach out to me with questions, comments, or concerns at one of the way below.

Git Hub: https://github.com/VenkateshUppala1238

Email: venkateshuppala1238@gmail.com
