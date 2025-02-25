
import java.util.Random;
import java.util.Scanner;

// Game class: Encapsulates the logic
class NumberGuessingGame {
    private int targetNumber;  // The number to guess
    private int attempts;      // Number of attempts
    private final int lowerBound, upperBound; // Range for the number
    private final Scanner scanner;

    // Constructor to initialize the game
    public NumberGuessingGame(int lowerBound, int upperBound) {
        this.lowerBound = lowerBound;
        this.upperBound = upperBound;
        this.scanner = new Scanner(System.in);
        startNewGame(); // Automatically start the game
    }

    // Method to generate a new number and reset attempts
    public void startNewGame() {
        Random random = new Random();
        this.targetNumber = random.nextInt(upperBound - lowerBound + 1) + lowerBound;
        this.attempts = 0;
        System.out.println("\n🎲 New game started! Guess a number between " + lowerBound + " and " + upperBound);
    }

    // Method to handle user guesses
    public void playGame() {
        int guess;
        while (true) {
            System.out.print("Enter your guess: ");
            guess = scanner.nextInt();
            attempts++;

            if (guess < targetNumber) {
                System.out.println("📉 Too low! Try again.");
            } else if (guess > targetNumber) {
                System.out.println("📈 Too high! Try again.");
            } else {
                System.out.println("\n🎉 Correct! You guessed the number " + targetNumber + " in " + attempts + " attempts.");
                break;
            }
        }
    }

    // Method to check if the player wants to play again
    public boolean playAgain() {
        System.out.print("\n🔄 Do you want to play again? (Y/N): ");
        char response = scanner.next().charAt(0);
        return response == 'Y' || response == 'y';
    }

    // Method to close the scanner
    public void closeGame() {
        scanner.close();
        System.out.println("👋 Thanks for playing! See you next time.");
    }
}

// Main class to run the game
public class GameRunner {
    public static void main(String[] args) {
        NumberGuessingGame game = new NumberGuessingGame(1, 100);

        do {
            game.playGame();
        } while (game.playAgain());

        game.closeGame();
    }
}
