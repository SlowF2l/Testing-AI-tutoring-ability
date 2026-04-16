A multi-agent system that stress-tests an AI Python tutor by simulating students with specific misconceptions encoded into their system prompts.

## Setup
- Student Agent: Llama 3.3 70B (Groq) with misconception encoded in system prompt
- Tutor Agent: Llama 3.3 70B (Groq) with Socratic teaching rules
- 5 experiments × 6 turns each = 30 total conversation turns evaluated

## Misconceptions tested
  1. DataFrame.where() filters rows like SQL WHERE (Category 1.2 - Faulty Data Analysis Logic)
  2. Using != 0 and > 0 are equivalent for counting non-zero entries (Category 1.3 - Incorrect Data Handling)
  3. Using & vs 'and' on boolean pandas masks are interchangeable (Category 3.1 - Incorrect Programming Assumptions)
  4. Iterating over DataFrame rows with a for-loop is the normal correct approach (Category 2.1 - Suboptimal Coding)
  5. Replacing NaN with 0 before calculations is always safe and correct (Category 1.3 - Incorrect Data Handling)
  
## Key findings
- One of the experiment reveals a subtle failure - the tutor embedded the solution code inside a question, technically maintaining Socratic form while violating the answer-withholding principle. This suggests LLM tutors can appear Socratic while implicitly giving away answers. 

## Files
- ai_tutoring.ipynb — full implementation
- transcripts.txt — all 3 conversation transcripts
- results.csv — rubric scores per experiment
