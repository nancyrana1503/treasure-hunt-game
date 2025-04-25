# 🗺️ Treasure Hunt Game
**Gameplay Logic**

In this project, **Treasure Hunt Game** we will be implementing the full gameplay experience using structures in C. Players navigate a hidden path, seeking treasure while avoiding bombs, with stats updated in real-time after each move.

---

## 🎮 Features

- Interactive gameplay on a hidden path
- Player lives, treasure count, and move tracking
- Real-time game board updates with position indicators
- Symbolic game elements:
  - `!` = Bomb 💣
  - `$` = Treasure 💎
  - `&` = Bomb + Treasure (Life Insurance 💼)
  - `.` = Nothing found
- Game ends when player runs out of lives or moves
---

## 🧠 Concepts Practiced

- Structs (`PlayerInfo`, `GameInfo`) to group related data
- Array-based history tracking
- Conditional logic to simulate game rules
- Looping for move validation and board updates
- Symbol mapping and formatted board display

---

## 🎯 Game Objective

Explore a hidden path filled with treasure and danger. Each move may result in:

- 💥 A bomb (loses 1 life)
- 💎 A treasure (gains 1 treasure point)
- 💼 A life-insured treasure (bomb + treasure)
- 😶 Nothing

Try to **collect as much treasure as possible** before your **lives or moves run out**!

---

## 🧪 Sample Output (Trimmed)

```
================================ 
         Treasure Hunt! 
================================ 

PLAYER Configuration 
-------------------- 
Enter a single character to represent the player: V
Set the number of lives: 0 
     Must be between 1 and 10! 
Set the number of lives: 11 
     Must be between 1 and 10! 
Set the number of lives: 3 
Player configuration set-up is complete 

GAME Configuration 
------------------ 
Set the path length (a multiple of 5 between 10-70): 9
     Must be a multiple of 5 and between 10-70!!! 
Set the path length (a multiple of 5 between 10-70): 41 
     Must be a multiple of 5 and between 10-70!!! 
Set the path length (a multiple of 5 between 10-70): 19 
     Must be a multiple of 5 and between 10-70!!! 
Set the path length (a multiple of 5 between 10-70): 20 
Set the limit for number of moves allowed: 2 
    Value must be between 3 and 15 
Set the limit for number of moves allowed: 16 
    Value must be between 3 and 15 
Set the limit for number of moves allowed: 10 

BOMB Placement 
--------------
Enter the bomb positions in sets of 5 where a value of 
1=BOMB, and 0=NO BOMB. Space-delimit your input. 
(Example: 1 0 0 1 1) NOTE: there are 20 to set! 
   Positions [ 1- 5]: 1 0 0 1 1 
   Positions [ 6-10]: 1 1 0 0 0 
   Positions [11-15]: 0 0 1 1 1
   Positions [16-20]: 1 0 0 0 0 
BOMB placement set 

TREASURE Placement 
------------------ 
Enter the treasure placements in sets of 5 where a value 
of 1=TREASURE, and 0=NO TREASURE. Space-delimit your input. 
(Example: 1 0 0 1 1) NOTE: there are 20 to set! 
   Positions [ 1- 5]: 0 1 1 0 0 
   Positions [ 6-10]: 0 0 0 0 0 
   Positions [11-15]: 1 1 0 0 1 
   Positions [16-20]: 0 1 1 1 1 
TREASURE placement set 

GAME configuration set-up is complete... 

------------------------------------ 
TREASURE HUNT Configuration Settings 
------------------------------------ 
Player: 
   Symbol     : V 
   Lives      : 3 
   Treasure   : [ready for gameplay] 
   History    : [ready for gameplay] 

Game: 
   Path Length: 20 
   Bombs      : 10011110000011110000 
   Treasure   : 01100000001100101111 

==================================== 
~ Get ready to play TREASURE HUNT! ~ 
==================================== 

  -------------------- 
  |||||||||1|||||||||2 
  12345678901234567890 
+---------------------------------------------------+ 
  Lives:  3  | Treasures: 0  |  Moves Remaining:  10 
+---------------------------------------------------+ 
Next Move [1-20]: 0 
  Out of Range!!! 
Next Move [1-20]: 21 
  Out of Range!!! 
Next Move [1-20]: 8 

===============> [.] ...Nothing found here... [.]
         
         V 
  -------.------------ 
  |||||||||1|||||||||2 
  12345678901234567890 
+---------------------------------------------------+ 
  Lives: 3 | Treasures: 0 | Moves Remaining: 9 
+---------------------------------------------------+ 
Next Move [1-20]: 10 

===============> [.] ...Nothing found here... [.] 

          V
  -------.-.---------- 
  |||||||||1|||||||||2 
  12345678901234567890 
+---------------------------------------------------+ 
  Lives: 3 | Treasures: 0 | Moves Remaining: 8 
+---------------------------------------------------+ 
Next Move [1-20]: 1 

===============> [!] !!! BOOOOOM !!! [!] 
  V 
  !------.-.----------
  |||||||||1|||||||||2
  12345678901234567890 
+---------------------------------------------------+ 
  Lives: 2 | Treasures: 0 | Moves Remaining: 7 
+---------------------------------------------------+ 
Next Move [1-20]: 15 

===============> [&] !!! BOOOOOM !!! [&] 
===============> [&] $$$ Life Insurance Payout!!! [&] 

                V
  !------.-.----&----- 
  |||||||||1|||||||||2
  12345678901234567890 
+---------------------------------------------------+ 
  Lives: 1 | Treasures: 1 | Moves Remaining: 6 
+---------------------------------------------------+ 
Next Move [1-20]: 20 

===============> [$] $$$ Found Treasure! $$$ [$] 

                     V
  !------.-.----&----$ 
  |||||||||1|||||||||2
  12345678901234567890 
+---------------------------------------------------+ 
Lives: 1 | Treasures: 2 | Moves Remaining: 5 
+---------------------------------------------------+ 
Next Move [1-20]: 8

===============> Dope! You've been here before! 

          V 
  !------.-.----&----$ 
  |||||||||1|||||||||2 
  12345678901234567890 
+---------------------------------------------------+ 
Lives: 1 | Treasures: 2 | Moves Remaining: 5 
+---------------------------------------------------+ 
Next Move [1-20]: 3 

===============> [$] $$$ Found Treasure! $$$ [$] 

    V 
  !-$----.-.----&----$ 
  |||||||||1|||||||||2 
  12345678901234567890 
+---------------------------------------------------+ 
Lives: 1 | Treasures: 3 | Moves Remaining: 4 
+---------------------------------------------------+ 
Next Move [1-20]: 5 

===============> [!] !!! BOOOOOM !!! [!] 

No more LIVES remaining! 

      V 
  !-$-!--.-.----&----$ 
  |||||||||1|||||||||2 
  12345678901234567890 
+---------------------------------------------------+ 
Lives: 0 | Treasures: 3 | Moves Remaining: 3 
+---------------------------------------------------+ 

################## 
# Game over! # 
################## 

You should play again and try to beat your score!
```

---

## 📌 Notes

- Player's move history prevents repeated entries
- All positions and states are dynamically calculated based on initial game settings
- The board updates after every move and includes position rulers for easy reference

---
