# Student Portal Application

This comprehensive README provides an overview of a C# application designed for managing student records, capturing marks, and tracking student modules. The application utilizes a SQL database to store and retrieve data related to students, modules, marks, and user credentials for authentication.

## Table of Contents

- [Database Schema](#database-schema)
- [User Authentication](#user-authentication)
- [Student Registration](#student-registration)
- [Student Marks Management](#student-marks-management)
- [Student Modules Management](#student-modules-management)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Database Schema

The first step in developing this application is designing the SQL database schema. The database is structured to include tables for students, modules, marks, and user credentials for authentication purposes.

### Tables

1. **Students Table**
   - **Columns**:
     - `StudentID` (Primary Key)
     - `Name`
     - `DateOfBirth`
     - `ContactInformation`

2. **Modules Table**
   - **Columns**:
     - `ModuleID` (Primary Key)
     - `ModuleName`
     - `Description`

3. **Marks Table**
   - **Columns**:
     - `MarkID` (Primary Key)
     - `StudentID` (Foreign Key referencing Students Table)
     - `ModuleID` (Foreign Key referencing Modules Table)
     - `MarkValue`

4. **Users Table**
   - **Columns**:
     - `UserID` (Primary Key)
     - `Username`
     - `Password` (Hashed and Salted)

### Relationships

- The `StudentID` in the **Students Table** is the primary key and is used as a foreign key in the **Marks Table** to associate each mark with a student.
- The `ModuleID` in the **Modules Table** is the primary key and is used as a foreign key in the **Marks Table** to link marks with specific modules.

Sample data or scripts should be provided to populate these tables initially.

## User Authentication

The application implements user authentication to ensure that only authorized users (e.g., administrators or teachers) can access the system. Users can log in with their credentials, and the application validates login attempts against the data stored in the **Users Table** of the database.

## Student Registration

The registration form allows administrators or authorized users to add new students to the database. It collects the following student details:

- Name
- Date of Birth
- Contact Information
- Student ID

This information is then inserted into the **Students Table** in the database.

## Student Marks Management

To input and save student marks for different modules, the application provides a user-friendly form. Each mark is associated with the student's ID and the module ID in the database. Validation ensures that marks are within a reasonable range (e.g., 0-100 for percentage-based marks).

## Student Modules Management

A form is designed for adding and managing student modules. This form allows users to:

- Add new modules with a name and description.
- Edit existing modules, updating their names or descriptions.
- Delete modules, removing them from the database.

Module information is stored in the **Modules Table**.

## Getting Started

Follow the steps below to get started with the application.

### Prerequisites

Before running the application, make sure you have the following installed:

- Visual Studio or another C# development environment
- SQL Server or another compatible database server

### Installation

1. Clone this GitHub repository to your local machine.
2. Open the project in your C# development environment.
3. Configure the database connection string in the application's configuration files.
4. Ensure that the required NuGet packages are installed.
5. Build and run the application.

### Usage

1. Launch the application.
2. Log in using valid user credentials.
3. Use the provided forms to manage student records, marks, and modules.
4. Explore the features to familiarize yourself with the application's functionality.

## Contributing

Contributions to this project are welcome. If you would like to contribute, please follow the [Contribution Guidelines](CONTRIBUTING.md).

## License

This project is licensed under the [MIT License](LICENSE).
