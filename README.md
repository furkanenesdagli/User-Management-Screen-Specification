# User Management Screen Specification

## Overview
This document specifies the user interface for the User Management Screen. It includes the requirements, UI components, behaviors, and initial state when the user accesses the screen.

## Requirements
- Display a list of users with their details.
- Allow adding a new user.
- Allow editing an existing user.
- Enable or disable users.
- Hide disabled users.
- Save user information.

## UI Components

### Main Components
1. **User List Table**
   - Columns: ID, User Name, Email, Enabled
   - Features:
     - Sortable columns
     - Checkbox to hide disabled users

2. **New User Form**
   - Fields:
     - Username (Text input)
     - Display Name (Text input)
     - Phone (Text input)
     - Email (Text input)
     - User Roles (Dropdown selection with multiple options: Guest, Admin, SuperAdmin)
     - Enabled (Checkbox)
   - Buttons:
     - Save User

3. **Buttons**
   - `+ New User` button to add a new user.
   - `Save User` button to save user information.

### User List Table

#### Columns
- **ID**: Unique identifier for the user.
- **User Name**: The username of the user.
- **Email**: The email address of the user.
- **Enabled**: Boolean value indicating if the user is enabled or disabled.

#### Features
- **Hide Disabled Users**: Checkbox to filter out disabled users from the list.
- **Sortable Columns**: Clicking on the column headers should sort the list based on that column.

### New User Form

#### Fields
- **Username**: A required text input for the user's username.
- **Display Name**: A text input for the user's display name.
- **Phone**: A text input for the user's phone number.
- **Email**: A required text input for the user's email address.
- **User Roles**: A dropdown allowing selection of multiple user roles. Available options are:
  - Guest
  - Admin
  - SuperAdmin
- **Enabled**: A checkbox to indicate if the user is enabled.

#### Buttons
- **Save User**: Saves the user information entered in the form.

## Behavior

### On Page Load
- Display the list of all users with columns ID, User Name, Email, and Enabled.
- The list should be sorted by ID by default.
- The `Hide Disabled User` checkbox should be unchecked.
- The `New User` form should be empty and hidden by default.

### Adding a New User
- When the `+ New User` button is clicked:
  - The `New User` form should be displayed.
  - The form fields should be empty.
- When the `Save User` button is clicked:
  - Validate that required fields (Username, Email) are not empty.
  - Save the new user information.
  - Add the new user to the user list.
  - Clear the form fields.

### Editing an Existing User
- When a user row is clicked in the user list:
  - Populate the `New User` form with the user's current information.
  - Change the `Save User` button text to `Update User`.
- When the `Save User` button is clicked:
  - Validate the fields.
  - Save the updated user information.
  - Update the user list with the new information.
  - Clear the form fields and hide the form.

### Hiding Disabled Users
- When the `Hide Disabled User` checkbox is checked:
  - Filter out the disabled users from the list.
- When the `Hide Disabled User` checkbox is unchecked:
  - Display all users, including the disabled ones.
