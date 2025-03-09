# Onecal-Scheduler

A well-structured guide to setting up and running the **Onecal-Scheduler** (MERN stack) project locally.  

## *Features*  

✔ Landing Page – A visually appealing introduction to the app  
✔ User Authentication – Magic link-based email sign-in  
✔ Profile View – Manage user details  
✔ Booking System – Reserve time slots on a shared calendar  
✔ Cancellation – Remove own bookings  
✔ View Reservations – See all booked slots  
✔ Usage Statistics – Track bookings and cancellations  

## *Tech Stack*  

- *Frontend:* React, TailwindCSS  
- *Backend:* Node.js, Express.js  
- *Database:* MongoDB  
- *Authentication:* Magic Link (JWT, Nodemailer)
- *Environment Variables Management:* dotenv
- *Email Service:* Nodemailer (Gmail SMTP)  

### *Prerequisites*  

Before setting up the project, ensure you have the following installed:  
- Node.js (v16 or later) – [Download](https://nodejs.org/)  
- MongoDB (local or Atlas) – [Setup Guide](https://www.mongodb.com/)  

### *Backend Setup*  

1. Open a terminal and navigate to the backend folder:  
   sh
   cd Backend
   
2. Install dependencies:  
   sh
   npm install
   
3. Configure the .env File:
   Step 1: Open the Backend folder and create a .env file if it does not exist.
   Step 2: Add the following environment variables inside .env:
   env
   DB_LOCAL_URI=your_mongodb_connection_string  # (Use local MongoDB Compass or MongoDB Atlas connection string)
   PORT=5000  # (Port number for the backend server)
   SECRET_KEY=your_secret_key  # (Secret key for encoding JWT tokens)
   EMAIL_USER=your_email@gmail.com  # (Your email ID for sending emails)
   EMAIL_PASS=your_email_password  # (Your email password or app-specific password)
   BASE_URL=http://localhost:5173  # (Frontend React URL, usually localhost for development)

MongoDB Setup (Choose One Option Below)
Option 1: Using Local MongoDB (Compass)
- Open MongoDB Compass
- Click "New Connection" and connect using:
  cpp
  mongodb://127.0.0.1:27017
- Update your .env file:
 DB_LOCAL_URI=mongodb://127.0.0.1:27017/onecalDB

Option 2: Using MongoDB Atlas (Cloud)
- Create an account on MongoDB Atlas.
- Create a free cluster → Connect → Choose "Connect your application"
- Copy the MongoDB connection string, and replace <username> & <password>:
  ini
  DB_LOCAL_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/schedulerDB?retryWrites=true&w=majority

4. Start the backend server:  
   sh
   npm start
- If successful, your terminal should display:
  Server running on PORT 5000
  Connected to MongoDB

### *Frontend Setup*  

1. Open a new terminal and navigate to the frontend folder:  
   sh
   cd Frontend
   
2. Install dependencies:  
   sh
   npm install
   
3. Configure the .env File:
- In the Frontend folder, create a .env file if it does not exist.
- Add the following line to connect the frontend with the backend:
   env
   VITE_BASE_URL=http://localhost:5000  # (Set your backend local server URL)
   
5. Start the frontend server:  
   sh
   npm run dev
-If successful, your terminal should display:
VITE v4.0.0  ready in 100ms
Local: http://localhost:5173/

### *Run the App*  

Once both the frontend and backend servers are running:  
- Open http://localhost:5173 in your browser.  
- Use the magic link authentication to log in.
  
### *How Magic Link Authentication Works*

- Enter your email on the login page.
- A magic link will be sent to your email.
- Click the link to automatically log in without a password.
- No need to remember passwords!

