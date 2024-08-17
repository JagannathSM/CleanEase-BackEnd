# 🧹 CleanEase Site BackEnd

## 🚀 Overview
This repository contains the backend of a functional booking platform for a cleaning service. The backend is built with Node.js and Express.js, providing a robust and scalable solution for managing user bookings, user authentication and other logic. MongoDB is used as the database to store and manage data.

## 🧰 Tech Stack

- **Node.js 🟢: JavaScript runtime for server-side programming.
- **Express.js : Web framework for building RESTful APIs.
- **MongoDB 🍃: NoSQL database for storing and managing data.
- **JWT 🔐: JSON Web Tokens for secure user authentication.
- **Mongoose : ODM (Object Data Modeling) library for MongoDB, facilitating data interaction.
- **Socket-io : For Real time Notification generation about booking status from Admin to User.

## 📂 Folder Structure
```
/src
|-- controllers
|   |-- authController
|   |-- UserController
|   |-- BookingController
|   |-- NotificationController
|   |-- razorPayController
|   |-- UserCheckListController
|   |-- cleanEaseController
|   |-- AdminController
|-- DB
|   |-- ConnectMongoDB
|-- MiddleWare
|   |-- Admin
|   |-- auth
|-- Models
|   |-- CleanServices
|   |-- CleanSubCategories
|   |-- Notification
|   |-- User
|   |-- UserBookings
|   |-- UserChecklist
|-- Routes
|   |-- adminRoutes
|   |-- authRoutes
|   |-- bookingRoutes
|   |-- cleanEaseRoutes
|   |-- notificationRoutes
|   |-- razorPayRoutes
|   |-- userRoutes
|   |-- userCheckListRoutes
|-- Utils
|   |-- EmailServices
|-- server.js
|-- package
|-- package-lock
```

## 🧪 How to Run the Frontend
**Install Dependencies** 📦
   ```bash
	npm install express
	npm install mongoose
	npm install jsonwebtoken
	npm install bcryptjs
	npm install body-parser
	npm install nodemailer
	npm install razorpay
	npm install dotenv
	npm install cors
	npm install socket.io
   ```


**Environment files required fields**
```bash
PORT=SERVER_RUNNING_PORT
MONGODB_URI=YOUR_MONGODB_ATLAS_URI
JWTSECRET=YOUR_JSON_WEB_TOKEN_SECRET
SALT=JSON_WEB_TOKEN_SALT
GMAIL_PASS=YOUR_NODEMAILER_PASSWORD
GMAIL_ACC=YOUR_NODEMAILER_EMAIL
VERIFY_REGISTER=YOUR_FRONTEND_URL_FOR_REGISTER_VERIFICATION
VERIFY_PASSWORD=YOUR_FRONTEND_URL_FOR_FORGOT_PASSWORD_VERIFICATION
TEST_KEY_ID=YOUR_RAZOR_PAY_ID
TEST_KEY_SECRET=YOUR_RAZOR_PAY_SECRET
```

**API END-POINT EXPLANATION**

AUTH-ROUTE ---> /api/auth

	POST	- /register --> To Create User in DB and send an Account Activation Link for user to activate his/her account.
	GET	- /register-check/:registerToken --> To check the register token generated for the user and activate his/her account and generate JWT(JSON WEB TOKEN).
	POST	- /login --> To Login registered User and generate JWT
	POST	- /resetPass --> Check the user mailID and send the reset pass token to user mailID.
	GET	- /resetPass-check/:passResetToken --> To verify the reset pass token and allow user to reset there password.
	PUT	- /updatePass/:passResetToken --> To Update the user password.

            </li>
        </ol>
    </li>
</ol>

