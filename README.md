# I'm starting a game with asteroids and I use the turtle python library.
#
import os                 # for os.path
import random            # for random.choice
import time              # for time.sleep
import math               # for math.sqrt
import turtle            # for turtle graphics

# Set up the screen
wn = turtle.Screen()
wn.bgcolor("skyblue")            # background color of the screen
wn.title("Space Invaders")         # title of the screen

# Draw border
border_pen = turtle.Turtle()
border_pen.speed(0)
border_pen.color("white")
border_pen.penup()
border_pen.setposition(-300,-300)        # set the position of the turtle
border_pen.pendown()
border_pen.pensize(3)
for side in range(4):            # draw a square
    border_pen.fd(600)
    border_pen.lt(90)          # turn left 90 degrees
border_pen.hideturtle()          # hide the turtle

# Set the score to 0
score = 0

# Draw the score on the screen
score_pen = turtle.Turtle()
score_pen.speed(0)
score_pen.color("white")   # color of the text
score_pen.penup()
score_pen.setposition(-290, 310)
scorestring = "Score: %s" %score      # %s is a placeholder for the score
score_pen.write(scorestring, False, align="left", font=("Arial", 14, "normal"))
score_pen.hideturtle()


# Create the player turtle
player = turtle.Turtle()      # create a turtle object
player.color("blue")            # color of the player
player.shape("triangle")        # shape of the player
player.penup()
player.speed(0)         # speed of the player
player.setposition(0, -250)    # position of the player
player.setheading(90)

playerspeed = 15                   # speed of the player

