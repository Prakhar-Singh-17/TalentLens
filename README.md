# TalentLens 🚀

TalentLens is an AI-powered platform designed to revolutionize interview preparation and resume analysis. It intelligently compares a candidate's resume against a job description, identifies skill gaps, generates tailored technical and behavioral interview questions, and provides a personalized day-wise preparation roadmap. 🎯

--- 

## 🌟 Project Status

| Feature          | Status      |
|------------------|-------------|
| Build Status     | [![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/Prakhar-Singh-17/TalentLens) |
| Version          | [![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/Prakhar-Singh-17/TalentLens) |
| License          | [![License: ISC](https://img.shields.io/badge/License-ISC-yellow.svg)](https://opensource.org/licenses/ISC) |
| Stars            | [![Stars](https://img.shields.io/github/stars/Prakhar-Singh-17/TalentLens?style=social)](https://github.com/Prakhar-Singh-17/TalentLens) |
| Forks            | [![Forks](https://img.shields.io/github/forks/Prakhar-Singh-17/TalentLens?style=social)](https://github.com/Prakhar-Singh-17/TalentLens) |

--- 

## 📝 Table of Contents

- [About the Project](#about-the-project) 💡
- [Key Features](#key-features) ✨
- [Tech Stack](#tech-stack) 💻
- [Project Structure](#project-structure) 📂
- [Installation](#installation) 🛠️
- [Usage](#usage) ▶️
- [How to Use](#how-to-use) 📖
- [API Reference](#api-reference) 🌐
- [Contributing](#contributing) 🤝
- [License](#license) 📄
- [Important Links](#important-links) 🔗
- [Footer](#footer) 🌟

--- 

## 💡 About the Project

TalentLens is a sophisticated web application built using a MERN (MongoDB, Express.js, React.js, Node.js) stack, enhanced with AI capabilities powered by Google's Gemini API. It addresses the critical need for effective job interview preparation by providing users with:

- **AI-driven Resume Analysis:** Compares a candidate's resume against specific job descriptions to highlight areas of strength and potential weakness.
- **Personalized Interview Guidance:** Generates relevant technical and behavioral interview questions based on the analysis.
- **Skill Gap Identification:** Pinpoints specific skills a candidate may be lacking for a target role, along with their severity.
- **Customized Preparation Plans:** Offers a structured, day-wise roadmap to help candidates focus their study and practice efforts.

The application aims to empower job seekers, particularly students, freshers, and early-career professionals, by providing them with data-driven insights and actionable preparation strategies to boost their confidence and success in interviews. 🎓✨

--- 

## ✨ Key Features

- **AI-Powered Interview Report Generation:** Leverages Google Gemini API to create comprehensive interview reports.
- **Resume Parsing:** Extracts text content from uploaded PDF resumes using `pdf-parse`.
- **User Authentication:** Secure registration and login system with JWT authentication and HTTP-only cookies.
- **Role Matching:** Calculates a `matchScore` indicating how well a candidate's profile aligns with a job description.
- **Technical & Behavioral Questions:** Generates targeted questions with explanations of interviewer intent and suggested answers.
- **Skill Gap Analysis:** Identifies and categorizes skill gaps by severity (`low`, `medium`, `high`).
- **7-Day Preparation Plan:** Provides a structured daily focus and task list for effective interview preparation.
- **Responsive UI:** Built with React and styled using Tailwind CSS for a modern, user-friendly interface.
- **Protected Routes:** Ensures that only authenticated users can access certain application features.
- **Lottie Animations:** Integrates engaging animations for loading and error states.

--- 

## 💻 Tech Stack

- **Frontend:**
  - React.js
  - Vite
  - Tailwind CSS
  - React Router
  - `react-hook-form`
  - `axios`
  - `react-toastify`
  - Lottie animations (`@lottiefiles/dotlottie-react`, `lottie-react`)

- **Backend:**
  - Node.js
  - Express.js
  - Mongoose (for MongoDB)
  - `dotenv`
  - `jsonwebtoken` (for JWT authentication)
  - `bcrypt` (for password hashing)
  - `cors` (for cross-origin requests)
  - `cookie-parser`
  - `multer` (for file uploads)
  - `pdf-parse`
  - `zod` & `zod-to-json-schema` (for data validation and schema generation)
  - `@google/genai` (for Gemini API integration)

- **Database:**
  - MongoDB

--- 

## 📂 Project Structure

The project is divided into two main parts: `backend` and `frontend`.

```
TalentLens/
├── backend/
│   ├── aiFeatures/
│   │   └── aiServices.js       # AI logic using Gemini API
│   ├── controllers/
│   │   ├── aiServiceController.js
│   │   └── userController.js
│   ├── middlewares/
│   │   ├── authMiddleware.js     # JWT verification
│   │   └── fileMiddleware.js     # Multer for file uploads
│   ├── models/
│   │   ├── resumeResponseModel.js # Mongoose schema for AI reports
│   │   └── userModel.js          # Mongoose schema for users
│   ├── routes/
│   │   ├── aiServiceRoutes.js    # API routes for AI services
│   │   └── userRoutes.js         # API routes for user authentication
│   ├── .env                      # Environment variables (should not be committed)
│   ├── index.js                  # Backend entry point (Express server)
│   ├── package.json              # Backend dependencies and scripts
│   └── temp.js                   # Example data for testing AI generation
│
└── frontend/
    ├── public/
    │   ├── _redirects
    │   ├── 503_error.json
    │   ├── loading.json
    │   └── sandy_loading.json
    ├── src/
    │   ├── App.jsx               # Main application component with routing
    │   ├── AuthContext/
    │   │   └── AuthContextProvider.jsx # Context for authentication state
    │   ├── components/
    │   │   ├── Navbar.jsx
    │   │   └── ProtectedRoute.jsx
    │   ├── index.css             # Global CSS (Tailwind import)
    │   ├── main.jsx              # Frontend entry point
    │   ├── pages/
    │   │   ├── GenerateReport.jsx
    │   │   ├── Home.jsx
    │   │   ├── Login.jsx
    │   │   ├── LottieCheck.jsx
    │   │   ├── PreviousReports.jsx
    │   │   ├── Register.jsx
    │   │   └── ViewReport.jsx
    │   └── utilites/
    │       ├── axiosConfig.js    # Axios instance configuration
    │       └── zodSchemas.js      # Zod validation schemas
    ├── eslint.config.js          # ESLint configuration
    ├── index.html                # Main HTML file
    ├── package.json              # Frontend dependencies and scripts
    └── vite.config.js            # Vite configuration
```

--- 

## 🛠️ Installation

### Prerequisites

- **Node.js:** Ensure you have Node.js installed (v18 or higher recommended).
- **MongoDB:** A running MongoDB instance (local or cloud-based like MongoDB Atlas).

### Backend Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Prakhar-Singh-17/TalentLens.git
   cd TalentLens
   ```

2. **Navigate to the backend directory:**
   ```bash
   cd backend
   ```

3. **Install dependencies:**
   ```bash
   npm install
   ```

4. **Create a `.env` file:**
   In the `backend` directory, create a `.env` file with the following variables:
   ```
   MONGO_URL=your_mongodb_connection_string
   JWT_SECRET=your_super_secret_key
   GEMINI_API_KEY=your_gemini_api_key
   FRONTEND_URL=http://localhost:5173 # Or your frontend URL
   ```

5. **Start the backend server:**
   ```bash
   node index.js
   ```
   *(Alternatively, you can add `"start": "node index.js"` to the `scripts` in `backend/package.json` and run `npm start`)*

### Frontend Setup

1. **Navigate to the frontend directory:**
   ```bash
   cd ../frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure `.env` for Vite:**
   Create a `.env` file in the `frontend` directory (or configure your Vite environment variables). You'll need to set the backend URL. For local development, it might look like this:
   ```
   VITE_BACKEND_URL_LOCAL=http://localhost:8080
   VITE_BACKEND_URL_PROD=your_production_backend_url
   ```

4. **Start the frontend development server:**
   ```bash
   npm run dev
   ```

--- 

## ▶️ Usage

TalentLens provides a streamlined workflow for job seekers to prepare for interviews:

1.  **Authentication:** Register a new account or log in to an existing one.
2.  **Generate Report:** Navigate to the "Generate Report" section. Here you will:
    *   Paste the **Job Description** into the provided text area.
    *   Upload your **Resume** as a PDF file.
    *   Optionally, provide a **Self Description** to give the AI more context.
    *   Click "Generate Report".
3.  **View Report:** Once generated, you'll be redirected to a detailed report page. This page includes:
    *   **Overall Match Score:** A percentage indicating how well your profile aligns with the job description.
    *   **Technical Questions:** A list of potential technical questions, their interviewer intent, and suggested answers.
    *   **Behavioral Questions:** Similar to technical questions, focusing on soft skills and experience.
    *   **Skill Gaps:** Identified areas where your profile might be lacking, with severity.
    *   **Preparation Roadmap:** A day-wise plan to guide your study.
4.  **Previous Reports:** Access a list of all previously generated reports, sortable by date, allowing you to revisit past analyses.

--- 

## 📖 How to Use

**Scenario:** A user is applying for a "MERN Stack Developer" role and wants to prepare effectively.

1.  **Access the Application:** Go to the deployed application URL or run it locally.
2.  **Login/Register:** Log in or create an account.
3.  **Generate a Report:**
    *   Copy the job description for the "MERN Stack Developer" role and paste it into the "Job Description" textarea on the "Generate Report" page.
    *   Upload your resume PDF file.
    *   (Optional) Add a self-description highlighting your experience with MERN technologies and passion for backend development.
    *   Click the "Generate Report" button.
4.  **Review the Analysis:** Upon completion, the application will display a report:
    *   **Match Score:** See how well your resume matches the MERN Stack Developer requirements.
    *   **Questions:** Study the technical questions (e.g., about Node.js event loop, MongoDB indexing) and behavioral questions (e.g., about teamwork, problem-solving), along with suggested answers and intentions.
    *   **Skill Gaps:** If your resume lacks details on Docker or TypeScript (bonus skills for the role), the report will highlight this with a severity level.
    *   **Preparation Plan:** Follow the 7-day plan to focus on areas like Node.js concepts, React best practices, and database optimization.
5.  **Track Progress:** Visit "Previous Reports" to review past analyses and track your interview preparation journey.

--- 

## 🌐 API Reference

The backend exposes several API endpoints:

**User Routes (`/user`)**

- **`POST /register`**: Registers a new user.
  - **Request Body:** `{ "username": "string", "email": "string", "password": "string" }`
- **`POST /login`**: Logs in a user and returns a JWT token in cookies.
  - **Request Body:** `{ "email": "string", "password": "string" }`
- **`GET /profile`**: Retrieves the logged-in user's profile information (requires authentication).
- **`GET /logout`**: Logs out the user by clearing the authentication cookie.

**AI Service Routes (`/ai`)**

- **`POST /aiReport`**: Generates an interview report. Requires authentication and a PDF file named `resume` in `multipart/form-data`.
  - **Request Body (form-data):** `{ "resume": File, "jobDescription": "string", "selfDescription": "string" }`
  - **Response:** `{ "message": "Interview report generated successfully.", "interviewReport": { ...report details... } }`
- **`GET /allReports`**: Fetches all interview reports for the logged-in user (requires authentication).
- **`GET /fetchReport/:id`**: Fetches a specific interview report by its ID (requires authentication).

--- 

## 🤝 Contributing

Contributions are welcome! If you'd like to contribute to TalentLens, please follow these steps:

1.  Fork the repository.
2.  Create a new branch for your feature (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

Please ensure your code adheres to the project's coding standards and includes relevant tests if applicable.

--- 

## 📄 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE.md) file for details. (Note: No LICENSE file was found in the provided analysis, assuming ISC based on `backend/package.json`.)

--- 

## 🔗 Important Links

- **Live Demo:** [TalentLens Demo](https://talentlens.netlify.app/) (Note: This is an assumed URL, please replace if a live demo exists)
- **Repository:** [Prakhar-Singh-17/TalentLens](https://github.com/Prakhar-Singh-17/TalentLens)

--- 

## 🌟 Footer

<p align="center">
  🚀 Created by Prakhar Singh
  <br />
  <a href="https://github.com/Prakhar-Singh-17/TalentLens">View Project on GitHub</a>
  | 
  <a href="mailto:prakhar@example.com">Contact Author</a>
  <br />
  <br />
  Give this project a :star: if you found it useful!
  <br />
  Report any issues or suggest features on the <a href="https://github.com/Prakhar-Singh-17/TalentLens/issues">GitHub Issues</a> page.
</p>


---
**<p align="center">Generated by [ReadmeCodeGen](https://www.readmecodegen.com/)</p>**
