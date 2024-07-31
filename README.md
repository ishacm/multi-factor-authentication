# Two-Factor/Multi-Factor Authentication: Using the MERN stack and Google Authenticator

Two-Factor Authentication Multi-Factor Authentication (MFA), is an open-source standard that greatly enhances user security while being pretty straightforward to implement. Many websites use this simple yet powerful security measure when logging-in their users.

## How does it work?

In addition to the usual ID and password pair, you are required to provide an additional secret code, usually 6-digit long, to login which you obtain from an authenticator application (e.g. [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2) or [this Chrome extension](https://chrome.google.com/webstore/detail/authenticator/bhghoamapcdpbohphigoooaddinpkbai)) installed in your phone or web browser which you have registered with the platform or website you are logging into by simply scanning a QR code. After the initial registration step, the authenticator app doesn’t even need to be online to give you the required secret OTP. Magic! Right?

As it is with all things in computer science, it turns out it is not magic, rather it is only some solid logic. At the heart of 2FA/MFA, the kind we are going to implement, are two cryptographic algorithms. The first algorithm when simplified takes as input three things:

1. The current approximate time on the clock
2. A user specific secret key
3. And an OTP usually consisting of 6 digits

Its output is a simple yes or no specifying the validity of the input triplet. The second algorithm is similar to the first one except that instead of taking an OTP as the third input, it spits one out.

Thus, by having a server and a client which share the clock and a secret, the client’s claim of possessing the secret previously shared by the server can be verified without actually sharing the secret. This secret can then be used for user authentication.

## Prerequisites

Before starting, make sure you have a recent version of the following installed and set up:

1. [Node.js](https://nodejs.dev/en/learn/how-to-install-nodejs/)
2. [MongoDB](https://www.mongodb.com/docs/manual/administration/install-community/)
3. [Postman](https://www.postman.com/downloads/) with [this collection](https://github.com/SalmanFarooqShiekh/2fa/blob/main/backend/postman/Express-2FA.postman_collection.json) imported
4. [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2) (or a [similar](https://chrome.google.com/webstore/detail/authenticator/bhghoamapcdpbohphigoooaddinpkbai) app)

## Backend setup:

1. Project Setup:

Create a new directory called '2fa' and a subdirectory 'backend'
Initialize the project with npm
Install required packages (express, mongoose, passport, etc.)


2. Basic Express Server:

Create an initial 'index.js' file with a basic Express server setup


3. Controller Setup:

Create a 'controllers.js' file for handling route logic
Implement a basic signup controller


4. Database Configuration:

Create 'db.js' to set up MongoDB connection using mongoose
Create 'models.js' to define the User schema


5. Authentication Setup:

Create 'auth.js' for Passport strategies
Implement signup strategy using Passport local strategy


6. Environment Configuration:

Create 'env.js' for storing sensitive information like JWT secret


7. Signup Endpoint:

Implement and test the signup endpoint


8. Login Endpoint:

Implement login controller and Passport strategy
Handle cases for users with and without 2FA enabled


9. Protected Route:

Implement a protected '/api/profile' route using JWT authentication


10. 2FA Setup:

Create endpoints for generating 2FA secret and verifying OTP
Implement controllers for 2FA secret generation and OTP verification


Login Step 2:

Implement a second login step for users with 2FA enabled


2FA Disabling:

Create an endpoint to disable 2FA for a user


11. Testing:

Use Postman to test all implemented endpoints

---

## Frontend setup:


1. Features

- User registration
- User login with optional 2FA
- Profile management
- Enable/Disable 2FA
- QR code generation for 2FA setup

2. Technologies Used

- React.js
- React Router for navigation
- JavaScript


