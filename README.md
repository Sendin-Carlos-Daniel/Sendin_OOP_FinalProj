### **Water Conservation Challenge 101**

**Overview**

_This project is a simple console-based application that helps users track their daily water usage and provides tips on how to conserve water. It incorporates core object-oriented programming concepts such as Abstraction, Encapsulation, Inheritance, and Polymorphism to create a structured and interactive user experience._

**Features**

- `Set a daily water usage goal.`

- `Log daily water usage and keep track of total water consumption.`

- `View progress on how close the user is to meeting their daily water goal.`

- `Receive water-saving tips to help reduce consumption.`

- `Exit the application with a thank you message.`

**Key Concepts Used**

- `Abstraction:` 

> An abstract class ConservationChallenge101 defines the structure and behavior for water conservation challenges. It contains abstract methods that must be implemented by subclasses.

- `Encapsulation`: 

> The program uses private fields for water usage data and provides controlled access to them through getter and setter methods.

- `Inheritance`: 

> The WaterConservation class extends the abstract ConservationChallenge101 class and implements the abstract displayTips method.

- `Polymorphism`: 

> The WaterConservation class provides a specific implementation of the displayTips method, overriding the abstract method from the parent class.

**Code Structure**

1. _ConservationChallenge101 (Abstract Class)_

_Attributes:_

- ` dailyGoal:` The daily goal for water usage in liters (private).

- `totalUsage:` The total water used, starting at zero (private).

_Methods:_

- `getDailyGoal():` Returns the current daily goal.

- `setDailyGoal(double dailyGoal):` Sets a new daily goal.

- `getTotalUsage():` Returns the total water usage.

- `addUsage(double usage):` Adds water usage to the total.

- `displayTips()`: An abstract method to display water-saving tips (implemented in subclasses).

- `showProgress():` Displays the user's progress compared to their daily goal.

2. _WaterConservation (Subclass)_

_Methods:_

`displayTips():` Implements the abstract method from ConservationChallenge101 to provide water-saving tips specific to the WaterConservation challenge.

3. _ConversationChallenge101 (Main Class)_
 
This is the main class where the program runs. It uses a Scanner object to interact with the user and presents a menu to:

- Set a new daily water usage goal.

- Log the water usage for the day.

- View the progress report (how close they are to their goal).

- Get water-saving tips.

- Exit the program.

**Usage**

1. When the program starts, it will ask you to choose from a list of options:

- Set your daily water usage goal.

- Log today's water usage.
 
- View total water usage and progress.

- Get water-saving tips.

- Exit the program.

2. After you select an option, follow the prompts to interact with the application.

**Example** Interaction

![Image](https://github.com/user-attachments/assets/eddb487c-317a-4887-881f-e6fa693d42ca)
![Image](https://github.com/user-attachments/assets/009af27d-f034-4e7e-bdf8-782d3450771c)

**Code** 

```
import java.util.Scanner;

// Abstraction: Abstract class defines the structure for all conservation challenges
abstract class ConservationChallenge101 {
    private double dailyGoal; // Encapsulation: Private field
    private double totalUsage; // Encapsulation: Private field

    // Constructor
    public ConservationChallenge101(double dailyGoal) {
        this.dailyGoal = dailyGoal;
        this.totalUsage = 0;
    }

    // Getters and Setters for encapsulation
    public double getDailyGoal() {
        return dailyGoal;
    }

    public void setDailyGoal(double dailyGoal) {
        this.dailyGoal = dailyGoal;
    }

    public double getTotalUsage() {
        return totalUsage;
    }

    public void addUsage(double usage) {
        this.totalUsage += usage;
    }

    // Abstract method for displaying tips
    public abstract void displayTips();

    // Method to display progress
    public void showProgress() {
        System.out.println("\n=== Progress Report ===");
        System.out.println("Total water used: " + totalUsage + " liters");
        if (totalUsage <= dailyGoal) {
            System.out.println("Great job! You are within your daily goal of " + dailyGoal + " liters.");
        } else {
            System.out.println("You exceeded your daily goal of " + dailyGoal + " liters. Let's try to conserve more tomorrow!");
        }
        System.out.println();
    }
}

// Inheritance: Subclass for water conservation
class WaterConservation extends ConservationChallenge101 {
    // Constructor
    public WaterConservation(double dailyGoal) {
        super(dailyGoal);
    }

    // Polymorphism: Implementing abstract method
    @Override
    public void displayTips() {
        System.out.println("\n=== Water-Saving Tips ===");
        System.out.println("1. Turn off the tap while brushing your teeth.");
        System.out.println("2. Fix leaks to prevent water wastage.");
        System.out.println("3. Use a bucket instead of a hose for washing cars.");
        System.out.println("4. Install water-efficient fixtures.");
        System.out.println("5. Collect rainwater for non-potable uses.\n");
    }
}

public class ConservationCh101 {
    public static void main(String[] args) {
        Scanner cd = new Scanner(System.in);

        // Initialize the conservation challenge with a default goal
        WaterConservation challenge = new WaterConservation(100);

        System.out.println("=== Water Conservation Challenge ===");
        System.out.println("Track your daily water usage and learn tips to save water.\n");

        boolean exit = false;

        while (!exit) {
            System.out.println("Choose an option:");
            System.out.println("1. Set your daily water usage goal");
            System.out.println("2. Log today's water usage");
            System.out.println("3. View total water usage and goal progress");
            System.out.println("4. Get water-saving tips");
            System.out.println("5. Exit");
            System.out.print("Enter your choice: ");

            int choice = cd.nextInt();
            cd.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    System.out.print("\nEnter your new daily water usage goal (in liters): ");
                    double newGoal = cd.nextDouble();
                    challenge.setDailyGoal(newGoal);
                    System.out.println("Your daily goal has been set to " + challenge.getDailyGoal() + " liters.\n");
                    break;

                case 2:
                    System.out.print("\nEnter the amount of water you used today (in liters): ");
                    double waterUsed = cd.nextDouble();
                    challenge.addUsage(waterUsed);
                    System.out.println("You logged " + waterUsed + " liters. Keep it up!\n");
                    break;

                case 3:
                    challenge.showProgress();
                    break;

                case 4:
                    challenge.displayTips();
                    break;

                case 5:
                    System.out.println("\nThank you for participating in the Water Conservation Challenge. Keep saving water!");
                    exit = true;
                    break;

                default:
                    System.out.println("\nInvalid choice. Please try again.\n");
                    break;
            }
        }

        cd.close();
    }
}


