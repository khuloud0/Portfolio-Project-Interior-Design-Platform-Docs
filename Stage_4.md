
# Interior Design Platform

## Overview

The Interior Design Platform is a web-based application designed to support the execution process of interior design projects.

The platform connects homeowners, designers, and service providers by allowing homeowners to submit design requests, designers to create execution plans, and providers to submit offers for project tasks.

The project was developed as an MVP using Flask, React, and PostgreSQL.

---

## Technologies Used

- Backend: Flask
- Frontend: React
- Database: PostgreSQL
- Database Management Tool: Postico
- Version Control: Git and GitHub
- Project Management: GitHub Project Board and GitHub Issues
- Testing: Manual testing and API testing using VS Code

---

## MVP Development and Execution

### Development Objectives

The main objective of the MVP was to build the functional core of the interior design execution platform.

The MVP implementation focused on:

- Building the backend using Flask
- Building the frontend using React
- Creating and managing the database using PostgreSQL
- Connecting frontend features with backend API endpoints
- Testing user flows, form validation, API responses, and database persistence

---

## Agile Methodology

The project was developed using an Agile workflow.

Development was organized into four 1-week sprints. Each sprint focused on a specific part of the platform and included planning, implementation, testing, review, and improvement.

---

## Quality Standards

Code quality and project organization were maintained through:

- GitHub source control management workflow
- Feature branches
- Pull Requests
- Code reviews
- GitHub Issues and Project Board tracking
- QA testing using VS Code
- Manual frontend testing
- Local database verification using Postico

---

## Team Roles and Responsibilities

| Role | Assigned Member | Responsibilities |
|---|---|---|
| Project Manager | Banan | Sprint planning, tracking GitHub Project tasks, and unblocking the team |
| backend Lead | Khuloud | backend & Took on part of the Frontend and UI/UX responsibilities after the team restructuring. |
| QA Engineer | Layan | Creating test plans, validating API endpoints using VS Code, and manual UI testing |
| Developer | Raghad | Implementing React components, Flask classes, and PostgreSQL schema |

---

## Sprint Execution Plan

## Sprint 1: Infrastructure and Design Intake

### Goal

Set up the development environment and enable homeowners to submit design requests.

### Tasks

- Initialize PostgreSQL database with `users` and `design_requests` tables
- Develop React `RequestForm` component for project specifications and budget
- Implement Flask `/requests` POST endpoint

### QA Focus

- Validate form submission
- Confirm data is correctly saved in the database
- Verify API response using VS Code

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
- Test API responses through VS Code

---

## Sprint 3: Provider Offers and Designer Tagging

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
- Validate offer creation through VS Code
- Confirm recommendation tags display correctly in the UI

---

## Sprint 4: Selection and Project Dashboard

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

## Project Management and QA Documentation

This section documents the team workflow, sprint process, source control, bug tracking, testing evidence, and production environment used during the project.

---

## Sprint Reviews

Sprint reviews were conducted at the end of each sprint to evaluate the completed work, demonstrate implemented features, and discuss feedback.

During the sprint reviews, the team reviewed:

- Completed tasks
- Implemented features
- Tested features
- Bugs found during development
- Improvements needed for the next sprint

Although no separate screenshots were captured specifically for sprint review meetings, the GitHub Project Board was used as evidence of sprint progress, task completion, assigned responsibilities, and completed features.

Sprint review evidence:

- GitHub Repository: https://github.com/khuloud0/interior-design-platform
- GitHub Project Board: https://github.com/users/khuloud0/projects/2/views/1

---

## Retrospectives

After each sprint, the team reflected on the development process and discussed what went well, what challenges were faced, and what could be improved in the following sprint.

The retrospective discussions helped the team identify issues related to:

- Task progress
- Bug fixing
- Validation problems
- Communication
- Testing improvements
- Workflow improvements

Although no separate retrospective screenshots were captured, retrospective outcomes were reflected in updated tasks, resolved bugs, and improvements tracked in the GitHub Project Board and GitHub Issues.

Retrospective evidence:

- GitHub Repository: https://github.com/khuloud0/interior-design-platform
- GitHub Project Board: https://github.com/users/khuloud0/projects/2/views/1

---

## Sprint Planning

Sprint planning was conducted before starting each sprint to define sprint goals, assign tasks, set priorities, and organize the work between team members.

The team divided the project work into:

- Backend tasks
- Frontend tasks
- Database tasks
- Authentication tasks
- Validation tasks
- Testing tasks
- Bug-fixing tasks

Each task was assigned to a team member with a status, priority, and sprint label.

The GitHub Project Board was used to manage sprint planning and track sprint progress.

Sprint planning evidence:

- GitHub Repository: https://github.com/khuloud0/interior-design-platform
- GitHub Project Board: https://github.com/users/khuloud0/projects/2/views/1

---

## Source Repository

The project source code is maintained using Git and GitHub.

Git was used for:

- Version control
- Collaboration
- Tracking code changes
- Managing branches
- Reviewing Pull Requests
- Merging completed work into the main project repository

Repository link:

- https://github.com/khuloud0/interior-design-platform

---

## Git Workflow and QA Strategy

### Branching Strategy

All development work was completed using feature branches.

Main branches used:

- `main`
- `develop`
- `feature/feature-name`

### Branch Rules

The team followed these branch rules:

- No direct commits to `main`
- All developers created branches from `develop`
- Each feature was developed in a separate `feature/feature-name` branch
- Completed features were submitted through a Pull Request
- The SCM Manager reviewed Pull Requests before merging into `develop`

