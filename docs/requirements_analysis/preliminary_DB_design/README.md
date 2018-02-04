# Preliminary Database Design

## Entities

Currently, seven database entities are planned:
- Employee
- Department
- Room
- TimeBlock
- TimeSlot
- EmployeeTimeBlock
- RoomTimeBlock

### Employee
The Employee entity is comprised of personal information (first name, last name, etc), as well username and password. Additionally, there is a boolean is_admin key to allow for functionality permissions.
Employee is in a many to one relationship with Department and in a many to many relationship with TimeBlock through EmployeeTimeBlock.

### Department
The Department entity is comprised of the name of the department. Department is in a one to many relationship with Employee.

### Room
The Room entity is comprised of building and room number. Room is in a many to many relationship with TimeBlock through RoomTimeBlock.

### TimeBlock
The TimeBlock entity is comprised of employee, time_slot, and date. TimeBlock is in a many to many relationship with Employee through EmployeeTimeBlock, in a many to many relationship with room through RoomTimeBlock, and in a one to many relationship with TimeSlot.

### TimeSlot
The TimeSlot entity is comprised of name. It is an enumerated entity, which will be created on database creation and then cannot be written to by users of the system. It will enumerate all possibly time slots within a day. This will enable efficient checks for schedule availability.

### EmployeeTimeBlock
The EmployeeTimeBlock entity is comprised of foreign keys to Employee and TimeBlock. It is a bridge table between the 2 entities.

### RoomTimeBlock 
The RoomTimeBlock entity is comprised of foreign keys to Room and TimeBlock. It is a bridge table between the 2 entities.
