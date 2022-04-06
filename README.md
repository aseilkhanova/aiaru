# aiaru
about amasing game 
tic tac toe 
import pygame
import sys


def check_win(mas,sign):
    zeroes = 0
    for row in mas:
        zeroes+= row.count(0)
        if row.count(sign)==3:
            return sign
        for col in range(3):
            if mas[0][col]==sign and mas[1][col]==sign and mas[2][col]==sign:
                return sign
        if mas[0][0] == sign and mas[1][1] == sign and mas[2][2] == sign:
            return sign
        if mas[0][2] == sign and mas[1][1] == sign and mas[2][0] == sign:
            return sign
        if zeroes==0:
            return 'Piece'
        return False

pygame.init()
size_block = 100
margin = 15
width = height = size_block * 3 + margin * 4

size_window = (width, height)
screen = pygame.display.set_mode(size_window)
pygame.display.set_caption("tic tac toe")

black = (0, 0, 0)
red = (255, 0, 0)
green = (0, 255, 0)
white = (255, 255, 255)
mas = [[0]*3 for i in range(3)]
query = 0 # 1 2 3 4 5 6 7
game_over = False


