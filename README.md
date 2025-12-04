# QA LLM Assignment – Gemini & Postman

This repository contains a small QA automation assignment that uses **Google Gemini** and **Postman** to:
- Send test prompts to an LLM (Large Language Model)
- Capture the model responses
- Ask the LLM itself to **evaluate** those responses as `PASS` or `FAIL`

The goal is to demonstrate how to:
- Work with a free LLM API
- Automate testing using Postman collections, environments, and test scripts
- Prepare the setup to be used as a Postman Monitor

---

## 1. Project Structure (English)

- `Postman collection.json`  
  Postman collection that contains all requests for the assignment.  
  It includes two main flows:

  - **Prompt 1 flow**
    - **Ask Question 1**  
      Sends the prompt:  
      > Which city is the capital of the country where the Eiffel Tower is located?  
      Stores the model answer in an environment variable (e.g. `model_answer_1`).

    - **Evaluator 1**  
      Sends the model answer back to Gemini and asks it to evaluate the answer  
      (expected: `PASS` or `FAIL`).  
      Stores the evaluation in an environment variable (e.g. `q1_answer`).

  - **Prompt 2 flow**
    - **Ask Question 2**  
      Sends the prompt:  
      > Tell me a story of an animal that has ears in shape of a triangle and does meow.  
      Stores the story in environment variables (original and escaped versions).

    - **Evaluator 2**  
      Sends the answer back to Gemini and asks it to evaluate if it correctly refers to a cat.  
      Stores the evaluation in an environment variable (e.g. `q2_answer`).

- `environment.json` (or similar)  
  Postman environment file that contains:
  - `GEMINI_API_KEY` – your API key for Gemini
  - Variables for storing the model answers and evaluation results

> **Note:** Make sure the file you commit to GitHub does **not** contain your real API key.

---

## 2. Prerequisites

- Postman Desktop application  
- A Google account  
- A **Gemini API key** from Google AI Studio

---

## 3. Setup (English)

### 3.1 Import the Environment

1. Open Postman.
2. Go to **Environments** → **Import**.
3. Select the environment file (e.g. `environment.json`).
4. Open the imported environment.
5. Set the **Current Value** of `GEMINI_API_KEY` to your actual Gemini key.
6. Click **Save**.
7. Select this environment from the top-right environment dropdown in Postman.

> When sharing this repository publicly, replace the actual key with a placeholder  
> like `YOUR_GEMINI_API_KEY` before committing.

### 3.2 Import the Collection

1. Go to **Collections** → **Import**.
2. Select `Postman collection.json`.
3. Confirm that the collection appears with all four requests.

---

## 4. How to Run the Collection

### Option A – Run Requests Manually

1. Select the correct environment.
2. Run the requests in this order:
   1. `Prompt 1 / Ask Question 1`
   2. `Prompt 1 / Evaluator 1`
   3. `Prompt 2 / Ask Question 2`
   4. `Prompt 2 / Evaluator 2`
3. For each request, open the **Test Results** tab and verify that all tests pass.
4. Check the environment variables to see:
   - The raw model answers
   - The evaluation results (`PASS` / `FAIL`)

### Option B – Run the Whole Collection

1. Right-click on the collection → **Run collection**.
2. Select the environment.
3. Click **Run**.
4. You should see 4 requests executed and all tests passing if:
   - The API key is valid
   - The Gemini API is reachable

### Option C – Use a Monitor (Optional)

You can also configure a Postman Monitor to run this collection on a schedule  
(e.g. hourly or daily) to observe LLM behavior over time.

---

## 5. What This Project Demonstrates

- Integrating a **free LLM API** (Google Gemini) with Postman
- Using Postman:
  - Collections
  - Environments
  - Test scripts
- Storing and reusing responses via environment variables
- Basic **LLM-based evaluation** (LLM checks its own answers and returns PASS/FAIL)
- Preparing the setup for scheduled execution via Postman Monitor

---

## 6. Security Notice

- Never commit your real `GEMINI_API_KEY` to a public repository.
- Keep the real key only in:
  - Local Postman environment (Current Value)
  - Secrets in CI/CD if needed
- In this repository, use placeholders instead of real secrets.

---
