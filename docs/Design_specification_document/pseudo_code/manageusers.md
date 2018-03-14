# Manage Users

## ManageUsers

### def showAddUser
	- Inputs: None
	- call AddUser ui

### def populate_user_list
	- Inputs: None
	- get all Employee instances from database
	- populate table with Employee data

### def delete_user_list
	- Inputs: None
	- clear table

### def showGeneratePassword
	- Inputs: None
	- get index of button
	- call GeneratePassword ui with index

### def showDeleteUser
	- Inputs: None
	- get index of button
	- call DeleteUser ui with index

## class AddUser

### def save_user
	- Inputs: None
	- get username and password from user input
	- create user in the database
	- deletes and repopulates user list
	- raises exception if username or password not entered
	- raises exception if username already exists in database

### def \_check_username
	- Inputs: str username
	- checks the username is in the database
	- returns boolean

### def cancel
	- Inputs: None
	- close popup

### def generate_password
	- Inputs: None
	- generate 10 digit alphanumeric random password
	- set text on password input box

## class DeleteUser

### def delete_user
	- Inputs: None
	- delete user from database
	- delete and repopulate user table

### def cancel
	- Inputs: None
	- close popup

## class GeneratePassword

### def generate
	- Inputs: None
	- generate 10 digit alphanumeric random password
	- set password to GeneratePassword.employee
	- update GeneratePassword.employee in the database
	- delete and repopulate user table 
	- raises exception if there is a database integrity error

### def cancel
	- Input: None
	- close popup

