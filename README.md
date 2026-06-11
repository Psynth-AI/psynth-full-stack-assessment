# Psynth Full Stack Engineer Take-Home Assessment

## Introduction

Thank you for your interest in joining Psynth.

This assessment is designed to evaluate your ability to build and deliver a small full-stack application using technologies similar to those used by our engineering team.

We are primarily evaluating:

* Code quality
* API design
* Frontend/backend integration
* Engineering judgment
* Ability to leverage AI tools effectively
* Communication and documentation

This assessment should take approximately **2–3 hours** to complete.

---

# Scenario

You are building a simple internal **Document Review Queue** application.

Internal users need a way to manage documents submitted for review.

Each document contains:

* ID
* Title
* Submitter Name
* Category
* Status
* Priority
* Created Date
* Summary

Users should be able to:

* View documents
* Filter documents
* Create documents
* Update document status
* Delete documents

This is intentionally a simple, neutral domain so that we can focus on engineering fundamentals.

Do **not** include PHI, PII, patient information, healthcare records, or sensitive personal data.

---

# Technical Requirements

## Frontend

Build the frontend using:

* React
* TypeScript

The frontend should provide:

### Document List

Display all documents returned by the API.

### Filtering

Allow filtering by status:

* Pending
* In Review
* Approved
* Rejected

### Document Details

Allow users to view details of a selected document.

### Create Document

Allow users to create a new document.

### Update Document

Allow users to update the status of a document.

### Delete Document

Allow users to delete a document.

### User Experience

Handle:

* Loading states
* Error states
* Empty states

The UI does not need to be heavily styled.

We care more about structure, maintainability, and functionality than visual design.

---

## Backend

Build the backend using:

* Python
* FastAPI

Create the following endpoints:

```http
GET    /documents
GET    /documents/{document_id}
POST   /documents
PATCH  /documents/{document_id}
DELETE /documents/{document_id}
```

### Backend Expectations

* Use Pydantic models
* Validate requests
* Return appropriate HTTP status codes
* Return meaningful error messages
* Keep implementation simple and maintainable
* Expose OpenAPI documentation through FastAPI

---

# Data Requirements

Use mocked data only.

Do not use:

* PostgreSQL
* MongoDB
* MySQL
* SQLite
* External services

Store the initial data in a local JSON file.

Suggested file location:

```text
backend/data/documents.json
```

Load the JSON file when the application starts.

You may keep the data in memory while the application is running.

---

# Mock Data

Use the following mock data as the starting dataset.

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
  },
  {
    "id": "doc_005",
    "title": "Product Requirements Draft",
    "submitter_name": "Casey Nguyen",
    "category": "Product",
    "status": "pending",
    "priority": "medium",
    "created_at": "2026-06-05T11:20:00Z",
    "summary": "Initial product requirements draft for review before planning."
  },
  {
    "id": "doc_006",
    "title": "Engineering Design Notes",
    "submitter_name": "Morgan Patel",
    "category": "Engineering",
    "status": "in_review",
    "priority": "high",
    "created_at": "2026-06-06T13:10:00Z",
    "summary": "Technical design notes for a proposed internal workflow improvement."
  },
  {
    "id": "doc_007",
    "title": "Customer Feedback Summary",
    "submitter_name": "Riley Johnson",
    "category": "Customer Success",
    "status": "approved",
    "priority": "medium",
    "created_at": "2026-06-07T08:45:00Z",
    "summary": "Summary of recent customer feedback grouped by theme."
  },
  {
    "id": "doc_008",
    "title": "Internal Policy Update",
    "submitter_name": "Drew Carter",
    "category": "Operations",
    "status": "pending",
    "priority": "low",
    "created_at": "2026-06-08T15:35:00Z",
    "summary": "Proposed update to an internal operations policy."
  }
]
```

Candidates may add additional mock records if useful.

---

# Valid Field Values

## Status

```text
pending
in_review
approved
rejected
```

## Priority

```text
low
medium
high
```

---

# Docker Requirements

Your solution must include Docker support.

Required files:

```text
docker-compose.yml
frontend/Dockerfile
backend/Dockerfile
```

The following command should start the application:

```bash
docker compose up --build
```

Expected URLs:

```text
Frontend:
http://localhost:5173

Backend:
http://localhost:8000

