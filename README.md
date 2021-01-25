#  Reverse Engineering Authentication (Homework-14)

# Description
This app gives the user the ability to create an account, and with the account created, the user is provided with a secure login and log out process and experience. All user data is stored in a MySQL database.

# User Story
As someone who wants to log in safely to my “XY account, I want to know that my personal details are safely stored so that I don’t have to worry about details of my login being stolen.

# Tech Used
BCRYPTJS -EXPRESS -EXPRESS-SESSION -MYSQL2 -PASSPORT -PASSPORT-LOCAL -SEQUELIZE

# How to
It required that clone this repository into your local storage in order for you to begin using this app, After which you take the following 5 steps;
1)Create a MySQL dB called "passport_demo".
 2)Go into the config file, open config.js, and insert your MySQL ie username, password, etc 
3)Open the terminal in the current repo and run "npm i" to install all node packages. 
4)To connect to the server successfully run "node server.js"  in the terminal. 
5)Open the browser and put "http://localhost:8080" in the search bar. 

# Folder and File Details
Inside the “Develop” folder we have the following files and folder:
* CONFIG {
** MIDDLEWARE{
*** isAuthenticated.js {restricts routes that the user is not allowed to visit if not logged in. if the user is logged in, it continues with request }.
}
** config.json { connection configuration to connect to server }.
** passport.js { contains javascript logic that tells passport we want to log in with an email address and password }.
}
* MODELS{
** index.js { connects to database and imports users login data }.
** user.js { requires "bcrypt" for password hashing. this makes our database secure even if compromised. Here we have JS that defines what is stored on our database }.
}
* PUBLIC {
** Js{
*** login.js { contains code for getting references to our form and inputs,code for when the form is submitted,validation that email and password are entered, then we run the loginUser function and clear the form. The loginUser does a post to our "api/login" route and if successful, redirects us the the members page.}
*** members.js { This file just does a GET request to figure out which user is logged in and updates the HTML on the page }.
*** signup.js {Contains getting references to our form and input. When the signup button is clicked, we validate that the email and password are not blank. If we have an email and password,the signUpUser function is run and then does a post to the signup route. If successful, we are redirected to the members page , otherwise we log any errors. If there's an error, handle it by throwing up a bootstrap alert}.
}
** Stylesheet{ style.css { contains all the margin fot both the login and signup forms}.}
** login.html {This page contains the login form design in code and shows the login in the browser }.
** members.html {This page contains the logout button and is displayed after members login as proof of the authentication process }.
** signup.html { This page contains the signup form design in code and shows the signup form in the browser. }.
}
* ROUTES {
** api-routes.js { contains routes for signing in, logging out, and getting users specific data to be displayed client-side z}.
** html-routes.js { routes that check whether the user is signed in, whether the user already has an account etc, and sends them to the correct HTML page }.
}
* server.js { requires packages, sets up PORT, creates express and middleware, creates routes and syncs database/logs message in terminal on successful connection to server };
* package.json { contains all package info, node modules used, version info etc }.