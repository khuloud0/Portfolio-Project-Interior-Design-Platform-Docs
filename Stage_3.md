# Stage 3: Technical Documentation
**Project:** Interior Design & Contractor Marketplace Platform

## Overview
This platform bridges the gap between homeowners and credible interior designers, with an extended pipeline to connect designers with trusted contractors for whole design execution. The goal is to mitigate professional reliability within the interior design and contracting market by providing a verified, transparent, and seamless user journey from initial room request to physical project completion.

---

## 1. User Stories & Prioritization (MoSCoW Method)

These user stories define the core functionality from the perspective of our three main user types: Homeowners, Designers, and Contractors.

| Priority | User Story |
| :--- | :--- |
| **Must Have** | **As a Homeowner**, I want to submit a detailed design request (room type, size, style preferences) so that designers understand my needs. |
| | **As a Homeowner**, I want to browse verified designer profiles and select one based on their portfolio and credibility rating. |
| | **As a Designer**, I want to receive requests and submit digital draft designs to the homeowner for review. |
| | **As a Homeowner**, I want to pay securely for the final digital design once I approve the draft. |
| **Should Have** | **As a Homeowner**, I want the option to upgrade my digital design to implementation so the designer manages the physical execution. |
| | **As a Designer**, I want to search a directory of credible contractors to hire for the execution phase. |
| | **As a Contractor**, I want to maintain a profile with my credentials and past work to attract interior designers on the platform. |
| **Could Have** | **As a user (all)**, I want an in-app messaging system so that I can communicate seamlessly without leaving the platform. |
| **Won’t Have** | **As a Homeowner**, I want an AI to automatically generate my design. *(Out of scope: The core value is human credibility and connection).* |

---

## 2. Mockups / Wireframes

The following wireframes outline the main user interface screens of the MVP, focusing on the multi-sided marketplace flow.

| | | |
|:---:|:---:|:---:|
| **Home / Landing Page**<br>Value prop & search bar | **Designer Directory**<br>List of credible designers | **Designer Profile**<br>Portfolio, reviews, "Hire Me" |
| **Project Request Form**<br>Room, size, budget, style | **Homeowner Dashboard**<br>Track drafts & project status | **Designer Dashboard**<br>Manage requests & active jobs |
| **Draft Review & Payment**<br>Approve design & Checkout | **Contractor Directory**<br>For designers executing builds | **Contractor Profile**<br>Licenses, past projects, ratings |

---

## 3. Design System Architecture

### Overview
The MVP utilizes a **three-layer web architecture** (Frontend, Backend, Database) to support the complex relational data of a three-sided marketplace (Homeowner, Designer, Contractor).

### Main Components

| Component | Technology | Responsibility |
| :--- | :--- | :--- |
| **Frontend** | **React** | Handles dynamic UI for distinct user dashboards (Homeowner, Designer, Contractor) and project forms. |
| **Backend** | **Flask (Python)** | Manages business logic: user verification, matching algorithms, payment routing, and project state management. |
| **Database** | **PostgreSQL (SQL)** | Stores highly relational data including user profiles, project details, transactions, and credibility reviews. |

### Data Flow
1. **Request Phase:** Homeowner inputs project specs via React frontend. Data is sent to Flask backend.
2. **Matching Phase:** Homeowner selects a designer. Backend creates a "Project Sandbox" linking the two users in the SQL database.
3. **Draft & Payment Phase:** Designer uploads digital drafts via frontend. Homeowner approves and pays. Backend processes payment (via Stripe API) and unlocks the final files.
4. **Execution Phase (Optional):** If the Homeowner opts for  application, the backend updates the project status. The Designer queries the database for verified Contractors, initiating a secondary connection.

---

## 4. Define Components, Classes, and Database Design

### 01. Frontend Components (React)
| Component | Description |
| :--- | :--- |
| `UserRouter` | Directs users to the correct dashboard based on role (Homeowner vs. Designer). |
| `ProfileCard` | Reusable UI displaying a Designer or Contractor's rating, name, and specialty. |
| `ProjectRequestForm` | Multi-step form collecting room details, dimensions, and style preferences. |
| `DraftViewer` | Interface for homeowners to view, comment on, and approve uploaded designs. |
| `PaymentGateway` | Secure checkout component for processing digital design payments. |

### 02. Backend Classes (Flask/Python)
| Class | Attributes | Methods |
| :--- | :--- | :--- |
| **User** (Base) | `id`, `role`, `name`, `email`, `is_verified` | `login()`, `update_profile()` |
| **Designer** | Inherits User + `portfolio_url`, `rating` | `submit_draft()`, `search_contractors()` |
| **Project** | `id`, `homeowner_id`, `designer_id`, `status` | `update_status()`, `upgrade_to_execution()` |
| **Transaction** | `id`, `project_id`, `amount`, `status` | `process_payment()`, `issue_payout()` |

### 03. Database Design (SQL)