API Documentation:
http://localhost:8000/docs
```

---

# AI Tool Usage

At Psynth, engineers are expected to use AI tools effectively.

For this assessment, you are required to use one or more AI tools.

Examples include:

* ChatGPT
* Claude
* Gemini
* Cursor
* GitHub Copilot
* Windsurf
* Cline
* Any equivalent AI coding assistant

In your README include a section called:

```text
AI Tool Usage
```

Describe:

## Tools Used

Which AI tools you used.

## How You Used Them

Examples:

* Boilerplate generation
* API implementation
* React components
* Docker setup
* Documentation

## Accepted Suggestions

What AI-generated code or suggestions you kept.

## Modified Suggestions

What AI-generated code you changed.

## Rejected Suggestions

What AI-generated code or recommendations you rejected and why.

## Validation Process

How you verified AI-generated output was correct.

We are not evaluating whether you used AI.

We are evaluating how effectively you used it.

---

# Video Walkthrough

Record a short video, approximately **5 minutes**.

The video should include:

## Application Demo

Show:

* Document list
* Filtering
* Creating a document
* Updating a document
* Deleting a document

## Technical Walkthrough

Explain:

* Project structure
* Frontend architecture
* Backend architecture
* API design decisions
* Tradeoffs made

## AI Discussion

Explain:

* Which AI tools were used
* How they helped
* What they got wrong
* How you validated their output

Accepted platforms:

* Loom
* YouTube, unlisted
* Vimeo
* Google Drive

Include the video URL in your README.

---

# README Requirements

Your repository README should contain:

* Project Overview
* Tech Stack
* Setup Instructions
* Docker Instructions
* API Endpoint Summary
* Known Limitations
* Tradeoffs Made
* AI Tool Usage
* Video Walkthrough Link
* Future Improvements

---

# Bonus

The following are optional and are not required.

Examples:

* Search functionality
* Sorting
* Pagination
* Better UX
* Additional API filters
* Improved validation
* Responsive design improvements

A clean and complete implementation of the required features is preferred over partially completed bonus features.

---

# Out of Scope

Do not spend time implementing:

* Authentication
* Authorization
* Databases
* CI/CD
* Automated testing frameworks
* Cloud deployment
* Production-grade styling

---

# Evaluation Criteria

## Functionality — 30%

* CRUD operations work correctly
* Frontend and backend integrate correctly
* Application behaves as expected
* Docker setup works correctly

## Code Quality — 25%

* Readable code
* Maintainable structure
* Separation of concerns
* Appropriate abstractions
* Avoids unnecessary complexity

## API Design — 15%

* Clear endpoint design
* Appropriate validation
* Proper error handling
* Predictable request and response shapes

## Frontend Implementation — 15%

* Clean React implementation
* Clear state management approach
* Loading, error, and empty states are handled
* User actions provide visible feedback

## Communication — 10%

* Documentation quality
* Clear README
* Tradeoff explanations
* Complete setup instructions

## AI Tool Usage — 5%

* Effective use of AI
* Understanding of generated code
* Ability to evaluate AI output critically
* Clear explanation of what was accepted, modified, and rejected

---

# Submission Instructions

## Submission Format

The assessment must be submitted as a GitHub repository.

Do not submit:

* ZIP files
* Email attachments
* Google Drive folders containing source code
* Screenshots
* Code snippets

## Repository Requirements

Your repository must contain:

* Frontend source code
* Backend source code
* Mock data
* Docker configuration
* README
* Video walkthrough link

## Required GitHub Sharing

You MUST share your repository with these GitHub users:

```text
sbpsynth
alicioalves
tomymaritano
```

This requirement is mandatory.

If your repository is private, ensure that `sbpsynth` has been granted access before submission.

## Final Submission Steps

1. Create a GitHub repository.
2. Push your completed solution.
3. Share the repository with `sbpsynth`.
4. Verify that access has been granted.
5. Ensure the README contains the walkthrough video link.
6. Send us the repository URL.

## Submission Checklist

Before submitting, verify:

* [ ] CRUD functionality works
* [ ] Frontend loads correctly
* [ ] Backend loads correctly
* [ ] Docker setup works
* [ ] `docker compose up --build` runs successfully
* [ ] Frontend is available at `http://localhost:5173`
* [ ] Backend is available at `http://localhost:8000`
* [ ] API docs are available at `http://localhost:8000/docs`
* [ ] README is complete
* [ ] AI Tool Usage section is included
* [ ] Walkthrough video link is included
* [ ] No secrets or credentials are committed
* [ ] Repository has been shared with `sbpsynth`

---

# What We Are Looking For

We are not looking for a perfect solution.

We are looking for evidence that you can:

* Build working software
* Make reasonable engineering decisions
* Communicate clearly
* Use AI tools effectively
* Deliver a complete solution

A simple, complete, well-structured solution will score higher than a complex but unfinished one.

Good luck, and we look forward to reviewing your submission.
