﻿# Sports Facility Booking Platform - Server

This repository contains the backend of the **Sports Facility Booking Platform**, which allows users to book, manage, and monitor reservations for sports facilities. The platform supports user registration, authentication, booking management, and various role-based access controls for secure bookings and facilities management.

---

## Live Demo

You can access the live demo of the application: [here](https://sports-facility-booking-platform-alpha.vercel.app).

---

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation and Setup](#installation-and-setup)
- [Environment Variables](#environment-variables)
- [Running the Application](#running-the-application)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **User Authentication**: Secure JWT-based authentication.
- **User Roles**: Admin and User roles with different levels of access.
- **Facility Booking**: Users can book sports facilities for specific dates and times.
- **Facility Management**: Admins can create, update, and soft-delete facilities.
- **Booking Management**: Users can create and cancel bookings; admins can manage all bookings.
- **Real-Time Availability**: Check the availability of facilities for specific times.
- **Data Validation**: Strong data validation with Zod and Mongoose.
- **Centralized Error Handling**: Unified error handling across the application.

---

## Technologies Used

- **Node.js**: Backend runtime environment
- **Express.js**: Web framework for Node.js
- **MongoDB & Mongoose**: Database and ORM for data storage and querying
- **TypeScript**: Typed JavaScript for safer and more predictable code
- **JWT**: JSON Web Token for secure authentication
- **Zod**: Schema validation for request bodies
- **Bcrypt**: Password hashing
- **Prettier & ESLint**: Code formatting and linting

---

## Installation and Setup

Follow these steps to set up the project on your local machine:

### 1. Clone the Repository

```bash

git clone https://github.com/mdiibrahim/Sports-Facility-Booking-Platform-Server.git
cd Sports-Facility-Booking-Platform-Server

```

### 2. Install Dependencies

```bash

npm install

```

This will install all the necessary packages listed in `package.json`.

### 3. Create Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

```env

PORT=5000
DATABASE_URL=<Your MongoDB Connection String>
JWT_ACCESS_SECRET=<Your Access JWT Secret>
JWT_REFRESH_SECRET=<Your Refresh JWT Secret>
JWT_ACCESS_EXPIRES_IN=1h
JWT_REFRESH_EXPIRES_IN=7d
BCRYPT_SALT_ROUNDS=10
NODE_ENV=development

```

---

### 4. Start the Application

To start the application in development mode, run:

```bash

npm run dev

```

This will start the server on the specified port, with automatic restarting on file changes.

---

## Environment Variables

Ensure the following environment variables are set up in your `.env` file:

- **PORT**: The port on which the server will run (default: 5000).
- **DATABASE_URL**: MongoDB connection string.
- **JWT_ACCESS_SECRET**: Secret key for generating JWT access tokens.
- **JWT_ACCESS_EXPIRES_IN**: Time after which the access token expires (e.g., `1h`).
- **BCRYPT_SALT_ROUNDS**: The number of rounds for bcrypt hashing (default: 10).
- **NODE_ENV**: Set to `development` for development mode.

---

## Running the Application

After the setup, you can run the application in different modes:

- **Development Mode**:

  ```bash

  npm run start:dev

  ```

- **Production Mode**:

  ```bash

  npm run start:prod

  ```

---

## API Documentation

### Authentication

- **POST** `/api/auth/signup` - Register a new user
- **POST** `/api/auth/login` - Log in an existing user

### Facility Management

- **POST** `/api/facility` - Create a new facility (Admin Only)
- **GET** `/api/facility` - Get all facilities
- **PUT** `/api/facility/:id` - Update a facility (Admin Only)
- **DELETE** `/api/facility/:id` - Soft delete a facility (Admin Only)

### Booking

- **POST** `/api/bookings` - Create a new booking (User Only)
- **GET** `/api/bookings` - Retrieve all bookings (Admin Only)
- **GET** `/api/bookings/user` - Get bookings for the logged-in user (User Only)
- **GET** `/api/bookings/check-availability` - Get available slots for specific date
- **DELETE** `/api/bookings/:id` - Cancel a booking (User Only)

---

### Validation

Each endpoint uses schema validation for request bodies using Zod and Mongoose, ensuring data meets the required criteria before processing.

---

### Linting and Formatting

To check for linting errors and automatically format code, run:

```bash

npm run lint
npm run prettier

```

---

## Contributing

We welcome contributions! Please follow these steps to contribute:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature-name`.
3. Commit your changes: `git commit -m "Add some feature"`.
4. Push to the branch: `git push origin feature/your-feature-name`.
5. Submit a pull request.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.txt) file for details.

---
