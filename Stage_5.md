## Interior Design Platform

### Project Overview

The Interior Design Platform is a web-based MVP designed to connect homeowners with credible interior designers. The platform helps homeowners submit design requests, review designer profiles, and start a structured design process with trusted professionals.

The project was developed as part of a staged software development process, moving from ideation and planning to technical documentation, database implementation, backend development, testing, and final presentation.

The main goal of the platform is to solve the problem of trust and accessibility in the interior design process by creating a structured system where homeowners can connect with credible designers and, in future stages, trusted contractors for real-life execution.


---


## 1. Results Summary

### MVP Core Functionalities

The MVP focused on the main features needed to demonstrate the platform concept and user journey.

The core functionalities include:

- User registration and authentication
- Login system using JWT-based authentication
- Role-based user structure for homeowners, designers, and providers
- Homeowner design request submission
- Designer profile structure
- Provider profile structure
- Offer model for designer responses
- Selected offer model to connect accepted offers with projects
- Project model to track accepted work
- Execution plan and execution steps structure
- PostgreSQL database schema with relationships between main entities
- Backend API structure using Flask routes and services
- Database migrations using Flask-Migrate and Alembic
- Data validation and system security considerations

---

## 2. Comparison to Initial Objectives

### Initial Project Objective

The initial objective was to build a platform that bridges the gap between homeowners and credible interior designers, with an extended pipeline to connect designers with trusted contractors for real-life execution.

The platform aimed to:

- Help homeowners submit interior design requests easily
- Allow designers to receive and respond to design requests
- Support credibility through structured profiles and organized data
- Build a scalable backend and database structure
- Prepare the foundation for future contractor and execution management features

### Final Outcome

The MVP successfully achieved the main foundation of the system. The project delivered a working backend structure, database models, relationships, authentication logic, and the main workflow needed to support the interior design request process.

The project outcome matches the initial objectives because the MVP provides the core technical structure required for:

- Homeowner request creation
- Designer and provider profile management
- Offers and selected offers
- Project tracking
- Execution planning
- Future expansion into contractor coordination and real-life execution

---

## 3. Key Metrics and Outcomes

| Area | Outcome |
|---|---|
| MVP completion | Core backend and database functionality completed |
| Database implementation | PostgreSQL schema created with main project entities |
| Authentication | JWT-based authentication implemented |
| Data integrity | Foreign key relationships and model constraints added |
| Development workflow | GitHub Issues and GitHub Project Board used for task tracking |
| Testing | Manual testing and bug-fix verification performed |
| Documentation | Project stages, technical decisions, and final report documented |
| Presentation readiness | Final project presentation content prepared |

---

## 4. Technical Results

### Backend

The backend was developed using Flask. The structure was organized into models, routes, services, and utility files to keep the code clean and maintainable.

Main backend components include:

- `models/`
- `routes/`
- `services/`
- `utils/`
- `config.py`
- `run.py`

### Database

PostgreSQL was used as the main database. SQLAlchemy was used to define the models and relationships, while Flask-Migrate and Alembic were used to manage database migrations.

Main database models include:

- `User`
- `DesignerProfile`
- `ProviderProfile`
- `DesignRequest`
- `Offer`
- `SelectedOffer`
- `Project`
- `ExecutionPlan`
- `ExecutionStep`

### Authentication and Security

JWT authentication was used to manage user login and secure access to protected routes.

Security considerations included:

- Password hashing
- Token-based authentication
- Protected routes
- Input validation
- Clear relationship constraints in the database
- Separation between routes, services, and models

---

# Lessons Learned

## 1. What Went Well

### Clear Project Idea

The team had a clear problem to solve: homeowners often struggle to find credible interior designers and trusted execution support. This helped the team stay focused on the platform’s purpose.

### Strong Technical Foundation

The backend and database structure were built carefully. The use of PostgreSQL, SQLAlchemy, and Flask-Migrate helped create a scalable and organized system.

### Improved Understanding of Backend Development

During the project, the team improved their understanding of:

- Database relationships
- Foreign keys
- Backend routes
- Models and services
- Authentication flow
- API structure
- GitHub workflow
- Debugging and fixing errors

### Task Tracking

