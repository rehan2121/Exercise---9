🗂️ RP Task Editor

Welcome to the RP Task Editor! This is a simple task management program that allows you to add, view, delete, and manage tasks. You can also track your monthly spending based on the tasks you've entered.

📋 Features

Add Task: Add a new task with details like date, description, amount, and category.
View Task: View all tasks stored in the system.
Delete Task: Remove a specific task from the list.
Mark As Complete: Mark a task as complete (though this feature is not fully implemented yet).
Monthly Spending: Calculate and display your total spending for the month.
📜 Code Explanation

Here's a breakdown of how the code works:

Global List
python
Copy code
Task_editor = []    # This is the global list to store tasks
Task_editor is a global list that holds all the tasks you add.
Add Task
python
Copy code
def add_task():
    # Collect task details from user input
    date = input("Enter The Date (YYYY-MM-DD): ")
    desc = input("Enter The Description: ")
    amnt = int(input("Enter The Amount: "))
    cate = input("Enter The Category Of The Product: ")

    # Create a task dictionary and append it to the global list
    task = {
        "Date": date,
        "Description": desc,
        "Amount": amnt,
        "Category": cate
    }

    Task_editor.append(task)
    print("Task Is Stored!\n", task)
Collects the date, description, amount, and category of the task.
Stores the task in the Task_editor list.
View Task
python
Copy code
def view_task():
    if Task_editor:
        for index, task in enumerate(Task_editor, start=1):
            print(f"{index}. {task['Date']} | {task['Description']} | {task['Amount']} | {task['Category']}")
    else:
        print("No tasks found.")
Displays all tasks in the list with their details.
If no tasks are present, it notifies the user.
Delete Task
python
Copy code
def delete_task():
    if not Task_editor:
        print("There are no tasks to delete.")
        return print("Please Add The Task")

    # Print the tasks with their corresponding numbers
    for index, task in enumerate(Task_editor, start=1):
        print(f"{index}. {task}")

    delete = int(input("Enter the task number to delete: "))

    # Delete the selected task
    if (1 <= delete <= len(Task_editor)):
        deleted_task = Task_editor.pop(delete - 1)
        print(f"The Task Is Deleted!")
    else:
        print("Invalid task number.")
Lists all tasks with numbers and allows the user to delete a task by its number.
Notifies if the task is successfully deleted or if the input is invalid.
Mark As Complete
python
Copy code
def mark_as_complete():
    # Print all tasks
    for index, task in enumerate(Task_editor, start=1):
        print(f"{index}, {task}")

    complete = int(input("Enter The Number : "))
    
    if (1 <= complete <= len(Task_editor)):
        print(f"Mark As a Mark As a Complete : {Task_editor[complete - 1]}")
    else:
        print("Nothing Edited Yet")
Displays all tasks and allows the user to mark a task as complete. (Note: The feature is not fully implemented yet.)
Monthly Spending
python
Copy code
def monthly_spending():
    if not Task_editor:
        print("First Please Add The Task Please")
    else:
        for index, task in enumerate(Task_editor, start=1):
            print(f"{index}, {task}")

        adding_task = sum(task["Amount"] for task in Task_editor)
        if (adding_task == 1000000):
            print(f"This Is The Monthly Spending : ₹{adding_task} Laks")
        elif (adding_task == 10000000):
            print(f"This Is The Monthly Spending : ₹{adding_task} Crore")
        else:
            print(f"This Is The Monthly Spending : ₹{adding_task} Billion")
Calculates and displays the total amount spent based on the tasks. Handles different thresholds for lakhs, crores, and billions.
Menu Display
python
Copy code
def menu_display():
    while True:
        greet = "\n<-----Welcome To RP Task Editor----->"
        menu = ("""
        1. Add Task
        2. View Task
        3. Delete Task
        4. Mark As Complete Task
        5. Monthly Spending
        6. Exit The Programme
        """)
        print(greet.center(50))
        print(menu.center(50))

        Choose = int(input("Enter The Number : "))
        if (Choose == 1):
            add_task()

        elif (Choose == 2):
            view_task()

        elif (Choose == 3):
            delete_task()

        elif (Choose == 4):
            mark_as_complete()
        
        elif (Choose == 5):
            monthly_spending()

        elif (Choose == 6):
            thank = "<-----Thank You For Visiting The Programme----->"
            print(thank.center(50))
            quit()

        else:
            print(f"!We Will Working On This Features!")
            quit()
Displays the main menu and allows the user to choose different options.
Exits the program if the user selects the exit option.
🚀 Getting Started

Copy the code into a Python file (e.g., task_editor.py).
Run the file using Python.
Follow the prompts to manage your tasks.
🛠️ Troubleshooting

Ensure you input valid data when adding tasks.
For any issues or bugs, check the code and make sure the input data types are correct.
