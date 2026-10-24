# CourseMaster - Frontend (Debugged)

Live Link: [https://course-master4981.netlify.app/](https://course-master4981.netlify.app/)


Original Frontend Repository: [courseMaster_frontEnd](https://github.com/Pullock4981/courseMaster_frontEnd)

A modern e-learning platform frontend built with React, Redux Toolkit, React Router DOM, and Tailwind CSS. This repository contains debugging and code-quality improvements made to the existing CourseMaster frontend as part of a bug-bashing assessment.

## Project Name & Description

**CourseMaster** is a full-featured e-learning platform where students can browse, purchase, and consume courses. The frontend provides an intuitive interface for students to enroll in courses, watch video lectures, complete assignments, and take quizzes. Administrators can manage courses, track enrollments, review assignments, and view analytics through a dedicated admin dashboard.

This repository contains the frontend application after assessment-related debugging and improvements. The work focuses on identifying and fixing issues in the existing codebase while preserving the application's original functionality and design.

## Technology Stack

- **React 19** — UI library
- **Vite** — Build tool and development server
- **Redux Toolkit** — State management
- **React Router DOM** — Client-side routing
- **Tailwind CSS + DaisyUI** — Styling and UI components
- **Axios** — HTTP client
- **ESLint** — Code quality and linting

## Assessment Scope

The debugging assessment focuses on reviewing the existing frontend, identifying reproducible issues, implementing appropriate fixes, and verifying that existing functionality continues to work.

The scope includes:

- UI rendering and responsive layout
- Course listing and course card presentation
- Error handling and API integration
- Unused variable declarations and code-quality warnings
- Regression testing of affected functionality

## Bugs Fixed & Code Improvements

The following issues have been identified and addressed during the assessment.

### 1. Long Course Titles Overflowing Course Cards

**Issue:** Long course titles could overflow their available space or fail to wrap correctly within course cards.

**Fix:** Updated the course title styling to support word wrapping, limit titles to two lines, and maintain consistent card title height.

**Changes made:**
- Added `block` layout styling.
- Added `break-words` and `[overflow-wrap:anywhere]`.
- Added `line-clamp-2` to limit titles to two lines.
- Added `min-h-[3.5rem]` for consistent title height.
- Used `.trim()` to remove leading and trailing whitespace from course titles.

### 2. Course Loading Error Handling

**Issue:** The course-loading error handler displayed a generic error message even when a more specific JavaScript error message was available.

**Fix:** Updated the error handler to use the caught error's message when the value is an `Error` instance, with a fallback message for other thrown values.

**Changes made:**

```jsx
setError(
    err instanceof Error
        ? err.message
        : "Failed to load courses"
);
```

### 3. Unused Variable Declarations in Course Player

**Issue:** The editor or linter reported unused declaration warnings for `isUpcoming` and `liveClassDate` in `coursePlayer.jsx`.

**Fix:** Removed the unused variable declarations to reduce unnecessary code and eliminate the associated warnings.

**Verification:** Recheck the relevant lint diagnostics and test the course player to confirm that existing functionality remains unaffected.

**Note:** The fixes above describe the changes made during the assessment. Their verification status should be updated after testing.

## Installation

1. Clone your corrected frontend repository:

   ```bash
   git clone <YOUR_FRONTEND_REPOSITORY_URL>
   ```

2. Navigate to the project directory:

   ```bash
   cd course-master-frontend-debugged
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

4. Create a `.env` file in the project root (see `.env.example`, if available).

5. Start the development server:

   ```bash
   npm run dev
   ```

6. Build for production:

   ```bash
   npm run build
   ```

## Environment Variables

Create a `.env` file in the project root with the following variable:

```env
VITE_API_BASE_URL=http://localhost:5000/api
```

**Required Variable:**

- `VITE_API_BASE_URL` — The base URL of the backend API.

For local development, configure the URL to match your locally running backend. For production, use the deployed backend API URL expected by the application.

Never place private credentials or backend secrets in frontend environment variables.

## Project Structure

```text
src/
├── components/
│   ├── CourseCard/
│   └── shared/
├── layouts/
├── pages/
│   ├── admin/
│   ├── CoursePlayer/
│   ├── CousrseDetails/
│   ├── Home/
│   ├── Login/
│   ├── Register/
│   └── student/
├── routes/
├── services/
├── store/
└── utils/
```

This structure follows the original project documentation. Refer to the actual repository for the current folder and file names.

## Features

### Public Features

- Browse courses with pagination, search, sorting, and filtering
- View detailed course information
- User registration and login

### Student Features

- Enroll in courses
- Watch video lectures through YouTube integration
- Mark lessons as completed
- Track learning progress
- Submit assignments using text or Google Drive links
- Take quizzes and receive score feedback
- View enrolled courses through the student dashboard

### Admin Features

- Create, update, and delete courses
- Manage course syllabuses, modules, lessons, videos, assignments, and quizzes
- Manage course batches
- View all enrollments
- Review and grade student assignments
- Filter enrollments by course or student
- Filter assignments by status
- View administrative analytics

## API Integration

The frontend communicates with the CourseMaster backend API.

### Key API Endpoints Used

- **Authentication:** `/api/auth/register`, `/api/auth/login`, `/api/auth/me`
- **Courses:** `/api/courses`
- **Enrollments:** `/api/enrollments/:courseId`, `/api/enrollments/my`
- **Assignments:** `/api/assignments/submit`, `/api/assignments/my`, `/api/assignments/stats`
- **Quizzes:** `/api/quizzes/submit`, `/api/quizzes/my`, `/api/quizzes/stats`
- **Admin:** `/api/admin/courses`, `/api/admin/enrollments`, `/api/admin/assignments`, `/api/admin/analytics`

For complete API documentation, refer to the backend repository's README.

## Testing & Verification

The following checks should be performed after applying the fixes:

- [ ] Course titles wrap correctly without overflowing their cards.
- [ ] Long unbroken words remain within card boundaries.
- [ ] Course cards remain readable at different viewport widths.
- [ ] Course-loading errors display the intended error message.
- [ ] The course player continues to work after removing unused declarations.
- [ ] Relevant editor or ESLint warnings are resolved.
- [ ] Existing course browsing and navigation functionality remains unaffected.
- [ ] The production build completes successfully.

Only mark a check as completed after performing the corresponding test.

## Development

- The development server uses Vite, typically at `http://localhost:5173`.
- Hot Module Replacement (HMR) is enabled.
- ESLint is configured for code quality.

## Deployment

The original frontend is deployed on Netlify:

[https://course-master4981.netlify.app/](https://course-master4981.netlify.app/)

When deploying your corrected version, configure the appropriate production `VITE_API_BASE_URL` in the hosting environment and rebuild the application.

## Assessment Deliverables

- Corrected frontend source code
- Documented bugs and code-quality findings
- Fixes implemented in the relevant source files
- Testing and verification of the implemented changes
- Google Docs bug-bashing report
- GitHub repository containing the corrected frontend

## Author

**Md Zilhaj Un Noor**

- GitHub: [ZilhajSajid](https://github.com/ZilhajSajid)
- Portfolio: [My Portfolio](https://my-portfolio-eight-liart-27.vercel.app/)

---

This repository is a debugging and improvement version of the existing CourseMaster frontend, prepared for an assessment. Original project features and technologies are retained while the documented fixes and verification work reflect the changes made during the assessment.
