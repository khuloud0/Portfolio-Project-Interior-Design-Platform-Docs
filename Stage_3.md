# User Stories

The following user stories define the key functionalities of the **Interior Design Platform MVP** from the user's perspective. These stories are prioritized using the **MoSCoW** method.

| Priority | User Story |
| :--- | :--- |
|**Must Have** | As a user, I want to select room type, size, style, and color so that I can receive personalized interior design suggestions instantly. |
| | As a user, I want to view 2–4 design suggestions based on my inputs so that I can compare and choose the most suitable option. |
| | As a user, I want to generate design suggestions without logging in so that I can quickly use the platform without barriers. |
|**Should Have** | As a user, I want the system to match my inputs with relevant design templates so that I receive accurate and useful suggestions. |
|**Could Have** | As a user, I want to save a design suggestion so that I can revisit it later. |
|| As a user, I want to be prompted to sign up only when I try to save a design so that I don’t need to create an account before exploring the platform. |
|**Won’t Have** | As a user, I want the system to generate designs using AI so that I get highly personalized results. |
|| As a user, I want to view my room design in 3D so that I can better visualize the final outcome. |

# Mockups / Wireframes

The following wireframes illustrate the main user interface screens of the MVP, **focusing on user flow and functionality** rather than visual design.

<img src="Home.png" width="150">

<img src="Abut Us.png" width="150">

<img src="How it wrks page.png" width="150">

<img src="Desin Form.png" width="150">

<img src="loading screen.png" width="150">


# Design System Architecture

## Overview
The Interior Design Platform MVP follows a simple **three-layer web architecture** to ensure clarity, scalability, and maintainability. The system is composed of a frontend interface, a backend application, and a relational database.

---

## Main Components

| Component | Technology | Responsibility |
| :--- | :--- | :--- |
| **Frontend** | **React** | Handles user interaction and collects inputs such as room type, size, style, and color preferences. |
| **Backend** | **Flask (Python)** | Processes requests, applies filtering logic, and manages API endpoints. |
| **Database** | **SQL** | Stores structured data including design templates, categories, and user data. |

---

## Architectural Layers

### 1. Presentation Layer (Frontend)
* Built with **React** to provide a responsive and minimalist user interface.
* Focuses on capturing user preferences through a clean, Swiss-style design.
* Ensures a frictionless experience by allowing interaction without immediate authentication.

### 2. Logic Layer (Backend)
* Powered by **Flask** to handle core business logic and API routing.
* Implements the filtering algorithm to match user specifications with available design assets.
* Manages secure communication between the client and the data store.

### 3. Data Layer (Database)
* Utilizes **SQL** to maintain structured relationships between designs, styles, and colors.
* Ensures data integrity and allows for efficient querying as the material library expands.

### The following diagram illustrates the high-level system architecture and data flow of the Interior Design Platform MVP.

<img src="architecture.png" width="300">

## Data Flow

The following steps outline the data movement within the platform, from user input to the final result:

1.  **User Input:** The user interacts with the **React frontend** by entering design preferences, such as room type, size, style, and color.
2.  **Request:** The frontend sends an **HTTP request** containing these preferences to the **Flask backend**.
3.  **Processing:** The backend validates the input and applies the filtering logic.
4.  **Query:** The backend queries the **SQL database** to retrieve the most relevant design templates based on the user's criteria.
5.  **Response:** The retrieved results are sent back to the frontend.
6.  **Display:** The frontend renders the matching design suggestions, allowing the user to view and compare their options instantly.

## External Services

| Status | Details |
| :--- | :--- |
| **Current MVP** | The current MVP does not rely on external APIs, as it uses a predefined template-based system for generating design suggestions. |
| **Future Scope** | Future versions may integrate external services such as AI-based design generation or third-party visualization tools to enhance personalization and visualization capabilities. |

## Technical Justification

The technology stack was strategically selected to prioritize speed, maintainability, and data integrity for the MVP:

* **Python:** Selected for its simplicity, high readability, and robust support for rapid MVP development, allowing for faster iteration cycles.
* **Flask:** Chosen as a lightweight micro-framework that enables quick implementation of RESTful APIs. Its minimalist and modular nature makes the system easier to scale and maintain without unnecessary overhead.
* **SQL:** Utilized for its superior efficiency in handling relational data. This is essential for managing the structured relationships between room types, architectural styles, color palettes, and the corresponding design templates.

