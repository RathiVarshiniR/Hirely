# Hirely – Database Schema (Draft)

## Users
- _id
- name
- email (unique)
- password (hashed)
- role: jobSeeker | recruiter | admin | employer
- profile:
  - bio
  - location
  - experienceYears
  - skills[]
  - avatarUrl
  - phone
- createdAt
- updatedAt

## Jobs
- _id
- title
- description
- companyId (ref Users)
- location
- salary: { min, max, currency }
- jobType: full-time | part-time | contract | internship
- category
- requiredSkills[]
- experienceLevel
- applicantsCount
- status: draft | published | closed | archived
- createdAt
- updatedAt

## Applications
- _id
- jobId (ref Jobs)
- candidateId (ref Users)
- recruiterId (ref Users)
- resumeId (ref Resumes)
- status: applied | reviewing | shortlisted | rejected | hired
- rating (1-5)
- notes
- appliedAt
- updatedAt

## Resumes
- _id
- userId (ref Users)
- fileName
- fileUrl
- isPrimary
- uploadedAt
- updatedAt