# Gitolite-Manager

## What?

Web Interface to manage Gitolite, currently it only allows you to add users and create repositories, an it lacks of CSS (for now). Written with node.

It provides a commit for each action it does so is really easy to understand. Also, once you implement this, you should never use the repo method (while this line is here and the "issue" is not solved).

**NOTE:** The way currently it manages the conf file is by rewriting it so make sure you did all right, but since this is git based you can always reverse :). And then, after all that, if anything goes wrong, check everything before asking for my head.

##TODO

* Add Groups
* Use credentials when created the user to filter access to the tools
* Add edit and delete actions for Users, Groups and repos.
* Pack it so we can just npm and be ready to use it.

## Why?

I needed a way to manage Gitolite but using the provided repo wasn't enough. I did this to let people manage it without having to pull & push and edit files and all. 

## How?

Installation goes like this:

* Set the config variables in the app.js
* Make sure a updated copy of gitolite-admin is in the path you provided
* Make sure that the user who is running this node can push the repo.
* Run the database.sql on mysql
* Manually add the Users, Repos and Groups if they already exist (Directly to the database).
   * **Note:** in the fields R, RW, RW+, owners and members in the repositories and groups tables respectively. is an "array" comma separated of their ids.. in case of a group, it is referred with an at (@). 
   *Example: "@1,3,5" refers to the group with id 1, and members with id 3 and 5.*

* **Congrats, you should be good to go, run the node and go to the URL you provided**

## Wanna Help?

Feel free to fork this, add your own stuff and if you are kind enough, do a pull request.