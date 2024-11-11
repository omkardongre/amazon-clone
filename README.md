# Amazon Clone - React + Redux + NestJS

This project is an Amazon-inspired e-commerce application built with a modern web stack, including **React**, **Redux Toolkit**, **NestJS**, **MongoDB**, and **TypeScript**. It leverages **Docker** for database management and **Stripe** for payment processing. The project focuses on best practices for building and structuring a **RESTful API** and creating a responsive, scalable front-end with **React**.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Setup](#setup)
- [Usage](#usage)
- [Testing](#testing)
- [Folder Structure](#folder-structure)
- [Future Improvements](#future-improvements)
- [License](#license)

## Features

- **User Authentication:** Users can register and log in with secure password hashing and JWT-based route protection.
- **CRUD Operations:** Basic CRUD operations for products and users using NestJS and MongoDB.
- **Global State Management:** Uses Redux Toolkit to manage global states, such as authentication and cart.
- **UI Components with Material UI:** Styled components using Material UI.
- **Custom React Hooks:** Custom hooks to simplify form handling and manage input state.
- **Payment Gateway:** Integrates Stripe for payment processing.
- **Testing:** Includes unit testing with React Testing Library and end-to-end (E2E) testing with Cypress.

## Tech Stack

- **Frontend:** React, Redux Toolkit, TypeScript, Material UI
- **Backend:** NestJS, Express, Mongoose, bcrypt, JWT
- **Database:** MongoDB (with Docker for MongoDB and Mongo-Express)
- **Testing:** React Testing Library, Jest, Cypress
- **Deployment:** Docker, MongoDB, Mongo-Express, Stripe

## Getting Started

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/amazon-clone.git
   cd amazon-clone
   ```

2. **Install dependencies for both frontend and backend:**

   ```bash
   cd client
   npm install
   cd ../server
   npm install
   ```

3. **Set up environment variables:** Create `.env` files in the root of both the `client` and `server` folders.

   - **Backend (.env):**

     ```plaintext
     MONGO_URI=mongodb://mongo:27017/amazon_clone
     JWT_SECRET=your_jwt_secret
     STRIPE_SECRET_KEY=your_stripe_secret_key
     ```

   - **Frontend (.env):**

     ```plaintext
     REACT_APP_API_URL=http://localhost:5000/api
     REACT_APP_STRIPE_PUBLIC_KEY=your_stripe_public_key
     ```

## Setup

1. **Start MongoDB with Docker:**

   ```bash
   docker-compose up
   ```

2. **Run the backend (NestJS) server:**

   ```bash
   cd server
   npm run start:dev
   ```

3. **Run the frontend (React) server:**

   ```bash
   cd client
   npm start
   ```

   Your application should now be accessible at `http://localhost:3000`.

## Usage

### Authentication

- Register and log in with secure password handling (bcrypt) and JWT-based authentication.

### Product Management

- Browse a selection of products with global cart state management using Redux Toolkit.

### Cart and Payment

- Add items to the cart and proceed with checkout using Stripe.

## Testing

### Unit Testing

- Using **React Testing Library** and **Jest**, unit tests are written for both functions and components.

### Integration & E2E Testing

- **Cypress** is used for end-to-end testing, simulating user interactions like form filling, triggering events, and API interactions.

Run tests with:

```bash
npm test # for unit tests
npm run cypress # for end-to-end tests
```

## Folder Structure

```
amazon-clone/
├── client/                   # React frontend
│   ├── src/
│   │   ├── components/       # UI components
│   │   ├── hooks/            # Custom hooks
│   │   ├── pages/            # Application pages
│   │   ├── redux/            # Redux Toolkit slices
│   │   ├── App.tsx           # Main App component
│   │   └── index.tsx         # Entry point
│   └── public/
│       └── index.html
├── server/                   # NestJS backend
│   ├── src/
│   │   ├── auth/             # Authentication module
│   │   ├── products/         # Product module
│   │   ├── users/            # User module
│   │   ├── app.module.ts     # Main module
│   │   └── main.ts           # Entry point
├── docker-compose.yml        # Docker setup for MongoDB and Mongo-Express
└── README.md
```

## Future Improvements

- **Enhanced Search and Filters:** Add filtering by category, price range, and rating.
- **Wishlist and Order History:** Enable users to save favorite items and view past orders.
- **Real-Time Notifications:** Use WebSockets to send order status updates.
- **Enhanced Security:** Implement additional security features, such as refresh tokens and CSRF protection.

## License

This project is licensed under the MIT License.

```