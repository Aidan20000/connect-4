# connect-4
import turtle

n = 1
turncounter = 1
width = 60

# Makes turtle and screen
s = turtle.Screen()
t = turtle.Turtle()

# Makes row borders
t.color("purple")
t.pensize(5)
x = -248
for q in range(8):
    t.penup()
    t.goto(x, -135)
    t.setheading(90)
    t.pendown()
    t.forward(320)
    x = x + 60

t.pensize(1)
t.color("black")
# Defines a square
def square():
    t.circle(40, 360, 4)

# Turtle Starting Position
t.penup()
t.goto(-190, -190)
t.pendown()
t.right(45)

# Asks for move
while (n > 0):
    if (turncounter % 2 == 1):
        t.fillcolor("red")
    else:
        t.fillcolor("blue")
    #Asks for row and height
    row = int(input("What column?"))
    row = row - 1

    height = int(input("How many peices are in that column?"))
    height = height + 1

    # Where turtle ends up
    xcor = row * width
    ycor = 55 * height

    # Makes peice according to instructions
    t.penup()
    t.goto(-190 + xcor, -190 + ycor)
    t.pendown()
    t.begin_fill()
    square()
    t.end_fill()
    turncounter = turncounter + 1

# Keeps it on screen
s.mainloop()
