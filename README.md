# project2 - [CropCircle](https://project2-cropcircle.herokuapp.com/coding)

## Introduction
CropCircle is a small group collaboration for the coding bootcamp at UNCC. It is a means of learning new material, practicing old material and showing off to potential employers the skills and abilities of the group members. CropCircle is a fully functioning forum that allows clients to create a unique username and join loose discussions covering different topics.

## Authors
- Gregory Desmarais
- Bradley Cordle
- Charles Danner
- Dylan Trimble

## Technologies Used
- node.js
- mysql2 npm
- sequelize npm
- jwt (JSON Web Token) npm
- express npm
- express-handlebars npm
- bcrypt npm
- BootStrap
- JQuery

## How it works!
CropCircle uses Express.js as the server for handling different HTTP requests as well as handlebars as the template engine to divvy out different pages. The navbar and footer for the site are partials that, while the body of the different pages are different rendered handlebars pages. The homepage, comment section and category pages all have different handlebars templates. 

CropCircle is an open website that is meant to be surfed and read by anyone and everyone. It is not neccessary for users to create their own accounts in order to use the site in this way. However; in order for users to make posts or comments it is required for them to create an account. The reason for this is two fold. First, there is front end javascript in place to redirect users that are not logged in to the log in modal if they try to make a comment or a post. In case a bug were to happen or some unforseen circumstance that allowed a user to accidentally bypass this, the server is looking for a valid JSON webtoken inside the header of each put or post HTTP request coming into the server (with the exception of users logging in or signing up). The jwt node module has its own validation function that can check to make sure the value being sent is a valid JSON web token or not. If the request contains an invalid web token or no web token at all, then the server will respond with a status of 403. This will let the client know that the URL endpoint they are trying to access is off limits for them. 

When users sign up for the site, their passwords are encrypted using the node module bcrypt. This is an extra layer of protection for our users. It allows users to confidently know that their password will not be compromised.

When users first use the site, they will notice that their is a favorites drop down in the navbar. This lets users easily move from one category to the other without having to type the names of the different categories into the search bar. When users are logged in, they can change this favorites drop down to fit their own interests. Users can unfollow different boards as well as follow ones that are not in the default selection. This lets users customize their own experiences and only have the things that they are interested in be a part of their experience. 

The main content of CropCircles is the ideas of and communication between the different users. CropCircle is simply a means for which they can communicate in an efficient manner. 

The server will then query the database to return all posts for that category.  

### Link to video demo of site in action: 
https://github.com/charlesdanner/project2/raw/master/video/Screen%20Recording.wmv

### Link to site: 
Example: [https://project2-project-boogaloo.herokuapp.com/coding](https://project2-cropcircle.herokuapp.com/coding).