### Define Components, Classes, and Database Design :- 

### 01. Frontend Components

The frontend is composed of reusable UI components that support the main MVP flow, from entering user preferences to viewing and saving design suggestions.

**Main Frontend Components**

The frontend is built using **React**, following a modular component-based structure to ensure reusability and a clean Swiss-style minimalist interface.

| Component | Description |
| :--- | :--- |
| **App** | The root component that manages the main application flow and overall state. |
| **Navbar** | Displays the application title and navigation links. |
| **DesignForm** | The core interface that collects user inputs (room type, size, style, and color). |
| **InputField / SelectField** | Reusable UI elements for text inputs and dropdown selections. |
| **ResultsList** | A container that displays the collection of generated design suggestions. |
| **DesignCard** | A UI card representing a single design suggestion, including its image and details. |
| **SaveButton** | Enables users to save a specific design to their profile. |
| **LoginModal / SignupForm** | Triggered when an unauthenticated user attempts to save a design. |
| **Dashboard** | A personalized view for authenticated users to manage their saved designs. |

### 02. Backend Classes

The backend is implemented using Flask and Python. The system is structured around core classes that represent users, design templates, and saved designs, while service logic handles filtering and suggestion generation. Python and Flask were selected in the project stack for backend development.

**Main Backend Classes**

| Class | Attributes | Methods |
| :--- | :--- | :--- |
| **User** | `id`, `name`, `email`, `password_hash` | `register()`, `login()`, `save_design()` |
| **DesignTemplate** | `id`, `room_type`, `room_size`, `style`, `color`, `image_url`, `description` | `get_all()`, `filter_by_preferences()` |
| **SavedDesign** | `id`, `user_id`, `design_id`, `saved_at` | `save()`, `get_user_saved_designs()` |
| **RecommendationService** | (Internal helper logic) | `generate_suggestions()`, `match_templates()` |
| **AuthService** | (Stateless) | `validate_user()`, `hash_password()`, `verify_password()` |

### 03.  Database Design

**Main Tables**

 👤 **Users Table**

| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique user identifier |
| **name** | VARCHAR | Full name of the user |
| **email** | VARCHAR / UNIQUE | Primary contact and login email |
| **password_hash** | VARCHAR | Securely encrypted password |

 🛋️ **Room Types Table**

| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique room type identifier |
| **name** | VARCHAR | Example: Bedroom, Living Room, Kitchen |

 🎨 **Styles Table**

| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique style identifier |
| **name** | VARCHAR | Example: Modern, Minimalist, Swiss |

🖌️ **Colors Table**

| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique color identifier |
| **name** | VARCHAR | Example: White, Beige, Charcoal |

 📐 **Design Templates Table**

| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique template identifier |
| **room_type_id** | INT / FK | References `room_types.id` |
| **style_id** | INT / FK | References `styles.id` |
| **color_id** | INT / FK | References `colors.id` |
| **room_size** | VARCHAR | Small / Medium / Large |
| **image_url** | TEXT | Path or URL to the template image |
| **description** | TEXT | Detailed design notes |

💾 **Saved Designs Table**

| Column | Type | Description |
| :--- | :--- | :--- |
| **id** | INT / PK | Unique saved design identifier |
| **user_id** | INT / FK | References `users.id` |
| **design_template_id** | INT / FK | References `design_templates.id` |
| **saved_at** | TIMESTAMP | Date and time the design was saved |

### 04. Relationships

A design template belongs to one room type, one style, and one color category. A user can save many design templates, and each saved record links one user to one design template.

**Relationship Summary**

* **room_types (1) → (Many) design_templates:** Each room type can be associated with multiple design templates.
* **styles (1) → (Many) design_templates:** Each design style can be applied to various templates.
* **colors (1) → (Many) design_templates:** Each color scheme can be used across multiple design templates.
* **users (1) → (Many) saved_designs:** A single user can save multiple designs to their profile.
* **design_templates (1) → (Many) saved_designs:** A specific design template can be saved by many different users.

### 05. ER Diagram

<img src="ERdiagram.png" width="300">

### 06. Design Rationale

