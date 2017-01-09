# Mosiac
#### by Affirmative Action
## Description
A visual, social media platform with an emphasis on just the art itself.

## Instructions
### Step 1: Install gems
  	In the terminal, type
     		% bundle
  
  The following gems were used:
  
 - bootstrap
 - bcrypt
 - faker
 - paginate
 - act_as_votable
 - carrierwave
 
### Step 2: Raking and running
	First, create the database (this is likely unnecessary although advised)
		% rake db:migrate
	Then run the server
		% rails s

### Step 3: Viewing our website
    In a browser, go to
        % localhost:3000

### Note
	If the gem, 'postgres' doesn't work (as it continued to give us problems through our development), we found using 
		% sudo apt-get install libpq-dev
	and then going through the above steps again circumvented the problem.

## User Guide

 - Start off by creating an account. All you have to do is provide us with you name, email, and password (no account validation so you can get started right off the bat!)
 - Customize your avatar (using Gravatar)! Make it something cool and unique
 - Start following people to populate your feed
 - Make posts: these will appear on your feed and profile view
 - Click the like button to like another person's work

## Features

Our platform has tons of great features! With Mosiac you can:

 - Upload Music
 - Upload Pictures and Paintings
 - Post short stories, poems, and other pieces of writing
 - Follow your artistic companions
 - Like other people's work
 - A feed to keep you updated with all the latest work

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
 > belongs_to :user, acts_as_votable
attr_accessor to Audio and Picture Uploader

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
 > defines upvote, create and destroy (but only by the correct user)

 - sessions/ relationships
 > defines create and destroy

 - user
 > defines following, followers, show, new, edit and create

 - static_page
 > checks if user is logged in, session's view

## Contributions

	Omar: User Profile, Presenter
	Alexandre: Back-end Designer, Presenter
	Jordan: File Management, Presenter
	Osman: Front-end Designer
