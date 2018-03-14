# Login

## class Login

### def handleLogin
	- Input: None
	- gets username and password from user input
	- gets Employee instance from database via username
	- if login succeeds, sets Login.user to Employee instance
	- raises exception if Login.user.password != password
	- raises exception if username not in database

### def forgot_password
	- Input: None
	- calls ForgotPassword popup

## class ForgotPassword

### def cancel_change
	- Input: None
	- closes window with no effect

### def submit_change
	- Input: None
	- gets username and email from user input
	- gets Employee instance from database via username
	- raises exception if Employee instance email does not equal user input
	- raises exception if username not in database
	