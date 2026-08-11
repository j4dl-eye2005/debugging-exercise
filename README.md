# JavaScript Debugging Exercise

This repository contains a simple event-driven webpage built for a debugging practice activity.

## Project Overview

The goal is to identify and fix common HTML and JavaScript issues in a basic interactive webpage. The completed project should:

- Display a personalized greeting when the button is clicked.
- Show a message while the user is typing.
- Change the webpage background color.
- Reset the webpage to its original state.
- Display debugging messages in the browser console.
- Run without errors in the browser console.

## Files

- `index.html` — page structure and script inclusion.
- `style.css` — page styling.
- `script.js` — JavaScript behavior, event handlers, and debugging logic.
- `README.md` — project documentation.
- `LAB ACT 2_EDP (DEBUGGING EXERCISE).docx` — assignment instructions and grading checklist.

## Debugging Table

| No. | Error Found | Type of Error | Correction Made |
| --- | --- | --- | --- |
| 1 | There is an incorrect file reference in the style.css syntax in HTML file | Incorrect file reference | `<link rel="stylesheet" href="style.css">` |
| 2 | The element selector `#name` should be `#nameInput` in script.js | Incorrect element selector | `const nameInput = document.querySelector("#nameInput");` |
| 3 | The execution of the .js script is wrongly placed in the html file which is nearly placed at the .css stylesheet instead of being inside the bottom of the body, which causes it not to work or to be executed | Syntax error | The `<script src="script.js"></script>` has to be placed near the `</body>` instead |
| 4 | The event type “clicked” is wrong and should be “click” instead in script.js | Incorrect event type | `colorButton.addEventListener("click", changeBackground);` |
| 5 | The username uses an assignment operator instead of a comparison operator in script.js which results in not displaying a warning message "Please enter your name." | Logical error | `if (userName === "")` |
| 6 | The `displayGreeting` has a parentheses so the function is being executed immediately, not being passed as a handler | Incorrect event-handler assignment | `greetButton.addEventListener("click", displayGreeting);` |
| 7 | `changeBackground()` uses `lightblue` without declaring it, so it will throw an error at runtime. | Runtime error | `document.body.style.backgroundColor = "lightblue";` |
| 8 | The “typing message” requirement, the input should update on the `input` event, not the `change` event. | Incorrect event type | `nameInput.addEventListener("input", showTypedText);` |
| 9 | The background color remains lightblue instead of going back to the default background color | Logical error | ```js
function changeBackground() {
    const currentColor = document.body.style.backgroundColor;

    if (currentColor === "lightblue") {
        document.body.style.backgroundColor = "#f3f4f6";
    } else {
        document.body.style.backgroundColor = "lightblue";
    }

    console.log("Background color changed.");
}
``` |
| 10 | Even without typing a name, it already allows me to perform an action like changing the background or reset | Logical error | ```js
function changeBackground() {
    if (nameInput.value.trim() === "") {
        resultMessage.textContent = "Please enter your name.";
        return;
    }

    const currentColor = document.body.style.backgroundColor;
    ...
}

function resetPage() {
    if (nameInput.value.trim() === "") {
        resultMessage.textContent = "Please enter your name.";
        return;
    }

    heading.textContent = "Event-Driven Webpage";
    ...
}
``` |

### Key debugging and grading checks

- Correct CSS filename or file reference.
- Ensure JavaScript runs after HTML elements load.
- Correct element selectors and IDs.
- Fix empty-input validation logic.
- Fix invalid event types and handler assignment.
- Use `input` event for live typing messages.
- Ensure greeting, background change, and reset features work correctly.
- No console errors.

## How to Use

1. Open `index.html` in a web browser.
2. Type your name into the input field.
3. Click `Display Greeting` to show the greeting message.
4. Click `Change Background` to toggle the page background.
5. Click `Reset` to return the page to its original state.

## Notes

The project is built as a debugging exercise that requires correcting the initial code and verifying the page works without console errors.
