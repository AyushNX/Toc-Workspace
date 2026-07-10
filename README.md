# TOC Workspace

**Interactive Theory of Computation Learning and Simulation Platform**

TOC Workspace is a browser-based, installation-free platform for constructing, simulating, and visualizing formal-language models — DFA, NFA/ε-NFA, Mealy & Moore machines, Pushdown Automata, and Turing Machines — alongside a Context-Free Grammar Studio, automatic Regex↔Automaton and Grammar↔NPDA converters, and an integrated assignment/quiz module. Built with plain HTML5, CSS3, and JavaScript (ES6), it runs entirely client-side and is deployed as a static site on Netlify.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [JSON Automaton Format](#json-automaton-format)
- [Deployment](#deployment)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Features

| Module | Description |
|---|---|
| 🔵 **DFA** | Visual state/transition editor, determinism validation, step-by-step string simulation |
| 🟣 **NFA / ε-NFA** | Multi-transition & epsilon-move support, parallel-state simulation, subset construction to DFA |
| 🟢 **Mealy & Moore Machines** | Transducer construction, output-sequence simulation, Mealy ↔ Moore conversion |
| 🟠 **Pushdown Automata (PDA)** | Stack-augmented transitions with live stack visualization |
| 🔴 **Turing Machines** | Single-tape, multi-tape, and non-deterministic (NTM) support with animated tape/head view |
| 📘 **CFG Studio** | Grammar entry & validation, simplification, derivation & parse-tree visualization |
| 🔁 **Regex → Automaton** | Thompson's construction from a regular expression to an NFA (+ optional DFA) |
| 🔁 **Grammar → NPDA** | Automatic construction of a non-deterministic PDA from a context-free grammar |
| 💾 **JSON Import/Export** | Save, share, and reload any automaton or grammar as a portable `.json` file |
| 📝 **Assignment & Quiz Module** | Auto-graded exercises on formal language theory |
| 🛠️ **Admin/Architect Review Portal** | Instructor dashboard to review submissions and manage exercises |

---

## Tech Stack

- **HTML5** — semantic structure & canvas/SVG rendering surface
- **CSS3** — responsive Flexbox/Grid layout, custom properties, animations
- **JavaScript (ES6+)** — application logic, simulation engines, conversion algorithms
- **JSON** — data interchange and client-side persistence format
- **Netlify** — static hosting with continuous deployment

No frameworks, no backend server, no database required.

---

## Project Structure

```
toc-workspace/
├── index.html                 # Application shell / entry point
├── assets/
│   ├── css/                   # Stylesheets
│   └── icons, images/
├── src/
│   ├── modules/
│   │   ├── dfa/
│   │   ├── nfa/
│   │   ├── mealy-moore/
│   │   ├── pda/
│   │   ├── turing-machine/
│   │   ├── cfg-studio/
│   │   ├── regex-converter/
│   │   └── grammar-npda/
│   ├── engine/                 # Shared simulation & conversion engines
│   ├── storage/                # JSON import/export, LocalStorage utilities
│   ├── quiz/                   # Assignment & quiz module
│   └── admin/                  # Admin/Architect review portal
├── data/
│   └── samples/                # Sample automata & quiz JSON files
├── netlify.toml                # Netlify build/deploy configuration
├── package.json
└── README.md
```

> Adjust this tree to match your actual repository layout.

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v16+) and npm — for local dev tooling only
- A modern web browser (Chrome, Firefox, Edge, or Safari — latest two versions)
- [Git](https://git-scm.com/)

### Installation

```bash
# Clone the repository
git clone https://github.com/AyushNX/Toc-Workspace
cd toc-workspace

# Install dev dependencies (linting/build tools)
npm install

# Run locally with a simple static server
npx live-server .
# or
npx serve .
```

Then open the printed local URL (e.g., `http://localhost:3000`) in your browser.

No build step is strictly required — since the app is pure HTML/CSS/JS, you can also just open `index.html` directly in a browser for quick testing.

---

## Usage

1. Launch the app and select a module (DFA, NFA, PDA, Turing Machine, CFG Studio, Regex Converter, etc.) from the navigation bar.
2. Use the visual canvas to add states/transitions, or enter a grammar/regular expression, depending on the module.
3. Enter a test input string and click **Simulate** to watch the automaton execute step by step.
4. Export your automaton via **Export JSON**, or import a previously saved `.json` file via **Import JSON**.
5. Head to the **Assignments** tab to attempt auto-graded quizzes and exercises.
6. Instructors can access the **Admin/Architect Portal** to review submissions and manage the exercise bank.

---

## JSON Automaton Format

Every automaton is represented as a portable JSON document. Example (DFA):

```json
{
  "type": "DFA",
  "states": ["q0", "q1", "q2"],
  "alphabet": ["0", "1"],
  "startState": "q0",
  "acceptStates": ["q2"],
  "transitions": [
    { "from": "q0", "symbol": "0", "to": "q1" },
    { "from": "q0", "symbol": "1", "to": "q0" },
    { "from": "q1", "symbol": "1", "to": "q2" }
  ],
  "metadata": { "createdAt": "2026-07-10T00:00:00Z", "author": "learner_id" }
}
```

PDA, Turing Machine, and CFG schemas follow a similar structure, extended with stack/tape/grammar-specific fields. Sample files are available in `data/samples/`.

---

## Local Development

Do not run this app via file:// URL. Use a local HTTP server.
Recommended

npx serve . -l 5173

Then open:

http://localhost:5173


---

## Roadmap

- [ ] Cloud-backed persistence via Netlify Functions
- [ ] Animated DFA minimization (Myhill–Nerode)
- [ ] Universal Turing Machine simulation
- [ ] Real-time collaborative editing
- [ ] Analytics & personalized recommendations in the review portal
- [ ] Touch-optimized editor for mobile/tablet
- [ ] Support for linear-bounded automata & Chomsky hierarchy tools

See open [Issues](../../issues) for details.


---