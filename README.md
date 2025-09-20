# TaskForge — Task Management App

Description
A web-based task management app where users can add, edit, and delete tasks, authenticate via JWT, organize tasks by project, and view tasks sorted by priority.

## Tech Stack
- React
- Node.js / Express

## Requirements
- Use JWT for user authentication in backend routes (protect routes with middleware that verifies the Authorization header)
- Categorize tasks by project ID and fetch accordingly (use URL parameters to specify project)
- Display tasks sorted by priority on the client (use Array.sort in React before rendering)

## Installation
1. Clone the repository:
   bash
   git clone https://github.com/your-username/TaskForge.git
   cd TaskForge
   
2. Backend setup:
   bash
   cd backend
   npm install
   
3. Frontend setup:
   bash
   cd frontend
   npm install
   
4. Create a `.env` file in the `backend` directory and add the following variables:
   dotenv
   PORT=5000
   JWT_SECRET=<your_jwt_secret>
   DATABASE_URL=<your_database_connection_string>
   

## Usage
1. Start the backend server:
   bash
   cd backend
   npm run dev
   
2. Start the frontend development server:
   bash
   cd frontend
   npm start
   
3. Open your browser and navigate to `http://localhost:3000` to access the app.

## Implementation Steps
1. Initialize the backend with Express and configure JSON parsing middleware.
2. Implement JWT authentication:
   - Create `POST /api/auth/register` and `POST /api/auth/login` routes.
   - Generate JWT tokens upon successful login/registration.
   - Protect task routes with middleware that verifies the `Authorization` header.
3. Set up database connection using the `DATABASE_URL` environment variable to persist users, projects, and tasks.
4. Define RESTful API routes in `backend/routes`:
   - `GET /api/tasks`
   - `GET /api/projects/:projectId/tasks`
   - `POST /api/tasks`
   - `PUT /api/tasks/:id`
   - `DELETE /api/tasks/:id`
5. Develop the React frontend:
   - Configure React Router for navigation between projects and task lists.
   - Create an authentication context/provider to store and attach JWT tokens.
   - Build components for adding, editing, deleting, and listing tasks.
   - Fetch tasks filtered by project ID from `/api/projects/:projectId/tasks`.
   - Use `Array.sort((a, b) => b.priority - a.priority)` to sort tasks by priority before rendering.
6. Test all features end-to-end: user registration/login, protected routes, task CRUD operations, project filtering, and priority sorting.

## API Endpoints
- POST /api/auth/register  
- POST /api/auth/login  
- GET /api/tasks  
- GET /api/projects/:projectId/tasks  
- POST /api/tasks  
- PUT /api/tasks/:id  
- DELETE /api/tasks/:id

---

Feel free to contribute by opening issues or submitting pull requests.