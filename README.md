# literate-succotash — Quiz CLI

## Project overview
This repository contains a small interactive command-line Quiz application (test-app) implemented with modern Node.js (ES modules). The CLI loads question data from JSON, presents category selection and question prompts, tracks score and progress, and shows a review of incorrect answers. It is a compact demo showcasing async/await, modular code organization, terminal colorization, and simple input utilities.

Key files
- test-app/index.js — CLI entrypoint and main loop (category selection, question count, run quiz, show results)
- test-app/src/quiz.js — Quiz game logic, scoring, progress rendering, and review
- test-app/src/input.js — Readline-based input helpers (menus, prompts, confirmations)
- test-app/src/colors.js — Small ANSI colorization helpers for terminal output
- test-app/data/questions.json — Quiz data (categories such as "javascript", "nodejs", "general")

## Setup instructions
Prerequisites
- Node.js >= 18 (the package.json declares Node 18+)
- npm (or any Node package manager)

Steps
1. Clone the repository (or download the code you were provided):
   git clone https://github.com/jmchoi/literate-succotash
2. Change into the CLI app directory:
   cd literate-succotash/test-app
3. Install dependencies (if any):
   npm install
   Note: This project uses only Node built-ins in the utilities shown; there may be no external dependencies, but running npm install is recommended if package.json is updated later.

## How to run the project
From the test-app directory:

- Start via npm script:
  npm start

- Or run directly with Node:
  node index.js

- If index.js has execute permission you can also run:
  ./index.js

Typical CLI flow
1. Choose a quiz category from the presented menu.
2. Choose the number of questions or accept defaults (the CLI prompts for question count).
3. Answer multiple-choice questions one-by-one.
4. View your score and a review of incorrect answers at the end.
5. Use provided prompts to restart or exit.

Notes
- The quiz reads questions from test-app/data/questions.json. Edit or extend this file to add categories and questions.
- Input helpers include selection menus, confirm prompts, and a "press Enter to continue" utility to improve UX.

## Key features
- Interactive, terminal-based quiz experience
- Category-based quizzes driven by JSON data (test-app/data/questions.json)
- Clean modular structure using ES modules (import/export)
- Async/await-based input handling using Node's readline
- ANSI color helpers for improved terminal output (colors.js)
- Fisher–Yates shuffle for randomizing question order (in quiz logic)
- Progress rendering and score tracking with end-of-quiz review of incorrect answers
- Minimal/no external dependencies — intended as a small, educational demo

If you want, I can:
- Generate a more detailed README (installation notes, development workflow, contributing guidelines)
- Print any file's full contents (name the file)
- Create a short "how to add questions" guide that includes a JSON schema example for questions.json