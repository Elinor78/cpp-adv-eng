# Preliminary Database Design

## Entities

Currently, four database entities are planned:
- Employee
- Department
- TimeBlock
- TimeSlot

### Employee
The Employee entity is comprised of personal information (first name, last name, etc), as well username and password. Additionally, there is a boolean is_admin key to allow for functionality permissions.
Employee is in a many to one relationship with Department and in a one to may relationship with TimeBlock.

### Department
The Department entity is comprised of the name of the department. Department is in a one to many relationship with Employee.

### TimeBlock
The TimeBlock entity is comprised of employee, time_slot, and date. TimeBlock is in a many to one relationship with Employee and in a one to many relationship with TimeSlot.

### TimeSlot
The TimeSlot entity is comprised of name. It is an enumerated entity, which will be created on database creation and then cannot be written to by users of the system. It will enumerate all possibly time slots within a day. This will enable efficient checks for schedule availability.
