# ✨ Resume Refiner AI Agent – n8n Project

## I. Overview

This project is an AI-powered Resume Refiner Agent built using [n8n](https://n8n.io/).  
It allows users to submit a resume and a job description link through a form.  
The workflow then analyzes both using OpenAI, generates personalized resume improvement suggestions, formats them as structured JSON, and emails a clear summary back to the user.

---

## II. AI Agent Flow Diagram

![n8n AI Workflow](Github%20screenshots/n8n%20AI%20workflow.png)

![Resume Refiner Diagram](Github%20screeshots/ResumeRefiner.drawio.png)


---

## III. Building the Agent

### 1. What approach did you take to design your agent?

I aimed to create an end-to-end automation that helps job seekers refine their resumes using AI.  
The design includes a simple form where users input their resume text and a job description link.  
Once submitted, the data is processed in n8n through OpenAI and formatted into an email-friendly structure.

### 2. What challenges did you face in parsing, formatting, or integrating?

- Parsing the AI's raw output into clean, usable JSON.
- Dealing with inconsistent formatting when the AI didn’t follow instructions closely.
- Errors from the “On Form Submission” node when required fields were not properly mapped or validated.

### 3. How did you ensure that the AI returned JSON reliably?

- I included specific formatting instructions in the prompt asking the AI to return a fixed JSON structure.
- I gave the AI an example of the desired format to follow.

---

## IV. Troubleshooting

### 1. What issues did you encounter and how did you resolve them?

- **“Problem running workflow” error using the “On Form Submission” node**  
  → Fixed by reviewing field mappings, making sure all required inputs were connected, and checking for undefined values.

- **AI returning unstructured text instead of JSON**  
  → Improved by updating the prompt and using JSON schema examples.

- **Messy email formatting**  
  → Resolved by converting the JSON into a structured Markdown/HTML format inside a Set node before sending it.

---

## V. Optimization

### 1. What might you improve or add in future iterations?

- Automatically extract job descriptions from LinkedIn or Indeed links.
- Add a visual front-end form (e.g. Webflow or React).
- Retry logic if AI response fails or times out.
- Store user requests in a database for tracking improvements.

---

🧠 Exploring AI x Automation with n8n + OpenAI
