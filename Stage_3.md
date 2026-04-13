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