Using GitHub Issues and the Project Board helped organize the work, track bugs, and follow task progress.

### Problem Solving

Several technical issues were solved during development, including migration problems, model relationship updates, validation errors, and Git rebase conflicts.

---

## 2. Challenges Faced

### Database and Migration Issues

One challenge was managing database migrations correctly. Some migrations did not detect changes at first, and the team had to check the Flask setup, model imports, and migration commands.

### Backend Complexity

The backend structure included many connected files, such as models, routes, services, and utility files. Understanding how these files work together required careful review and practice.

### Git and Branch Management

Git conflicts and rebasing created challenges. The team had to resolve conflicts carefully to avoid losing code and to keep the project history clean.

### Time Management

Because the project included planning, documentation, coding, testing, and presentation preparation, time management was important. Some tasks required more time than expected.

### Testing Time

Testing was performed throughout the project, but more time could have been allocated for deeper testing, especially for edge cases and full user journeys.

---

## 3. How Challenges Were Addressed

| Challenge | How It Was Addressed |
|---|---|
| Migration issues | Checked Flask app setup, verified model imports, and reran migration commands |
| Database relationship errors | Reviewed model relationships and foreign keys carefully |
| Git conflicts | Resolved conflicts manually and continued the rebase process step by step |
| Backend complexity | Organized code into models, routes, services, and utilities |
| Validation issues | Added and improved validation logic |
| Testing limitations | Used manual testing and bug-fix verification |

---

## 4. Improvements for Future Projects

For future projects, the team can improve by:

- Starting testing earlier in the development process
- Writing clearer task assignments from the beginning
- Creating more detailed API documentation
- Adding automated tests
- Improving frontend and backend integration earlier
- Scheduling more frequent team check-ins
- Allocating more time for debugging and final polishing
- Preparing the demo earlier to avoid last-minute issues

---

# Team Retrospective

A team retrospective was conducted to reflect on the project experience and identify what worked well, what was challenging, and how the team can improve in future projects.

## Retrospective Questions

The team discussed the following questions:

1. What worked well as a team?
2. What challenges did we face?
3. How were the challenges resolved?
4. How can we improve collaboration in future projects?

---

## What Worked Well

- The team had a shared understanding of the project idea.
- Tasks were tracked using GitHub Issues and the Project Board.
- Team members contributed to different parts of the project.
- Technical problems were discussed and solved step by step.
- Documentation helped clarify the project stages and decisions.
- The team improved their understanding of real software development workflows.

---

## What Could Be Improved

- Task responsibilities could have been assigned more clearly from the beginning.
- More time should have been given to testing.
- Communication could be more frequent during complex technical tasks.
- The team should document technical decisions immediately after making them.
- Demo preparation should start earlier.

---

## Retrospective Summary

The project gave the team practical experience in building a full-stack MVP. The team learned how to move from an idea to a technical implementation, how to manage backend and database development, and how to reflect on project results professionally.

The biggest lesson was that successful software projects require both technical skills and clear collaboration. Strong planning, communication, documentation, and testing are as important as writing code.

---

# Presentation Slide Deck Content

## Suggested Final Presentation Structure

### Slide 1 — Project Title and Team Introduction

**Title:** Interior Design Platform  
**Subtitle:** Connecting Homeowners with Credible Interior Designers

**Content:**

- Team name and members
- Project overview
- Main goal of the platform
- Short introduction to the problem and solution

---

### Slide 2 — Problem Statement

**Title:** The Problem

Homeowners often face difficulty finding credible interior designers who match their needs, style, budget, and expectations.

Common problems include:

- Lack of trust in designer credibility
- Difficulty comparing designers
- Unclear request and communication process
- Limited structured connection between design and real-life execution
- No organized way to move from request to offer to project

---

### Slide 3 — Project Solution

**Title:** Our Solution

The Interior Design Platform provides a structured digital process that connects homeowners with credible interior designers.

The platform allows:

- Homeowners to submit design requests
- Designers to create profiles and respond to requests
- Offers to be managed clearly
- Selected offers to become projects
- Execution plans and steps to support future implementation

The platform bridges the gap between homeowners and credible interior designers, with an extended pipeline to connect designers with trusted contractors for real-life execution.

