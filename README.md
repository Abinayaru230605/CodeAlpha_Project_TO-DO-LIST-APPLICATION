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
 

  ![WhatsApp Image 2024-06-28 at 13 18 53_2c77e40a](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/9b073a71-f3a9-498b-988b-0f1f66694f40)
  ![WhatsApp Image 2024-06-28 at 13 18 53_037973a0](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/d24597d4-b4d6-40d1-a2c1-54ac7df6db4b)
![WhatsApp Image 2024-06-28 at 13 18 53_44a0417d](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/10fc1d09-5de3-4fdc-8761-e2efe3102bb7)
![WhatsApp Image 2024-06-28 at 13 18 54_6ed34170](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/b88db44d-330d-4f2a-a9d2-c6f76f70eca3)
![WhatsApp Image 2024-06-28 at 13 18 54_9cdbfe92](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/93ee8c35-b991-4ed9-ade9-ebae90dd608c)
![WhatsApp Image 2024-06-28 at 13 18 54_e3b3ea9c](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/4e61c658-1ef8-4411-83f2-a24fa1c59d32)
![WhatsApp Image 2024-06-28 at 13 18 54_057acd3e](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/64fca20c-de15-4603-94b7-6c4b96954c56)
![WhatsApp Image 2024-06-28 at 13 18 55_1e33f651](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/3ddfa699-9c84-4b91-9af5-ffeceaa73243)
![WhatsApp Image 2024-06-28 at 13 18 55_a74f53ec](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/f8168b16-591f-450a-9a98-b0fe054c6e70)
![WhatsApp Image 2024-06-28 at 13 18 55_c841e0f8](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/00bf3388-6d5b-4e68-8960-7a02e2f79fe3)
![WhatsApp Image 2024-06-28 at 13 18 55_da324f6b](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/36339ea9-fdc9-420d-b6bb-0b3b1080b326)
![WhatsApp Image 2024-06-28 at 13 18 55_37e33ec4](https://github.com/Abinayaru230605/CodeAlpha_Project_TO-DO-LIST-APPLICATION/assets/167668420/4234e1bb-600b-401f-adbb-8b53b34c284f)