### Git Branch Workflow

Before starting a new feature:

```bash
git pull origin develop
git checkout -b feature/feature-name
```

After completing the feature:

```bash
git add .
git commit -m "Add feature description"
git push origin feature/feature-name
```

Then, a Pull Request was created from `feature/feature-name` to `develop`.

---

## Pull Request Rules

Each Pull Request included:

- Clear description of the implemented feature
- Screenshots if frontend changes were made
- VS Code test results for backend endpoints
- Confirmation that the code runs without errors
- At least one peer review from the SCM Manager

### Pull Request Checklist

- [ ] Clear description of the implemented feature
- [ ] Frontend screenshots added, if applicable
- [ ] VS Code testing completed
- [ ] Code runs without errors
- [ ] Peer review completed
- [ ] SCM Manager approval received

---

## Bug Tracking

Bug tracking was managed using GitHub Issues and the GitHub Project Board.

Bugs and improvements were tracked, assigned to team members, prioritized, and updated based on their status.

Examples of bugs and improvements tracked during the project include:

- Register duplicate phone validation
- Register duplicate email validation
- Password validation errors
- Phone number format validation
- Email validation restrictions
- Sign-in validation behavior
- Form validation improvements
- Frontend responsiveness improvements
- Designer profile image upload handling

Bug tracking evidence:

- GitHub Issues / Project Board: https://github.com/khuloud0/interior-design-platform
- GitHub Project Board: https://github.com/users/khuloud0/projects/2/views/1

---

## Testing Evidence and Results

Testing was performed throughout the project to ensure that the main features worked correctly and that bugs were resolved.

Testing included:

- Manual testing
- Form validation testing
- Authentication testing
- API endpoint testing
- Database testing
- Bug-fix verification
- End-to-end workflow testing

---

## API Testing Strategy

All Flask endpoints were tested using VS Code.

The QA Engineer verified:

- Correct HTTP status codes
- Correct JSON response format
- Required field validation
- Error handling
- Successful database persistence

### Example Endpoints Tested

- `POST /requests`
- `POST /plans`
- `POST /steps`
- `POST /offers`
- `POST /select-offer`

### VS Code API Testing Checklist

- [ ] Correct HTTP status code returned
- [ ] Correct JSON response format returned
- [ ] Required fields validation works
- [ ] Error handling works correctly
- [ ] Data is saved successfully in the database

---

## Tested Features

| Feature | Test Case | Result |
|---|---|---|
| User registration | Register with valid user information | Passed |
| Duplicate email validation | Register using an already existing email | Passed |
| Duplicate phone validation | Register using an already existing phone number | Passed |
| Password validation | Register with missing uppercase, lowercase, number, or special character | Passed |
| Phone validation | Phone number must follow the required format | Passed |
| Login validation | User cannot log in with invalid credentials | Passed |
| Backend authentication | JWT authentication works after login | Passed |
| Database connection | Backend connects successfully to PostgreSQL | Passed |
| Designer profile | Designer profile data can be stored and managed | Passed |
| Design request form | Homeowner can submit a design request | Passed |
| Execution plans | Designer can create execution plans | Passed |
| Execution steps | Designer can create project steps | Passed |
| Provider offers | Provider can submit an offer | Passed |
| Offer selection | Homeowner can select an offer | Passed |
| Project dashboard | Project status can be tracked | Passed |
| Bug fixes | Reported bugs were tested again after fixing | Passed |

Testing evidence:

- GitHub Issues / Project Board: https://github.com/khuloud0/interior-design-platform
- GitHub Project Board: https://github.com/users/khuloud0/projects/2/views/1

---

## Definition of Done

A task was considered complete only when:

- [ ] Code builds without errors
- [ ] Unit tests passed, if applicable
- [ ] VS Code API testing completed
- [ ] Documentation updated
- [ ] Pull Request reviewed and approved
- [ ] QA verified the feature locally

---

## Production Environment

The project was developed and tested in a local development environment.

No online production deployment was used for this version of the project. The frontend, backend, and database were run locally during development and testing.

---

## Backend API Deployment

The backend API was run locally during development and testing. The local backend API allowed the frontend application to communicate with the backend server and PostgreSQL database.

Local backend API:

```bash
http://localhost:5000
```

---

## Local Frontend

The frontend application was also run locally during development.

Example local frontend URL:

```bash
http://localhost:5173
```

or

```bash
http://localhost:3000
```

depending on the frontend development server configuration.

---

## Database

The project uses PostgreSQL as the database system.

The PostgreSQL database was hosted locally during development. Postico was used as a database client to view, manage, and present the database tables and records.

Database provider:

```md
Local PostgreSQL
```

Database management tool:

```md
Postico
```

No external database hosting provider was used for this version of the project.

---

## Environment Variables

The backend requires environment variables to connect to the database and manage authentication securely.

Real secret values should not be committed to GitHub. They should be stored in a local `.env` file and excluded using `.gitignore`.

---

## Project Links

- GitHub Repository: https://github.com/khuloud0/interior-design-platform
- GitHub Project Board: https://github.com/users/khuloud0/projects/2/views/1

---

## Summary

The project was managed using GitHub as the main collaboration platform. The team used GitHub Project Board and GitHub Issues for sprint planning, sprint reviews, retrospectives, bug tracking, task assignment, and progress monitoring.

The application was developed and tested locally using Flask, React, PostgreSQL, and Postico.

The MVP focused on enabling homeowners to submit design requests, designers to create execution plans, providers to submit offers, and homeowners to select providers and track project progress.
````
