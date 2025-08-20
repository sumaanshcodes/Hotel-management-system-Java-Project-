# Hotel-management-system-Java-Project-
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Hotel hotel = new Hotel();
        Scanner sc = new Scanner(System.in);
        int choice;

        do {
            System.out.println("\n--- Hotel Reservation System ---");
            System.out.println("1. View Available Rooms");
            System.out.println("2. Book a Room");
            System.out.println("3. Cancel Booking");
            System.out.println("4. View All Bookings");
            System.out.println("0. Exit");
            System.out.print("Enter choice: ");
            choice = sc.nextInt();
            sc.nextLine(); // consume newline

            switch (choice) {
                case 1 -> hotel.showAvailableRooms();
                case 2 -> {
                    System.out.print("Enter your name: ");
                    String name = sc.nextLine();
                    System.out.print("Enter room category (Standard/Deluxe/Suite): ");
                    String category = sc.nextLine();
                    hotel.bookRoom(name, category);
                }
                case 3 -> {
                    System.out.print("Enter room number to cancel: ");
                    int roomNum = sc.nextInt();
                    hotel.cancelBooking(roomNum);
                }
                case 4 -> hotel.viewBookings();
                case 0 -> System.out.println("Goodbye!");
                default -> System.out.println("Invalid choice.");
            }
        } while (choice != 0);
    }
}
