# View Calendar

## class ViewCalendar

### def showDate
	- Input: Date date
	- call delete_meeting_list to clear table
	- convert input pyqt5 Date to python Date
	- query database to get Meeting instances associated with date and ViewCalendar.user
	- populate table with meeting name and times

### def translate_timeslot
	- Input TimeSlot ts
	- translates ts to int
	- due to a quirk of Enum in sqlalchemy, have to try to translate both by enumerated key and enumerated value of TimeSlotEnum
	- returns int

### def show_time
	- Input list[int] times
	- translates first and final index of times into str like: [0,1] ==> "9:00 am - 9:30 am"
	- returns str


### def delete_meeting_list
	- Input: None
	- clears table ui