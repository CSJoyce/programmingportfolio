# Programming  1 Portfolio
Chris Joyce

cjoyce764@gmail.com

### Python Group Project

A mouse controlled Python game in which the player attempts to find hidden chests in a black room while simultaneously being hunted down by monsters.  As time progresses, new monsters spawn in, and each time a chest is found a new one is spawned in a random location on the screen.  Score will be the time that they player survives.

![scrcap](https://github.com/CSJoyce/Lights-Game/blob/master/Screen%20Shot%202018-04-13%20at%201.30.30%20PM.png)

import math

def setup(): 
    size(displayWidth, displayHeight, P3D)
    noStroke()

def draw(): 
    background(0)
    e1.display()
    translate(mouseX, mouseY)
    fill(255)
    sphere(30)
    e1.move(mouseX, mouseY)

class Enemy(object):
    def __init__(self, x, y, speed):
        self.x = x 
        self.y = y
        self.speed = speed
    
    def display(self):
        fill(255, 10, 10)
        ellipse(self.x, self.y, 10, 10)
        ellipse(self.x +20, self.y, 10, 10)
    
    def move(self, playerX, playerY):
        ang = atan2((playerY - self.y), (playerX - self.x))
        self.x += self.speed*cos(ang)
        self.y += self.speed*sin(ang)

e1 = Enemy(random(1,500), random(1,500), 5)
