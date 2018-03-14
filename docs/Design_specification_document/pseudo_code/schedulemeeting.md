# Schedule Meeting

## class ScheduleTableWidget

### def reset_table
	- Input: None
	- resets cell check box widgets on table
	- removes all rows
	- populates table with owner data 
	- populates table with room data if available
	- populates table with participant data if any

### def owner_availability
	- Input: None
	- gets availability by calling \_get_employee_meetings using ScheduleTableWidget.user
	- populates ScheduleTableWidget.user.username in table
	- populates checkboxes with user availability 

### def update_participant
	- Input: Employee participant
	- gets availability by calling _get_employee_meetings using participant
	- populates participant.username in table
	- populates checkboxes with participant availability

### def add_participant
	- Input: str username
	- Input: Employee participant
	- gets availability by calling \_get_employee_meetings using participant
	- populates participant.username in table
	- populates checkboxes with participant availability
	- raises exception if participant already in meeting
	- raises exception if username is not in database
	- raises exception if tries to add owner to meeting

### def \_check_username
	- Input: str username
	- calls EmployeeData.check_username to check if username in database
	- returns boolean

### def add_room
	- Input: Room room
	- gets availability by calling \_get_room_meetings using room
	- populates room.roomname in table
	- populates checkboxes with room availability
	- sets ScheduleTableWidget.chosen_room to room
	- raises exception if more than one room added
	- raises exception if ScheduleTableWidget.date is not set

### def \_get_room_meetings
	- Input: Room room
	- calls RoomData.get_room_meetings_by_date to get meetings
	- for all the meetings, translates meeting.timeslots into int for indexing, 
	- returns indexed times

### def \_get_employee_meetings
	- Input: Employee employee
	- calls MeetingData.get_meetings_by_date_and_user to get meetings
	- for all the meetings, translates meeting.timeslots into int for indexing, 
	- returns indexed times

### def \_update_room
	- Input: None
	- updates availability for ScheduleTableWidget.chosen_room by calling _get_room_meetings
	- populates room.roomname in table
	- populates checkboxes with room availability

## class ScheduleMeeting

### def \_add_date
	- Input: None
	- get user input for date
	- set ScheduleTableWidget.date to date
	- call ScheduleTableWidget.reset_table

### def \_add_room
	- Input: None
	- calls SearchRoom popup window

### def add_room
	- Input: str roomname
	- calls ScheduleTableWidget.add_room

### def \_add_participant
	- Input: Nont
	- call SearchParticipant popup window

### def add_participant
	- Input: str username
	- call ScheduleTableWidget.add_participant

### def save_meeting
	- Input: None
	- call ScheduleMeeting._check_times, ScheduleMeeting._check_date ScheduleMeeting._check_title check times, date and title
	- if calls pass, retrieve data from ScheduleTableWidget
	- save meeting to database
	- reset ScheduleTableWidget

### def \_check_times
	- Input: None
	- gets all checkboxes from ScheduleTableWidget
	- raises exception if times are not sequential
	- raises exception if no times are chosen
	- bulk saves times to database
	- returns TimeSlot list

### def \_check_date
	- Input: None
	- gets date from ScheduleMeeting user input
	- checks that date is in the correct range
	- raises exception if meeting is on weekend
	- raises exception if meeting is not within 14 days

### def \_check_title
	- Input: None
	- gets title from ScheduleMeeting user input
	- checks that title is not empty string
	- raises exception if title is empty string

## EmployeeSearchWidget

### get_employees
	- Input: None
	- gets all employees from database
	- populates search dropdown with employee usernames

## class SearchParticipant

### def add
	- Input: None
	- get user input (username) from EmployeeSearchWidget
	- call ScheduleMeeting.add_participant with username

## class RoomSearchWidget

### get_rooms
	- Input: None
	- gets all rooms from database
	- populates search dropdown with room names

## class SearchRoom

### def add
	- Input: None
	- gets user input (roomname) from RoomSearchWidget
	- call ScheduleMeeting.add_room with roomname

		



