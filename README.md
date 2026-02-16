# Student-Task-Manager
A simple web-based task management system designed for students to organize assignments and deadlines. Users can add, edit, delete, and mark tasks as completed. The goal of the project was to improve productivity and practice frontend development and basic application logic. Tech Stack:  HTML, CSS, JavaScript (or Python Flask if you prefer backend)

------HTML-----
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Task Manager</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>Student Task Manager</h1>

        <input type="text" id="taskInput" placeholder="Enter a new task">
        <button onclick="addTask()">Add Task</button>

        <ul id="taskList"></ul>
    </div>

    <script src="script.js"></script>
</body>
</html>

-----CSS-----
body {
    font-family: Arial, sans-serif;
    background: #f4f6f8;
    display: flex;
    justify-content: center;
    margin-top: 50px;
}

.container {
    background: white;
    padding: 20px;
    width: 350px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

h1 {
    text-align: center;
}

input {
    width: 70%;
    padding: 8px;
}

button {
    padding: 8px;
    cursor: pointer;
}

li {
    margin-top: 10px;
}

.completed {
    text-decoration: line-through;
    color: gray;
}

-----SCRIPT.JS-----
function addTask() {
    let taskInput = document.getElementById("taskInput");
    let taskText = taskInput.value;

    if (taskText === "") {
        alert("Please enter a task");
        return;
    }

    let li = document.createElement("li");
    li.textContent = taskText;

    li.onclick = function () {
        li.classList.toggle("completed");
    };

    let taskList = document.getElementById("taskList");
    taskList.appendChild(li);

    taskInput.value = "";
}
