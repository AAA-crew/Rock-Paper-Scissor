# Rock Papper Scissors







import sys
import random
import enum


def play_rps():
    class RPS(enum.Enum):
        Rock = 1
        Papper = 2
        Scissors = 3

    player_c = input("Enter... \n1 For Rock \n2 For Papper \n3 For Scissors\n")

    if player_c not in ["1", "2", "3"]:
        print("You need to choose 1, 2, or 3")
        return play_rps

    player = int(player_c)

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

    print("play again?")

    while True:
        play_again = input("\ny for yes\nf for no\n")

        if play_again.lower() not in ["y", "f"]:
            continue
        else:
            break

    if play_again.lower() == "y":
        return play_rps()

    elif play_again.lower() == "f":
        print("Thanks for playing")
        print("Bye👋👋")
        sys.exit("Bye 👋")


play_rps()
