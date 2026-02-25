# literate-succotash

A small Node.js test-app that demonstrates modern JavaScript patterns and CLI interaction for learning and testing purposes.

---

## Table of Contents

- [Project Overview](#project-overview)  
- [Features & Learning Goals](#features--learning-goals)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [How to Run the Project](#how-to-run-the-project)  
- [Running Tests](#running-tests)  
- [Project Structure](#project-structure)  
- [Examples (sample run & banner)](#examples-sample-run--banner)  
- [Contribution Guidelines](#contribution-guidelines)  
- [Create branch & open Merge Request (minimal commands)](#create-branch--open-merge-request-minimal-commands)  
- [License](#license)

---

## Project Overview

literate-succotash is a small, focused test application intended to demonstrate and teach core Node.js and JavaScript features via a CLI test app. It's useful as a hands-on example for ES modules, async/await flows, reading user input, modular code organization, file I/O for data-driven questions, and simple terminal UI using ANSI colors.

---

## Features & Learning Goals

This repository / test-app demonstrates:

- ES modules (import / export)
- Async / await usage for asynchronous control flow
- Using readline (or equivalent) for interactive CLI prompts
- Classes for encapsulating app logic and state
- Useful Array methods (map, filter, reduce, find, etc.) in practice
- File I/O to load and persist question data (JSON)
- ANSI color output for readable terminal banners and feedback

Goal: be a small, readable example project that trainers and learners can inspect, run, and extend.

---

## Prerequisites

- Node.js >= 18 (required for stable ES module support and built-in test runner)
- npm (comes with Node.js)
- Git (for cloning and contributing)

---

## Installation

1. Clone the repository:
   - git clone <repo-url>
   - cd literate-succotash

2. The runnable app lives under the test-app directory. Install dependencies there:
   - cd test-app
   - npm install

Notes:
- package.json for the CLI and tests is located inside test-app.
- No global installs are required.

---

## How to Run the Project

From the repository root:

1. Change into the app folder:
   - cd test-app

2. Install dependencies (if not already):
   - npm install

3. Start the CLI test app:
   - npm start

If you prefer to run the entry file directly (some environments), ensure the CLI entry file is executable. Example:
- chmod +x test-app/<entry-file>
- ./test-app/<entry-file>

(Replace <entry-file> with the actual CLI script used by the project, if you want to run directly. The usual approach is using npm start.)

---

## Running Tests

From test-app:

- npm test

This project uses Node's built-in test runner (node --test) via the npm test script. Running `npm test` will execute the tests defined in the test-app package.

---

## Project Structure

A brief overview of the repository layout (top-level/high-level):

- README.md
  - This file (project documentation).
- test-app/
  - package.json  (scripts: start, test, etc.)
  - src/ (or similar) — app source code (ES modules, classes, CLI logic)
  - data/
    - questions.json (question bank used by the CLI; add questions here)
  - bin/ or index files — CLI entry point (referenced by npm start)
  - tests/ — unit / integration tests run by `npm test`

Notes/assumptions:
- The primary runnable application and package.json are under test-app/.
- Questions are stored in data/questions.json; add or update entries there to change quiz content.

---

## Examples (sample run & banner)

Below is an illustrative text example showing what you might see when you run the app. Exact wording and colors depend on the implementation, but this is representative.

1) Initial banner (colored with ANSI codes):

Welcome banner (sample):
> =======================================  
>  literate-succotash — JavaScript Test App  
>  A small CLI that demonstrates ES modules, async/await, classes, and file I/O  
> =======================================

2) Sample interactive question prompt:

Terminal:
> Question 1 of 5:
> What does Array.prototype.map return?
> 1) The same array, mutated
> 2) A new array with mapped values
> 3) Undefined
> 4) It depends
> Your answer: 2

Feedback:
> ✔ Correct — returns a new array with the results of calling a provided function on every element.
> Score: 1 / 1

At the end:
> Final score: 4 / 5  
> Thanks for playing!

(Colors would be applied for the banner, correct/incorrect marks, and score using ANSI escape sequences.)

---

## Contribution Guidelines

Contributions are welcome. Suggested process:

1. Create a feature branch off main:
   - git checkout -b feat/some-new-feature

2. Implement changes and run the app locally:
   - cd test-app
   - npm install
   - npm start
   - npm test

3. Adding or editing questions:
   - Edit test-app/data/questions.json
   - Follow the existing JSON structure; run the app to verify formatting and behavior.

4. Commit messages:
   - Use clear, conventional messages, e.g.:
     - docs: update README
     - feat: add new question type
     - fix: correct scoring logic

5. Open a Pull Request / Merge Request against main:
   - Provide a concise title and description of the change; reference related issues if any.

6. Tests:
   - Ensure `npm test` passes before submitting a PR.

---

## Create branch & open Merge Request (minimal commands)

Below is a minimal list of commands to create the branch `exercise`, update README.md, push it, and open a merge request (PR) against `main`. Replace <remote> and <repo-url> as needed.

1. Create and switch to the new branch:
- git checkout -b exercise

2. Edit README.md (make your README changes locally, e.g. using your editor)

3. Stage and commit:
- git add README.md
- git commit -m "docs: add detailed README for literate-succotash"

4. Push the branch to origin:
- git push -u origin exercise

5. Open a pull request (using GitHub CLI) from exercise → main:
- gh pr create --title "docs: update README" --body "Improve README with installation, usage, examples, and contribution guidelines." --base main --head exercise

If you don't have the GitHub CLI, you can open a PR using the GitHub web UI by navigating to the repository and choosing "Compare & pull request" for your pushed branch.

Note: The above commands are minimal examples. Adapt branch naming conventions and commit message formats to match your team's standards.

---

## License

This project is licensed under the MIT License (see package.json and LICENSE).