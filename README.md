# 🧹 CleanEase Site BackEnd

## 🚀 Overview
This repository contains the backend of a functional booking platform for a cleaning service. The application is designed with a focus on providing a smooth and intuitive user experience. The backend is built with Node.js and Express.js, providing a robust and scalable solution for managing user bookings, user authentication and other logic. MongoDB is used as the database to store and manage data.

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

<ol>
    <li>AUTH-ROUTE ---> /api/auth
        <ol>
            <li>
                POST -- /register --> To Create User in DB and send an Account Activation Link for user to activate his/her account.
            </li>
            <li>
                GET  -- /register-check/:registerToken --> To check the register token generated for the user and activate his/her account and generate JWT(JSON WEB TOKEN).
            </li>
            <li>
                POST -- /login --> To Login registered User and generate JWT.
            </li>
            <li>
                POST -- /resetPass --> Check the user mailID and send the reset pass token to user mailID.
            </li>
            <li>
                GET  -- /resetPass-check/:passResetToken --> To verify the reset pass token and allow user to reset their password.
            </li>
            <li>
                PUT  -- /updatePass/:passResetToken --> To Update the user password.
            </li>
        </ol>
    </li>
    <li>USER-ROUTE ---> /api/user (REQUIRED USER JWT)
        <ol>
            <li>
                GET  -- /getProfile --> To get the user details.
            </li>
            <li>
                PUT  -- /updateProfile --> To update user details.
            </li>
        </ol>
    </li>
    <li>BOOKING-ROUTE ---> /api/bookings (REQUIRED USER JWT)
        <ol>
            <li>
                POST -- /create/:cleanSubCategoriesID --> User to create bookings.
            </li>
            <li>
                GET  -- /get --> Get All User's Bookings.
            </li>
            <li>
                PUT  -- /update/:userBookingID --> To edit the user booking.
            </li>
            <li>
                DELETE -- /delete/:bookingID --> To delete user bookings.
            </li>
            <li>
                POST -- /review/:_id --> To create user review.
            </li>
            <li>
                GET  -- /review/:_id --> To get all reviews for particular service (NO NEED FOR JWT).
            </li>
            <li>
                DELETE -- /review/:_id/:deleteID --> To delete the user review.
            </li>
            <li>
                PUT  -- /review/:_id/:reviewID --> To Update the user Review.
            </li>
            <li>
                PUT  -- /payment-update --> To Update the payment status for user bookings.
            </li>
        </ol>
    </li>
    <li>NOTIFICATION-ROUTE ---> /api/notification (REQUIRED USER JWT)
        <ol>
            <li>
                POST -- /create --> Create User Notification.
            </li>
            <li>
                GET  -- /get --> Get user Notification.
            </li>
            <li>
                DELETE -- /delete/:_id --> To Delete User Notification.
            </li>
        </ol>
    </li>
    <li>CLEANEASE-ROUTE ---> /api/data
        <ol>
            <li>
                GET  -- / --> Get all main services from clean ease.
            </li>
            <li>
                GET  -- /:cleanServiceID --> Get all subCleanServices.
            </li>
        </ol>
    </li>
    <li>RAZORPAY-ROUTE ---> /api/payment (REQUIRED USER JWT)
        <ol>
            <li>
                POST -- /create-order --> To create RazorPay Order.
            </li>
            <li>
                POST -- /validate --> To validate the RazorPay Payment.
            </li>
        </ol>
    </li>
    <li>USER-CHECKLIST-ROUTE ---> /api/checklist (REQUIRED USER JWT)
        <ol>
            <li>
                POST -- /create --> Create a new checklist item for user.
            </li>
            <li>
                GET  -- /get --> Get all checklist items.
            </li>
            <li>
                PUT  -- /update/:_id --> To Update Particular checklist item.
            </li>
            <li>
                DELETE -- /delete/:_id --> Delete a particular checklist item.
            </li>
        </ol>
    </li>
    <li>ADMIN-ROUTE ---> /api/admin (REQUIRED ADMIN JWT)
        <ol>
            <li>
                GET  -- /get-bookings --> To get all Users Booking details.
            </li>
            <li>
                PUT  -- /update-booking/:_id --> To update the user Booking.
            </li>
            <li>
                GET  -- /get-total-users --> To get the details of total users.
            </li>
            <li>
                GET  -- /get-users-with-bookings --> To get users with total number of bookings.
            </li>
        </ol>
    </li>
</ol>

