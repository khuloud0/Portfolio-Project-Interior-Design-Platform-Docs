# User Stories

The following user stories define the key functionalities of the ***Interior Design Platform MVP*** from the user's perspective. These stories are prioritized using the **MoSCoW** method.

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

![System Architecture](images/architecture.png)

