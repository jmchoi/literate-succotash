# literate-succotash

## Project overview

literate-succotash includes a small example project (in the `test-app/` folder): a terminal-based interactive Quiz CLI written in modern JavaScript (ES modules). The app demonstrates Node.js features such as async/await, file system operations, readline-based user input, classes/OOP, and simple terminal styling with ANSI codes.

Key points:
- A simple, dependency-free CLI quiz application.
- Bundled example question data in JSON (multiple categories).
- Designed for learning and demonstration rather than production use.

## Setup instructions

Requirements:
- Node.js 18 or newer (the project uses ES modules and modern Node APIs).

Quick start:

1. Clone the repository (if you haven't already):

   git clone https://github.com/jmchoi/literate-succotash.git

2. Change into the example app directory:

   cd literate-succotash/test-app

3. (Optional) Install dependencies. This example has no external dependencies, but running npm install is harmless:

   npm install

4. Run the quiz:

   npm start

This runs `node index.js` and launches the interactive quiz in your terminal.

## Usage examples

- On start you will see a banner and be prompted to choose a category (e.g., "JavaScript Basics").
- After selecting a category, choose how many questions to answer (All, 3, or 5 depending on availability).
- For each question, select the numbered option corresponding to your answer.
- After each question you'll see whether you were correct, an explanation (if available), and a progress bar.
- At the end you'll see a summary with your score, performance message, and a list of questions you answered incorrectly for review.

Notes on interaction:
- Input is numeric when choosing options.
- Confirmations use `y`/`n`.
- Press Enter when prompted to continue between questions.

## File structure

Root
- README.md (this file)
- test-app/
  - index.js            # CLI entry point; loads questions and runs the main loop
  - package.json        # Project metadata (name: quiz-cli)
  - data/
    - questions.json    # Quiz data organized by category (JSON)
  - src/
    - input.js          # Readline wrappers & input helpers (select, confirm, prompt)
    - quiz.js           # Quiz class: game logic, scoring, rendering results
    - colors.js         # Small ANSI color utilities for terminal styling

## Data format (questions.json)

- questions.json contains an object with a `categories` map.
- Each category has:
  - `name` (string)
  - `questions` (array of question objects)

Each question object contains:
- `question` (string)
- `options` (array of strings)
- `answer` (number, index of the correct option)
- `explanation` (optional string)

To add a new category or question, edit `test-app/data/questions.json` and follow the existing structure.

## Extending the project

Ideas for extension or improvement:
- Add unit tests for the Quiz class and input helpers.
- Persist high scores to a local file or simple database.
- Add timed questions or scoring variations.
- Internationalization / support for loading external question sets.
- Improve UI using libraries like Ink (React for CLIs) or add color themes.

## Notes & assumptions

- The example app is intentionally dependency-free to make it easy to inspect and learn from.
- package.json specifies Node >=18 in `engines` — please use an up-to-date Node runtime.
- The project's primary purpose is educational/demonstrative.

## License

This repository includes an example project with an MIT-style notice in `test-app/package.json`. Check repository-level LICENSE if present.

## Contact / Contribution

If you'd like changes to the README (more examples, expanded setup, or a different structure), tell me which sections you'd like adjusted and I will update the file accordingly.