# Use Case Scenarios

## Admin User use cases

### Admin deletes room
  - In admin only interface
  - Admin selects room to delete
  - Admin deletes room and is supplied with a modal popup to confirm deletion
  - Room is deleted from the database along with all associated meetings
  - Admin is redirected to Room list with room deleted
  
### Admin creates room
 - In admin only interface
 - Admin selects room from room list
 - Admin is taken to room view
 - Admin inputs room information (building and number)
 - Admin saves room
 - Room is added to the database
 - Admin is redirected to room list with new room added
 
### Admin modifies room
 - In admin only interface
 - Admin selects room from room list
 - Admin is taken to room view
 - Admin inputs room information
 - Admin saves room
 - Room is updated in the database
 - Admin is redirected to room list 
 
### Admin views rooms
 - In admin only interface
 - Admin views list of available rooms 
 - list view contains room view, select, delete and create functionality
 
### Admin creates user
 - In admin only interface
 - Admin inputs Employee user information (only username and password)
 - Admin saves Employee
 - Employee added to database
 - Admin is redirected to Employee list with new Employee added
 - Admin must use outside tools to convey the username and password to the new Employee user
 
### Admin deletes user
 - In admin only interface
 - Admin selects Employee from Employee list
 - Admin is taken to Employee view
 - Admin deletes Employee
 - Employee is deleted from database, along with all owned meetings and is removed from meetings he/she was attending
 - Admin is redirected to Employee list
 
### Admin resets user password
 - In admin only interface
 - Admin selects Employee from Employee list
 - Admin is taken to Employee view
 - Admin selects reset password
 - Admin is take to reset password view
 - Admin resets password for that Employee
 - Employee is updated in the database
 - Admin is redirected to Employee list with new Employee added
 - Admin must use outside tools to convey the new password to the Employee
 
## Employee User use cases

###
