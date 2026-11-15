## 🌐 About the Project

Portfolio Dev is my professional portfolio, the site you are looking at right now. It presents projects, work experience, courses, technologies and languages, and everything is trilingual: the whole site, copy and content, shows up in Portuguese, English or Spanish from a single source of data.

The content is not written inside the components. It lives in the database and is updated by scripts, so changing a text or adding a project does not require touching the screen code.

Live site: [lloliveira.dev](https://lloliveira.dev)

## 🚀 Architecture Overview

- **Server-first rendering**: each page fetches and translates its data on the server and hands the browser only plain text.
- **Server Actions as the only data door**: there are no API routes, and database access never reaches the browser.
- **Translation in three layers**: interface copy, database content and structured résumé sections.
- **Content versioned in scripts**: each script carries all three languages and can be run again with no side effects.

- ✅ Language in the route (`/pt`, `/en`, `/es`), with no duplicated pages
- ✅ Localized content stored as `{ pt, en, es }` JSON and reduced to text before it reaches the screen
- ✅ Light and dark themes, with the same color palette in both
- ✅ Project images and READMEs come from a dedicated assets repository

## 🛠️ Key Features

### 🏠 Home and About
- ✅ An introduction with the main technologies orbiting the photo
- ✅ An About page told as a river: scrolling carries the story sideways
- ✅ Photos credited to their authors

### 📄 Resume
- ✅ Side tabs: experience, technologies, courses and languages
- ✅ A career map, with the line climbing through areas of work
- ✅ Details of each experience in tabs, with figures highlighted
- ✅ Technologies with proof of use: since when, and in which experiences, courses and projects

### 🗂️ Projects
- ✅ Filter by category
- ✅ Each project shows its README in the visitor's language

### ✉️ Contact
- ✅ A validated form that saves to the database and sends an email

## 🧭 What's Next

- 🔜 Bring the AI assistant back, with the usage limit enforced on the server
- 🔜 Redesign the remaining resume sections (courses and languages)
- 🔜 Dates and images for every project
