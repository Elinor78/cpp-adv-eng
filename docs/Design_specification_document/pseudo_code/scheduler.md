# Scheduler

## class Scheduler

### def \_set_button
	- Input: PushButton button
	- sets the selected button to background color of lightsalmon

### def is_admin
	- Input: None
	- return value of Scheduler.user.is_admin
	- returns boolean

### def showDailySchedule
	- Input: None
	- call _set_button on Scheduler.view_daily_schedule_button
	- call DailySchedule with Scheduler.user

### def showScheduleMeeting
	- Input: None
	- call _set_button on Scheduler.schedule_meeting_button
	- call ScheduleMeeting with Scheduler.user

### def showViewCalendar
	- Input: None
	- call _set_button on Scheduler.view_calendar_button
	- call ViewCalendar with Scheduler.user

### def showProfile
	- Input: None
	- call _set_button on Scheduler.view_profile_button
	- call ViewProfile with Scheduler.user

### def showNotifications
	- Input: None
	- call _set_button on Scheduler.view_notifications_button
	- call ViewNotifications with Scheduler.user

### def showLogout
	- Input: None
	- call _set_button on Scheduler.logout_button
	- call Logout with Scheduler.user

### def showManageRooms
	- Input: None
	- call _set_button on Scheduler.manage_rooms_button
	- call ManageRooms with Scheduler.user

### def showManageUsers
	- Input: None
	- call _set_button on Scheduler.manage_users_button
	- call ManageUsers with Scheduler.user
