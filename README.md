 scan the ENTIRE repository and build an internal mental model:                                                         1. List every file and its role in one sentence                                                                         2. Map all dependencies between modules (who calls whom)
 3. Identify integration points
 4. Flag “danger zones” — places where one wrong change breaks something else
 5. Flag “workarounds” — code that works but is fragile, temporary, or non-standard
 6. Note missing error handling, missing tests, hardcoded values

  Based on this                                                                                                         Create a single self-contained HTML file with these sections:                                                           1. APPLICATION MAP
Visual overview (use CSS/SVG, no external libraries) showing:
 ∙ Main modules and their relationships
 ∙ Data flow: user action → frontend → __backend__\  → external APIs
 ∙ Click any module → sidebar shows: what it does, what it depends on, what breaks if you touch it
2. CRITICAL PATHS (in plain English)
Step-by-step walkthroughs of the most important flows:
 ∙ New client registration + subdomain creation (________ API)
 ∙ _____ payment → webhook → ____ state update
 ∙ Authentication flow
 ∙ Any scheduled ___\\\ Functions
Each step shows: which file, which function, what it does, what can go wrong
3. DANGER ZONES
A red-flagged list of files/functions that are:
 ∙ Risk level 1-5 (5 = touch this and production breaks)
 ∙ Why it’s risky
 ∙ What to check before editing
 ∙ How to test after editing
4. WORKAROUND REGISTER
Every hack, temporary solution, or non-standard pattern:
 ∙ What it does
 ∙ Why it exists (if determinable from code)
 ∙ What the proper solution would be
 ∙ Urgency: can wait / fix soon / fix before scaling
5. FLASHCARDS (interactive)
Generate 60+ question/answer cards covering:
 ∙ Architecture questions (“What happens when a new client signs up?”)
 ∙ Debugging questions (“Stripe webhook isn’t firing — where do you check first?”)
 ∙ Data model questions (“What does a client document look like in _____?”)
 ∙ Infrastructure questions (“How is a subdomain created? Which API? Which function?”)
Implement as a flip-card UI in pure HTML/CSS/JS
6. ENVIRONMENT & SECRETS MAP
List every environment variable and database config key:
 ∙ What it does
 ∙ Where it’s used
 ∙ What breaks if it’s missing or wrong
 ∙ Where to find/regenerate it
(Do NOT include actual values — only names and descriptions)
7. ______ ARCHITECTURE
 ∙ database collections with field-by-field explanation
 ∙ Security rules — explain what each rule allows/blocks in plain language
 ∙ Cloud Functions — each function’s trigger, purpose, and side effects
 ∙ ______ Hosting configuration
8. DEPLOYMENT CHECKLIST
Step-by-step: how to deploy a change safely
 ∙ What to check before deploying
 ∙ Deploy commands in order
 ∙ How to verify deployment succeeded
 ∙ How to rollback if something breaks
Requirements for the HTML file:
 ∙ Zero external dependencies (no CDN, no fonts, no images from web)
 ∙ Dark mode by default
 ∙ Sidebar navigation between sections
 ∙ Search functionality (JS, searches all content)
 ∙ Print-friendly CSS for sections
 ∙ Every “danger” item visually distinct (red border, warning icon)
 ∙ Every “workaround” item visually distinct (orange/yellow)
 ∙ Mobile readable (just in case)
 ∙ File size: optimize for readability, not minimalism — verbose is fine
Output
Save as: /docs/knowledge-base.html
After creating it, give me a summary of:
 ∙ How many danger zones you found (by risk level)
 ∙ How many workarounds you found
 ∙ The 3 most critical things I should understand about this codebase


The subpoint I gave you are just reference. Adjust to our project.
