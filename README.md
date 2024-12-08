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
