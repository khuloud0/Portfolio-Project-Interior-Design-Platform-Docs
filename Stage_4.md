# Stage 4: MVP Development and Execution

## Objectives
* Implement the MVP based on the technical documentation developed in the previous stage.[cite: 2]
* Adopt Agile principles to divide work into manageable sprints, ensuring iterative development and continuous improvement.[cite: 2]
* Assign roles and responsibilities, emphasizing the importance of Project Manager, SCM, and QA roles for project organization and quality assurance.[cite: 2]
* Promote collaboration among team members with clear task assignments, deadlines, and dependencies.[cite: 2]
* Monitor progress through metrics, address deviations from the plan, and prioritize deliverables effectively.[cite: 2]

## Importance of Stage 4
This stage represents the most intensive phase of the project, translating plans and designs into a functional MVP.[cite: 2] Non-technical roles like Project Manager, SCM, and QA are vital to maintaining organization, ensuring the integrity of the codebase, and delivering high-quality results.[cite: 2] The adoption of Agile methodologies, such as sprints, fosters adaptability, consistent progress, and team alignment.[cite: 2]

## Key Roles for Stage 4
* **Project Manager (PM):** Oversees planning, sprint organization, and progress tracking. Coordinates team activities and ensures deadlines are met. Manages deviations and adapts the plan as needed.[cite: 2]
* **Source Control Manager (SCM):** Ensures proper use of version control (e.g., Git). Maintains branch integrity, conducts code reviews, and enforces best practices.[cite: 2]
* **Quality Assurance (QA):** Develops and executes test plans, including unit, integration, and user acceptance testing. Ensures all deliverables meet the predefined quality standards before deployment.[cite: 2]
* **Technical Roles:** Developers, database administrators, and other technical members responsible for implementing features, APIs, UI components, or other project elements.[cite: 2]

---

## Tasks for Stage 4

### 0. Plan and Define Sprints
**Purpose:** To divide the development phase into short, manageable iterations.[cite: 2]

Based on the MoSCoW priorities and architectural layers defined in Stage 3, here is the prioritized sprint plan for the interior design execution platform:

#### **Sprint 1: Foundation & Design Requests (Weeks 1-2)**
* **Goal:** Establish the base architecture and allow homeowners to submit design requests.
* **Frontend (React):** Set up `App` structure and `Navbar`.[cite: 2] Build the `RequestForm` component for homeowners.[cite: 2]
* **Backend (Flask/PostgreSQL):** Initialize database with `users`, `provider_profiles`, and `design_requests` tables.[cite: 2] Implement the `/requests` POST endpoint.[cite: 2]
* **QA:** Test local database connection, validate the design request form for accurate input handling, and verify the `/requests` endpoint with Swagger.[cite: 2]

#### **Sprint 2: Execution Planning (Weeks 3-4)**
* **Goal:** Enable designers to deconstruct requests into actionable execution steps.
* **Frontend (React):** Build the `ExecutionPlanView` and `StepCard` components.[cite: 2]
* **Backend (Flask/PostgreSQL):** Create `execution_plans` and `execution_steps` tables.[cite: 2] Implement `/plans` and `/steps` POST endpoints.[cite: 2]
* **QA:** Verify execution plan creation and step structure.[cite: 2] Ensure steps are properly linked to their parent plans in the database.

#### **Sprint 3: Provider Offers & Designer Recommendations (Weeks 5-6)**
* **Goal:** Allow providers to submit offers and designers to tag recommendations.
* **Frontend (React):** Develop `OffersList`, `OfferCard`, and `RecommendationBadge` components.[cite: 2]
* **Backend (Flask/PostgreSQL):** Build the `offers` table.[cite: 2] Implement the `/offers` POST endpoint and the `RecommendationService` logic.[cite: 2]
* **QA:** Test the offer submission flow.[cite: 2] Validate that designers can successfully tag the best-fit offers and that the frontend updates accordingly.

#### **Sprint 4: Final Package, Selection & Tracking (Weeks 7-8)**
* **Goal:** Complete the core workflow by enabling provider selection and project tracking.
* **Frontend (React):** Build the `SelectionPanel`, `ProjectOverview`, and `ContactProviderButton` components.[cite: 2]
* **Backend (Flask/PostgreSQL):** Create `selected_offers` and `projects` tables.[cite: 2] Implement `/select-offer` POST and `/projects/{id}` GET endpoints.[cite: 2]
* **QA:** Perform end-to-end (E2E) manual testing on the offer selection and project confirmation flow.[cite: 2] Ensure real-time status indicators (Pending, In Progress, Completed) update correctly.[cite: 2]

---

### 1. Execute Development Tasks
**Purpose:** To implement features and deliverables according to the sprint plan.[cite: 2]
* **Instructions:**
  * Developers focus on assigned React and Flask tasks for the current sprint, adhering to clean code standards.[cite: 2]
  * The SCM manages the `main`, `develop`, and `feature/*` branches.[cite: 2] Code must pass peer review via Pull Requests (PRs) before merging into `develop`.[cite: 2]
  * QA conducts tests on completed tasks to identify bugs or improvements.[cite: 2]

### 2. Monitor Progress and Adjust
**Purpose:** To track team performance, measure progress, and address any issues.[cite: 2]
* **Instructions:**
  * Conduct daily discussion to review completed frontend/backend tasks, discuss blockers, and plan the day’s work.[cite: 2]
  * Use the GitHub Projects board to update task statuses and track metrics such as sprint velocity.[cite: 2]
  * Adjust sprint goals or reassign tasks (e.g., shifting UI work if backend API dependencies are delayed) as necessary.[cite: 2]

### 3. Conduct Sprint Reviews and Retrospectives
**Purpose:** To review progress, demo completed features, and reflect on process improvements.[cite: 2]
* **Instructions:**
  * At the end of each sprint, demo completed features (like the Request Form or Selection Panel).[cite: 2]
  * Conduct a retrospective answering: What worked well? What challenges did we face? What changes can we make to improve the next sprint?[cite: 2]

### 4. Final Integration and QA Testing
**Purpose:** To ensure all components work together seamlessly and meet quality standards.[cite: 2]
* **Instructions:**
  * Conduct integration tests to verify the end-to-end functionality of the MVP, tracing the data flow from `Homeowner Request` -> `Designer Plan` -> `Provider Offer` -> `Final Selection`.[cite: 2]
  * QA executes the final test plan, including manual UI testing and Swagger API testing for correct JSON formats and HTTP status codes.[cite: 2]
  * Fix any critical bugs identified before finalizing the local deployment.[cite: 2]

---

### 5. Deliverables Repository Links

[GitHub Project Board](https://github.com/users/khuloud0/projects/2/views/1)
