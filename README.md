# Deadline Rescue

A local, browser-only HCI prototype for assessment triage. No application dependencies or backend are required. Data is stored in this browser's localStorage.

## Run

```powershell
cd "C:\Users\yungs\OneDrive\Documents\School Projects\deadline-rescue-hci"
npm start
```

Open http://localhost:4417. Stop the local server with Ctrl+C.

## Priority model

Each open task receives a transparent relative score:

`(module assessment weight × task contribution × urgency factor) ÷ estimated task hours`

Urgency factors are 2.5 when overdue, 2.25 when due today, 2.0 within two days, 1.65 within five days, 1.3 within ten days, and 1.0 otherwise. Starting with the highest score, the day plan includes tasks that fit the remaining time budget; tasks that do not fit are skipped while shorter tasks are considered. If no task fits, the shortest open task is shown with a prompt to change the budget or estimate. At zero minutes the system does not recommend work.

This is a demonstrator rule, not a validated scheduling or grade-prediction model. Weight and contribution estimates can be approximate, tasks may have dependencies not represented here, and the user can override the suggested next task. Study Buddy is a local preview only; it does not send messages or create a share link.

## Prototype checks

`npm run check` performs JavaScript syntax checks. The interface uses semantic form controls, visible keyboard focus, labels, text status cues, responsive breakpoints, and reduced-motion preferences. These design choices are not a claim of full WCAG conformance.
