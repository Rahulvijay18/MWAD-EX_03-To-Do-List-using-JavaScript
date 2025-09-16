# MWAD-EX_03-To-Do-List-using-JavaScript
## Name: RAHUL VIJAY V
## Reg no: 212223040164

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
### index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="box">
    <h1>📝 To-Do List</h1>

    <div class="inputs">
      <input type="text" id="taskInput" placeholder="Enter task...">
      <button id="addBtn">➕ Add</button>
      <button id="clearAll">🧹 Clear All</button>
    </div>

    <p id="counter">Tasks Left: 0 | Done: 0</p>

    <ul id="list"></ul>
  </div>

  <script src="script.js"></script>
</body>
</html>

```
### style.css
```
body {
  background: linear-gradient(135deg, #2961e6, #2575fc);
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.box {
  background: #ffffff;
  padding: 20px;
  border-radius: 15px;
  width: 380px;
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
  text-align: center;
}

h1 {
  text-align: center;
  margin-bottom: 15px;
  color: #333;
}

.inputs {
  display: flex;
  gap: 5px;
  margin-bottom: 15px;
}

#taskInput {
  flex: 1;
  padding: 8px;
  border: 2px solid #ddd;
  border-radius: 8px;
  outline: none;
  font-size: 14px;
}

button {
  background: #4cafef;
  color: #fff;
  border: none;
  padding: 8px 12px;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.3s;
}
button:hover {
  background: #1e88e5;
}

#clearAll {
  background: #f76c6c;
}
#clearAll:hover {
  background: #d64545;
}

#counter {
  text-align: center;
  font-weight: bold;
  margin: 10px 0;
  color: #444;
}

#list {
  list-style: none;
  padding: 0;
  margin: 0;
}

#list li {
  background: #f4f4f4;
  margin-bottom: 8px;
  padding: 8px 10px;
  border-radius: 8px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: 0.3s;
}

#list li.done {
  text-decoration: line-through;
  background: #c8f7c5;
  color: #333;
}

#list button {
  background: transparent;
  border: none;
  cursor: pointer;
  font-size: 16px;
}
#list button:hover {
  transform: scale(1.2);
}

```
### script.js
```
const taskInput = document.getElementById("taskInput");
const addBtn = document.getElementById("addBtn");
const taskList = document.getElementById("list");
const counter = document.getElementById("counter");
const clearAllBtn = document.getElementById("clearAll");

addBtn.addEventListener("click", addTask);

taskInput.addEventListener("keypress", (e) => {
  if (e.key === "Enter") addTask();
});

clearAllBtn.addEventListener("click", () => {
  taskList.innerHTML = "";
  updateCounter();
});

function addTask() {
  const text = taskInput.value.trim();
  if (text === "") {
    alert("Please enter a task!");
    return;
  }

  const li = document.createElement("li");

  const span = document.createElement("span");
  span.textContent = text;

  const doneBtn = document.createElement("button");
  doneBtn.textContent = "✔";
  doneBtn.addEventListener("click", () => {
    li.classList.toggle("done");
    updateCounter();
  });

  const editBtn = document.createElement("button");
  editBtn.textContent = "✎";
  editBtn.addEventListener("click", () => {
    const newText = prompt("Edit your task:", span.textContent);
    if (newText !== null && newText.trim() !== "") {
      span.textContent = newText.trim();
    }
  });

  const delBtn = document.createElement("button");
  delBtn.textContent = "✖";
  delBtn.addEventListener("click", () => {
    li.remove();
    updateCounter();
  });

  li.appendChild(span);
  li.appendChild(doneBtn);
  li.appendChild(editBtn);
  li.appendChild(delBtn);

  taskList.appendChild(li);

  taskInput.value = "";
  updateCounter();
}

function updateCounter() {
  const total = taskList.getElementsByTagName("li").length;
  const completed = taskList.querySelectorAll(".done").length;
  const pending = total - completed;
  counter.textContent = `Tasks Left: ${pending} | Done: ${completed}`;
}

```
## OUTPUT

<img width="1917" height="901" alt="Screenshot 2025-09-17 012253" src="https://github.com/user-attachments/assets/36db1bbb-9dc1-4239-8e9e-b7adecab5679" />

### Adding todo event

<img width="1919" height="907" alt="Screenshot 2025-09-17 012312" src="https://github.com/user-attachments/assets/728ccb21-867d-4ab1-a490-04879a45decb" />

### Event Completed

<img width="1919" height="902" alt="Screenshot 2025-09-17 012324" src="https://github.com/user-attachments/assets/21ce5eb7-37ae-4314-8633-2f0d9a31501c" />

### Event Editing
<img width="1919" height="907" alt="Screenshot 2025-09-17 012337" src="https://github.com/user-attachments/assets/72cb657b-daeb-467d-8454-ca7a38986383" />

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
