# Manage rooms

## class ManageRooms

### def showAddRoom
	- Input: None
	- call AddRoom ui

### def populate_room_list
	- Input: None
	- get all Room instances from database
	- populate table with Room data

### def delete_room_list
	- Input: None
	- clear contents of the table

### def showEditRoom
	- Input: None
	- get index of edit button
	- call DeleteRoom ui with index

## class AddRoom

### def cancel
	- Input: None
	- close popup

### def save_room
	- Input: None
	- get user input
	- call integer validation on number, building, capacity
	- create room in database
	- delete and repopulate room list on ui
	- raises exception if a data integrity error occurs

### def validate_is_int
	- Input: int input, str field
	- checks that input is an integer
	- raises exception if input is not an integer

## class DeleteRoom

### def delete_room
	- Input: None
	- deletes self.room from database
	- deletes and repopulates table in ui

### def cancel
	- Input: None
	- close popup

## class EditRoom

### def cancel
	- Input: None
	- close popup

### def save_room
	- Input: None
	- get user input
	- call integer validation on number, building, capacity
	- update room in database
	- delete and repopulate room list on ui
	- raises exception if a data integrity error occurs

### def validate_is_int
	- Input: int input, str field
	- checks that input is an integer
	- raises exception if input is not an integer
