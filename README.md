# Tech Titans - AI Clinical Note Summariser

A WeThinkCode_ hackathon project by team **Tech Titans**: a web tool that turns unstructured clinical notes into clear, structured medical summaries and patient-friendly explanations, powered by Meta's Llama language model.

## The problem

Clinicians spend a large part of their day writing and reading free-text notes. Key information (symptoms, vitals, diagnoses, medications, follow-ups) gets buried, handovers take longer, and patients often leave without a summary they can understand.

## Our solution

Clinicians paste or upload their notes and choose the kind of summary they need:

- **Clinical summary** - structured sections for symptoms, vital signs, diagnoses, medications, test results and follow-up plan.
- **Patient summary** - the same information in plain, patient-friendly language.

The result can be copied to the clipboard or downloaded as a text file.

## Features

- Paste clinician notes or upload them
- Choose between clinical and patient-friendly summaries
- Formatted output with clear section headings
- One-click copy and download
- Loading indicator while the model processes the notes
- Simple login and profile creation screens

## What is in this repository

This repository contains the **front end** of the solution:

| File | Purpose |
|-|-|
| `login.html` | Sign-in page |
| `createProfile.html` | New user profile page |
| `Summary.html` | Main note-summarisation screen |
| `summaryDeco.css` | Styling for the summary screen |
| `summaryLogic.js` | Sends notes to the summarisation API, formats the response, copy and download helpers |

The front end calls a separate backend API that formats the prompt, sends the notes to Llama (run locally through Ollama) and returns the structured summary. The backend is not included in this repository.

## Architecture

1. **Front end** - note input, summary type selection, output panel.
2. **Backend API** - validates input, builds the prompt, calls the model, structures the output.
3. **AI layer** - Meta Llama through Ollama: normalises medical text, extracts key entities and writes the summary.
4. **Privacy** - notes are processed in memory only; nothing is stored long-term.

## Tech stack

- HTML, CSS and JavaScript (front end)
- Meta Llama through Ollama (AI model)
- REST API between front end and backend

## Running the front end

1. Clone the repository.
2. Open `login.html` (or `Summary.html`) in a browser, or serve the folder with any static server, for example `python -m http.server 8000`.
3. Point the API endpoints in `summaryLogic.js` at a running backend.

## Team

Built by **Tech Titans** for the WeThinkCode_ Healthcare AI Hackathon, including [Mohau Mokoena](https://github.com/TheGreatMohau288).

## License

MIT
