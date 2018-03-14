# View Notifications

## class ViewNotifications

### def populate_meetings


### def translate_timeslot
	- Input: TimeSlot ts
	- translates ts to int
	- due to a quirk of Enum in sqlalchemy, have to try to translate both by enumerated key and enumerated value of TimeSlotEnum
	- returns int

### def accept_decline
	- Input: None
	- get index of button pressed
	- call AcceptMeeting with EmployeeMeeting instance at index

### def cancel_meeting
	- Input: None
	- get index of button pressed
	- call CancelMeeting with EmployeeMeeting instance at index

### def show_time
	- Input list[int] times
	- translates first and final index of times into str like: [0,1] ==> "9:00 am - 9:30 am"
	- returns str

## class CancelMeeting

### def cancel
	- Input: None
	- delete CancelMeeting.meeting from database
	- call ViewNotifications.populate_meetings
	- close popup

### def keep
	- Input: None
	- close popup

## class AcceptMeeting

### def accept
	- Input: None
	- call database with accept_meeting and AcceptMeeting.employee_meeting
	- call ViewNotifications.populate_meetings
	- close popup 

### def decline
	- Input: None
	- call database with decline_meeting and AcceptMeeting.employee_meeting
	- call ViewNotifications.populate_meetings
	- close popup 

