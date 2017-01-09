## Description
A simple Ruby on Rails clone of Twitter.

## Instructions
### Step 1: Install gems
  	In the terminal, type
     		% bundle
  
  The following gems were used:
  
 - bootstrap
 - bcrypt
 - faker
 - paginate
 
### Step 2: Raking and running
	First, create the database
		% rake db:migrate
	Then run the server
		% rails s

### Step 3: Viewing my website
    In a browser, go to
        % localhost:3000

### Note
	If the gem, 'postgres' doesn't work (as it initially gave me problems in my development), I found using 
		% sudo apt-get install libpq-dev
	and then going through the above steps again circumvented the problem.

## User Guide

 - Start off by creating an account. All you have to do is provide your name, email, and password (no account validation so you can get started right off the bat!)
 - Customize your avatar (using Gravatar)
 - Start following people to populate your feed
 - Make posts: these will appear on your feed and profile view

## (Notable) Documentation

### Model

 - User
 > validates all user authentication
has_many :following
has_many :followers
has_many :microposts
defines user's feed

 - Relationship
 > belongs_to :follower, belongs_to :followed
 
 - Micropost
 > belongs_to :user

### Views
 - Users/edit
 > change user settings

 - Users/index
 > displays all users

 - Users/show
 > user's profile page

 - Static_Pages
 > either displays home or a user's feed depending on whether they are logged in

 - Shared/micropost_form
 > seen in action underneath the user's stats in their feed; this is the different submission options and text box for posting
 
 - Shared/stats
 > displays number of posts, followers and those user follows

 - Shared/feed
 > generates feed in the home page

 - Sessions
 > new is simply for a new login session

 - Microposts
 > displays the posts themselves individually with data type

 - Layouts/header
 > used as the navbar

### Controller

 - microposts
 > create and destroy (but only by the correct user)

 - sessions/ relationships
 > defines create and destroy

 - user
 > defines following, followers, show, new, edit and create

 - static_page
 > checks if user is logged in, session's view
