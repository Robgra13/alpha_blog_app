# ALPHA BLOG APP

This is my first bigger rails app. What is it about and what I learned by creating it?
Basics like:
* Using GitHub
* How to create migration files and use database
* Using rails console
* Learned about MVC
* Learned how to build front of the app with Bootsrtap

# What can you do and how it is made?
* Everything is handcoded (not using scaffold or devise gem)

1. First I created Article object that has title and description and also validations for those two parameters.
   You can create Articles, update them or destroy. You can also list all of them.

2. While I have validations for Article parameters I created action that inform why Article can not be saved
   and also display information if Article was saved successfully.

3. Next thing is creating a User and it association with Articles. User has many Articles. Article belongs to user.
   User has its username, email and secure password. This funcionality is allowed by BCrypt. While User has its own validations
   I added messeges about errors similar to those for Articles. Next I created sign up form for new users and show view
   so you can see all the users in Bloggers tab.

4. Another thing to care about were sessions. I added loging in/out funcionality.
   If User is logged-in then view shows link to its profile and log-out link.
   If User is not logged then there is possibility to log-in and sign up.

5. Added restrictions
    Each user can only edit/delete its own Articles. 
    Each user can only edit/delete its own profile
    Only logged in user can create Articles.
    But those restrictions were only in views. If someone try to enter edit/destroy action by url application would allow it.
    Then I added second layer of security at controllers level for Articles and Users.

6. Adding admin user and permissions
   By adding new admin column to Users table which value is false by default I get new possibilities.
   After editing views and controllers Admin User can edit/delete Articles of other Users and also
   edit/delete their profiles.

7. Next step is creating new feature: Categories. For categories I of course create its table, model, controller and views
   which are based on many-to-many association with Articles.
   Important: from this moment I am not only creating Categories model, but I am also writing test based on build in Rails Minitest.
   Last table that I create is Article_Category that sistematizes assigning Category to Article.

.app edited and uploaded once more.