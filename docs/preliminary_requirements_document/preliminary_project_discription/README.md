# Preliminary Project Description

The purpose of this document is to give a preliminary description of the scheduling project.

## Customer Description

Below is the original customer description, included for completeness.

The overall aim of this project is to create a useful meeting-scheduling platform that will enable employees to quickly, easily, and effectively schedule meetings. Any employee will be able to schedule a meeting by selecting the employees they wish to invite through a user-friendly GUI interface. A time slot during which all invited employees are available will then be selected by the user, taking into consideration other meetings the employees are attending and the times they are available (thereby preventing employees from being double-booked in multiple meetings). Finally, any available meeting room that is large enough to accommodate all the invited employees at the time specified will be chosen by the user; if there is no room available for the given time and employees, then the program will inform the user of this exception. 

The employee who invited the others is considered the owner of the meeting and given the ability to modify the schedules of attendees and rooms as well as the ability to cancel or update the meeting. Any update to the meeting will result in notifications (about the changes) to all of the invited employees. Invited employees may decline or accept to attend the meeting and in either case they have to inform the meeting owner. 

Each employee will be able to see what meetings they have on any given day by viewing a calendar that displays meetings they are invited to or hosting.
Employees can update their schedules by adding/deleting/changing the contents of their time slots and selecting visible/not visible to other employees. 

Special administrative users can create employee and room records. Rooms are fully described by the administrator, while employee records are created with only a username and password. Regular employees will be able to log in, change the password, and fill in their own details including the hours of the day they are available for meetings. Administrators will have the ability to modify or delete rooms, as well as delete users or reset their password.

## End Users

The end users will be employees of the company. These employees can be divided into two roles, each with distinct responsibilites and funtionality: Employee and Admin. The roles are not mutually exclusive. An Admin is also an Employee, though an Employee may or may not be an Admin. 

All Employees will have access to the following funtionality:
- Create a meeting
- View meetings
- Accept or Decline meetings
- Update Employee Profile
- Block out time in schedule

Additionally, an Employee who has created a meeting will have access to the following functionality:
- Update meeting
- Delete meeting

Admins will have exclusive access to the following funtionality:
- Create room
- Update room
- Delete room
- Create Employee user
- Delete Employee user
- Reset Employee user’s password

## Current System

This will be a desktop application that requires login. Once an employee has logged in, pending meeting notifications will be available immediately in the notifications tab. The home page will be the view schedule page. All functionality will be presented through a master template that exists on every page to facilitate navigation. Admin functionality will be available only if the logged in user is an Admin.

The schedules of each Employee will be kept in a system wide database so that they are available to the various functions that use them. 

For simpliciy’s sake, reset password will require communication between an Admin and Employee that takes place outside the system. The mechanism of this communication is beyond the spec of this document. The reset password functionality will supply the Admin with the new password and it is his or her responsibility to convey that information to the Employee. 

Resolving scheduling conflicts will be dealt with in the following way: If an Employee creates a meeting, the time of the meeting will be blocked out on all the attendees’ schedules. No other employee will be able to schedule an attendee for a meeting that conflicts with a blocked out time. This block also extends to an Empoyee’s ability to block out time in their own schedule. The consequences of this are that a pending meeting (not yet accepted or declined by an Employee), will block out time even if it is eventually declined, but the developers feel it is a simpler and cleaner solution than allowing for pending meetings to overlap. 

Once a meeting has been accepted by an Employee, it cannot be removed from that Employee’s schedule except by the owner of the meeting deleting the meeting. In other words, decline and accept are one time only functionality. If a meeting is deleted, the block of time scheduled is freed for all attendees and the owner of the meeting. 


## Available Computing Equipment

This project will be focused on working in a Mac OSX environment. The developers will mainly be working on Mac OSX systems and the demo will be performed on a Mac OSX system.


