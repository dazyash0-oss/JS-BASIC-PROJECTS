
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cozy To-Do List</title>
    <style>
        /* --- CSS STYLING --- */
        
        body {
            background-color: #fdfaf6; /* Warm Cream */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #4a3e3d;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .todo-container {
            background-color: #ffffff;
            width: 100%;
            max-width: 400px;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(244, 190, 198, 0.3);
            border: 1px solid #f9ecea;
        }

        h2 {
            text-align: center;
            color: #ff7b90; /* Vibrant Pastel Pink */
            margin-top: 0;
            margin-bottom: 25px;
            font-size: 28px;
            font-weight: 200;
            letter-spacing: -0.5px;
        }

        .input-section {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

        #task-input {
            flex: 1;
            padding: 12px 15px;
            border: 2px solid #fcecee;
            border-radius: 12px;
            background-color: #fffdfb;
            font-size: 16px;
            font-weight: bold;
            color: #4a3e3d;
            outline: none;
            transition: border-color 0.3s;
        }

        #task-input:focus {
            border-color: #ffb3c1;
        }

        #add-btn {
            background-color: #ff9ebb; /* Pastel Pink Button */
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 12px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.2s, transform 0.1s;
        }

        #add-btn:hover {
            background-color: #ff7b90;
        }

        #add-btn:active {
            transform: scale(0.95);
        }

        #task-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .task-item {
            display: flex;
            align-items: center;
            background-color: #fff9f9;
            padding: 12px 15px;
            border-radius: 12px;
            margin-bottom: 10px;
            border-left: 4px solid #ffccd5;
            animation: fadeIn 0.3s ease;
            transition: all 0.3s;
        }

        /* Cute Custom-toned Checkbox Wrapper */
        .task-checkbox {
            appearance: none; /* Removes default boring browser checkbox */
            -webkit-appearance: none;
            width: 20px;
            height: 20px;
            border: 2px solid #ffccd5;
            border-radius: 6px;
            background-color: #ffffff;
            cursor: pointer;
            margin-right: 12px;
            display: grid;
            place-content: center;
            transition: all 0.2s;
        }

        /* Checkbox hover effect */
        .task-checkbox:hover {
            border-color: #ff9ebb;
            background-color: #fff0f2;
        }

        /* Checkbox state when checked */
        .task-checkbox:checked {
            background-color: #ff9ebb;
            border-color: #ff9ebb;
        }

        /* Adds a tiny white checkmark inside when checked */
        .task-checkbox:checked::before {
            content: "✓";
            color: white;
            font-size: 14px;
            font-weight: bold;
        }

        .task-text {
            flex: 1;
            font-size: 16px;
            transition: all 0.3s;
        }

        /* Styles applied when checkbox is ticked */
        .task-item.completed {
            background-color: #f7f5f4;
            border-left-color: #d6ccc2;
            opacity: 0.6;
        }

        .task-item.completed .task-text {
            text-decoration: line-through;
            color: #a09392;
        }

        .delete-btn {
            background: none;
            border: none;
            color: #ffb3c1;
            font-size: 18px;
            cursor: pointer;
            font-weight: bold;
            transition: color 0.2s;
            padding: 0 5px;
        }

        .delete-btn:hover {
            color: #ff4d6d;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(5px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <div class="todo-container">
        <h2>MY TASKS</h2>
        
        <div class="input-section">
            <input type="text" id="task-input" placeholder="Add a new cozy task..." autocomplete="off">
            <button id="add-btn">Add</button>
        </div>

        <ul id="task-list">
            </ul>
    </div>

    <script>
        const taskInput = document.getElementById('task-input');
        const addBtn = document.getElementById('add-btn');
        const taskList = document.getElementById('task-list');

        function addTask() {
            const taskText = taskInput.value.trim();

            if (taskText === "") {
                alert("Please type a task first! ✨");
                return;
            }

            const li = document.createElement('li');
            li.className = 'task-item';

            // Insert HTML inside the <li> including the checkbox
            li.innerHTML = `
                <input type="checkbox" class="task-checkbox">
                <span class="task-text">${taskText}</span>
                <button class="delete-btn">&times;</button>
            `;

            // Interactivity #1: Detect checkbox changes to toggle the "completed" layout
            const checkbox = li.querySelector('.task-checkbox');
            checkbox.addEventListener('change', function() {
                if (checkbox.checked) {
                    li.classList.add('completed');
                } else {
                    li.classList.remove('completed');
                }
            });

            // Interactivity #2: Delete button removes the task completely
            const deleteBtn = li.querySelector('.delete-btn');
            deleteBtn.addEventListener('click', function() {
                li.remove();
            });

            taskList.appendChild(li);
            taskInput.value = "";
        }

        addBtn.addEventListener('click', addTask);

        taskInput.addEventListener('keypress', function(event) {
            if (event.key === 'Enter') {
                addTask();
            }
        });
    </script>
</body>
</html>
