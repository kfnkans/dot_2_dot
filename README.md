# Dot 2 Dot
*Overview*: This game is similar to connect 4. In connect 4, the first person to connect 4 circles diagonally wins. But, in this game,  a player has to do more than connect 4 circles (referred to dots) to win the game entirely. A player has to connect two dots to each other with a line on each turn. In addition,  a player is trying to create a square (4 lines) while trying to preventing their opponent from creating a square. 

## Rules
- The objective of the game is to get more squares than your opponent while not putting themselves in a position to lose as few of squares as possible.
 - The player can lose a square if they are the third line in a square of 4 dots. If the player gets a square, the player’s initial or chosen color is either inside the box (initial) or fills the box (color).   
- The smallest dimension is 8 (across) by 8 (down).
- In the event of a tie, the down dimension stays the same and while the across dimension is halfed. So for the 8 by 8, it will be 4 by 8. Always round up.
    - Continue the game until a user gets a square. So, it’s a sudden death game.
- A user doesn’t lose entirely if 
    - They lose a square. 
- If a user wins a square,  
    - They get another turn to draw a line.  
- - - 
### Winning Entirely
- The amount of squares they have created exceeds the number the of dots it is possible to connect to.  
- If they have more squares than their opponent at the end of the game. 
  The end of the game is defined by no more dots to connect lines to.
- It is not possible for the other user to win due to the aforementioned reasons.

# **Game Design**
- This game will be using html, css, and javascript. 
### **Going First** 🥇
- *Player A* is prompted about playing  the computer or not. 
 - Avoid making it an alert prompt. Make the indication an onscreen one. 
 - Flip a coin 🪙 to decide which user goes first in every game.   
  - Prompt *Player A* to guess how the coin will land.
   - If *Player A* guesses correctly, then it’s their turn. 
   - Otherwise, it's *Player B* goes first.

## Dot Connecting
-A *Player [A|B]* can connect two dots that are adjacent to each other, vertically or horizontally with a line (representing the color of the user chose is drawn to the center of each circle).   
-The “O”/dot at the upper-most left corner is coordinate (0, 0), the one directly to the right is (0, 1), subsequent ones to the right are (0, n+1)  
-Going directly down from the (0, 0) coordinate is the (1, 0), subsequent ones are (n+1, 0) 
    OOOOOOOOOOOO
    OOOOOOOOOOOO
    OOOOOOOOOOOO
    OOOOOOOOOOOO
    OOOOOOOOOOOO
### Drawing circles in HTML 
-Separate based on logic on which it functions.
-In html, represent the dots as svg circles. Let’s start with 16 by 16 (adjust to other dimensions later on). 
-Divide the clickable portion of each dots into 2 intersecting lines (left to right & top to bottom)?
-How do I make sure that these dots are laid out in a requested dimension and so on? 
-The exact middle* of any of these shapes is where a line is drawn and connects to.
-As long as the circle doesn’t meet any of these conditions  
    - Isn’t in the outermost layer [find the pattern for it] 
    - Isnt already connected in the same direction. How do we enforce this impermittable acton ?  
    - if user clicks on target circles then print a small dialog box, display a dialog box outside of the game screen.  
-A user should be able to highlight the two circles they want to connect to draw a line. Or they can click on the part of the circle they want to and draw a line in a direction they want to connect to.  Make sure that there is flexibility encoded to allow the dots to be visible across the different dimensions.  

**Selectable elements (Dots)**
- Each dot that a user clicks on has to obey a rule of only connecting to a directly adjacent dot.  
- A user begins by selecting a starting point and an adjacent one. 
  - If the user attempts to select a position that isn’t possible, there is an *indication at the bottom right of the screen*. 


### Timer 
- Up to 10 seconds for each player TO SELECT before it automates to the best selection.
(Ensure that the automated selectionabides by the rules)  
### Ticker  
- Functions as a scoreboard. 
 -Place the scoreboard at the bottom right of the screen indicating the 2 users, 
  and a number beneath representing the squares that they have. 
 - Modify and update the ticker so that when a player gets a square the 
   corresponding part of the scoreboard increments.

### Window   
- Using css, make it visible and large enough on different window dimensions.  
- Make sure that these circles don’t stack on top of one another when the window size shrinks. 

### Create a test to ensure its functionality.  
- Drawing a line between the two dots? 
  - Making sure that it automatically connects to the adjacent circle?   
  - Recognizing if a user is the last one to draw a line to complete a square? 
- Recognizing when the game is over?  
- Alternate between a player (AI | non AI) or another user?    
- Giving each user/square winner an additional turn? 
- AI Algorithm that follows the rules
### Stretch Tasks  
- Difficulty Settings
 - Automated algorithm that follows the rules and adjusts based on the settings (easy, medium, difficult). Display the code it follows and break it down.