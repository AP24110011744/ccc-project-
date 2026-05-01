# Plagiarism Checker
 
A full-stack web application that compares two text documents for similarity using the **Longest Common Subsequence (LCS)** algorithm. Matched tokens are highlighted side-by-side in both documents, and an animated circular score ring displays the overall similarity percentage.

---
 
## Features
 
- **LCS-based similarity detection** — tokenizes and compares documents at the word level using dynamic programming
- **Side-by-side diff view** — matched tokens are highlighted in both documents simultaneously
- **Animated score ring** — SVG circular progress indicator with color-coded severity
- **File upload support** — accepts `.txt`, `.md`, `.js`, `.py`, `.html`, `.css`, `.json`, and `.csv` files
- **Dark themed UI** — modern interface with animated gradient background
- **Self-contained** — includes both frontend and backend in a single repository
---
 
## Project Structure
 
```
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
```
 
---
 
## Tech Stack
 
| Layer     | Technology                  |
|-----------|-----------------------------|
| Frontend  | HTML5, CSS3, Vanilla JS     |
| Backend   | Node.js, Express 5          |
| Algorithm | Longest Common Subsequence  |
| CORS      | `cors` middleware           |
 
---
 
## Getting Started
 
### Prerequisites
 
- [Node.js](https://nodejs.org/) v16 or higher
- npm (bundled with Node.js)
### Installation
 
1. **Clone the repository**
   ```bash
   git clone https://github.com/AP24110011744/ccc-project-.git
   cd ccc-project-
   ```
 
2. **Install dependencies**
   ```bash
   npm install
   ```
 
3. **Start the server**
   ```bash
   npm start
   ```
 
4. **Open in browser**
   Navigate to `http://localhost:3000` (or whichever port the server binds to).
---
 
## How It Works
 
1. The user uploads two documents via the browser UI.
2. The frontend reads both files as plain text and sends them to `POST /api/compare`.
3. The server tokenizes the text and runs the LCS algorithm (defined in `lcs.js`) to find the longest common token sequence.
4. The server responds with a similarity percentage and the token indices that matched in each document.
5. The frontend highlights matched tokens in both document panels and animates the score ring.
### API Reference
 
#### `POST /api/compare`
 
**Request body (JSON):**
 
| Field   | Type   | Description             |
|---------|--------|-------------------------|
| `text1` | string | Full text of document 1 |
| `text2` | string | Full text of document 2 |
 
**Response body (JSON):**
 
| Field           | Type     | Description                         |
|-----------------|----------|-------------------------------------|
| `percentage`    | number   | Similarity score from 0 to 100      |
| `tokens1`       | string[] | Tokenized array of document 1       |
| `tokens2`       | string[] | Tokenized array of document 2       |
| `matchIndices1` | number[] | Matched token indices in document 1 |
| `matchIndices2` | number[] | Matched token indices in document 2 |
 
---
 
## Similarity Score Legend
 
| Score Range | Colour | Interpretation      |
|-------------|--------|---------------------|
| 0 – 29%     | Red    | Low similarity      |
| 30 – 69%    | Amber  | Moderate similarity |
| 70 – 100%   | Green  | High similarity     |
 
---
 
## Supported File Types
 
`.txt` · `.md` · `.js` · `.py` · `.html` · `.css` · `.json` · `.csv`
 
---
 
## Testing
 
Sample test files are included in the repository root. Upload `test1.txt` and `test2.txt` through the UI to verify the algorithm is working correctly before using your own documents.
 
---
 
## Contributing
 
1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add your feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a pull request
