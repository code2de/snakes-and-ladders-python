import random
snakes = {16: 6, 47: 26, 49: 11, 56: 53, 62: 19, 64: 60, 87: 24, 93: 73, 95: 75, 98: 78}
ladders = {1: 38, 4: 14, 9: 31, 21: 42, 28: 84, 36: 44, 51: 67, 71: 91, 80: 100}
player_positions = [0, 0]

def roll_dice():
    return random.randint(1, 6)

def check_snake_or_ladder(position):
    if position in snakes:
        print(f"Oops! You got attacked by a snake at {position}. Move down to {snakes[position]}")
        return snakes[position]
    elif position in ladders:
        print(f"Yay! You climbed a ladder at {position}. Move up to {ladders[position]}")
        return ladders[position]
    return position

def play_game():
    player_turn = 0
    while True:
        print(f"\nPlayer {player_turn + 1}'s turn")
        input("Press Enter to roll the dice...")
        dice_value = roll_dice()
        print(f"Player {player_turn + 1} rolled a {dice_value}")
        player_positions[player_turn] += dice_value
        if player_positions[player_turn] > 100:
            player_positions[player_turn] -= dice_value
            print("You can't move, you need to land exactly on 100!")
        else:
            player_positions[player_turn] = check_snake_or_ladder(player_positions[player_turn])
        
        print(f"Player {player_turn + 1} is now on square {player_positions[player_turn]}")
        if player_positions[player_turn] == 100:
            print(f"\nCongratulations! Player {player_turn + 1} wins the game!")
            break
        player_turn = (player_turn + 1) % 2

if __name__ == "__main__":
    print("Welcome to Snakes and Ladders!")
    play_game()
