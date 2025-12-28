🏢 Hirely -
Interactive Online Job Portal with Application Tracking System (MERN Stack)

📈Progress

📌Day 1
- Setup backend project and installed dependencies.
- Created `.env` with PORT and MongoDB Atlas connection string.
- Verified server starts with `npm run dev`.

📌Day 2
- Created free MongoDB Atlas cluster and connected with Mongoose.
- Added basic `User` model and `/api/auth/register` route.
- Tested POST `/api/auth/register` and confirmed documents appear in `hirely_dev.users` on Atlas.
  
📌 Day 3

•   Converted backend to consistent ES module syntax (import/export) and fixed MongoDB IP whitelist errors. 
•  Implemented secure /api/auth/register with bcrypt password hashing and stored hashes in the users collection.
•  Implemented /api/auth/login with bcrypt compare and JWT token, plus JWT middleware protecting /api/jobs/create and /api/users/me routes.
