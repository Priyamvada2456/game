from getpass import getpass

def check_winner(p1, p2):
    if p1 == p2:
        return "tie"
    elif (p1 == "snake" and p2 == "water") or \
         (p1 == "water" and p2 == "gun") or \
         (p1 == "gun" and p2 == "snake"):
        return "player1"
    else:
        return "player2"

choices = ["snake", "water", "gun"]
score1 = 0
score2 = 0
rounds = 0

print("🎮 Best of 3: Snake, Water, Gun")
print("Choices: snake 🐍, water 💧, gun 🔫")

while rounds < 3 and score1 < 2 and score2 < 2:
    print(f"\n--- Round {rounds + 1} ---")
    p1 = getpass("Player 1, enter your choice (hidden): ").lower()
    p2 = getpass("Player 2, enter your choice (hidden): ").lower()

    if p1 not in choices or p2 not in choices:
        print("Invalid input! Please choose only from: snake, water, or gun.")
        continue

    result = check_winner(p1, p2)
    
    if result == "tie":
        print("It's a tie!")
    elif result == "player1":
        score1 += 1
        print("Player 1 wins this round!")
    else:
        score2 += 1
        print("Player 2 wins this round!")

    print(f"Score → Player 1: {score1} | Player 2: {score2}")
    rounds += 1

print("\n🏁 Final Result:")
if score1 > score2:
    print("🎉 Player 1 wins the game!")
elif score2 > score1:
    print("🎉 Player 2 wins the game!")
else:
    print("It's a draw!")
# game
It's a snake water  and gun game
