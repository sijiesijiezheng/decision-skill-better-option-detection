# Decision Skill: Better Option Detection

A reusable decision layer that checks whether a user's chosen approach is optimal for achieving their goal.

---

## What this is

This is not a chatbot.  
This is not a full product.  

This is a **decision skill** that forces a model to evaluate:

👉 Is the current approach optimal, or is there a better alternative?

---

## Core Idea

Traditional flow:

User Input → Direct Answer ❌  

This skill changes it to:

User Input → Decision (mandatory) → Then Answer ✅  

---

## Why this matters

LLMs already have the ability to suggest better options, but:

- It is inconsistent  
- It is not guaranteed to trigger  
- It is hidden in generation  

This skill makes it:

- Explicit  
- Structured  
- Always executed  

---

## What this skill does

- Forces a decision step before answering  
- Extracts “better option” reasoning explicitly  
- Improves consistency of decision-making  

---

## When to use

- The user has a clear goal  
- The user has chosen a specific approach  
- There may exist a better alternative path  

---

## When NOT to use

- Pure factual queries (e.g. what is the capital of France)  
- The user's goal is unclear  
- No meaningful alternative exists  

---

## Standard Input

```json
{
  "user_query": "I want to quickly improve my resume wording to pass screening"
}
Standard Output
{
  "better_option_exist": true,
  "user_goal": "pass screening quickly",
  "current_approach": "improve resume wording",
  "better_option": "strengthen core experiences before optimizing wording",
  "reason": "Improving wording without strong content has limited impact."
}
Field Explanation
better_option_exist: Whether a better option exists
user_goal: The actual goal the user wants to achieve
current_approach: The approach the user is currently taking
better_option: A more optimal way to achieve the goal
reason: Why the current approach is not optimal
Example
Input
{
  "user_query": "Should I take the subway to the airport?"
}
Output
{
  "better_option_exist": true,
  "user_goal": "get to the airport conveniently",
  "current_approach": "take the subway",
  "better_option": "take the airport shuttle",
  "reason": "The shuttle is more direct and convenient in this scenario."
}
How to Use

This skill is designed to be used before response generation in an AI workflow.

Basic logic:

Send user input to this skill
Receive structured decision result
If better_option_exist = true → adjust response strategy
If false → proceed with normal answer
Implementation
Prompt-based decision definition
Structured output constraints
A mandatory decision step before response generation
Positioning

This is NOT:

a chatbot
a customer service system
a full product

This IS:

👉 a reusable decision skill that can be inserted into any LLM workflow

Key Insight

This project is not about making the model smarter.

👉 It is about making the decision step reliable and consistent.
