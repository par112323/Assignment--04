this.data// Node class to represent a node in the singly linked list
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

// LinkedList class
class LinkedList {
    Node head;

    // Method to insert a new node at the end
    public void insert(int data) {
        Node newNode = new Node(data);

        if (head == null) {
            head = newNode;
            return;
        }

        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Method to perform linear search
    public int linearSearch(int key) {
        Node current = head;
        int position = 0;

        while (current != null) {
            if (current.data == key) {
                return position; // Return position if key found
            }
            current = current.next;
            position++;
        }

        return -1; // Return -1 if key not found
    }

    // Method to display the linked list
    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("null");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();

        // Insert some elements
        list.insert(10);
        list.insert(20);
        list.insert(30);
        list.insert(40);
        list.insert(50);

        System.out.println("Linked List:");
        list.display();

        // Search for an element
        java.util.Scanner sc = new java.util.Scanner(System.in);
        System.out.print("Enter the value to search: ");
        int key = sc.nextInt();

        int result = list.linearSearch(key);

        if (result != -1) {
            System.out.println("Element " + key + " found at position " + result);
        } else {
            System.out.println("Element " + key + " not found in the list.");
        }

        sc.close();
    }
}

