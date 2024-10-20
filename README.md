import sys
import random
import enum


# Rock Papper Scissors
class RPS(enum.Enum):
    Rock = 1
    Papper = 2
    Scissors = 3


play_again = True

while play_again:

    player_c = input("Enter... \n1 For Rock \n2 For Papper \n3 For Scissors\n")
    player = int(player_c)

    if player < 1 or player > 3:
        sys.exit("You need to choose 1, 2, or 3")

    computer = random.choice([1, 2, 3])

    print(f"\nYou Choose {str(RPS(player)).replace('RPS.', '')}")
    print(f"Computer Choose {str(RPS(computer)).replace('RPS.', '')}")

    if (
        (player == 1 and computer == 3)
        or (player == 2 and computer == 1)
        or (player == 3 and computer == 2)
    ):
        print("You Win 👌")
    elif player == computer:
        print("Tie 😒")
    else:
        print("You Lose 🐍")

    play_again = input("\nplay again?\ny for yes\nf for no\n\n")
    if play_again.lower() == "y":
        continue
    elif play_again.lower() == "f":
        print("Thanks for playing")
        play_again = False


sys.exit("Bye 👋")
