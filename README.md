# ThesisFlow AI

**ThesisFlow AI** is an automated research assistant that streamlines the scientific workflow. By providing your research field, problem statement, and optional dataset, the tool automatically selects the appropriate analysis, designs the study, generates and executes code, and produces a complete research paper formatted in LaTeX.

---

## 🚀 How It Works

ThesisFlow AI operates as a collaborative workflow between three core components:

*   **You (The User):** Describe your problem and provide data. You maintain control by approving the research plan before execution and verifying test results before the final paper is written.
*   **Gemma (The AI Designer):** Designs the study, explains the methodologies in plain language, writes the analytical code, and self-corrects its own analysis.
*   **DevRelay (The Execution Engine):** Runs the generated code securely and returns real outputs, errors, and performance timings.

---

## 🛠 Operating Modes

### Demo Mode
Replays a pre-recorded Gemma design and analysis for a sample study, including a real recorded execution run. Ideal for previewing capabilities without setting up external APIs.

### Live Mode
Connects directly to your own language models and code execution endpoints. 

> ⚠️ **Note:** Live mode requires downloading this page locally, as the hosted preview blocks external network requests. All API keys remain securely in your local browser tab's memory.

---

## ⚙️ Configuration & Connections

### 1. Language Model Setup
Choose from the following backend options to power the AI design phase:
*   **Demo:** Pre-recorded sessions.
*   **Google AI Studio:** Connect via Gemma API endpoints.
*   **OpenAI-Compatible Endpoints:** Connect to local or remote providers such as Ollama, vLLM, or OpenRouter.
    *   **Default Model Name:** `gemma-3-27b-it`
    *   **Default Base URL:** `http://localhost:11434/v1`

### 2. Execution Setup (DevRelay)
To run code in Live Mode, configure a DevRelay execution server. The expected API contract is:

*   **Endpoint Protocol:** `POST`
*   **Payload Schema:** `{language: "python", code: string, timeout_s: number}`
*   **Response Schema:** `{stdout, stderr, exit_code, duration_ms}`

*To customize the connection to a custom API runner, adjust the `devrelayRun()` function directly within the source file.*
