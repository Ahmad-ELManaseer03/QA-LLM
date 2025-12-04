<div align="center">

# QA LLM Assignment · Gemini & Postman

Automation mini-project for testing LLM responses using **Google Gemini API** and **Postman**.

</div>

---

## ✨ Overview

This repository contains a small QA automation project that:

- Sends predefined prompts to a Large Language Model (**Gemini**)
- Stores the model responses in Postman **environment variables**
- Uses the LLM itself to evaluate its answers as `PASS` or `FAIL`
- Can be run manually, as a full collection, or via a Postman Monitor

The focus is on **QA mindset** and **automation workflow**, not on building a backend application.

---

## ⚙️ Tech Stack

- **Postman** – requests, collections, environments, and test scripts  
- **Google Gemini API** – text generation and evaluation  
- **JavaScript (Postman tests)** – parsing responses and setting variables  

---

## 📁 Project Structure

| File                         | Type        | Description                                             |
|------------------------------|------------|---------------------------------------------------------|
| `Postman collection.json`    | Collection | All requests for prompts and evaluators                 |
| `environment,.json`          | Environment| Environment variables (API key, model answers, results) |

---

## 🧠 Flows & Scenarios

The collection is organized into two main flows:

### 1. Prompt 1 – Capital City Check

**Goal:** Verify that the model knows the capital city where the Eiffel Tower is located.

Typical structure:

1. **Ask Question 1**  
   - Prompt:  
     > Which city is the capital of the country where the Eiffel Tower is located?  
   - Sends the request to Gemini.  
   - Extracts the model answer from the JSON response.  
   - Stores the answer in an environment variable (for example: `model_answer_1`).

2. **Evaluator 1**  
   - Sends a second request to Gemini.  
   - Asks Gemini to evaluate the answer from `model_answer_1`.  
   - Expects a short decision such as `PASS` or `FAIL`.  
   - Stores the evaluation result (for example: `q1_answer`).

---

### 2. Prompt 2 – Story About a Cat

**Goal:** Check whether the model can generate a story about a cat based on a description.

Typical structure:

1. **Ask Question 2**  
   - Prompt:  
     > Tell me a story of an animal that has ears in shape of a triangle and does meow.  
   - Sends the request to Gemini.  
   - Extracts the story text.  
   - Stores it in environment variables (for example: `model_answer_2` and an escaped version like `q2_answer_escaped`).

2. **Evaluator 2**  
   - Sends another request to Gemini.  
   - Asks Gemini to evaluate whether the story clearly refers to a **cat**.  
   - Expects a decision such as `PASS` or `FAIL`.  
   - Stores the evaluation result (for example: `q2_answer`).

---

## 🚀 Setup

### 1. Import the Environment

1. Open **Postman**.
2. Go to **Environments** → **Import**.
3. Select `environment,.json`.
4. Open the imported environment and set:
   - `GEMINI_API_KEY` in the **Current Value** field.
5. Save the environment.
6. Select this environment from the top-right dropdown in Postman.

---

### 2. Import the Collection

1. Go to **Collections** → **Import**.
2. Select `Postman collection.json`.
3. Confirm that the collection is visible with all requests:
   - `Prompt 1 / Ask Question 1`
   - `Prompt 1 / Evaluator 1`
   - `Prompt 2 / Ask Question 2`
   - `Prompt 2 / Evaluator 2`

---

## ▶️ How to Run

### Option A – Run Requests Manually

1. Select the correct environment.
2. Send the requests in this order:
   1. `Prompt 1 / Ask Question 1`
   2. `Prompt 1 / Evaluator 1`
   3. `Prompt 2 / Ask Question 2`
   4. `Prompt 2 / Evaluator 2`
3. Open the **Test Results** tab for each request.
4. Check:
   - Status code assertions  
   - Text parsing assertions  
   - That the environment variables are populated with:
     - Model answers  
     - Evaluation results (`PASS` / `FAIL`)

---

### Option B – Run the Whole Collection

1. Right-click the collection → **Run collection**.
2. Select the same environment.
3. Start the run.
4. Review:
   - Number of requests executed  
   - Number of tests passed  

---

### Option C – Use a Monitor (Optional)

You can attach this collection to a Postman Monitor to:

- Run it on a schedule (for example: hourly/daily)
- Track how the model’s behavior changes over time
- Keep a record of responses and evaluations

---

## 🎯 Learning Outcomes

By using this repository, you demonstrate:

- Working with an **LLM API** in a QA context
- Structuring **Postman collections** and **environments**
- Writing **Postman test scripts** to:
  - Validate HTTP responses
  - Parse JSON safely
  - Store and reuse values through environment variables
- Designing a simple **LLM-based evaluation loop**:
  - Prompt → Model answer → Evaluator → PASS/FAIL
