# Salon Appointment Scheduler

## Overview

The Salon Appointment Scheduler is a command-line application built with Bash and PostgreSQL. It allows customers to view available salon services, book appointments, and register their details if they are visiting for the first time.

This project was completed as part of the freeCodeCamp Relational Database certification projects to practice Bash scripting, SQL queries, database relationships, and user input handling.

## Features

- Displays a numbered list of available salon services.
- Allows customers to select a service using its service ID.
- Validates service selections and redisplays the list when an invalid service is selected.
- Collects customer phone numbers and identifies existing customers.
- Registers new customers and stores their phone numbers and names.
- Schedules appointments with the selected service and appointment time.
- Stores customer and appointment information in a PostgreSQL database.
- Displays a confirmation message after an appointment is scheduled.

## Technologies Used

- **Bash:** Handles user interaction, input validation, and application logic.
- **PostgreSQL:** Stores customer, service, and appointment data.
- **SQL:** Creates tables, retrieves customer information, and inserts records into the database.
- **Git and GitHub:** Used for version control and project sharing.

## Database Structure

The project uses a PostgreSQL database named `salon`, containing three tables.

### 1. Customers

Stores customer information.

| Column | Description |
|---|---|
| `customer_id` | Unique, automatically incrementing customer ID |
| `phone` | Customer phone number; must be unique |
| `name` | Customer's name |

### 2. Services

Stores the salon services offered.

| Column | Description |
|---|---|
| `service_id` | Unique, automatically incrementing service ID |
| `name` | Name of the salon service |

Example services include:
- Cut
- Color
- Perm

### 3. Appointments

Stores customer appointments and links each appointment to a customer and a service.

| Column | Description |
|---|---|
| `appointment_id` | Unique, automatically incrementing appointment ID |
| `customer_id` | Foreign key referencing the customer |
| `service_id` | Foreign key referencing the selected service |
| `time` | Scheduled appointment time |

## Getting Started

### Prerequisites

Ensure the following are installed and available in your environment:

- Bash
- PostgreSQL
- `psql` command-line client
- Git (optional, for version control)


### Running the Application

Give the script executable permissions:

```bash
chmod +x salon.sh
```

Run the scheduler:

```bash
./salon.sh
```

Follow the prompts to select a service, enter your phone number, provide your name if you are a new customer, and choose an appointment time.

## Example Usage

A sample interaction for a new customer:

```text
~~~~~ MY SALON ~~~~~

1) cut
2) color
3) perm

What would you like to have done?
1

What's your phone number?
555-555-5555

I don't have a record for that phone number, what's your name?
Fabio

What time would you like your cut, Fabio?
10:30

I have put you down for a cut at 10:30, Fabio.
```

Returning customers can book another appointment using their existing phone number without entering their names again.

## Saving the Database

To export the database structure and data to a SQL file, run the following command from your terminal:

```bash
pg_dump -cC --inserts -U freecodecamp salon > salon.sql
```

The resulting `salon.sql` file can be used to recreate the database in a compatible PostgreSQL environment.

## Learning Outcomes

Through this project, I practiced:

- Writing Bash scripts with variables, loops, conditionals, and `read`.
- Executing PostgreSQL queries from Bash.
- Using SQL commands to create tables and insert and retrieve data.
- Implementing primary keys and foreign key relationships.
- Enforcing unique customer phone numbers.
- Handling returning customers and registering new customers.
- Validating user input in a command-line application.
- Connecting a shell script to a relational database.

## Future Improvements

Potential enhancements include:

- Validating phone numbers and appointment times.
- Preventing double bookings for the same time slot.
- Allowing customers to view, reschedule, or cancel appointments.
- Adding service prices and appointment durations.
- Improving error handling for database connection failures.

## Acknowledgements

This project was developed as part of the [freeCodeCamp Relational Database Certification](https://www.freecodecamp.org/), which provides hands-on practice with Bash, PostgreSQL, and relational database concepts.

