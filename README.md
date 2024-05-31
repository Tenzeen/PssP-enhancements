# Patient Self Service Portal Enhancements

## HHA 504 // Week 11 // Assignment 9

In this repository, we build upon our previous iteration of our patient self-service portal with new functionality, particularly account registration and login capability.

## New Features

- **Redesigned Landing Page and "Company Name"**
  - Sign Up and Log In buttons
- **Three Different Account Types**
  - Patient
  - Care Provider
  - Admin
- **Restricted Viewing by MRN for Patient Accounts**
- **Patient Editing and Deleting Functionalities for Admins and Care Providers**
- **New Table `patient_portal.production_accounts`**
  - Account information tab
  - Account email and username edit functionality

## Database Setup

In order to enable registering and logging in, we first need to create a table `production_accounts` in the database `patient_portal` to hold this information. This table's fields include:
- Usernames
- Emails
- Passwords
- Account Types
- Date Created
- Date Last Logged In

The MySQL script for creating and inserting an admin account into the table is located at `./scripts_mysql/userTable.sql`.

## Frontend Enhancements

To redesign our landing page, we revisit Bootstrap to look for a template to edit. We settle for Bootstrap's Jumbotron and apply a background image style to its container and edit the text to be more appropriate for an up-and-coming health portal. We also rename the portal **Bethesda Health Portal**.

## Backend Enhancements

### Account Types

To add a new account type `care_provider`, we create a new API endpoint in `app.py` for `register_care_provider`, as well as a new `register_care_provider.html`.

### Account Editing

In order to apply edit functionality for an account's usernames and emails, we add a `<td>` below existing account fields in `account.html` and make all fields besides email and username `readonly`. We also create a new API endpoint called `/update_account`.
