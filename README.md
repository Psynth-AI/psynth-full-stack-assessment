# Full Stack Engineer Take-Home Assessment

## Overview

Build a small full stack **Document Review Queue** application using:

* **Frontend:** React
* **Backend:** Python FastAPI
* **Data:** Mocked data provided in the repository
* **Runtime:** Docker / Docker Compose

This assessment is designed to take approximately **2–3 hours**.

The goal is not to build a production-ready system. We want to evaluate how you structure code, integrate frontend and backend, handle CRUD flows, and communicate your technical decisions clearly.

---

# Business Context

Internal users need a simple way to review documents submitted to a queue.

Each document has:

* ID
* Title
* Submitter Name
* Category
* Status
* Priority
* Created Date
* Short Summary

Users should be able to view documents, filter them, create new documents, update their status, and delete documents.

This is a neutral domain. Do **not** include PHI, PII, patient information, or healthcare-specific data.

---

# Requirements

## Backend Requirements

Create a FastAPI backend that exposes REST endpoints for the document review queue.

### Required Endpoints

```http
GET    /documents
GET    /documents/{document_id}
POST   /documents
PATCH  /documents/{document_id}
DELETE /documents/{document_id}
```

### Backend Expectations

* Use mocked data loaded from a local JSON file.
* Keep data in memory while the application is running.
* Use Pydantic models for request and response validation.
* Return appropriate HTTP status codes.
* Include basic validation.
* Return meaningful error responses for invalid or missing documents.
* Include OpenAPI documentation through FastAPI defaults.

### Suggested Status Values

```text
pending
in_review
approved
rejected
```

### Suggested Priority Values

```text
low
medium
high
```

---

## Frontend Requirements

Create a React frontend that consumes the FastAPI API.

### Required Features

Users should be able to:

* View a list of documents
* Filter documents by status
* View document details
* Create a new document
* Update a document status
* Delete a document
* See loading states
* See error states

The UI does not need to be heavily styled, but it should be clean, usable, and organized.

---

# Mock Data

Use the following data as a starting point.

```json
[
  {
    "id": "doc_001",
    "title": "Vendor Contract Review",
    "submitter_name": "Alex Morgan",
    "category": "Legal",
    "status": "pending",
    "priority": "high",
    "created_at": "2026-06-01T10:00:00Z",
    "summary": "Contract requires review before vendor onboarding."
  },
  {
    "id": "doc_002",
    "title": "Marketing Campaign Brief",
    "submitter_name": "Jamie Lee",
    "category": "Marketing",
    "status": "in_review",
    "priority": "medium",
    "created_at": "2026-06-02T14:30:00Z",
    "summary": "Campaign brief for Q3 launch needs approval."
  },
  {
    "id": "doc_003",
    "title": "Security Checklist",
    "submitter_name": "Taylor Smith",
    "category": "Security",
    "status": "approved",
    "priority": "high",
    "created_at": "2026-06-03T09:15:00Z",
    "summary": "Checklist for internal security review."
  },
  {
    "id": "doc_004",
    "title": "Office Supply Request",
    "submitter_name": "Jordan Brown",
    "category": "Operations",
    "status": "rejected",
    "priority": "low",
    "created_at": "2026-06-04T16:45:00Z",
    "summary": "Request for additional office equipment."
  }
]
```

You may add additional mock records if needed.

---

# Docker Requirements

The project must include Docker support.

At minimum, provide:

```text
docker-compose.yml
frontend/Dockerfile
backend/Dockerfile
```

Running the following command should start both applications:

```bash
docker compose up --build
```

### Expected Local URLs

```text
Frontend:     http://localhost:5173
Backend API:  http://localhost:8000
API Docs:     http://localhost:8000/docs
```

---

# AI Tool Usage (Required)

You are **required** to use AI tools while completing this assessment.

In your submission, include a section in the README called:

```text
AI Tool Usage
```

Describe:

* Which AI tools you used
* What you used them for
* What code or suggestions you accepted
* What code or suggestions you modified
* What code or suggestions you rejected
* Any mistakes, risks, or limitations you observed from the AI-generated output

