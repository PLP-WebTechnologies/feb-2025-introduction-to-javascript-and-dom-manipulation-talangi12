7# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

Happy Coding! 💻✨
# HTML 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dynamic DOM Manipulation</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Welcome to the Dynamic Page!</h1>
    </header>

    <main>
        <p id="dynamicText">This is the initial text.</p>
        <button id="styleButton">Change Style</button>
        <div id="elementContainer">
            <p class="initialElement">This is an initial paragraph.</p>
        </div>
        <button id="addElementButton">Add Element</button>
        <button id="removeElementButton">Remove Element</button>
    </main>

    <footer>
        <p>&copy; 2025 Dynamic Interactions</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

# CSS 
body {
    font-family: sans-serif;
    margin: 20px;
}

header {
    background-color: #f0f0f0;
    padding: 10px;
    text-align: center;
}

main {
    margin-top: 20px;
}

#dynamicText {
    font-weight: bold;
    color: navy;
}

.styled {
    background-color: lightgreen;
    color: darkgreen;
    padding: 5px;
    border: 1px solid green;
}

.newElement {
    background-color: lightblue;
    padding: 8px;
    margin-top: 5px;
    border: 1px solid blue;
}

footer {
    text-align: center;
    margin-top: 30px;
    font-size: 0.8em;
    color: gray;
}

# Javascript 
// Function to change text content
function changeText() {
    const textElement = document.getElementById('dynamicText');
    textElement.textContent = 'The text has been dynamically changed!';
}

// Function to modify CSS styles
function changeStyle() {
    const textElement = document.getElementById('dynamicText');
    textElement.classList.toggle('styled'); // Toggles a CSS class
}

// Function to add a new element
function addElement() {
    const container = document.getElementById('elementContainer');
    const newParagraph = document.createElement('p');
    newParagraph.textContent = 'A new paragraph added dynamically.';
    newParagraph.classList.add('newElement');
    container.appendChild(newParagraph);
}

// Function to remove the last added element
function removeElement() {
    const container = document.getElementById('elementContainer');
    const lastElement = container.lastElementChild;
    if (lastElement && !lastElement.classList.contains('initialElement')) {
        container.removeChild(lastElement);
    } else if (lastElement && lastElement.classList.contains('initialElement')) {
        alert("Cannot remove the initial paragraph.");
    } else {
        alert("No elements to remove.");
    }
}

// Event listeners
document.addEventListener('DOMContentLoaded', () => {
    const styleButton = document.getElementById('styleButton');
    const addButton = document.getElementById('addElementButton');
    const removeButton = document.getElementById('removeElementButton');

    styleButton.addEventListener('click', changeStyle);
    addButton.addEventListener('click', addElement);
    removeButton.addEventListener('click', removeElement);

    // Initial text change on load (optional)
    changeText();
});

