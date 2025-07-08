# ai-recruiter

## Overview

ai-recruiter is a web application designed as an intelligent job recruitment platform. It aims to connect job applicants with suitable company job openings by leveraging a data-driven approach, including a machine learning component for personalized recommendations. Applicants can create detailed profiles, specify their job preferences and experiences, and receive suggestions for companies that match their criteria.

## Architecture

The application is built with the following main components:

*   **Backend:** A Ruby on Rails application serving a JSON API. It handles business logic, data persistence, and interactions with the database.
*   **Frontend:** A Single Page Application (SPA) built with React and Redux. It provides the user interface for applicants and handles client-side state management.
*   **Database:** A relational database (likely MySQL) managed via Rails Active Record.
*   **Machine Learning:** A Python-based component using Keras (with a TensorFlow backend) to train a neural network model. This model is intended to predict suitable companies for applicants based on their profiles.

## Key Technologies

*   **Backend:** Ruby on Rails, Ruby
*   **Frontend:** React, Redux, JavaScript, Axios, SASS/SCSS
*   **Machine Learning:** Python, Keras, TensorFlow, Pandas, Scikit-learn
*   **Database:** SQL (schema suggests MySQL compatibility)

## Features (Inferred from Codebase)

*   **Applicant Profiling:** Applicants can input detailed information including age, gender, college education, past job experiences (roles and industries), desired job roles and industries, and preferences for company culture (e.g., working hours, satisfaction, motivation, mentorship).
*   **Company Listings:** The platform stores information about companies, including their industry, website links, logos, and aggregated ratings on various aspects.
*   **Job Postings:** Companies can have specific job openings (`company_jobs`) linked to generic job titles.
*   **API-driven:** The React frontend interacts with the Rails backend via a comprehensive JSON API.
*   **AI-Powered Recommendations:** A Keras-based neural network is designed to learn from applicant data and company selections to provide personalized company recommendations. The training script (`keras/applicants_svm.py`) processes applicant features and company data to predict matches.
    *   *Note:* The current ML script focuses on training and evaluation; model saving and live integration with the Rails app are not explicitly implemented in the reviewed script.
*   **Data Scraping:** The `scraper/` directory contains Python scripts, suggesting that some data (e.g., for colleges, companies, industries) might be gathered through web scraping.

## Setup and Running the Application

*(The following are general Rails/React instructions and may need to be adapted based on specific project configurations not detailed in the current README.)*

**Prerequisites:**

*   Ruby (see `.ruby-version` for specific version)
*   Node.js and Yarn/npm (for the frontend)
*   Python (for ML and scraping scripts)
*   A compatible database system (e.g., MySQL)

**Backend (Ruby on Rails):**

1.  Navigate to the project root.
2.  Install Ruby dependencies: `bundle install`
3.  Configure `config/database.yml` for your database.
4.  Create the database: `rails db:create`
5.  Run database migrations: `rails db:migrate`
6.  Seed initial data (if `db/seeds.rb` is populated): `rails db:seed`
    *   The `db/fixtures/` directory contains CSV files and seed scripts (e.g., `colleges_seed.rb`, `companies_seed.rb`) which are likely used for initial data population, possibly via a Rake task or the main seed file.
7.  Start the Rails server: `rails server`

**Frontend (React):**

1.  Navigate to the `frontend/` directory.
2.  Install JavaScript dependencies: `yarn install` (or `npm install`)
3.  Start the React development server: `yarn start` (or `npm start`)

**Machine Learning Component:**

*   The script `keras/applicants_svm.py` can be run to train the recommendation model.
*   It requires Python dependencies listed in its import statements (TensorFlow, Keras, Pandas, scikit-learn). These would typically be managed with `pip` and a `requirements.txt` file (not present in the root of `keras/`).
*   The script expects a dataset named `ai_recruiter_development.csv` in the `keras/` directory.

## How to Run Tests

*(Instructions for running tests are not available in the current project documentation. Typically, for a Rails app, tests are run using `rails test`.)*

---

This README is based on an analysis of the codebase. Specific details regarding deployment, advanced configuration, or operational procedures may require further documentation.
