# two
import java.util.Scanner;

public class RaceGame {      
    public static void main(String[] args) {      
        Scanner input = new Scanner(System.in);      
        int playerIndex = 0;      
        int[][] cars = new int[2][10];

        while (true) {      
            System.out.println("Select player 1 or player 2 to start the race:");      
            System.out.print("1. Player 1");      
            System.out.print("2. Player 2");      
            int playerIndex = input.nextInt();

            if (playerIndex == 1) {      
                playerIndex = 0;      
            } else if (playerIndex == 2) {      
                playerIndex = 1;      
            }

            System.out.println("Race started!");

            while (true) {      
                System.out.println("Turn " + (playerIndex + 1));

                // Ask player 1 and player 2 to select their 赛车位置      
                int carIndex1 = input.nextInt();      
                int carIndex2 = input.nextInt();

                // Check if carIndex1 and carIndex2 are valid      
                if (cars[playerIndex][carIndex1] != 0 || cars[playerIndex][carIndex2] != 0) {      
                    System.out.println("Car is already moving. Please select another car.");      
                    continue;      
                }

                // Check if car is moving      
                if (cars[playerIndex][carIndex1] == 0 || cars[playerIndex][carIndex2] == 0) {      
                    System.out.println("Car is moving. Please select another car.");      
                    continue;      
                }

                // Check if car is destroyed      
                if (cars[playerIndex][carIndex1] == 1 || cars[playerIndex][carIndex2] == 1) {      
                    System.out.println("Car has been destroyed. Please select another car.");      
                    continue;      
                }

                // Ask player 1 and player 2 to select their 赛车加速方向      
                int driveDirection1 = input.nextInt();      
                int driveDirection2 = input.nextInt();

                // Check if driveDirection1 and driveDirection2 are valid      
                if (driveDirection1 < 0 || driveDirection1 > 2 || driveDirection2 < 0 || driveDirection2 > 2) {      
                    System.out.println("Drive Direction is not valid. Please select another drive Direction.");      
                    continue;      
                }

                // Check if player 1 and player 2 have selected same drive Dir  
