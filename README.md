# homework-week14
the objective of this homework is to go through give codes and try to explain what the codes in different files do.  below is my take on things...


server.js is the starting point. before server.js can be run, "passport_demo" has to be generated in mysql workbench. line 15 of server.js exposes the contents of public folder to any middleware functions that may need to use them. line 19 use express session to store sessions id on the server side.  this session id can be referenced and making pulling up data associated with the client more efficient in later session. lines 22 and 23 import files with routes defined.  the last part of server.js syncs the database and tells the server to listen on port 8080.

config folder

passport.js defines the format of logins.  in this case, email is expected instead of username. email and password are authenicated here. the middleware functioin defined in isAuthenicated.js resticts users from accessing the page if they are not logged in.  config.json file defines the database used and set username and password for the database.

index.js defines the path to the database and the db object. user.js defines how Sequalize should create a table. the password enterned by the user is hashed then stored in the database table created by Sequalize.

public folder

this folder contains the different html pages along with corresponding javascript codes to run the html pages. signup.js posts users' credentials to the database.  login.js compares the credentials entered by user to those in the database.  if the entered set matches any set in the database, access is granted.  if that happens, the user will be taken to members page, where the user is welcomed with some sort of message.

routes folder

api-routes.js defines different routes for the three different html pages. there is local authentication for logins.  if the user already has credentials in the database, the use is routed the members page.  there is also a logout function defined in this file. when the user logs out, the user is routed to the login page.  html-routes.js also defines the different routs. the user is restricted from accessing members page with out proper credential.

