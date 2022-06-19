# digitaltolk


# BookingController file 

#  1
# This controller has more than 200 lines of code, 
# which makes sometimes harder for others to make changes in any code in future, its better to create
# related controllers and classes to split code into functions, also we always try to 
# limit lines of code around 100 or less.

# 2
# Always try as much as we can to make functions in controllers following laravel structure like
# index, create, store, show, edit, update, destroy -- create separate controllers for related functionality

# 3
# Validation Classes are not being used to validate requests

# 4
# Always Use Auth::user to find loggedIn user data rather than expecting token from request.
# like on line 70 --  $request->__authenticatedUser, should be Auth::user()

# 5
# Also get user id from Auth instead from request like on line 110 
# -- $request->get('user_id') should be Auth::user->id

# 6
# Responses at the end of each controller are not properly formatted, at some point its only 
# returning strings and at some point its returning data, like on line 192 and 254

# 7
# Data we get from requests always we follow specific patterns like we use snake case aur camel case, 
# this thing is not properly used


# BookingRepository file

# 1
# Same as booking controller files this repository has lots of lines of code which is 
# really hard to maintain structure.

# 2
# Lots of duplication of code is used in repository which is not good ,hard to maintain,
#  - Like mailer function code has been called many times in repo, create a separate function for mailer 
# and add code in that function and call that function anywhere you want,
#  - there anre many other place like from 137 to 140 same code has been repeated in whole function
# we can separate this code in function and call function there, these type of things are repeated in whole repo
# which is really hard to make changes in code,

# 3
# functions naming conventions is not being followed as i have suggested to keep files minimal with 
# proper naming conventions same as in controller with related repository

# 4
# Try avoiding using many if conditions, rather than writing code into if condition just return if
# required data not found

# 5
# Get admin an roles ids from database instead doing env('CUSTOMER_ROLE_ID'),

# 6
# Proper comments and functions expecting parametres are not defined

# 7
# Always use queues form sending mails,Sometimes, the Mail send process takes some time. 
# And you don't want to wait to send an email or another process on loading the server-side process



###################################################################################
                # Here is sum up regaridng coding structure
# - Always try to write code into chunks by separating code into functions and classes
#   by doing so, we can have control on our code, and its makes Unit testing easier
# - Unit test As name suggests to write test code in units rather than testing many features in single function
# - Separate data prepare logic and saving record in database in separate classes
# - The code we want to use in multiples files, create a separate class for that function 
#   and call that class and related function anywhere in app.



# I have not refactored code, I can replace little parts of code i did not do this and added comments for whole files, 
# also some functions has many lines of code so more time is needed to understand more than 2000 lines of
# code and then separate into chunks, but I have suggested by writing comments whats wrong in this code and what
# we can do write better code, I think this would be ideally enough to get an idea about my skills.
# I Always welcome new things suggestions and feedbacks and take these things as a process of learning.