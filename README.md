# CodeAlpha_Project_TO-DO-LIST-APPLICATION

I have built a simple c++ program to create a TO-DO LIST APPLICATION using classes.
This code allows you to:
- Add tasks.
- Mark tasks as completed.
- View the list of tasks with their completion status.

The tasks are stored in a fixed-size array, and the taskCount variable keeps track of the number of tasks added.


struct Task {
    string description;
    bool completed;
};

- *Task*: This structure represents a single task with two attributes:
  - description: A string that holds the description of the task.
  - completed: A boolean that indicates whether the task is completed (true) or not (false).

 //Constants and Function Declarations
cpp
const int MAX_TASKS = 100;

- *MAX_TASKS*: This constant defines the maximum number of tasks the application can handle. Here, it's set to 100.

 //Function Definitions

/Add Task

void addTask(Task tasks[], int &taskCount) {
    if (taskCount >= MAX_TASKS) {
        cout << "Task list is full!" << endl;
        return;
    }
    cout << "Enter the description of the task: ";
    cin.ignore();
    getline(cin, tasks[taskCount].description);
    tasks[taskCount].completed = false;
    taskCount++;
    cout << "Task added successfully!" << endl;
}

- *addTask*: This function adds a new task to the list.
  - tasks[]: The array of Task structures.
  - taskCount: The current number of tasks. Passed by reference to update the count.
  - It first checks if the task list is full. If so, it prints a message and returns.
  - It then prompts the user to enter the task description.
  - The task is added to the tasks array with the completed flag set to false.
  - The taskCount is incremented.

/Mark Task as Completed

void markTaskCompleted(Task tasks[], int taskCount) {
    cout << "Enter the task number to mark as completed: ";
    int taskNumber;
    cin >> taskNumber;
    if (taskNumber > 0 && taskNumber <= taskCount) {
        tasks[taskNumber - 1].completed = true;
        cout << "Task marked as completed!" << endl;
    } else {
        cout << "Invalid task number!" << endl;
    }
}

- *markTaskCompleted*: This function marks a task as completed.
  - tasks[]: The array of Task structures.
  - taskCount: The current number of tasks.
  - It prompts the user to enter the task number they want to mark as completed.
  - If the task number is valid (within the range of existing tasks), it sets the completed flag of the corresponding task to true.
  - If the task number is invalid, it prints an error message.

/ View Tasks
cpp
void viewTasks(const Task tasks[], int taskCount) {
    if (taskCount == 0) {
        cout << "No tasks available." << endl;
        return;
    }
    cout << "Current tasks:" << endl;
    for (int i = 0; i < taskCount; ++i) {
        cout << i + 1 << ". " << tasks[i].description << " ["
             << (tasks[i].completed ? "Completed" : "Pending") << "]" << endl;
    }
}

- *viewTasks*: This function displays the list of tasks.
  - tasks[]: The array of Task structures.
  - taskCount: The current number of tasks.
  - If there are no tasks, it prints a message indicating that.
  - Otherwise, it loops through the tasks and prints each task's description and its completion status.

/ Main Function
cpp
int main() {
    Task tasks[MAX_TASKS];
    int taskCount = 0;
    int choice;

    do {
        cout << "1. Add Task" << endl;
        cout << "2. Mark Task Completed" << endl;
        cout << "3. View Tasks" << endl;
        cout << "4. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                addTask(tasks, taskCount);
                break;
            case 2:
                markTaskCompleted(tasks, taskCount);
                break;
            case 3:
                viewTasks(tasks, taskCount);
                break;
            case 4:
                cout << "Exiting the application." << endl;
                break;
            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } while (choice != 4);

    return 0;
}

- *main*: This is the entry point of the program.
  - It initializes an array of Task structures with a size of MAX_TASKS and sets taskCount to 0.
  - It then enters a do-while loop to continuously prompt the user for their choice of action (Add Task, Mark Task Completed, View Tasks, or Exit).
  - Based on the user's choice, it calls the appropriate function.
  - If the user chooses to exit (choice 4), the loop terminates and the program ends.
 
  - ![WhatsApp Image 2024-06-28 at 13 18 53_17ac6041](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/6537bc7f-5147-4b0e-94d6-61f95f3e6e18)

