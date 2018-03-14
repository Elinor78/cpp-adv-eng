# View Profile

## class ViewProfile

### def save
	- Input: None
	- check that user input email and telephone are in corrent format
	- call database to update Employee instance with user input

### def change_password
	- Input: None
	- call ChangePassword ui

### def \_check_email
	- Input: None
	- use regex pattern to validate email user input
	- raise exception if email does not match regex pattern

### def \_check_telephone
	- Input: None
	- use regex pattern to validate telephone user input
	- raise exception if telephone does not match regex pattern

## class ChangePassword

### def change
	- Input: None
	- get user input for password 1 and password 2
	- call database to update Employee instance with new password
	- raises exception if either input is empty string
	- raises exception if inputs not equal