# Preliminary Database Design

## Entities

Currently, seven database entities are planned:
- Employee
- Department
- Meeting
- EmployeeMeeting
- Room
- TimeBlock
- TimeSlot

### Employee
The Employee entity is comprised of personal information (first name, last name, etc), as well username and password. Additionally, there is a boolean is_admin key to allow for functionality permissions.
Employee is in a many to one relationship with Department and in a many to many relationship with Meeting through EmployeeMetting.

### Department
The Department entity is comprised of the name of the department. Department is in a one to many relationship with Employee.

### Employee Meeting
The EmpoyeeMeeting entity is comprised of foreign keys to Employee and Meeting. It is a bridge between the two entities. Additionally, it contains the is_pending and is_accepted booleans that determine notifications for users.

### Meeting 
The Meeting entity is comprised of foreign keys to Room and Employee (owner). It also contains the date of the meeting.

### Room
The Room entity is comprised of building and room number. Room is in a one to many relationship with Meeting.

### TimeBlock
The TimeBlock entity is comprised of foreign keys to Meeting and TimeSlot. It is a bridge between the 2 entities.

### TimeSlot
The TimeSlot entity is comprised of begin_time. It is an enumerated entity, which will be created on database creation and then cannot be written to by users of the system. It will enumerate all possible time slots within a day. This will enable efficient checks for schedule availability.

## Technology

Currently we are planning to use SQLite3, which is a low profile relational database. 
