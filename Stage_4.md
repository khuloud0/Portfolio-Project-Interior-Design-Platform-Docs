# SCM and QA Plan

## 1. Development Objectives

### MVP Implementation
Build the functional core of the interior design execution platform using:

- **Flask** for the Backend
- **React** for the Frontend
- **PostgreSQL** for the Database

### Agile Methodology
Development will be executed in **four distinct 2-week sprints**.

### Quality Standards
Code quality will be maintained through:

- GitHub SCM workflow
- Code reviews
- Pull Requests
- QA testing using VS code
- Manual frontend testing

---

## 2. Team Roles & Responsibilities

| Role | Assigned Member | Responsibilities |
|---|---|---|
| Project Manager | [Banan] | Sprint planning, tracking GitHub Project tasks, and unblocking the team |
| SCM Manager | [Khulud] | Managing branches, reviewing Pull Requests, and maintaining code consistency |
| QA Engineer | [Layan] | Creating test plans, validating API endpoints via VS code, and manual UI testing |
| Developers | [Raghad] | Implementing React components, Flask classes, and PostgreSQL schema |

---

## 3. Sprint Execution Plan

## Sprint 1: Infrastructure & Design Intake

### Goal
Set up the development environment and enable homeowners to submit design requests.

### Tasks
- Initialize PostgreSQL database with `users` and `design_requests` tables
- Develop React `RequestForm` component for project specifications and budget
- Implement Flask `/requests` POST endpoint

### QA Focus
- Validate form submission
- Confirm data is correctly saved in the database
- Verify API response using Swagger

---

## Sprint 2: Actionable Execution Plans

### Goal
Allow designers to break down homeowner requests into actionable execution plans.

### Tasks
- Create `execution_plans` and `execution_steps` tables
- Develop `ExecutionPlanView` frontend component
- Develop `StepCard` frontend component
- Implement `/plans` and `/steps` endpoints for plan generation

### QA Focus
- Verify step creation
- Confirm parent-child relationships between plans and steps in the database
- Test API responses through Swagger

---

## Sprint 3: Provider Offers & Designer Tagging

### Goal
Populate the marketplace with provider bids and designer recommendations.

### Tasks
- Implement `Offer` class
- Implement `/offers` POST endpoint
- Develop `RecommendationService` to allow designers to tag best-fit offers
- Build `OffersList` frontend component
- Build `RecommendationBadge` UI component

### QA Focus
- Ensure providers can only bid on relevant `service_type` steps
- Validate offer creation through Swagger
- Confirm recommendation tags display correctly in the UI

---

## Sprint 4: Selection & Project Dashboard

### Goal
Allow homeowners to select providers and track project progress.

### Tasks
- Build `SelectionPanel` for homeowner provider confirmation
- Implement `/select-offer` logic
- Create `projects` table
- Create `ProjectOverview` dashboard for real-time project status tracking

### QA Focus
- Perform end-to-end workflow testing
- Validate project status updates such as `Pending` and `Completed`
- Confirm selected offers are correctly linked to projects

---

## 4. Git Workflow & QA Strategy

### Branching Strategy

All development work must be completed in feature branches.

```bash
main
develop
feature/feature-name

## Branch Rules

- No direct commits to `main`
- All developers must create a branch from `develop`
- Each feature must be developed in a separate `feature/feature-name` branch
- Completed features must be submitted through a Pull Request
- The SCM Manager must review Pull Requests before merging into `develop`

### Git Branch Workflow

```bash
# Move to develop branch
git checkout develop

# Update develop with latest changes
git pull origin develop

# Create a new feature branch
git checkout -b feature/feature-name

## Pull Request Description

### Feature Implemented
Describe the feature added in this Pull Request.

### Type of Change
- [ ] Frontend
- [ ] Backend
- [ ] Database
- [ ] Documentation
- [ ] Bug Fix

### Testing Completed
- [ ] Code runs without errors
- [ ] Backend endpoints tested
- [ ] VS code testing completed
- [ ] Frontend screenshots added, if applicable
- [ ] Database persistence verified

### Review
- [ ] Peer review completed
- [ ] SCM Manager approval received

## Swagger API Testing Checklist

### Endpoint Tested
`POST /endpoint-name`
`POST /requests`
`POST /plans`
`POST /steps`
`POST /offers`
`POST /select-offer`

### Verification
- [ ] Correct HTTP status code returned
- [ ] Correct JSON response format returned
- [ ] Required fields validation works
- [ ] Error handling works correctly
- [ ] Data is saved successfully in the database

## Definition of Done

- [ ] Code builds without errors
- [ ] Unit tests passed
- [ ] Swagger API testing completed
- [ ] Documentation updated
- [ ] Pull Request reviewed and approved
- [ ] QA verified the feature locally

Project Board: [https://github.com/users/khuloud0/projects/2/views/1](#)

