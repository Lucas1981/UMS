# UMS - January 2016
# ==================
#
# 20-01-2016
# ----------

# The story so far: Login management is quite easy, but I don't know if my method is ideal. The way I do it now: There is
# always a login screen on load. It gets shown (or, rather, hidden), depending on a login flag. When the flag is down,
# you see the login screen and you need to log in. When the flag is up, the login screen is lifted and you can go ahead.
# Big problem with this is that there are no sessions like PHP uses. Could be that this is a backend-only thing. Could be
# that Angular has a server-side version of session control. That would help a lot.
# 
# The user management system is actually easier. You list all the users and any extra data you want to give. You give all
# of the users a link with a $routeParam parameter, and then you click on it and index to the right user details. You can
# even add a new one (although now that's not saved to any database, so it's local). The trouble starts when you want to
# edit a user. Why? Because what do you edit? Do you bind the data of the actual user to the edit fields? That would be a
# destructive way of editing a user's data, because locally it's already stored. So do you make a copy of the initial
# settings, load these in the view, and either write or discard the settings depending on what the user editor decides 
# to do? How best to make a snapshot then? Also, the scope of the controller is not in the configurator. So if you want
# to make a snapshot of the current situation, how would you do that? Do you copy all attributes by hand or are there more
# elegant solutions to it?
#
# Initial
# -------
#
# So, this is a long term project where I want to put everything together I know from Angular, backend (in PHP/MySQL)
# and all the program logic I can think of. However, let's take it one step at a time and not try to build the best
# User Management System in the world (whatever that is) but just build á UMS. That should be enough to begin with.
#
# I think I can split the whole thing up in a couple of steps:
#
# 1. First and foremost a login function. You want to see a screen, you can't see it. You are redirected to the login.
# You log in (probably no backend at first). And boom you get to see the pretty page. You log out, your session is killed.
# Then you go back to the login screen again. Get all that out of the way. There's a lot more to this, like forgetting
# your password, registering, yadda yadda. But these first few steps are good for now.
#
# 2. User display. I just want a few things: A tab called "users" in the sidebar menu. Seeing all users in a row. Being
# able to click on the users individually. That's it really.
#
# 3. User management. I want to be able to add, change and delete users from a database. Also nice if the users can have a
# little avatar and then the total of users is displayed as a grid.
#
# 4. User interaction. Would be nice to have PM and chat. Very very simple though.
#
# 5. Notifications. Someone sends you a private message or a chat, you get a notification.
#
# 6. Search and sort users.
#
# That's all for now.
#