**👥 Users Table** (Handles all 3 roles)
| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique identifier |
| **role** | ENUM | 'Homeowner', 'Designer', 'Contractor' |
| **credibility_score** | DECIMAL | Aggregated rating (crucial for platform value) |

**📁 Projects Table**
| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique project identifier |
| **homeowner_id**| INT / FK | References Users.id |
| **designer_id** | INT / FK | References Users.id |
| **contractor_id**| INT / FK | References Users.id (Nullable until hired) |
| **phase** | ENUM | 'Drafting', 'Digital_Complete', 'Physical_Build' |

**💬 Reviews Table**
| Column | Type | Description |
| :--- | :--- | :--- |
| **reviewer_id** | INT / FK | Who wrote it |
| **reviewee_id** | INT / FK | Who received it |
| **rating** | INT | 1-5 scale (builds the credibility metric) |

### 04. Relationships
* **Users (Homeowner) (1) → (Many) Projects:** A homeowner can request multiple rooms/projects.
* **Users (Designer) (1) → (Many) Projects:** A designer can work on multiple projects simultaneously.
* **Users (Contractor) (1) → (Many) Projects:** Contractors can be assigned to multiple execution phases.
* **Projects (1) → (Many) Transactions:** A project may have multiple payments (e.g., Digital Draft fee, Physical Build milestones).

---

## 5. Sequence Diagrams (High-Level Overview)

*(Note: Replace these placeholders with actual image links to your generated sequence diagrams in your repository).*

**Sequence 1: Digital Design Flow**
`![Digital Design Flow Diagram](assets/digital_design_flow.png)`

1. Homeowner -> Platform: Submit request & select Designer.
2. Platform -> Designer: Notify of new project.
3. Designer -> Platform: Upload draft design.
4. Platform -> Homeowner: Notify draft is ready.
5. Homeowner -> Platform: Approve & Pay.
6. Platform -> Designer: Release funds.

**Sequence 2: Execution Flow**
`![Execution Diagram](assets/execution.png)`

1. Homeowner -> Platform: Select "Proceed to execution".
2. Platform -> Designer: Notify of project phase upgrade.
3. Designer -> Platform: Search Contractor directory.
4. Platform -> Designer: Return credible contractors.
5. Designer -> Contractor: Send execution request.

---

## 6. API Specifications

### External APIs
| Service | Purpose |
| :--- | :--- |
| **Stripe API** | Payment processing. To handle the homeowner's payment and route payouts to the interior designer. |
| **AWS S3 / Cloudinary** | Cloud storage for housing high-resolution portfolio images and project draft files. |

### Internal APIs
| Endpoint | Method | Description | Input | Output |
| :--- | :--- | :--- | :--- | :--- |
| `/api/designers` | **GET** | Fetch credible designers | `Filters (style, rating)`| `JSON: [{id, name, rating, portfolio}]` |
| `/api/projects` | **POST** | Create a new design request | `JSON: {room, size, designer_id}` | `JSON: {project_id, status}` |
| `/api/drafts` | **POST** | Designer uploads a draft | `File, project_id` | `JSON: {draft_url, timestamp}` |
| `/api/pay` | **POST** | Process digital design payment | `JSON: {project_id, amount}` | `JSON: {transaction_id, status}` |
| `/api/contractors`| **GET** | Designer queries contractors| `Filters (location, rating)`| `JSON: [{id, name, rating, license}]` |

---

## 7. SCM & QA Strategies

### Development & Version Control
* **Repository:** GitHub.
* **Branching Strategy:** Feature-branch workflow.
  * `main`: Production-ready, stable marketplace.
  * `develop`: Integration branch.
  * `feature/*`: Specific tasks (e.g., `feature/payment-gateway`).
* **Tools:** Visual Studio Code, Postman (for API testing).

### Quality Assurance (QA)
Testing will heavily focus on user-role permissions and transactional integrity.

* **Manual Testing Scenarios:**
  * Verify a Homeowner cannot access the Contractor Search (only Designers should see this in the current flow).
  * Validate that final high-res designs are locked until Stripe confirms payment success.
* **Automated API Testing:**
  * Ensuring the matching logic returns *only* designers/contractors above a certain credibility threshold.
* **Security Testing:** Validate authentication tokens so users can only access their own private project data and drafts.

---

## 8. Technical Justification

* **React (Frontend):** A component-based UI is essential for a marketplace. We can reuse components like `ProfileCard` and `ReviewStars` across the Designer and Contractor directories, drastically speeding up development time.
* **Flask (Backend):** Python's lightweight nature allows us to build and iterate on the matching and payment-routing logic rapidly without the boilerplate of larger frameworks.
* **PostgreSQL (Database):** A relational database is non-negotiable for this idea. The complex linkages between Homeowners, Designers, Contractors, Projects, and Payments require strict ACID compliance and foreign-key constraints to ensure no data is orphaned (e.g., a payment not linked to a specific design).
* **Stripe Integration:** Processing payments natively is a massive legal and security risk. Offloading this to Stripe ensures PCI compliance and handles complex multi-party payouts.
