# JavaScript Debugging Exercise

This repository contains a simple event-driven webpage built for a debugging practice activity.

## Project Overview

The goal is to identify and fix common HTML and JavaScript issues in a basic interactive webpage. The completed project should:

- Display a personalized greeting when the button is clicked.
- Show a live typing message as the user enters text.
- Change the webpage background color on demand.
- Reset the webpage to its original state.
- Display debugging messages in the browser console.
- Run without console errors.

## Files

- `index.html` — page structure and script inclusion.
- `style.css` — page styling.
- `script.js` — JavaScript behavior, event handlers, and debugging logic.
- `README.md` — project documentation.
- `LAB ACT 2_EDP (DEBUGGING EXERCISE).docx` — assignment instructions and grading checklist.

## Debugging Table

| No. | Error Found | Type of Error | Correction Made |
| --- | --- | --- | --- |
| 1 | Incorrect CSS reference in HTML | Incorrect file reference | Fixed `<link rel="stylesheet" href="style.css">` |
| 2 | Wrong input selector in JavaScript | Incorrect element selector | Changed selector to `#nameInput` |
| 3 | Script loaded before DOM elements were available | Load order issue | Placed `<script src="script.js"></script>` before `</body>` |
| 4 | Invalid event type `clicked` | Incorrect event type | Replaced with `click` |
| 5 | Assignment used instead of comparison in empty-name validation | Logical error | Changed `if (userName = "")` to `if (userName === "")` |
| 6 | Event handler was passed as a call expression | Incorrect event-handler assignment | Used `displayGreeting` instead of `displayGreeting()` |
| 7 | Background color logic did not toggle correctly | Logical/runtime error | Added `if (currentColor === "lightblue")` logic and used a default hex color |
| 8 | `showTypedText` required live updates while typing | Event handling error | Changed event listener to `input` |
| 9 | Background color stayed `lightblue` instead of resetting | Logical error | Added toggle logic with default `#f3f4f6` and `lightblue` |
| 10 | Actions could run without entering a name | Logical error | Added empty-name guard to `changeBackground()` and `resetPage()` |

## Key Fixes

- Ensured `script.js` loads after DOM elements.
- Corrected element selectors and event listener usage.
- Added guard clauses so actions require a non-empty name.
- Implemented background toggle logic with `lightblue` and default colors.
- Preserved console debugging output and page reset behavior.

## How to Use

1. Open `index.html` in a web browser.
2. Type your name into the input field.
3. Click `Display Greeting` to show the greeting message.
4. Click `Change Background` to toggle the page background.
5. Click `Reset` to return the page to its original state.

## Notes

The project is a debugging exercise that demonstrates how to correct DOM selectors, event handling, validation rules, and runtime logic in a simple JavaScript webpage.
