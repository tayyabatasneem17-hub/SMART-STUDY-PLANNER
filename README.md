# SMART-STUDY-PLANNER
<!DOCTYPE html>

<html lang="en">
    
<head>
    
    <meta charset="UTF-8">
    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Smart Study Planner</title>
    
    <style>
    
        body {
        
            font-family: Arial, sans-serif;
            
            background-color: #f2f2f2;
            
            padding: 20px;
            
        }
        
        h1 {
        
            text-align: center;
            
        }

        
        .planner {
        
            max-width: 500px;
            
            margin: 0 auto;
            
            background: #fff;
            
            padding: 20px;
            
            border-radius: 10px;

            
            box-shadow: 0 0 10px #ccc;
        }
        
        input, select, button {
        
            width: 100%;
            
            padding: 10px;
            
            margin: 5px 0;
            
            border-radius: 5px;

            
            border: 1px solid #ccc;
        }
        
        ul {
        
            list-style-type: none;
            
            padding: 0;
            
        }
        
        li {
        
            padding: 10px;
            
            margin: 5px 0;
            
            background: #e0e0e0;
            
            border-radius: 5px;
            
            display: flex;
            
            justify-content: space-between;
            
            align-items: center;
            
        }
        
        li.completed {
        
            text-decoration: line-through;
            
            background: #b0ffb0;
            
        }
        
        button.remove {
        
            background: red;
            
            color: white;
            
            border: none;
            
            padding: 5px 10px;
            
            border-radius: 5px;
            
            cursor: pointer;
            
        }
        
    </style>
    
</head>

<body>

    <h1>Smart Study Planner</h1>

    <div class="planner">
    
        <input type="text" id="taskInput" placeholder="Enter subject/topic">
        
        <input type="number" id="durationInput" placeholder="Duration (minutes)">
        
        <select id="priorityInput">
        
            <option value="High">High Priority</option>
            
            <option value="Medium">Medium Priority</option>
            
            <option value="Low">Low Priority</option>
            
        </select>
        
        <button onclick="addTask()">Add Task</button>

        <ul id="taskList"></ul>
        
    </div>

    <script>
    
        function addTask() {
        
            const taskInput = document.getElementById('taskInput');
            
            const durationInput = document.getElementById('durationInput');
            
            const priorityInput = document.getElementById('priorityInput');
            
            const taskList = document.getElementById('taskList');

            if (taskInput.value === "" || durationInput.value === "") {
            
                alert("Please enter a task and duration!");
                
                return;
            }

            const li = document.createElement('li');
            
            li.innerHTML = `
            
                <span>${taskInput.value} - ${durationInput.value} min - ${priorityInput.value}</span>
                
                <button class="remove" onclick="removeTask(this)">Remove</button>
            `;
            li.onclick = function() {
            
                li.classList.toggle('completed');
            }
            taskList.appendChild(li);

            taskInput.value = "";
            
            durationInput.value = "";
            
            priorityInput.value = "High";
        }

        function removeTask(button) {
        
            const li = button.parentElement;
            
            li.remove();
        }
    </script>
    
    </body>

</html>




output:

<img width="1920" height="1080" alt="{8DBBA480-7B1C-4FF9-935A-F3F52CA25875}" src="https://github.com/user-attachments/assets/18b38058-6547-4817-b2a3-92bb163ab190" />


