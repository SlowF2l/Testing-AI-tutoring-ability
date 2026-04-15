A multi-agent system that stress-tests an AI Python tutor by simulating students with specific misconceptions encoded into their system prompts.

## Setup
- Student Agent: Llama 3.3 70B (Groq) with misconception encoded in system prompt
- Tutor Agent: Llama 3.3 70B (Groq) with Socratic teaching rules
- 3 experiments × 6 turns each = 18 total conversation turns evaluated

## Misconceptions tested
1. print() returns a value that can be stored
2. return and print are interchangeable  
3. Mutable default arguments reset each function call

## Key findings
- Tutor guided all 3 students to correct understanding within 6 turns (scores: 8, 9, 8 out of 10)
- Best performance on Experiment 2 — tutor adapted when student began self-correcting
- Critical finding: Experiment 3 reveals a subtle failure mode — the tutor embedded 
  the solution code inside a question, technically maintaining Socratic form while 
  violating the answer-withholding principle. This suggests LLM tutors can appear 
  Socratic while implicitly giving away answers — a failure mode invisible to surface-level evaluation.

## Files
- ai_tutoring.ipynb — full implementation
- transcripts.txt — all 3 conversation transcripts
- results.csv — rubric scores per experiment

Run Cell 7, add the markdown cell, then save to Google Drive and push to GitHub. Your repo should have:
ai-tutor-stress-test/
├── ai_tutoring.ipynb
├── transcripts.txt
├── results.csv
└── README.md
Tell me when it's saved and we'll write the personal statement paragraph that references this work.# Testing-AI-tutor-s-
