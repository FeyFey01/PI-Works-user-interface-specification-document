# User Interface Specification Document

## User Management Screen

## 1. Initial Page Display

When the User Management Screen is opened:

* The **user list table** is displayed on the left side
* Existing users are loaded and shown immediately
* The **Hide Disabled User** checkbox is selected by default
* The **New User** form on the right side is empty
* No user is selected initially

---

## 2. Page Layout

The screen is divided into two main sections.

### 2.1 Left Section

* User list table
* **New User** button
* **Hide Disabled User** checkbox

### 2.2 Right Section

* New User form
* **Save User** button

---

## 3. UI Components

### 3.1 New User Button

* **Label:** `+ New User`
* **Location:** Top-left of the screen

#### Behavior

* Clears the user form on the right side
* Prepares the form for entering new user information
* Creates a **test user** and adds it to the user list table on the left

**Test user data:**

* Username: `Test User`
* Email: `testuser@piworks.net`
* Enabled: `true`
* Role: `Guest`

---

### 3.2 Hide Disabled User Checkbox

* **Label:** `Hide Disabled User`
* **Default State:** Checked

#### Behavior

* When checked:

  * Only enabled users are displayed in the user list
* When unchecked:

  * Both enabled and disabled users are displayed
* The user list updates immediately without a page reload

---

### 3.3 User List Table

The user list displays existing users in a tabular format.

#### Columns

| Column Name | Description             |
| ----------- | ----------------------- |
| ID          | Unique user identifier  |
| User Name   | Username of the user    |
| Email       | User’s email address    |
| Enabled     | Shows `true` or `false` |

#### Behavior

* Table data is read-only
* Users are displayed based on the state of the **Hide Disabled User** checkbox
* Table supports vertical scrolling
* Each row represents a single user

---

## 4. New User Form

The New User form is displayed on the right side of the screen.

### 4.1 Input Fields

| Field        | Type     | Description                |
| ------------ | -------- | -------------------------- |
| Username     | Text     | Unique username            |
| Display Name | Text     | Name shown in the system   |
| Phone        | Text     | User phone number          |
| Email        | Text     | User email address         |
| User Roles   | Dropdown | Guest / Admin / SuperAdmin |
| Enabled      | Checkbox | User active status         |

---

### 4.2 User Roles Dropdown

* Only one role can be selected
* Available options:

  * Guest
  * Admin
  * SuperAdmin

---

### 4.3 Enabled Checkbox

* When checked, the user is created as enabled
* When unchecked, the user is created as disabled

---

## 5. Save User Button

* **Label:** `Save User`
* **Location:** Top-right of the screen

### Behavior

* The button is disabled until at least one field value is changed and all required fields are non-empty.
* The button becomes enabled when all required conditions are satisfied.
* Form validation is done when the button is used.

---

## 6. Non-Functional Requirements

* The screen should be responsive for desktop resolutions
* UI actions should respond within 1 second
* No page reloads should be needed for filtering or form actions

---
