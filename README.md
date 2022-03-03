# CPS101
## Chapter 6
Create a program to read in a list of people's names including "You" (ending with -1), adding each person to the peopleInQueue queue. Then, remove each person from the queue until "You" is at the head of the queue. 

```java
import java.util.Scanner;
import java.util.LinkedList;
import java.util.Queue;

public class TicketingService {
    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        String personName = "";
        int counter = 1;
        int youPosition = 0;
        Queue<String> peopleInQueue = new LinkedList<String>();

        personName = scnr.nextLine();
        while (!personName.equals("-1")) {
            // TODO: Add personName to peopleInQueue and
            // determine position of "You" (youPosition)

            peopleInQueue.add(personName);

            personName = scnr.nextLine();
            counter++;

            if(personName.equals("You")||personName.equals("you")){
                youPosition = counter;
            }

        }
        System.out.println("Welcome to the ticketing service... ");
        System.out.println("You are number " + youPosition + " in the queue.");
        // TODO: In a loop, remove head person from peopleInQueue,
        // output their name and that they have purchased a ticket,
        // then output your position in the queue. When you are at
        // the head, output that you can purchase your ticket.

        for (int i = 0; i < peopleInQueue.size(); i++) {
            while (youPosition >= 1) {
                if (youPosition == 1) {
                    System.out.println("You can now purchase your ticket!");
                    personName = peopleInQueue.remove();
                    --youPosition;
                } else {
                    personName = peopleInQueue.remove();
                    --youPosition;
                    System.out.println(personName + " has purchased a ticket.");
                    System.out.println("You are now number " + youPosition);
                }
            }

            scnr.close();
        }
    }
}```
