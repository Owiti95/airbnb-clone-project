# airbnb-clone-project

Project Overview
Airbnb Clone is a full-stack web application inspired by the popular booking platform, Airbnb. This project simulates a real-world software development workflow, focusing on core aspects of backend development, database architecture, API design, and CI/CD integration. Built with a focus on scalability, security, and collaborative development, it provides a comprehensive learning experience for aspiring developers.

Project Goals
Recreate key functionalities of Airbnb, such as user authentication, property listings, and booking systems.

Practice collaborative software development using GitHub.

Apply best practices in backend development, API security, and CI/CD pipelines.

Design and document scalable, relational databases reflecting real-world use cases.

Integrate modern technologies to create a cohesive, production-ready application.

Tech Stack
Backend Framework: Django

Database: MySQL

API: RESTful and GraphQL

Version Control & Collaboration: Git & GitHub

Deployment & CI/CD: Docker, GitHub Actions

Team Roles

Backend Developer

Responsible for designing and implementing the server-side logic, API endpoints, and integration of third-party services. This role also involves managing the structure of the Django project, enforcing security practices, and aligning the backend logic with frontend and database requirements.

Database Administrator (DBA)

Focuses on the design, creation, and maintenance of the MySQL database. Responsibilities include writing optimized queries, ensuring data integrity, managing relationships between tables, setting up backups, and fine-tuning database performance through indexing and normalization.

DevOps Engineer

Manages the continuous integration and deployment (CI/CD) pipelines using tools like GitHub Actions and Docker. This role ensures smooth deployments, infrastructure monitoring, version control workflows, containerization, and scaling of the backend environment to support real-world demands.

QA Engineer

Responsible for testing all backend functionalities including API endpoints, data validation, and error handling. The QA Engineer writes automated test cases, conducts performance and security testing, and ensures the application meets predefined acceptance criteria and quality benchmarks.

Technology Stack

Django

A high-level Python web framework used to build the backend of the application. It enables rapid development of secure and maintainable web APIs and handles routing, authentication, and business logic.

MySQL

A relational database management system used to store and manage structured data such as user accounts, property listings, booking details, and transaction records. It supports robust querying, relationships, and indexing.

GraphQL

An advanced API query language used to enable flexible and efficient client-server data communication. It allows clients to request exactly what they need, minimizing over-fetching or under-fetching of data.

Docker

A containerization tool used to package the application and its dependencies into portable containers. It ensures consistency across development, testing, and production environments.

Git & GitHub

Version control and collaboration tools used to manage source code, track changes, and enable team collaboration via pull requests, issues, and branching workflows.

GitHub Actions

A CI/CD automation platform used to build, test, and deploy the application automatically on code commits. It helps maintain code quality and streamlines the release process.

API Security Tools

Includes authentication (e.g., JWT) and authorization mechanisms to protect endpoints, secure data transactions, and ensure safe access control within the application.

Database Design

The database for the Airbnb Clone project is designed with normalization and scalability in mind. It captures key relationships between users, properties, bookings, payments, and reviews to mirror a real-world booking platform.

Users

Represents individuals using the platform (hosts and guests).

Key Fields:

id: Unique identifier for each user

name: Full name of the user

email: User’s email address (used for login)

password_hash: Hashed password for secure authentication

is_host: Boolean indicating if the user is a property owner

Relationships:

A user can create multiple properties (if is_host is True)

A user can make multiple bookings

A user can leave multiple reviews

Properties

Represents listings available for booking.

Key Fields:

id: Unique identifier for each property

title: Name or title of the property

description: Detailed description of the property

price_per_night: Cost per night

host_id: Foreign key referencing the Users table

Relationships:

A property is owned by one user (host)

A property can have many bookings

A property can receive many reviews

Bookings

Tracks reservations made by users.

Key Fields:

id: Unique identifier for each booking

property_id: Foreign key referencing the Properties table

user_id: Foreign key referencing the Users table

check_in: Start date of booking

check_out: End date of booking

Relationships:

A booking belongs to one user and one property

A booking may be linked to one payment

Payments

Handles financial transactions related to bookings.

Key Fields:

id: Unique identifier for each payment

booking_id: Foreign key referencing the Bookings table

amount: Total payment amount

payment_status: Status (e.g., “completed”, “pending”)

payment_date: Timestamp of payment

Relationships:

Each payment is linked to a single booking

Reviews

Captures user feedback on properties.

Key Fields:

id: Unique identifier for each review

user_id: Foreign key referencing the Users table

property_id: Foreign key referencing the Properties table

rating: Numeric rating (e.g., 1–5)

comment: Written feedback

Relationships:

Each review is associated with one user and one property

Entity Relationships Summary

One User → many Properties, Bookings, Reviews

One Property → many Bookings, Reviews

One Booking → one Payment

One User can review multiple Properties, but only once per booking
