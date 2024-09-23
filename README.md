# ToDo Application
The ToDo Application is a task management tool.<p>
This application offers users the ability to manage tasks effectively, while also providing flexibility to extend the system and adapt to different use cases in the future. The project uses Golang, Gin framework, GORM, and MySQL, adhering to a layered architecture that separates concerns and ensures scalability and maintainability.

## Project Structure

This application follows a clean architecture with clear separation between the following layers:

1. Handler Layer: Handles incoming HTTP requests, processes them, and returns responses.
2. Use Case Layer: Implements the business logic and interactions between components.
3. Repository Layer: Handles communication with the database, following repository patterns.
4. Domain Layer: Contains the core entities and domain-specific logic.
5. Middleware Layer: Manages authentication and authorization processes.


## Technologies Used

1. Programming Language: Go (Golang)
2. Web Framework: Gin
3. Database: MySQL (GORM for ORM)


## Level 1: Basic CRUD Functionality (Simple Start)
1. User Registration and Login
    - Implement user registration and login with JWT authentication.
    - Store hashed passwords using bcrypt.

2. Acceptance Criteria:
    - Users can register and log in using a secure password.
    - JWT tokens are issued on login for session management.

3. ToDo CRUD Operations
    - Users can create, read, update, and delete ToDo items with basic fields: title, description, and due date.

### Acceptance Criteria:
- Basic CRUD operations work, and each user manages their own ToDo items.

### Level 2: Error Handling, Validation, and Enhancements
#### 1. Input Validation
- Implement validation for user inputs such as non-empty titles, valid due dates, and length limits on descriptions.
- Ensure meaningful error messages are returned to the user when inputs are invalid.
#### Acceptance Criteria:
- Validation errors return appropriate HTTP status codes and descriptive messages.
- Invalid ToDo creation or updates are rejected with feedback to the user.

### 2. Enhanced Error Handling
- Introduce custom error types for business logic validation, e.g., "ToDo already exists" or "User not found".

#### Acceptance Criteria:
- business logic errors are handled gracefully, with user-friendly error messages.

### 3. Soft Delete for ToDo Items
- Instead of permanently deleting ToDo items, introduce a soft delete feature where users can "archive" a task.
- Archived tasks are not displayed by default but can be restored later.

#### Acceptance Criteria:
- Users can archive and restore tasks.
- Archived tasks are not shown in the main list by default but can be retrieved if necessary.

### Level 3: Business Logic and Advanced Validation
#### 1. Task Deadlines and Overdue Validation
- Implement business logic to prevent setting due dates in the past.
- When displaying ToDo items, mark overdue tasks with a special status (e.g., "overdue").
#### Acceptance Criteria:
- Users cannot create or update a ToDo with a past due date.
- Overdue tasks are visually marked in the response.

#### 2. Task Completion and Statuses
- Add a completed status to each ToDo item, allowing users to mark a task as completed or incomplete.
- Ensure validation logic to prevent modifying completed tasks unless reverting to incomplete.

#### Acceptance Criteria:
- Users can toggle between completed and incomplete statuses.
- Completed tasks cannot be modified, except to change their status back to incomplete.