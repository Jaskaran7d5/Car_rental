Car Rental Management System - README

Overview:
This is a command-line-based car rental management application developed as a self-initiated project to implement object-oriented programming (OOP) concepts in C++. The project simulates a real-world rental system with class hierarchies, role-based access, and persistent data storage using file I/O. It runs through a terminal interface and has been tested on UNIX-based systems.

Data Storage and Structure:
The application uses text files to store persistent data. The following three files are required:

1. customers.txt and employees.txt
   Format:
   UserID, Name, Password, Position, Record, Payable, NumberOfCars, List of Car IDs

2. cars.txt
   Format:
   ID, Make, Model, Color, Condition, OwnerID, Year, DailyRate, DueDate
   Note: OwnerID "M" indicates the car is not currently rented.
         DueDate = 0 if the car is not rented.

The system includes a single Manager account with the default password: Mrental001.

Running the Application:
1. Compile the program using g++ version 11.0 or above:
   g++ rental.cpp -o rental

2. Run the compiled executable:
   ./rental      (for UNIX)
   rental.exe    (for Windows)

3. On startup, choose your role: Manager, Employee, or Customer.

4. Only customers can self-register. A new customer's record is initialized to the average of existing customer records (or 0 if none exist).

5. You must log in using your password. After three incorrect attempts, the application exits.

6. Once logged in, users see a role-specific menu:
   - Manager: Add/delete/update cars, employees, and customers
   - Employee/Customer: Rent and return cars, view current rentals, and clear dues

Rental Logic:
- A user can rent a car only if their record is above a minimum threshold and their dues are below a specified limit.
- The number of cars a user can rent is based on their record score.
- Employees receive a 15% discount on rental charges.
- Renting a car updates the user's payable amount and assigns the car to their ID.

Late Returns and Penalties:
- Late returns result in penalties applied at the time of return:
   - Customers pay a 25% penalty per late day.
   - Record scores are adjusted accordingly.
- Returning a car does not clear dues. Users must clear dues explicitly through the provided menu option.

Assumptions:
- Names and passwords are entered without spaces.
- Dates are provided in the YYYYMMDD format and are valid.
- Users pay their dues upon selecting the "Clear Dues" option.
- Menu selections and dates are assumed to be integer inputs.

Developer Notes:
This project was built to practice object-oriented design, file handling, and role-based logic in C++. The system can be extended further to include GUI support, real-time features, or integration with a relational database.

