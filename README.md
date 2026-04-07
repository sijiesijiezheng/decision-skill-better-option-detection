# AI Intent Deviation Decision Agent

## Overview
This project is a decision-based AI workflow designed to detect and correct user intent deviation in customer service scenarios.

In real-world interactions, users often express their needs inaccurately, which leads AI systems to provide technically correct but contextually inappropriate responses.

This system identifies such deviations and adjusts the response strategy accordingly.

---

## Problem

In customer service scenarios:
- Users may express incorrect or suboptimal requests
- Traditional AI systems respond only to literal input
- This leads to mismatched responses and poor user experience

Example:
User asks for: nearest bus station  
Actual better option: subway is significantly closer  

---

## Solution

This system introduces a **decision layer** into the AI workflow.

### Workflow Structure:
1. **User Input**
2. **Context Injection (e.g., distance data)**
3. **Decision Logic (LLM-based reasoning)**
4. **Conditional Routing (IF node)**
5. **Response Generation**

### Output Strategy:
- If no deviation → return single answer
- If deviation detected → return dual answer + recommendation

---

## Tech Stack

- n8n (workflow orchestration)
- OpenRouter API (LLM inference)
- JavaScript node (logic processing)
- HTTP Request nodes (LLM calls)

---

## Input / Output

**Input:**
- User query
- Context data (e.g., distances)

**Output:**
- Single response OR dual response with recommendation

---

## Current Stage

- Workflow logic validated
- Decision mechanism implemented
- External API integration (dynamic data) planned

---

## Author

Stella
