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

### Employee creates a new meeting
 - From home page, Employee selects "New Meeting"
 - Employee is redirected to new meeting view
 - Employee selects a name for the meeting
 - Employee selects a date for the meeting
 - schedule table is populated with blocked and available times for Employee on that date
 - Employee selects room from a dropdown
 - schedule table is populated with blocked and availble times for room on that date
 - Employee selects zero or more employees with a modal search
 - schedule table is updated with selected Employees
    - schedule table includes all time slots for the date
    - schedule table shows blocked and availble times for all selected users, as well as room
    - the top row is for selection (checkboxes under time slots)
    - if not all attendees/room are available for that time slot, checkbox is greyed and unable to be selected
 - Employee selects time when all selected attendees and room are available
 - Employee saves meeting
 - Meeting is added to the database, Employee is set to owner and attendee, owner's EmployeeMeeting is set to accepted=True and pending=False, all others are set to accepted=False and pending=True
 - Employee is redirected to home page
 - Notifications are sent to all attendees with status and meeting info
 
 #### Exceptions / Caveats
  - If Employee attempts to select room or attendees without first selecting date, an error is generated
  - If Empploye attempts to select attendees without first selecting date and room, an error is generated
  - Schedule conflicts are avoided by making it impossible to select a time that is not available for all attendees and room
  - The form and logic allows Employee to schedule meetings with only him or herself as an attendee, which allows for blocking out time. 
  - If an Employee attempts to save the meeting without a name, an error is generated
  - Once an Employee has begun selecting times for the meeting, the room, date and attendees cannot be changed. 

### Employee modifies a meeting
 - Employee must be the owner of a meeting to modify it
 - from home page, Employee selects Modify Meeting
 - Employee is redirected to owned meeting view
 - Employee selects meeting from a drop down of owned meetings
 - schedule table with populated room and attendees is displayed
 - Button with "Modify Meeting" is enabled (and Cancel Meeting)
 - If Employee clicks "Modify Meeting" a modal popup appears that asks if they are sure they want to do this, as the current meeting with be deleted and a new one will be created
 - If Employee clicks yes, meeting is deleted and Employee is redirected to "Create new meeting" page
 - "Create new meeting" page is populated with only the meeting name. All other fields must be filled in by Employee as in above use case
 - Notifications are sent to all attendees that the meeting was deleted and may be rescheduled

### Employee cancels a meeting
 - Employee must be the owner of a meeting to cancel it
 - from home page, Employee selects Cancel Meeting
 - Employee is redirected to owned meeting view
 - Employee selects meeting from a drop down of owned meetings
 - schedule table with populated room and attendees is displayed
 - Button with "Cancel Meeting" is enabled (and Modify Meeting)
 - If Employee clicks "Cancel Meeting" a modal popup appears that asks if they want to proceed
 - If Employee clicks yes, meeting is deleted and Employee remains on owned meeting view
 - Meeting is deleted from database
 - Notifications are sent to all attendees that meeting was deleted

### Employee Accepts a meeting
- From home page, Employee navigates to notifications tab
- Notifications view displays a list of notifications
  - Notifications are determined by EmployeeMeeting - if there are any pending=True, accepted=False, they are displayed
- Employee selects a meeting
- Employee is brought to meeting view, which includes meeting name, date, time owner, and attendees
- Employee selects "Accept" Button
- EmployeeMeeting.pending = False and .accepted = True are set in database

### Employee Declines a meeting
- From home page, Employee navigates to notifications tab
- Notifications view displays a list of notifications
  - Notifications are determined by EmployeeMeeting - if there are any pending=True, accepted=False, they are displayed
- Employee selects a meeting
- Employee is brought to meeting view, which includes meeting name, date, time owner, and attendees
- Employee selects "Decline" Button
- EmployeeMeeting.pending = False and .accepted = False are set in database


# Employee views schedule:
- Employee can view all meetings for the day (pending, accepted, owned).
- If meeting is owned, owner can click on the meeting to modify or cancel it. This will then follow the “Modify Meeting” or “Cancel Meeting” use case from "Employee is redirected to owned meeting view"
- If meeting is pending, attendee can click the meeting to accept or decline it. This will then follow the “Accept/Decline Meeting” use case.
- If meeting is accepted (not owned), attendee can click the meeting to accept or decline it. This will then follow the “Accept Meeting" or "Decline Meeting” use case from "Employee is brought to meeting view, which includes meeting name, date, time owner, and attendees".
- Employee can create a new meeting to update their schedule to set blocks of time to unavailable. This will update the employee schedule and not allow meetings to be scheduled during that time.


