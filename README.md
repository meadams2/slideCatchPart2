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

# Milestone 2: Gameplay Labels Working

Define a new class called Labels. Labels takes simpleGE.Label. 


