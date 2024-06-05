# WePC Veterinary Management System

## Overview

WePC Veterinary Management System is a comprehensive Java-based application designed to manage various aspects of a veterinary clinic. This system includes separate interfaces for pet owners, veterinarians, and administrative employees, each with tailored functionalities. GUI and Command-Line Interface applications are available and which offer the same functionalities.

### GUI Components

- **WePCGUI**: The main entry point of the application, handling user sign-in and sign-up.
- **PetOwnerGUI**: Interface for pet owners to view pet information, appointments, and view and pay invoices.
- **VetGUI**: Interface for veterinarians to view appointments, manage them by adding, deleting treatments, and medications.
- **EmpGUI**: Interface for administrative employees to manage appointments and access detailed appointment information.

## Prerequisites

- Java Runtime Environment
- MySQL database server with the `we_pc` dump file imported
- JDBC driver for MySQL (available in the `lib` folder)

## Setup

### Preparation

1. Create the MySQL Database for this project on your computer if you don’t have it yet.
2. Open the dump file and run the SQL code to create tables, insert data, and create procedures and functions.
3. Open the Java project and connect your IDE with the `mysql-connector-j-8.2.0.jar` as a dependency.
4. Open the Java program and run `Main.java` on GUI.
5. If CLI is preferred, you may also run `we_pc.java` to start the CLI application.

### Signup as a Pet Owner User

1. Although there is already some pet owner data inside the DB, you can sign up for a new pet owner user. You can sign up a new user by clicking the Sign-Up button; at this point, you can only sign up as a pet owner user.
2. If your sign-up information is not correct, an error will show up, and you need to re-sign up.
3. When you sign up successfully by clicking the sign-up button, the username for a pet owner will automatically prepend `CUS`. For example, if you sign up with the username `user1`, when logging in, you should type `CUSuser1` as your login username.

### Log In

1. If the username starts with `CUS`, it means the user is a pet owner, and it will turn to the pet owner user page.
2. If the username starts with a number, then the user is an employee. The starting number followed by `emp` represents the clinic that the employee belongs to. For example, when the username of an employee is `01emp00008`, then this employee belongs to the clinic with ID 1.
3. If the username is an employee username, then it will check whether it is a normal employee or a vet. When it checks that the user is a vet, it will turn to the vet page; if the employee is not a vet, it will turn to the employee page.

## User Interfaces

### Pet Owner Page

#### Sample Credentials

- Username: `CUSuser1`
- Password: `password123`
- Username: `CUSuser3`
- Password: `securepass1`

#### Features

1. **View Pet Information**: Displays all pets and their information, including pet ID, name, breed, height, weight, and status.
2. **View Appointment Information**: Displays all appointments for the pet owner.
    - **View Invoice**: Displays invoice details for each appointment, including appointment ID, time, description, patient ID, pet name, clinic ID, show-up status, vet ID, vet name, and room ID.
    - **View Treatments**: Displays treatments and medications associated with the appointment.
    - **Pay for Invoice**: Allows the pet owner to pay for the invoice. The amount paid updates the received amount and date. If the paid amount exceeds the total, it adjusts accordingly.
3. **Reset Password**: Allows the pet owner to reset their password.
4. **Sign Out**: Ends the session.

### Admin Employee Page

#### Sample Credentials

- Username: `05emp00014`
- Password: `coolpet`
- Username: `01emp00011`
- Password: `jaych08`

#### Features

1. **Make an Appointment**: Checks if the schedule is available and books an appointment.
2. **Cancel an Appointment**: Cancels an existing appointment if it is not associated with any expenditure.
3. **Display All Appointments**: Shows all appointments in the clinic.
4. **Display Appointment Details**: Provides detailed information about a specific appointment.
5. **Show-up Button**: Updates the appointment status when a pet shows up, assigns a room, and updates the show-up status.

### Vet Page

#### Sample Credentials

- Username: `05emp00010`
- Password: `dogdd34`
- Username: `02emp00003`
- Password: `newmoon95`

#### Features

1. **Appointment Management**: View and select veterinary appointments.
2. **Treatment Handling**: Add, view, and delete treatments for selected appointments. Adding treatments updates the appointment invoice.
3. **Medication Management**: Add medications and view available medications for pets. Adding medications updates the invoice.
4. **Complete an Appointment**: Releases the room and marks the appointment as completed or a no-show.

## Error Handling

On the Java level, the application handles errors with incorrect inputs during user interaction using the try-catch technique.

## Authors

WePC Veterinary Management System Team