We are not evaluating whether you used AI.

We are evaluating how thoughtfully and responsibly you used it.

---

# README Requirements

Your README should include:

1. Project Overview
2. Tech Stack
3. Setup Instructions
4. Docker Instructions
5. API Endpoint Summary
6. Known Limitations or Tradeoffs
7. AI Tool Usage
8. What You Would Improve With More Time
9. Video Walkthrough Link

---

# Solution Walkthrough (Required)

Please include a short video walkthrough (approximately **5 minutes**) demonstrating your solution.

The video should cover:

## Application Demo

* Running application
* Document list view
* Filtering functionality
* Creating a document
* Updating a document
* Deleting a document

## Technical Walkthrough

Briefly explain:

* Project structure
* Key frontend decisions
* Key backend decisions
* How frontend and backend communicate
* Any tradeoffs you made
* What you would improve with more time

## AI Usage Discussion

Please explain:

* Which AI tools you used
* How you used them
* Where they helped
* Where they produced incorrect or incomplete results
* How you validated AI-generated code

### Accepted Video Platforms

* Loom
* YouTube (unlisted)
* Google Drive
* Vimeo

Include the video link in your README.

---

# Submission Instructions

1. Create a new GitHub repository.
2. Push your completed solution to that repository.
3. Share the repository with the GitHub user:

```text
sbpsynth
```

4. Ensure the repository includes clear setup instructions.
5. Include your walkthrough video link in the README.
6. Do not submit ZIP files.
7. Do not include secrets, credentials, API keys, or private information.

---

# Evaluation Criteria

## Functionality

* CRUD operations work correctly
* Frontend communicates successfully with backend
* Loading and error states are handled appropriately
* Docker setup works correctly

## Code Structure

* Clear separation between frontend and backend
* Components and functions have clear responsibilities
* Code is readable and maintainable
* Avoids unnecessary complexity

## API Design

* REST endpoints are predictable and well structured
* Request and response models are clear
* Validation is present
* Error handling is reasonable

## Frontend Quality

* User interface is understandable and usable
* State management is clean
* API calls are organized
* User actions provide visible feedback

## Backend Quality

* FastAPI best practices are followed
* Pydantic models are used appropriately
* Mock data is handled cleanly
* Common edge cases are considered

## Communication

* README is clear and complete
* Tradeoffs are explained
* AI usage is disclosed thoughtfully

## Technical Understanding

* Candidate demonstrates understanding of their implementation
* Candidate can clearly explain architectural decisions
* Candidate uses AI tools thoughtfully rather than blindly accepting output
* Candidate understands tradeoffs and limitations of the chosen solution

---

# Bonus (Optional)

The following items are completely optional and are **not required** to complete the assessment.

These are intended to provide an opportunity to demonstrate additional skills if time permits.

Examples include:

* Search by title
* Sorting by created date
* Sorting by priority
* Pagination
* Responsive design improvements
* Additional API filtering capabilities
* Improved UX and user feedback
* Better Docker optimizations
* Additional validation rules

**Important:** A complete and clean implementation of the required features is valued more highly than partially completed bonus features.

---

# Out of Scope

Do not spend time on:

* Authentication
* Real database setup
* Complex permissions
* Production-grade styling
* Automated testing frameworks
* CI/CD pipelines
* Cloud deployment

Manual testing and clear code are sufficient for this assessment.

---

# Suggested Time Allocation

```text
Backend API                 45–60 minutes
Frontend UI/API Integration 60–90 minutes
Docker Setup                20–30 minutes
README & Cleanup            20–30 minutes
```

---

# What We're Looking For

We are primarily interested in:

* Clean, maintainable code
* Thoughtful architecture decisions
* Clear API design
* Frontend and backend integration
* Effective use of AI tools
* Ability to explain technical decisions
* Good engineering judgment

A simple, complete, and well-structured solution will score higher than a complex but unfinished one.

---

# Final Notes

Keep the solution simple and focused.

We prefer a smaller, clean, working solution over a larger incomplete one.

Good luck, and have fun building!
