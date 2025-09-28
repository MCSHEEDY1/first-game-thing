
def get_user_choice():
    """Prompt the user to choose Rock, Paper, or Scissors."""
    choices = ["rock", "paper", "scissors"]
    while True:
        user_input = input("Enter Rock, Paper, or Scissors: ").strip().lower()
        if user_input in choices:
            return user_input
        print("Invalid choice. Please try again.")


def get_computer_choice():
    """Randomly choose Rock, Paper, or Scissors for the computer."""
    return random.choice(["rock", "paper", "scissors"])


def determine_winner(user, computer):
    """Determine the winner between user and computer."""
    if user == computer:
        return "It's a tie!"

    winning_combos = {
        "rock": "scissors",  # Rock beats Scissors
        "paper": "rock",  # Paper beats Rock
        "scissors": "paper"  # Scissors beats Paper
    }

    if winning_combos[user] == computer:
        return "You win!"
    else:
        return "i won ur a losser!"


def play_game():
    """Play one round of Rock-Paper-Scissors."""
    print("\n--- Rock, Paper, Scissors ---")
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()

    print(f"\nYou chose: {user_choice.capitalize()}")
    print(f"Computer chose: {computer_choice.capitalize()}")

    result = determine_winner(user_choice, computer_choice)
    print(f"Result: {result}")


def main():
    """Run the game loop allowing multiple rounds."""
    while True:
        play_game()
        play_again = input("\nPlay again? (y/n): ").strip().lower()
        if play_again != "y":
            print("Thanks for playing! Goodbye!")
            break


if __name__ == "__main__":
    main()
