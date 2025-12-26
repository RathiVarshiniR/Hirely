# Hirely API Spec (Draft)

Base URL: `http://localhost:5000/api`

## Auth

### POST /auth/register
- Body: { name, email, password, role }
- Response: { user, accessToken, refreshToken }

### POST /auth/login
- Body: { email, password }
- Response: { user, accessToken, refreshToken }

### POST /auth/refresh-token
- Body: { refreshToken }
- Response: { accessToken }

## Users

### GET /profile
- Auth: access token
- Response: user profile

### PUT /profile
- Auth: access token
- Body: profile fields

## Jobs

### GET /jobs
- Query: search, location, jobType, salaryMin, salaryMax, page, limit
- Response: paginated jobs

### GET /jobs/:id
- Response: single job

### POST /jobs
- Auth: recruiter
- Body: job data

### PUT /jobs/:id
- Auth: recruiter (owner)
- Body: job data

## Applications

### POST /applications
- Auth: jobSeeker
- Body: { jobId, resumeId }
- Response: application

### GET /applications
- Auth: jobSeeker
- Query: status, page, limit

### PUT /applications/:id/status
- Auth: recruiter (owner)
- Body: { status }

## Admin

### GET /admin/users
- Auth: admin
- Query: role, status, page, limit