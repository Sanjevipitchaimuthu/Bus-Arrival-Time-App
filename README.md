# Bus-Arrival-Time-App
import java.util.*;

class Bus {
    int busNumber;
    String source, destination;
    String arrivalTime;

    public Bus(int busNumber, String source, String destination, String arrivalTime) {
        this.busNumber = busNumber;
        this.source = source;
        this.destination = destination;
        this.arrivalTime = arrivalTime;
    }

    public void displayBusInfo() {
        System.out.println("Bus Number: " + busNumber + ", Source: " + source + ", Destination: " + destination + ", Arrival Time: " + arrivalTime);
    }
}

public class BusArrivalTimeApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        List<Bus> buses = new ArrayList<>();
        buses.add(new Bus(101, "City A", "City B", "10:30 AM"));
        buses.add(new Bus(102, "City C", "City D", "2:15 PM"));

        System.out.println("Available Buses:");
 for (Bus bus : buses) {
            bus.displayBusInfo();
        }

        System.out.println("Enter Bus Number to check arrival time: ");
        int busNumber = scanner.nextInt();

        boolean found = false;
        for (Bus bus : buses) {
            if (bus.busNumber == busNumber) {
                System.out.println("Arrival Time for Bus " + busNumber + ": " + bus.arrivalTime);
                found = true;
                break;
            }
        }

        if (!found) {
            System.out.println("Bus not found.");
        }
        scanner.close();
    }
}
