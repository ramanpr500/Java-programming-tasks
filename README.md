import java.util.Scanner;
// Main class to run the library management system
public class SimpleLibraryManager {
    private final Library library;
    private final Scanner scanner;

    public SimpleLibraryManager() {
        library = new Library();
        scanner = new Scanner(System.in);
    }

    public void run() {
        while (true) {
            System.out.println("Library Management System");
            System.out.println("1. Add Item");
            System.out.println("2. Check Out Item");
            System.out.println("3. Return Item");
            System.out.println("4. Search by Title");
            System.out.println("5. Exit");

            int choice = scanner.nextInt();
            scanner.nextLine();  // Consume newline

            switch (choice) {
                case 1:
                    addItem();
                    break;
                case 2:
                    checkOutItem();
                    break;
                case 3:
                    returnItem();
                    break;
                case 4:
                    searchByTitle();
                    break;
                case 5:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }

    private void addItem() {
        System.out.println("Enter item title: ");
        String title = scanner.nextLine();
        Item item = new Item(title);
        library.addItem(item);
        System.out.println("Item added: " + item);
    }

    private void checkOutItem() {
        System.out.println("Enter title to check out: ");
        String title = scanner.nextLine();
        library.checkOutItem(title);
    }

    private void returnItem() {
        System.out.println("Enter title to return: ");
        String title = scanner.nextLine();
        library.returnItem(title);
    }

    private void searchByTitle() {
        System.out.println("Enter title to search: ");
        String title = scanner.nextLine();
        library.searchByTitle(title);
    }

    public static void main(String[] args) {
        SimpleLibraryManager manager = new SimpleLibraryManager ();
        manager.run();
    }
}
