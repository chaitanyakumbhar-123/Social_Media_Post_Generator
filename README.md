# 🐦 AI Tweet Generator with Iterative Optimization  
### LangGraph Workflow Project

## 📌 Overview

This project implements an **AI-powered Tweet Generator** using a graph-based workflow built with **LangGraph**.

The system:
1. Takes a topic as input  
2. Generates a tweet  
3. Evaluates it  
4. If needed, optimizes it  
5. Re-evaluates until approval (max 5 iterations)

---

## 🔁 Workflow Logic

The workflow follows this structure:

<img width="423" height="472" alt="image" src="https://github.com/user-attachments/assets/11cc97b0-44cc-4bd5-b9b9-f0817fa01be0" />


START  
→ Generate  
→ Evaluate  
→ (Approved → END)  
→ (Need Improvement → Optimize → Evaluate → ...)

If the evaluation fails, the tweet is optimized and sent back for re-evaluation.  
This loop continues for up to **5 iterations**, after which it is automatically approved.

---

## 🧠 How It Works

### 1️⃣ Generate Node
- Takes topic as input
- Creates an initial tweet

### 2️⃣ Evaluate Node
- Checks quality criteria
- Routes the workflow based on result:
  - `approved` → END
  - `need_improvement` → Optimize

### 3️⃣ Optimize Node
- Improves the tweet based on feedback
- Sends it back to Evaluate

This creates an **iterative improvement cycle**.

---

## 🛠️ Tech Stack

- Python
- LangGraph
- Jupyter Notebook
- TypedDict (State Management)

---

## ⚙️ Key Concepts Demonstrated

- StateGraph creation
- Conditional edges
- Iterative workflows
- Feedback-based optimization loop
- Graph compilation and execution

