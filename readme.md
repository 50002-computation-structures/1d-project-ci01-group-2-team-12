## **Dodger**

**Number of players:** 1 or 2 players

**Procedure:** 
In single-player mode, one player controls both movement buttons, requiring quick reflexes and coordination. (Players can also collaborate by communicating and working together to control the character.) The character must continuously dodge falling objects to stay in the game.

In multiplayer mode, two players each control a character and must work together to survive. Each player is responsible for controlling just one movement button, which only allows movement in one direction, with the left button allowing the left character to always move left (the character will move to rightmost position after moving from the leftmost position), and the right button allowing the right character to always move right (the character will move to leftmost position after moving from the rightmost position), making teamwork crucial. (Alternatively, players can choose to play alone by controlling both characters.) Obstacles will either spawn with one gap or two gaps, and both characters must pass through all available gaps (if two gaps spawn, the characters must each cover one gap; if one gap spawn, both characters must overlap at the gap). Both characters will still need to dodge all obstacles.

**Winning Condition:** The game is intended to be attaining highest score till collision with obstacle (lose), but a win condition is currently set at 9999 score where all player LEDs will light up.

**Losing Condition:** The game ends when the player collides with the obstacle (both single-player and multiplayer modes) or when both players fail to spread out to all possible dodge positions (only in multiplayer mode)

### Controls

- Left `io_button[3]` to shift the player left (single-player mode) or shift the left player left (multiplayer mode)
- Right `io_button[2]` to shift the player right (single-player mode) or shift the right player right (multiplayer mode)
- Special Button `io_dip[0][0]` (due to faulty io_button pinout) to provide special power mode lasting for 3 obstacles where obstacles are slowed down after achieving every multiple of 8 score
- Mode Change Button `io_dip[0][1]` (due to faulty io_button pinout) to allow for mode change to double player mode at any point of single player mode

### Display

- Score: `io_select[4] and io_segment[8]`
- Row 1 Obstacle: `io_led[0][0], io_led[0][2], io_led[0][4], io_led[0][6], io_led[1][0], io_led[1][2], io_led[1][4]`
- Row 2 Obstacles: `io_led[0][1], io_led[0][3], io_led[0][5], io_led[0][7], io_led[1][1], io_led[1][3], io_led[1][5]`
- Row 3 Obstacles: led[7:1]
- Player/Players: `io_led[1][6], io_led[2][0], io_led[2][2], io_led[2][4], io_led[2][6], io_led[1][7], io_led[2][1], io_led[2][3],io_led[2][5]`
- Special Mode Indicator: led[0]
- If Player/Players wins, all Player/Players leds will be illuminated
- If Player/Players lose, all Obstacles leds will be illuminated
