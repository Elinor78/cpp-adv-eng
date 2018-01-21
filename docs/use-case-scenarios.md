# Scenario for “Create new meeting” Use Case:
- (Employee)
- Select “New Meeting” button
- Select one or more employees to attend meeting.
- Select meeting time.
- Check that all selected employees are available at that time.
- Select a room.
- Check that the room is available at the selected meeting time.
- If checks pass, send notifications to attendees 
- If checks pass, set owner meeting state to accepted and attendees meeting state to pending
- If checks pass, set owner schedule as accepted and attendees schedules as pending

## Exceptions
- If a selected employee has a pending or accepted meeting sheduled during that time slot, a notification informs the scheduler (owner) that the meeting cannot be scheduled due to employee conflicts.
- If a room is scheduled with a pending or acceted meeting during the selected time slot, a notification informs the scheduler (owner) that the meeting cannot be scheduled due to room assignment conflicts.  
- If owner attempt to schedule a meeting outside the alloted time window (from current time to a month from now), a notification informs the owner that the meeting cannot be scheduled at that time.
- If owner attempts to schedule a meeting outside the daily time window, (8 am to 5 pm), a notification informs the owner that the meeting cannot be scheduled at that time.
- If owner attempts to schedule a meeting outside the weekly time window, (Mon to Fri), a notification informs the owner that the meeting cannot be scheduled at that time.

# Scenario for “Modify Meeting” Use Case:
- (Owner only)
- Select existing meeting from owned meetings.
- Modify the meeting by inviting or removing attendees, changing room, or changing time.
- Check availability of employees and room.
- If checks pass, send notifications to attendees.
- if checks pass, set owner meeting state to accepted and attendees meeting state to pending
- If checks pass, set owner schedule as accepted and attendees schedules as pending

## Exceptions
- If a selected employee has a pending or accepted meeting sheduled during that time slot, a notification informs the scheduler (user) that the meeting cannot be scheduled due to employee conflicts.
- If a room is scheduled with a pending or acceted meeting during the selected time slot, a notification informs the scheduler (user) that the meeting cannot be scheduled due to room assignment conflicts.  
- If owner attempt to schedule a meeting outside the alloted time window (from current time to a month from now), a notification informs the owner that the meeting cannot be scheduled at that time.
- If owner attempts to schedule a meeting outside the daily time window, (8 am to 5 pm), a notification informs the owner that the meeting cannot be scheduled at that time.
- If owner attempts to schedule a meeting outside the weekly time window, (Mon to Fri), a notification informs the owner that the meeting cannot be scheduled at that time.



# Scenario for “Cancel Meeting” Use Case:
- (Owner only)
- Owner selects existing meeting from owned meetings.
- Owner cancels meeting.
- Send notifications to attendees.
- Delete meeting.
- Remove meeting from owner and attendees’ schedules.

# Scenario for “Accept/Decline Meeting” Use Case:
- (non-owner only)
- Receive notification of meeting.
- Decline or accept meeting.
- Send notification to meeting owner.
- Update meeting to reflect accept or decline. If attendee has accepted the meeting, their schedule is updated with meeting as accepted and their entry in meeting is marked as accepted. If attendee has declined the meeting, their entry in meeting is marked as declined and meeting is removed from schedule


# Scenario for “View Schedule” Use Case:
- (Employee)
- Employee can view all meetings for the day (pending, accepted, owned).
- If meeting is owned, owner can click on the meeting to modify or cancel it. This will then follow the “Modify Meeting” or “Cancel Meeting” use case.
- If meeting is pending, attendee can click the meeting to accept or decline it. This will then follow the “Accept/Decline Meeting” use case.
- If meeting is accepted (not owned), attendee can click the meeting to accept or decline it. This will then follow the “Accept/Decline Meeting” use case.
- Employee can update their schedule to set blocks of time to unavailable. This will update the employee schedule and not allow meetings to be scheduled during that time.

## Exceptions
- If employee attempts to set a block of time to unavailable outside the alloted time window (from current time to a month from now), a notification informs the employee that the block cannot be scheduled at that time.
- If employee attempts to set a block of time to unavailable outside the daily time window, (8 am to 5 pm), a notification informs the owner that the block cannot be scheduled at that time.
- If employee attempts to set a block of time to unavailable outside the weekly time window, (Mon to Fri), a notification informs the employee that the block cannot be scheduled at that time.

# Scenario for “Create Employee” Use Case:
- (Admin only)
- Enter user name and temporary password (auto gen; not known to admin)
- Notification sent to employee with username and temp password
- Save employee record

# Scenario for "Delete Employee" Use Case:
- (Admin only)
- Retrieve employee record via username
- Delete employee

# Scenario for “Create Room” Use Case:
- (Admin only)
- Enter room location, capacity, etc (fully describe)
- create room record

# Scenario for "Modify Room" Use Case:
- (Admin only)
- Retrieve room record
- Modify location, capacity, etc (fully describe)
- save room record

# Scenario for "Delete Room" Use Case:
- (Admin only)
- Retrieve room record
- delete room record

# Scenario for "Reset Password" Use Case:
- (Admin only)
- Retrieve employee record via username
- Reset password (auto gen; not known to admin)
- Notification sent to employee with username and temp password
- Save employee record

# Scenario for "Change Password" Use Case:
- (Employee)
- Select change password
- enter old password and new password
- save employee record
