# To-do-list
to do list making by  html , css , java script
<!DOCTYPE html>
<html>
<head>
    <title>To-Do List</title>
    <style>
        body {
            font-family: fantasy;, sans-serif;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        h1 {
            text-align: center;
        }
        input[type="text"] {
            width: 100%;
            padding: 20px;
            box-sizing: border-box;
            margin-bottom: 20px;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px;
            border-bottom: 1px solid #ccc;
        }
        li:last-child {
            border-bottom: none;
        }
        button {
            background-color: #4CAF50;
            color: black;
            border: cadetblue;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin-top: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body bgcolor="blue">
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Enter a task">
        <button onclick="addTask()">Add Task</button>
        <ul id="taskList"></ul>
    </div>

    <script>
        function addTask() {
            var taskInput = document.getElementById("taskInput");
            var taskList = document.getElementById("taskList");
            var taskText = taskInput.value;

            if (taskText === "") {
                alert("Please enter a task!");
                return;
            }

            var li = document.createElement("li");
            var taskTextSpan = document.createElement("span");
            taskTextSpan.innerText = taskText;

            var deleteButton = document.createElement("button");
            deleteButton.innerText = "Delete";
            deleteButton.onclick = function() {
                li.remove();
            };

            li.appendChild(taskTextSpan);
            li.appendChild(deleteButton);
            taskList.appendChild(li);

            taskInput.value = "";
        }
    </script>
</body>
</html>
