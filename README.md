<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8" name="viewport" content="width=device-width, initial-scale=1">
  <title>Work</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">

<div class="container mt-5">
  <div class="card shadow">
    <div class="card-body">
      <h3 class="text-center mb-4">Darbs</h3>
      <div class="input-group mb-3">
        <input type="text" id="task-input" class="form-control" placeholder="Ievadi uzdevumu">
        <button class="btn btn-primary" onclick="addTask()">Pievienot</button>
      </div>
      <ul id="task-list" class="list-group"></ul>
    </div>
  </div>
</div>

<script>
function addTask() {
  const input = document.getElementById("task-input");
  const text = input.value.trim();
  if(text === "") return;

  const li = document.createElement("li");
  li.className = "list-group-item d-flex justify-content-between align-items-center";
  li.innerHTML = `<span>${text}</span><button class="btn btn-danger btn-sm">Dzēst</button>`;

  li.querySelector("span").onclick = function() {
    li.querySelector("span").classList.toggle("text-decoration-line-through");
    li.querySelector("span").classList.toggle("text-muted");

  };

  li.querySelector("button").onclick = function() {
    li.remove();
  };
  
  document.getElementById("task-list").appendChild(li);
  input.value = "";
}

</script>

</body>
</html>
