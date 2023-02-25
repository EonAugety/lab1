window.addEventListener('load', () => {
  const form = document.querySelector("#new-task-form");
  const taskInput = document.querySelector("#new-task-input");
  const taskDate = document.querySelector("#new-task-date");
  const listEl = document.querySelector("#tasks");

  form.addEventListener('submit', (e) => {
    e.preventDefault();

    // Get task description and due date from the input fields
    const taskDesc = taskInput.value;
    const taskDueDate = taskDate.value;

    // Create the task element
    const taskEl = document.createElement('div');
    taskEl.classList.add('task');

    // Add task description to the task element
    const taskDescEl = document.createElement('div');
    taskDescEl.classList.add('content');
    taskEl.appendChild(taskDescEl);

    const taskDescInputEl = document.createElement('input');
    taskDescInputEl.classList.add('text');
    taskDescInputEl.type = 'text';
    taskDescInputEl.value = taskDesc;
    taskDescInputEl.setAttribute('readonly', 'readonly');
    taskDescEl.appendChild(taskDescInputEl);

    // Add due date to the task element
    const taskDueDateEl = document.createElement('div');
    taskDueDateEl.classList.add('duedate');
    taskDueDateEl.textContent = taskDueDate;
    taskEl.appendChild(taskDueDateEl);

    // Add task actions (Edit/Delete) to the task element
    const taskActionsEl = document.createElement('div');
    taskActionsEl.classList.add('actions');

    const taskEditEl = document.createElement('button');
    taskEditEl.classList.add('edit');
    taskEditEl.innerText = 'Edit';

    const taskDeleteEl = document.createElement('button');
    taskDeleteEl.classList.add('delete');
    taskDeleteEl.innerText = 'Delete';

    taskActionsEl.appendChild(taskEditEl);
    taskActionsEl.appendChild(taskDeleteEl);

    taskEl.appendChild(taskActionsEl);
    listEl.appendChild(taskEl);

    // Reset input fields
    taskInput.value = '';
    taskDate.value = '';

    // Add event listener to Edit button
    taskEditEl.addEventListener('click', (e) => {
      if (taskEditEl.innerText.toLowerCase() == "edit") {
        taskEditEl.innerText = "Save";
        taskDescInputEl.removeAttribute("readonly");
        taskDescInputEl.focus();
      } else {
        taskEditEl.innerText = "Edit";
        taskDescInputEl.setAttribute("readonly", "readonly");
      }
    });

    // Add event listener to Delete button
    taskDeleteEl.addEventListener('click', (e) => {
      listEl.removeChild(taskEl);
    });
  });
});

// Toggle completed class on task element when clicked
const tasksContainer = document.getElementById('tasks');

tasksContainer.addEventListener('click', (event) => {
  const taskElement = event.target.closest('.task');
  if (taskElement) {
    taskElement.classList.toggle('completed');
  }
});
