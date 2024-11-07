# Slide and Catch Part 2

This game will be adapted off of the Slide and Catch Part 1 framework. The end goal for the project is to have the labels, sound, and scorekeeping working. Additionally, we will have an intro screen and game instructions. 

Milestones:
- __Milestone 1:__ Basic version of game active.
- __Milestone 2:__ Gameplay labels working
- __Milestone 3:__ State system 

# Milestone 1: Basic Version of the Game Active 

Upload SimpleGE to repository. Import SimpleGE and random. 

## Game Class

Define a new class called Game. Game takes simpleGE.Scene. Add the "FallScene.png" image. Background image is a picture taken while I was hiking on October 24, 2022 in Legion Park. 

Define a new method within Game class called process. Process takes self. Using simpleGE, check if the Wednesday image collides with the leaf. If true, then leaf should reset. If there's a collision, a sound should play. The sound was custom created by Marianne Adams using jfxr.frozenfractal.com. Sound will be initialized in game class. 

In game class, define new attribute self.leaves. Self.leaves is a list. Begin a for loop with a range of 10. For each iteration, append Leaf(self) to self.leaves. Update self.sprites to include self.leaves. Update process method in Game class. Add a for loop (for leaf in self.leaves). If Wednesday collides with a leaf, play a sound and reset.

## Wednesday Class

Create Wednesday class. Wednesday takes simpleGE.Sprite. Add the "Wednesday.png" image. Image is of my cat, and was taken December 2023. 

Set size to 75 x 75 and set position to 320 x 400. Define movement speed to be 5 pixels per frame.

Define a new process to check if the left or right arrow keys are pressed. If the left arrow key is pressed, the x value is the previous x value minus the movement speed. If the right arrow key is pressed, the x value is the previous x value added to the movement speed. Update Game class and add Wednesday to the Game schema. Add Wednesday to the list of sprites.

## Leaf Class

Create Leaf class. Leaf takes simpleGE.Sprite. Add the "FallLeaf.png" image. Image is from https://openclipart.org/detail/257622/leaf by NicholasJudy456. Set size to 30 x 30. Define minimum speed as 3 pixels per frame. Define maximum speed as 8 pixels per frame. 

Define new method called reset. Reset takes self. The x position of the leaf gets a random integer from 0 to the screen width. The y position of the leaf gets 0. The leaf speed (self.dy) gets a random integer between the minimum speed and the maximum speed. 

Add reset method to init().Define a new method called checkBounds. checkBounds takes self. If the bottom is greater than the screen height, reset(). Update Game class and add Leaf to Game schema. Add leaf to the list of sprites.

# Milestone 2: Gameplay Labels & Time-keeping Working

## Labels

Define a new class called LblScore that takes simpleGE.Label. LblScore will be the label with the game score. Label text should say "Score: 0" as the default. Center at (100, 30). 

Define new class called LblTime. LblTime takes simpleGE.Label. Label text should say "Time Left: 10" as the default. Center at (500, 30). 

Add lblScore and lblTime to self.sprites in Game class. 

## Timekeeping

Add timer to Game class using simpleGE.Timer(). Total time should be 10. Further define that if the time left is less than zero, final score gets self.score and stop the program. 

# Milestone 3: State System

## Instructions and Previous Score Label

Define new class called Instructions that takes simpleGE.scene. Define initializing method. Init method takes self and score. Set image to "FallScene.png". Response gets "Play" as default. 

Call simpleGE.MultiLabel and store in self.instructions. In self.instructions add text "You are Wednesday the Black Cat. Move with the left and right arrow keys and catch as many leaves as you can in only ten seconds. Good Luck!" Center instructions at (320, 240). Scale instructions to (500, 250). 

Add label with text "Last score: {previous score}". Label centered at (320, 400). 

Add self.instructions and self.lblScore to list of sprites. 

## Buttons

Buttons should do the respective action when clicked or the corresponding key is pressed. 

### Play Button

Initialize simpleGE.Button() and store in self.btnPlay. Play button should read "Play (up)". Center button at (100, 400). Add self.btnPlay to list of sprites. 

In Instructions class process method, define behavior of play button. If play button is clicked, response gets "Play" and Instructions scene stops. If up arrow key is pressed, response gets "Play" and instructions scene stops. 

### Quit Button

Initialize simpleGE.Button() and store in self.btnQuit. Quit button should read "Quit (down)". Center button at (550, 400). Add self.btnQuit to list of sprites.

In Instructions class process method, define behavior of quit. If quit is clicked, response gets "Quit" and instructions scene stops. If down key pressed, response gets "Quit" and instructions scene stops. 

## Gameplay in Main

Initialize a while loop with sentry variable "keepGoing". keepGoing gets true. Score starts at 0. Display instructions and start instructions. If instruction response is "Play", play the game. Score gets "game.score". Otherwise, keepGoing gets False. 




