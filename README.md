# Boot-camp-1
This is a simple Task Manager built using HTML, CSS, and JavaScript. It allows users to add tasks to a list and provides a delete option for each task.

Features
Add a task to the task list.
Display the task with a serial number.
Delete tasks from the list.
Code Explanation
HTML Structure
The structure consists of a form to input tasks and a table to display the list of tasks.
The <table> element contains a placeholder task (Workout) to illustrate how tasks will be displayed.
html
Copy code
<form action="">
    <input type="text" name="Add Task" id="task-input">
    <button type="submit">Add Task</button>
</form>
Table
The table has two columns: one for the serial number and one for the task.
The initial row contains an example task, "Workout."
html
Copy code
<table border="">
    <thead>
        <th colspan="2" style="text-align: center;">Task Manager</th>
    </thead>
    <thead>
        <th>Se. No.</th>
        <th>Tasks</th>
    </thead>
    <tr>
        <td>1</td>
        <td>Workout</td>
    </tr>
</table>
CSS Styling
The button has a custom background color and a pointer cursor for better user interaction.
css
Copy code
button {
    background-color: rgb(0, 200, 255);
    cursor: pointer;
}
JavaScript Functionality
The script captures the form submission, prevents the default page reload, and dynamically adds a new row to the task table with a delete button.
javascript
Copy code
document.querySelector('form').addEventListener('submit', function(e) {
    e.preventDefault(); // Prevent the form from reloading the page
    var task = document.querySelector('#task-input').value; // Get the task input value
    var tasks = document.querySelector('table'); // Target the table to append tasks

    // Create a new row for the task
    var newTask = document.createElement('tr');
    newTask.innerHTML = '<td>' + task + '</td>'; // Add task content
    newTask.innerHTML += '<td><button>Delete</button></td>'; // Add delete button

    tasks.appendChild(newTask); // Append the new task to the table
});
Issues
The #Tasks element referenced in the script should be table, as there's no element with the ID #Tasks.
The task variable should be used consistently, and the append method should be appendChild.
How to Use
Open the index.html file in a browser.
Add tasks using the input field and click the Add Task button.
The task will appear in the table.
(Upcoming Feature) Click the Delete button to remove the task from the list (this needs to be implemented in the script).
This README should help provide context for the project and guide users on how the task manager functions.
