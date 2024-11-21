
# User Management Screen - UI Specification

## Overview

This document specifies the requirements and behaviors for the **User Management Screen**, designed for managing user accounts. Developers should use this document to implement the UI as per the described functionalities.

---

## Page Components

### 1. **Toolbar**
- **+ New User Button**:
  - Adds a new user by displaying the "New User" form on the right.
- **Hide Disabled User Checkbox**:
  - When checked, filters out users whose "Enabled" status is `false` in the user list.

### 2. **User List Table**
- **Columns**:
  1. **ID**: Unique identifier of the user.
  2. **User Name**: The username of the user.
  3. **Email**: User's email address.
  4. **Enabled**: Boolean status indicating whether the user is active.

- **Behaviors**:
  - **Sorting**: Each column is sortable by clicking the header.
  - **Filtering**: 
    - By default, the table shows only enabled users (when the "Hide Disabled User" checkbox is checked). 
    - If unchecked, all users are displayed.

### 3. **New User Form**
Located on the right-hand side, the form contains the following fields:

- **Username**:
  - Textbox input for the user's unique identifier.
  - Required.
- **Display Name**:
  - Textbox input for the user's full name or display name.
  - Optional.
- **Phone**:
  - Textbox input for the user's phone number.
  - Optional.
- **Email**:
  - Textbox input for the user's email address.
  - Required and must be in valid email format.
- **User Roles**:
  - Dropdown allowing multiple selections of roles.
  - Available Roles: Guest, Admin, SuperAdmin.
  - At least one role must be selected.
- **Enabled Checkbox**:
  - A checkbox indicating whether the user is active.

- **Save User Button**:
  - Saves the user and updates the user list.
  - Validates all fields before saving.

---

## Initial State
1. **User List Table**:
   - Displays all active users (`Enabled: true`).
   - Columns sorted alphabetically by **User Name** by default.
2. **New User Form**:
   - All fields are empty, and the checkbox is unchecked.

---

## User Interactions

### Adding a New User
1. Click **+ New User** to open the form.
2. Fill in the required fields.
3. Click **Save User**:
   - On success: User is added to the list.
   - On failure: An error message is displayed.

### Editing an Existing User
1. Click a user in the table.
2. The form is populated with the user's data.
3. Make necessary edits and click **Save User**.

### Filtering Users
1. Toggle the **Hide Disabled User** checkbox to show/hide disabled users.

---

## Validation Rules
1. **Username**: Cannot be empty.
2. **Email**: Must be a valid email address.
3. **User Roles**: At least one role must be selected.

---

## Error Handling
- **Validation Errors**:
  - Highlight fields with errors.
  - Display error messages below respective fields.
- **Save Errors**:
  - Show a toast notification for system errors.

---

## Notes for Developers
- Use responsive design principles to ensure compatibility across devices.
- Ensure that all fields are accessible via keyboard and screen readers.
- Implement API integrations for user data retrieval and modifications.
