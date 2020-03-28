import turtle
wn = turtle.Screen()
wn.title("Game1 by saumya")
wn.bgcolor("white")
wn.setup(width=800,height=600)

#score
score_a=0
score_b=0

# paddle A
a = turtle.Turtle()
a.penup()
a.shape("square")
a.color("black")
a.shapesize(7,3,1)
a.speed(0)
a.goto(-400,0)


# paddle B
b = turtle.Turtle()
b.penup()
b.shape("square")
b.color("black")
b.shapesize(7,3,1)
b.speed(0)
b.goto(400,0)

#ball
ball=turtle.Turtle()
ball.penup()
ball.shape('circle')
ball.color('black')
ball.shapesize()
ball.speed(0)
ball.goto(0.00,0.00)
ball.dx=2
ball.dy=2

#pen
pen=turtle.Turtle()
pen.speed(0)
pen.color("black")
pen.penup()
pen.hideturtle()
pen.goto(0,260)
pen.write("Player A: 0  Player B: 0",align="center",font=("courier",20,"normal"))

#funtion to move paddles
def a_up():
    y=a.ycor()
    y+=10
    a.sety(y)

def a_down():
    y=a.ycor()
    y-=10
    a.sety(y)

def b_up():
    y=b.ycor()
    y+=10
    b.sety(y)

def b_down():
    y=b.ycor()
    y-=10
    b.sety(y)

# keyboards
wn.listen()
wn.onkeypress(a_up,'w')
wn.onkeypress(a_down,'s')
wn.onkeypress(b_up,'Up')
wn.onkeypress(b_down,'Down')

# game main loop
while True:
    wn.update()
    # move the ball
    ball.setx(ball.xcor() + ball.dx)
    ball.sety(ball.ycor() + ball.dy)

    # bouncing the boundaries
    if ball.ycor()>290:
        ball.sety(290)
        ball.dy *= -1

    if ball.ycor()<-290:
        ball.sety(-290)
        ball.dy *= -1

    if ball.xcor()>390:
        ball.goto(0,0)
        score_b += 1
        pen.clear()
        pen.write("Player A: {}  Player B: {}".format(score_a,score_b), align="center", font=("courier", 20, "normal"))

    if ball.xcor()<-390:
        ball.goto(0,0)
        score_a += 1
        pen.clear()
        pen.write("Player A: {}  Player B: {}".format(score_a,score_b), align="center", font=("courier", 20, "normal"))

    #paddle a
    if (ball.xcor()>373) and (ball.ycor()< (b.ycor()+70) and ball.ycor()>(b.ycor()-70)):
        ball.setx(373)
        ball.dx *= -1

    #paddle b
    if (ball.xcor()<-373) and (ball.ycor()< (a.ycor()+70) and ball.ycor()>(a.ycor()-70)):
        ball.setx(-373)
        ball.dx *= -1

wn.mainloop()
