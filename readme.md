# Voucher Management System 🎫

A robust backend system built with Node.js, Express, and Prisma, designed for managing user authentication and voucher operations. This system provides secure user registration and authentication, along with comprehensive voucher management features, including registration, listing, and deletion.

## 🚀 Key Features

- **User Authentication:** Securely register and authenticate users with JWT-based authentication.
- **Voucher Management:** Create, list, and delete vouchers with different types and statuses.
- **Role-Based Access Control:** Protect routes with authentication middleware to ensure only authorized users can access specific functionalities.
- **Error Handling:** Centralized error handling using custom error classes for consistent and informative error responses.
- **Database Interaction:** Utilizes Prisma for type-safe and efficient database interactions.
- **API Routing:** Well-defined API routes for user and voucher management.

## 🛠️ Tech Stack

- **Backend:**
  - Node.js
  - Express.js
  - express-async-errors
- **Database:**
  - Prisma
  - (Configured Database - e.g., PostgreSQL)
- **Authentication:**
  - JSON Web Tokens (JWT)
  - bcryptjs (for password hashing)
- **Middleware:**
  - cors
- **Build Tools:**
  - npm or yarn
- **Other:**
  - TypeScript

## 📦 Getting Started / Setup Instructions

### Prerequisites

- Node.js (>=16)
- npm or yarn
- A configured database (e.g., PostgreSQL, MySQL, SQLite)
- Prisma CLI (`npm install -g prisma`)

### Installation

1.  Clone the repository:

    ```bash
    git clone https://github.com/Kaua26323/Voucher-Protocol-Backend
    cd Voucher-Protocol-Backend
    ```

2.  Install dependencies:

    ```bash
    npm install # or yarn install
    ```

3.  Set up your environment variables:

    - Create a `.env` file in the root directory.
    - Add the following variables, adjusting the values as needed:

    ```
    DATABASE_URL="your_database_connection_string"
    PORT=3333
    JMT_SECRET="your_jwt_secret_key"
    ```

4.  Configure Prisma:

    ```bash
    npx prisma migrate dev
    npx prisma generate
    ```

### Running Locally

1.  Start the server:

    ```bash
    npm run dev # or yarn dev (if you have a dev script)
    ```

2.  The server will start on the port specified in your `.env` file (default: 3333).

### 🧍‍♂️ User Routes

|  Method  |    Endpoint     | Authentication | Description                                           |
| :------: | :-------------: | :------------: | :---------------------------------------------------- |
| **POST** | `/create-user`  |       ❌       | Creates a new user.                                   |
| **POST** |    `/login`     |       ❌       | Authenticates a user and returns a JWT token.         |
| **GET**  | `/user-details` |       ✅       | Returns details of the authenticated user.            |
| **GET**  |    `/isAuth`    |       ✅       | Verifies if the user's JWT token is valid and active. |

---

### 🎟️ Voucher Routes

|   Method   |       Endpoint        | Authentication | Description                                                  |
| :--------: | :-------------------: | :------------: | :----------------------------------------------------------- |
|  **POST**  |  `/register-voucher`  |       ✅       | Registers a new voucher for the authenticated user.          |
|  **GET**   |    `/get-vouchers`    |       ✅       | Retrieves all vouchers registered by the authenticated user. |
| **DELETE** | `/delete-voucher/:id` |       ✅       | Deletes a specific voucher by its ID.                        |

---

### 🔑 Authentication Legend

- **✅:** Requires authentication (JWT Token).
- **❌:** Does not require authentication.

## 📂 Project Structure

```
├── src/
│   ├── controllers/
│   │   ├── user/
│   │   │   ├── AuthUserController.ts
│   │   │   ├── CreateUserController.ts
│   │   │   ├── DetailsUserController.ts
│   │   │   └── IsAuthController.ts
│   │   ├── voucher/
│   │   │   ├── DeleteVoucherController.ts
│   │   │   ├── ListRegisteredVouchersController.ts
│   │   │   └── RegisterVoucherController.ts
│   ├── errors/
│   │   └── appError.ts
│   ├── middlewares/
│   │   └── isAuthenticated.ts
│   ├── prisma/
│   │   └── index.ts
│   ├── routes.ts
│   ├── server.ts
│   ├── services/
│   │   ├── user/
│   │   │   ├── AuthUserService.ts
│   │   │   ├── CreateUserService.ts
│   │   │   └── DetailsUserService.ts
│   │   ├── voucher/
│   │   │   ├── DeleteVoucherService.ts
│   │   │   ├── ListRegisteredVouchersService.ts
│   │   │   └── RegisterVoucherService.ts
├── .env
├── package.json
├── prisma/
│   └── schema.prisma
└── README.md
```

## 📝 License

This project is licensed under the [MIT License](LICENSE).

## 👏 Thanks

Thank you for checking out the Voucher Management System! We hope it helps you build amazing applications.
