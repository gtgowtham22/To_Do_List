# Ex03 To-Do List using JavaScript
## Date:10.2.2026

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>

<div class="container">
    <h1>TO-DO LIST</h1>

    <div class="input-container">
        <input type="text" id="taskInput" placeholder="Enter your task">
        <button id="addTaskBtn">ADD</button>
    </div>

    <ul id="taskList">
        <!-- Tasks will appear here -->
    </ul>
</div>

<script src="script.js"></script>

</body>
</html>
```
```
document.addEventListener("DOMContentLoaded", function () {

    const taskInput = document.getElementById("taskInput");
    const addTaskBtn = document.getElementById("addTaskBtn");
    const taskList = document.getElementById("taskList");

    // Add task
    addTaskBtn.addEventListener("click", addTask);

    function addTask() {
        let taskText = taskInput.value.trim();

        if (taskText === "") {
            alert("Please enter a task");
            return;
        }

        // Create list item
        let li = document.createElement("li");

        // Task text
        let span = document.createElement("span");
        span.textContent = taskText;

        // Checkbox
        let checkbox = document.createElement("input");
        checkbox.type = "checkbox";

        checkbox.addEventListener("change", function () {
            span.classList.toggle("completed");
        });

        // Delete button
        let deleteBtn = document.createElement("button");
        deleteBtn.textContent = "Delete";
        deleteBtn.classList.add("delete-btn");

        deleteBtn.addEventListener("click", function () {
            taskList.removeChild(li);
        });

        li.appendChild(checkbox);
        li.appendChild(span);
        li.appendChild(deleteBtn);

        taskList.appendChild(li);

        taskInput.value = "";
    }

    // Add task using Enter key
    taskInput.addEventListener("keypress", function (e) {
        if (e.key === "Enter") {
            addTask();
        }
    });

});
```
## OUTPUT
![5fa76fb7-feac-426b-8d87-5f484213347d](https://github.com/user-attachments/assets/d8ae6224-f194-424a-994d-ec2f6cc2b747)


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