---

### Slide 4 — Project Process

**Title:** Project Journey

The project was completed through multiple stages:

1. Ideation and problem selection
2. Project charter and MVP planning
3. Technical documentation
4. Database and backend development
5. Testing, results, lessons learned, and presentation

Each stage helped move the project from an idea into a working MVP foundation.

---

### Slide 5 — MVP Core Features

**Title:** MVP Features

The MVP includes:

- User registration
- User login
- JWT-based authentication
- Homeowner design request creation
- Designer profile structure
- Provider profile structure
- Offer management
- Selected offer management
- Project tracking
- Execution plan and execution steps
- PostgreSQL database relationships

---

### Slide 6 — Technical Showcase

**Title:** Technical Architecture

**Frontend:**

- React

**Backend:**

- Flask

**Database:**

- PostgreSQL

**Authentication:**

- JWT authentication

**ORM and Migrations:**

- SQLAlchemy
- Flask-Migrate
- Alembic

**Development Tools:**

- GitHub
- GitHub Issues
- GitHub Project Board
- VS Code
- Postico
- Local PostgreSQL environment

---

### Slide 7 — Database Design

**Title:** Database Structure

Main tables include:

- Users
- Designer Profiles
- Provider Profiles
- Design Requests
- Offers
- Selected Offers
- Projects
- Execution Plans
- Execution Steps

Key relationships:

- One user can have one designer profile
- One user can have one provider profile
- One homeowner can create many design requests
- A design request can receive offers
- A selected offer can become a project
- A project can have an execution plan
- An execution plan can include multiple execution steps

---

### Slide 8 — APIs and Backend Design

**Title:** Backend and API Structure

The backend was organized into:

- Models: define database tables and relationships
- Routes: handle API endpoints
- Services: contain business logic
- Utils: support authentication and validation

This structure helped make the backend more organized, readable, and easier to maintain.

---

### Slide 9 — MVP Demo

**Title:** MVP Demo

During the live demo, we will show:

- User registration
- User login
- Creating a design request
- Viewing the backend/database structure
- Showing how requests, offers, and projects are connected
- Explaining how the system supports the full user journey

Demo focus:

- Core functionality
- Database relationships
- User journey
- MVP readiness

---

### Slide 10 — Results

**Title:** Results and Outcomes

The MVP achieved the main project goals by creating a functional backend and database foundation for the platform.

Results include:

- Core system models completed
- Database relationships implemented
- Authentication structure added
- Main project workflow supported
- GitHub task tracking used
- Testing and bug fixes completed
- Final presentation and documentation prepared

---

### Slide 11 — Lessons Learned

**Title:** Lessons Learned

What went well:

- Clear project idea
- Strong database foundation
- Improved backend understanding
- Effective use of GitHub Issues
- Step-by-step problem solving

Challenges:

- Database migrations
- Backend file structure
- Git conflicts
- Time management
- Testing limitations

Future improvements:

- Start testing earlier
- Improve task assignment
- Add automated tests
- Prepare demo earlier
- Improve technical documentation during development

---

### Slide 12 — Team Retrospective

**Title:** Team Reflection

The team reflected on the project experience using retrospective questions:

- What worked well?
- What challenges did we face?
- How did we solve them?
- What can we improve next time?

Main reflection:

The project showed that building an MVP requires clear communication, structured planning, technical implementation, testing, and continuous improvement.

---

### Slide 13 — Future Recommendations

**Title:** Future Improvements

Future improvements for the platform include:

- Complete frontend and backend integration
- Add designer search and filtering
- Add portfolio image upload
- Add payment functionality
- Add contractor verification
- Add admin dashboard
- Add automated testing
- Improve UI responsiveness
- Deploy the platform online

---

### Slide 14 — Conclusion

**Title:** Conclusion

The Interior Design Platform successfully demonstrates the foundation of a digital solution that connects homeowners with credible interior designers.

The MVP provides the technical base for user authentication, design requests, offers, project creation, and future execution planning.

The project helped the team improve both technical and collaboration skills, and it can be expanded into a more complete platform in the future.

---



The Interior Design Platform MVP successfully demonstrates the project idea and provides a strong technical foundation for future development.
