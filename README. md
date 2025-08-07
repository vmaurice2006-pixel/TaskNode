class TaskNode {
    String title;
    TaskNode next;

    public TaskNode(String title) {
        this.title = title;
        this.next = null;
    }
}

class ToDoList {
    private TaskNode head;

    public ToDoList() {
        this.head = null;
    }

    public void addTask(String title) {
        TaskNode newTask = new TaskNode(title);
        if (head == null) {
            head = newTask;
            return;
        }
        TaskNode current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = newTask;
    }

    public void deleteTask(String title) {
        if (head == null) {
            System.out.println("Task list is empty.");
            return;
        }

        if (head.title.equals(title)) {
            head = head.next;
            System.out.println("Task deleted!");
            return;
        }

        TaskNode current = head;
        while (current.next != null && !current.next.title.equals(title)) {
            current = current.next;
        }

        if (current.next != null) {
            current.next = current.next.next;
            System.out.println("Task deleted!");
        } else {
            System.out.println("Task not found.");
        }
    }
    
    public void printTasks() {
        if (head == null) {
            System.out.println("No tasks in the list.");
            return;
        }
        System.out.println("Your Tasks:");
        TaskNode current = head;
        while (current != null) {
            System.out.println("- " + current.title);
            current = current.next;
        }
    }


    public boolean contains(String title) {
        TaskNode current = head;
        while (current != null) {
            if (current.title.equals(title)) {
                return true;
            }
            current = current.next;
        }
        return false;
    }
}

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        ToDoList myList = new ToDoList();
        Scanner scanner = new Scanner(System.in);
        int choice;

        do {
            System.out.println("1. Add task");
            System.out.println("2. Delete task");
            System.out.println("3. View all tasks");
            System.out.println("4. Search task");
            System.out.println("5. Exit");
            System.out.print("Enter choice: ");
            choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    System.out.print("Enter task title: ");
                    String title = scanner.nextLine();
                    myList.addTask(title);
                    System.out.println("Task added!");
                    break;
                case 2:
                    System.out.print("Enter task title to delete: ");
                    String titleToDelete = scanner.nextLine();
                    myList.deleteTask(titleToDelete);
                    break;
                case 3:
                    myList.printTasks();
                    break;
                case 4:
                    System.out.print("Enter task title to search: ");
                    String titleToSearch = scanner.nextLine();
                    if (myList.contains(titleToSearch)) {
                        System.out.println("Task found!");
                    } else {
                        System.out.println("Task not found.");
                    }
                    break;
                case 5:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
            System.out.println();
        } while (choice != 5);

        scanner.close();
    }
}
