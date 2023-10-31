# ToDo2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToDo-Liste</title>
    <style>
        /* Füge hier dein CSS hinzu, um die Benutzeroberfläche zu gestalten */
    </style>
</head>
<body>
    <h1>ToDo-Liste</h1>

    <div>
        <input type="text" id="task" placeholder="Neue Aufgabe eingeben">
        <button onclick="addTask()">Hinzufügen</button>
    </div>

    <ul id="taskList">
        <!-- Hier werden die Aufgaben angezeigt -->
    </ul>

    <script>
        function addTask() {
            // Diese Funktion fügt eine neue Aufgabe der Liste hinzu
            var taskInput = document.getElementById("task");
            var taskText = taskInput.value;

            if (taskText.trim() === "") {
                alert("Bitte eine Aufgabe eingeben.");
                return;
            }

            var taskList = document.getElementById("taskList");
            var taskItem = document.createElement("li");
            taskItem.textContent = taskText;

            var deleteButton = document.createElement("button");
            deleteButton.textContent = "Löschen";
            deleteButton.onclick = function() {
                taskList.removeChild(taskItem);
            };

            taskItem.appendChild(deleteButton);
            taskList.appendChild(taskItem);

            taskInput.value = "";
        }
    </script>
</body>
</html>