This database structure supports the MVP requirement of generating design suggestions based on structured user inputs such as room type, size, style, and color. It also supports the progressive authentication flow by allowing users to explore suggestions first and save selected designs after authentication. These requirements are aligned with the project scope and objectives.

---
### Generate Design Sequence

This sequence diagram illustrates how the system generates design suggestions **based on user input**.

<img src="userinput.png" width="600">

Save Design - This sequence diagram illustrates how a user saves a design, including the progressive authentication flow.

 <img src="SaveDesign.png" width="600">

 ### API Specifications

 **External APIs**

| Status | Details |
| :--- | :--- |
| **Current MVP** | Does not rely on external APIs; uses a predefined template-based system for generating design suggestions. |
| **Future Scope** | Future versions may integrate external services such as **AI-based design generation** or **third-party visualization tools** to enhance personalization and visualization capabilities. |

**Internal APIs**

The following table defines the internal API endpoints used in the system.

### 🚀 API Endpoints

| Endpoint | Method | Description | Input | Output |
| :--- | :--- | :--- | :--- | :--- |
| `/generate-design` | **POST** | Generate design suggestions based on user input | `JSON: { room_type, size, style, color }` | `JSON: [{ id, room_type, style, color, image_url }]` |
| `/login` | **POST** | Authenticate user | `JSON: { email, password }` | `JSON: { token, user_id }` |
| `/signup` | **POST** | Register a new user | `JSON: { name, email, password }` | `JSON: { message, user_id }` |
| `/save-design` | **POST** | Save a selected design | `JSON: { user_id, design_id }` | `JSON: { message: "Saved successfully" }` |
| `/saved-designs` | **GET** | Retrieve user's saved designs | `Query Params: user_id` | `JSON: [{ id, design_template_id, saved_at }]` |

**All endpoints follow RESTful design principles and return responses in JSON format**

### SCM & QA Strategies

The project uses **Git** and **GitHub** for version control and collaboration. Development is carried out using **Visual Studio Code** as the primary development environment. A structured branching strategy is followed to ensure organized development and code stability.

### Development & Version Control

#### Branching Strategy
* **main:** Contains stable, production-ready code.
* **develop:** Serves as the primary integration branch for ongoing development.
* **feature branches:** Dedicated branches created for specific tasks (e.g., `feature/design-form`, `feature/api-endpoints`).

#### Workflow
* Developers create a unique feature branch for every assigned task.
* Changes are committed regularly using clear and descriptive commit messages.
* **Pull Requests (PRs)** are opened to merge completed features into the `develop` branch.
* Peer code reviews are conducted to ensure quality and consistency before merging.
* Once the `develop` branch is verified as stable, it is merged into the `main` branch.

#### Development Tools
* **Visual Studio Code:** The primary IDE used for coding, linting, and debugging.
* **Swagger:** Utilized for comprehensive API documentation and interactive testing.

### Quality Assurance (QA)

The project follows a combination of manual testing and API validation techniques to ensure system functionality, reliability, and correctness.

### Testing & Deployment Strategy

* **Manual Testing:**
    * Validating the user input forms for responsiveness and accuracy.
    * Verifying that design generation results match the selected criteria.
    * Testing the "Save Design" functionality to ensure data persistence.
    * Rigorous testing of the login, signup, and authentication flows.
* **API Testing:**
    * Utilizing **Swagger** to test all API endpoints interactively.
    * Validating request and response formats (JSON) against expected schemas.
    * Ensuring the backend returns the correct HTTP status codes for all operations.

#### Test Scenarios
* **Valid Input:** Ensures the system provides accurate design results based on user preferences.
* **Invalid Input:** Confirms that the system handles errors gracefully with proper validation messages.
* **Unauthenticated Actions:** Verifies that attempting to save a design without logging in correctly triggers the authentication modal.
* **Authenticated User Flow:** Ensures logged-in users can successfully save designs and retrieve them via their dashboard.

#### Deployment Plan
* **Local Development:** The application is developed and tested locally using the **Flask** framework.
* **Database Setup:** **SQL** is used during the initial phase for its simplicity and rapid setup capabilities.
* **Future Deployment:** Subsequent versions are planned for deployment to a **cloud environment** (e.g.,AWS,..) for public access and scalability.







 

