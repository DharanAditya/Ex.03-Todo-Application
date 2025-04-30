## Ex03 To-Do List using JavaScript
## Date: 28-03-2025


## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM

STEP 1
Build the HTML structure (index.html).

STEP 2
Style the App (style.css).

STEP 3
Plan the features the To-Do App should have.

STEP 4
Create a To-do application using Javascript.

STEP 5
Add functionalities.

STEP 6
Test the App.

STEP 7
Open the HTML file in a browser to check layout and functionality.

STEP 8
Fix styling issues and refine content placement.

STEP 9
Deploy the website.

STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MY TASKS</title>
    <style>
        body { font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif, sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; flex-direction: column; }
        .container { width: 300px; }
        ul { list-style: none; padding: 0; }
        li { display: flex; justify-content: space-between; padding: 5px; border-bottom: 1px solid #ddd; }
        button { margin-left: 5px; }
        footer { margin-top: 20px; font-size: 14px; text-align: center; }
    </style>
</head>
<body>
    <div class="container">
        <h2>MY TASKS</h2>
        <input type="text" id="taskInput" placeholder="Add a task...">
        <button onclick="addTask()">Add</button>
        <ul id="taskList"></ul>
        <button onclick="filterTasks('all')">All</button>
        <button onclick="filterTasks('completed')">Completed</button>
        <button onclick="filterTasks('pending')">Pending</button>
    </div><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
    <footer class="bg-dark text-white text-center py-4 mt-2 ">
            <p>&copy; 2025 TODO. All rights reserved. BY DHARAN ADITYA (212223040035)</p>
        
    </footer>
    <script>
        let tasks = JSON.parse(localStorage.getItem('tasks')) || [];
        
        function saveTasks() {
            localStorage.setItem('tasks', JSON.stringify(tasks));
        }
        
        function renderTasks(filter = 'all') {
            const taskList = document.getElementById('taskList');
            taskList.innerHTML = '';
            tasks.filter(task => filter === 'all' || (filter === 'completed' ? task.done : !task.done))
                 .forEach((task, index) => {
                    const li = document.createElement('li');
                    li.innerHTML = `
                        <span style="text-decoration: ${task.done ? 'line-through' : 'none'}">${task.text}</span>
                        <div>
                            <button onclick="toggleTask(${index})">Done</button>
                            <button onclick="deleteTask(${index})">Incomplete</button>
                        </div>
                    `;
                    taskList.appendChild(li);
                });
        }
        
        function addTask() {
            const taskInput = document.getElementById('taskInput');
            if (taskInput.value.trim()) {
                tasks.push({ text: taskInput.value, done: false });
                taskInput.value = '';
                saveTasks();
                renderTasks();
            }
        }
        
        function toggleTask(index) {
            tasks[index].done = !tasks[index].done;
            saveTasks();
            renderTasks();
        }
        
        function deleteTask(index) {
            tasks.splice(index, 1);
            saveTasks();
            renderTasks();
        }
        
        function filterTasks(filter) {
            renderTasks(filter);
        }
        
        renderTasks();
    </script>
</body>
</html>
```

## OUTPUT
![Screenshot 2025-04-30 112540](https://github.com/user-attachments/assets/ba7668f1-9a8f-453b-9778-254adf0c4451)

![image](https://github.com/user-attachments/assets/d7da5be9-9119-4544-baa0-7a1e217f90a3)

![image](https://github.com/user-attachments/assets/016e6d49-a23d-4137-b81c-fa48c309cca8)

![Screenshot (29)](https://github.com/user-attachments/assets/97f08b63-72d0-4e0c-a92e-a91e2636b6bf)

