# Backend

## Class EmployeeData:

### def add_employee
	- Input: str username, str password
	- creates Employee object (using sqlalchemy, assumed from now on)
	- commits Employee object to database
	- returns Employee object

### def delete_employee
	- Input: int employee_id
	- queries database for Employee via employee_id
	- deletes Employee object
	- commits deletion to database

### def delete_employee_obj
	- Input: Employee employee
	- deletes Employee object
	- commits deletion to database

### def get_employee
	- Input: int employee_id
	- queries database for Employee via employee_id
	- returns Employee object

### def get_employee_by_username
	- Input: str username
	- queries database for Employee via username
	- returns Employee object

### def get_employee_meetings
	- Input: int employee_id
	- queries database for Employee via employee_id
	- returns Meeting list associated with Employee

### def get_all_employees
	- Input: None
	- queries database for all Employees
	- returns Employee list

### def update_employee
	- Input: int employee_id, dict kwargs
	- queries database for Employee via employee_id
	- sets key-value pairs of attributes on Employee object
	- commits Employee to database
	- returns Employee instance

### def update_employee_by_obj
	- Input: Employee employee
	- commits Employee to database
	- returns Employee instance

### def check_employee_exists
	- Input: str username
	- queries database for Employee via username
	- If query returns no response, return True
	- Else, return False

### def check_username
	- Input: str username
	- queries database for Employee via username
	- If query returns only 1 response, return True
	- Else, return False


## class EmployeeMeetingData

### def get_employee_meeting
	- Input: int meeting_id, int employee_id
	- queries database for EmployeeMeeting via meeting_id and employee_id (to ensure uniqueness)
	- returns EmployeeMeeting instance

### def update_employee_meeting
	- Input: EmployeeMeeting emp_meet, dict kwargs
	- set key-value paris of attributes on EmployeeMeeting object
	- commit EmployeeMeeting to database

### def accept_meeting
	- Input: EmployeeMeeting employee_meeting
	- set employee_meeting.pending to False
	- set employee_meeting.accepted to True
	- commit EmployeeMeeting to database

### def decline_meeting
	- Input: EmployeeMeeting employee_meeting
	- set employee_meeting.pending to False
	- set employee_meeting.accepted to False
	- delete EmployeeMeeting from database

## class MeetingData

### def create_meeting
	- Input: str title, int room_id, int owner_id, Date date, list[TimeSlot] timeslots, list[Employee] employees
	- creates Meeting instance with title, room_id, owner_id, date
	- creates relational table EmployeeMeeting for Employee instance in employees
	- adds timeslots to meeting
	- commits Meeting to database
	- returns Meeting instance

### def get_meetings_by_date_and_user
	- Input: Date date, Employee employee
	- queries database for Meeting objects where Meeting.date == date, EmployeeMeeting.employee == employee, and (EmployeeMeeting.pending == True or EmployeeMeeting.accepted == True)
	- returns Meeting list

### def get_meetings_by_user
	- Input: Employee employee
	- returns Meeting list associated with employee

### def get_owned_meetings
	- Input: int owner_id
	- queries database for Meeting objects owned by owner_id
	- returns Meeting list

### def delete_meeting
	- Input: Meeting meeting
	- Deletes all EmployeeMeeting instances associated with meeting
	- Deletes meeting

## class TimeSlotData

### def get_timeslot
	- Input: int timeslot_id
	- queries database for TimeSlot instance via timeslot_id
	- returns TimeSlot instance

### def bulk_create_timeslots
	- Input: list[str] times
	- creates TimeSlot instance for time in times
	- commits TimeSlot list to database
	- returns TimeSlot list

## class RoomData

### def add_room
	- Input: str roomname, int number, int building, int capacity(optional)
	- creates Room instance via inputs
	- returns Room instance

### def get_all_rooms
	- Input: None
	- queries database for all Room instances
	- returns Room list

### def get_room_by_name
	- Input: str roomname
	- queries database for Room instance via roomname
	- returns Room instance

### def get_room_by_id
	- Input: int room_id
	- queries database for Room instance via room_id
	- returns Room instance

### def update_room_by_object
	- Input: Room room_obj
	- commits room_obj to database
	- returns room_obj

### def delete_room
	- Input: Room room
	- deletes room from database

### def get_room_meetings_by_date
	- Input: Room room, Date date
	- queries database for Meeting instances where Meeting.room == room.id and Meeting.date == date
	- returns Meeting list




