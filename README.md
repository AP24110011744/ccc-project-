# ccc-project-

Plagiarism Checker
A full-stack web application that compares two text documents for similarity using the Longest Common Subsequence (LCS) algorithm. Matched tokens are highlighted side-by-side in both documents, and an animated circular score ring displays the overall similarity percentage.
Show Image
Show Image
Show Image

Features

LCS-based similarity detection — tokenizes and compares documents at the word level using dynamic programming
Side-by-side diff view — matched tokens are highlighted in both documents simultaneously
Animated score ring — SVG circular progress indicator with color-coded severity
File upload support — accepts .txt, .md, .js, .py, .html, .css, .json, and .csv files
Dark themed UI — modern interface with animated gradient background
Self-contained — includes both frontend and backend in a single repository


Project Structure
ccc-project-/
├── public/
│   ├── index.html       # App shell and upload UI
│   ├── style.css        # Dark theme, animations, score ring styles
│   └── script.js        # File reading, API call, and highlight logic
├── server.js            # Express server exposing POST /api/compare
├── lcs.js               # LCS algorithm and tokenizer
├── package.json         # Project metadata and dependencies
├── test1.txt            # Sample document 1 for testing
└── test2.txt            # Sample document 2 for testing

Tech Stack
LayerTechnologyFrontendHTML5, CSS3, Vanilla JSBackendNode.js, Express 5AlgorithmLongest Common SubsequenceCORScors middleware

Getting Started
Prerequisites

Node.js v16 or higher
npm (bundled with Node.js)

Installation

Clone the repository

bash   git clone https://github.com/AP24110011744/ccc-project-.git
   cd ccc-project-

Install dependencies

bash   npm install

Start the server

bash   npm start

Open in browser
Navigate to http://localhost:3000 (or whichever port the server binds to).


How It Works

The user uploads two documents via the browser UI.
The frontend reads both files as plain text and sends them to POST /api/compare.
The server tokenizes the text and runs the LCS algorithm (defined in lcs.js) to find the longest common token sequence.
The server responds with a similarity percentage and the token indices that matched in each document.
The frontend highlights matched tokens in both document panels and animates the score ring.

API Reference
POST /api/compare
Request body (JSON):
FieldTypeDescriptiontext1stringFull text of document 1text2stringFull text of document 2
Response body (JSON):
FieldTypeDescriptionpercentagenumberSimilarity score from 0 to 100tokens1string[]Tokenized array of document 1tokens2string[]Tokenized array of document 2matchIndices1number[]Matched token indices in document 1matchIndices2number[]Matched token indices in document 2

Similarity Score Legend
Score RangeColourInterpretation0 – 29%RedLow similarity30 – 69%AmberModerate similarity70 – 100%GreenHigh similarity

Supported File Types
.txt · .md · .js · .py · .html · .css · .json · .csv

Testing
Sample test files are included in the repository root. Upload test1.txt and test2.txt through the UI to verify the algorithm is working correctly before using your own documents.

Contributing

Fork the repository
Create your feature branch: git checkout -b feature/your-feature
Commit your changes: git commit -m 'Add your feature'
Push to the branch: git push origin feature/your-feature
Open a pull request
