# Pong Game Assembly 8086
https://user-images.githubusercontent.com/100795596/210141791-d5f75251-3a1c-47f9-b044-6dda24e1a94d.mp4

### [To Watch the full video]()
## Playing The Game:
- The game consists of two levels, which are slow and fast, according to the user’s choice. 
- Once the score for one of them reaches 5, the game ends, and the user often loses because the system is programmed in a smart way, and therefore it is difficult to     lose, but not impossible.
- Controlling the paddle --->>> Press 'w' or 'W' to move UP and Press 's' or 'S' to move DOWN.
- The ball will bounce back after colliding with any paddle or the top and bottom walls of the screen.
- If the ball strikes the left or right wall of the screen it will start from the center of the screen.
- It can be played by only one person with the computer.

## Key Sounds:
- When the use press keys ,a sound with 1000 HZ will be produced to simulate the game experience.
- Also when the user miss the ball, a sound with 6000 Hz will be produced to alert the user.

## Quitting The Game:
- Press 'Esc' key to exit the game.

# Important functions and Interrupts used in the game:
## Clearing the screen:
- Interrupt used - INT 10H.
- INT 10h and AH = 00h - Set Video Mode.
- AL = 13h 320x200 256 color graphics (MCGA,VGA) - THIS IS THE VIDEO MODE USED.

## Drawing A Pixel:
- Interrupt used - INT 10H.
- AH = 0Ch - set the configuration to writing the pixel.
- AL = 0Fh - choose white as color of the pixel.

## Checking Input From Keyboard:
- Interrupt used INT 16H - Keyboard BIOS Services
- AH = 01h - check if any key is being pressed (if not check the other paddle).
- AH = 00h - check which key is being pressed (AL = ASCII Character).

## Moving The Paddles And Balls:
- The velocities are added to the current positions of the paddles and the balls.
- The screen is cleared after the above operation for avoiding the formation of trails.

## The paddle Is Controlled By AI:
- Check if the ball is above the paddle : IF (BALL_Y + BALL_SIZE < PADDLE_RIGHT_Y) then move it up.
- Check if the ball is below the paddle : IF (BALL_Y >  BALL_HEIGHT  + PADDLE_RIGHT_Y) then move it down.
- IF none of them ,then don't move the paddle.

## Resources Used:
- Our Sections (FCIS MU)
- [YouTube Playlist](https://youtube.com/playlist?list=PLvpbDCl_H7mfgmEJPl1bTHlH5g-f0kWDM&si=EnSIkaIECMiOmarE)
- [Drawing Pictures](https://youtube.com/watch?v=wwxwYr88QsU&si=EnSIkaIECMiOmarE)
- [This Graphics mode uses SVGA configuration](https://en.wikipedia.org/wiki/Super_VGA) So we use it to be able to use 256 colors on 640x400.
- ASCII TABLE:
 
![photo_2022-12-31_15-49-18](https://user-images.githubusercontent.com/100795596/210138941-8d5d3e4d-9ec0-490b-baf1-924d13bc0280.jpg)


## Prerequisites:
- In the playlist, two programs were used, DOSBox 0.74 and Notepad++, but we preferred to use one program, GUI Turbo assembler with the change in the segments syntax
  from what was written in the vedios in the playlist.

