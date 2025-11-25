# Simple To-Do List Application
# Made for Codeshaft Internship Task

tasks = []

def show_menu():
    print("\n--- TO-DO LIST APPLICATION ---")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Update Task")
    print("4. Delete Task")
    print("5. Exit")

def add_task():
    task = input("Enter new task: ")
    tasks.append(task)
    print("Task added successfully!")

def view_tasks():
    if not tasks:
        print("No tasks available.")
    else:
        print("\nYour Tasks:")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def update_task():
    view_tasks()
    if tasks:
        try:
            task_no = int(input("Enter task number to update: "))
            if 1 <= task_no <= len(tasks):
                new_task = input("Enter updated task: ")
                tasks[task_no - 1] = new_task
                print("Task updated successfully!")
            else:
                print("Invalid task number.")
        except ValueError:
            print("Please enter a valid number.")

def delete_task():
    view_tasks()
    if tasks:
        try:
            task_no = int(input("Enter task number to delete: "))
            if 1 <= task_no <= len(tasks):
                tasks.pop(task_no - 1)
                print("Task deleted successfully!")
            else:
                print("Invalid task number.")
        except ValueError:
            print("Please enter a valid number.")

while True:
    show_menu()
    choice = input("Enter your choice: ")

    if choice == "1":
        add_task()
    elif choice == "2":
        view_tasks()
    elif choice == "3":
        update_task()
    elif choice == "4":
        delete_task()
    elif choice == "5":
        print("Exiting To-Do List Application. Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")
