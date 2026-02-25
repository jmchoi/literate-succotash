Project overview
literate-succotash contains a small interactive command-line quiz application (located in the test-app folder) designed to help users learn JavaScript, Node.js fundamentals, and general programming concepts. The quiz is implemented using modern Node.js features (ES modules, async/await) and demonstrates basic CLI input handling, simple UI via ANSI colors, and an extensible questions data format (JSON).

Setup instructions
Prerequisites

Node.js v18.0.0 or newer (package.json declares "engines": { "node": ">=18.0.0" }).
Get the code

Clone the repository you provided:
git clone https://github.com/jmchoi/literate-succotash.git
Change into the app directory:
cd literate-succotash/test-app
Install dependencies

This project has no external dependencies declared in package.json. If you add dependencies later, run:
npm install
Notes

The project uses ES modules (package.json contains "type": "module").
License: MIT (see package.json).
How to run the project
From the repository root or from the test-app directory, run one of the following:

Using npm script
cd test-app
npm start
(This runs node index.js as defined in package.json.)

Directly with Node
node test-app/index.js
or, if you are already inside test-app:
node index.js

Optional

Run test script (if tests are added later):
npm test
(Currently npm test runs node --test but no test files are included by default.)
How the CLI works

When started, the app displays a banner and prompts you to choose a quiz category.
Choose the number of questions (All / 3 / 5 where applicable).
Answer questions by entering the corresponding option number.
After each question you'll see immediate feedback and optional explanations.
At the end you get a summary with score, performance message, and a review of incorrect answers.
Customizing questions

Questions are stored in test-app/data/questions.json. You can add or edit categories and questions there. Each question object includes:
question (string)
options (array of strings)
answer (index of correct option, zero-based)
explanation (optional string)
Key features
Interactive CLI quiz with category selection and configurable question counts.
ES Module-based code (import/export) and modern Node.js idioms (async/await, Promises).
Clean, dependency-free terminal coloring using ANSI escape codes (no external packages required).
Simple, extensible JSON format for quiz content (easy to add new categories/questions).
Clear user prompts: selection menus, confirmations, and "press Enter to continue" pauses.
Score tracking and results summary with review of incorrect answers.
Demonstrates common JavaScript concepts (classes, array methods, destructuring, error handling) in a compact example.
Project structure (relevant files)

test-app/index.js — application entry point and main loop
test-app/package.json — project metadata and scripts
test-app/src/input.js — readline-based input helpers (select, prompt, confirm)
test-app/src/quiz.js — quiz logic and result rendering
test-app/src/colors.js — ANSI color helpers
test-app/data/questions.json — quiz content (categories and questions)