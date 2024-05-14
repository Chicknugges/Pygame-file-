import pygame
import sys
# Define colors
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
GRAY = (120, 120, 120)
BLUE = (0, 0, 255)
selected_level = None
# Initialize pygame
pygame.init()
# Set the window title
pygame.display.set_caption("Main Menu")
#text font
text_font = pygame.font.SysFont("Arial", 30)

# Add background image
background = pygame.image.load("847d279db1bbd9e5bd5d2af9947039c36214-M.jpeg")
floor = pygame.image.load("ground1.png")
floor = pygame.transform.scale(floor, (1024, 768))
concrete = pygame.image.load("Ground2.png")
concrete = pygame.transform.scale(concrete, (1024, 768))
ashphalt = pygame.image.load("ground3.png")
ashphalt = pygame.transform.scale(ashphalt, (1024, 768))
cardM = pygame.image.load("Picture1.png")
card1 = pygame.image.load("Picture2.png")
card2 = pygame.image.load("Picture3.png")
card3 = pygame.image.load("Picture4.png")
card4 = pygame.image.load("Picture5.png")
card5 = pygame.image.load("Picture6.png")
card6 = pygame.image.load("Picture7.png")
card7 = pygame.image.load("Picture8.png")
card8 = pygame.image.load("Picture9.png")
card9 = pygame.image.load("Picture10.png")
card10 = pygame.image.load("Picture11.png")
card11 = pygame.image.load("Picture12.png")
card12 = pygame.image.load("Picture13.png")
card13 = pygame.image.load("Picture14.png")
card14 = pygame.image.load("Picture15.png")
grass = pygame.image.load("PictureWOW.png")
grass = pygame.transform.scale(grass, (1024, 768))
Hazel_wilson = pygame.image.load("Hazel wilson.png")

# Create fonts
title_font = pygame.font.SysFont("Impact", 64)
button_font = pygame.font.SysFont('Impact', 30)

# Set screen size
screen_width = 1024
screen_height = 768
screen = pygame.display.set_mode((screen_width, screen_height))

#Variable for score
player_one_score = 0
player_two_score = 0

#variable for deck
deck_14 = []

#variable for element name
element_name = ("Element")

def draw_text(text, font, text_col, x, y):
    img = font.render(text, True, text_col)
    screen.blit(img, (x,y))

# Create buttons
new_button = pygame.Rect(screen_width / 3 - 75, screen_height / 1 - 500, 250, 50)
pygame.draw.rect(screen, BLACK, new_button)
play_button = pygame.Rect(screen_width/5-75, screen_height/2-25, 250, 50)
level_select = pygame.Rect(screen_width/5-75, screen_height / 1 - 500, 250, 50)
settings_button = pygame.Rect(screen_width/5-75, screen_height/2+50, 250, 50)
exit_button = pygame.Rect(screen_width/5-75, screen_height/2+125, 250, 50)
random_button = pygame.Rect(screen_width/5-75, screen_height/2+200, 250, 50)
resume_button = pygame.Rect(screen_width/5-75, screen_height/2-25, 250, 50)
scaled_M = pygame.transform.scale(cardM,(100,100))
card_M_button = scaled_M.get_rect(topleft=(750, 364))

scaled_1 = pygame.transform.scale(card1,(100,100))
card_1_button = scaled_1.get_rect(topleft=(750, 364))

scaled_2 = pygame.transform.scale(card2,(100,100))
card_2_button = scaled_2.get_rect(topleft=(750, 364))

scaled_3 = pygame.transform.scale(card3,(100,100))
card_3_button = scaled_3.get_rect(topleft=(750, 364))

scaled_4 = pygame.transform.scale(card4,(100,100))
card_4_button = scaled_4.get_rect(topleft=(750, 364))

scaled_5 = pygame.transform.scale(card5,(100,100))
card_5_button = scaled_5.get_rect(topleft=(750, 364))

scaled_6 = pygame.transform.scale(card6,(100,100))
card_6_button = scaled_6.get_rect(topleft=(750, 364))

scaled_7 = pygame.transform.scale(card7,(100,100))
card_7_button = scaled_7.get_rect(topleft=(750, 364))

tutorial = pygame.Rect(screen_width / 3 - 75, screen_height / 1 - 700, 250, 50)
pygame.draw.rect(screen, BLUE, tutorial)
full_screen_text = button_font.render("Tutorial", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=tutorial.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_1 = pygame.Rect(screen_width / 3 - 75, screen_height / 1 - 600, 250, 50)
pygame.draw.rect(screen, BLUE, Level_1)
full_screen_text = button_font.render("Level_1", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_1.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_2 = pygame.Rect(screen_width / 3 - 75, screen_height / 1 - 500, 250, 50)
pygame.draw.rect(screen, BLUE, Level_2)
full_screen_text = button_font.render("Level_2", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_2.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_3 = pygame.Rect(screen_width / 3.23 - 75, screen_height / 1 - 100, 250, 50)
pygame.draw.rect(screen, BLUE, Level_3)
full_screen_text = button_font.render("Level_3", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_3.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_4 = pygame.Rect(screen_width / 3.23 - 75, screen_height / 1 - 200, 250, 50)
pygame.draw.rect(screen, BLUE, Level_4)
full_screen_text = button_font.render("Level_4", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_4.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_5 = pygame.Rect(screen_width / 3.23 - 75, screen_height / 1 - 300, 250, 50)
pygame.draw.rect(screen, BLUE, Level_5)
full_screen_text = button_font.render("Level_5", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_5.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_6 = pygame.Rect(screen_width / 3.23 - 75, screen_height / 1 - 400, 250, 50)
pygame.draw.rect(screen, BLUE, Level_6)
full_screen_text = button_font.render("Level_6", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_6.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_7 = pygame.Rect(screen_width / 1.8 - 75, screen_height / 1 - 100, 250, 50)
pygame.draw.rect(screen, BLUE, Level_7)
full_screen_text = button_font.render("Level_7", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_7.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_8 = pygame.Rect(screen_width / 1.8 - 75, screen_height / 1 - 200, 250, 50)
pygame.draw.rect(screen, BLUE, Level_8)
full_screen_text = button_font.render("Level_8", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_8.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_9 = pygame.Rect(screen_width / 1.8 - 75, screen_height / 1 - 300, 250, 50)
pygame.draw.rect(screen, BLUE, Level_9)
full_screen_text = button_font.render("Level_9", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_9.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_10 = pygame.Rect(screen_width / 1.8 - 75, screen_height / 1 - 400, 250, 50)
pygame.draw.rect(screen, BLUE, Level_10)
full_screen_text = button_font.render("Level_10", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_10.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_11 = pygame.Rect(screen_width / 1.25 - 75, screen_height / 1 - 100, 250, 50)
pygame.draw.rect(screen, BLUE, Level_11)
full_screen_text = button_font.render("Level_11", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_11.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_12 = pygame.Rect(screen_width / 1.25 - 75, screen_height / 1 - 200, 250, 50)
pygame.draw.rect(screen, BLUE, Level_12)
full_screen_text = button_font.render("Level_12", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_12.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_13 = pygame.Rect(screen_width / 1.25 - 75, screen_height / 1 - 300, 250, 50)
pygame.draw.rect(screen, BLUE, Level_13)
full_screen_text = button_font.render("Level_13", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_13.center)
screen.blit(full_screen_text, full_screen_text_rect)

Level_14 = pygame.Rect(screen_width / 1.25 - 75, screen_height / 1 - 400, 250, 50)
pygame.draw.rect(screen, BLUE, Level_14)
full_screen_text = button_font.render("Level_14", True, WHITE)
full_screen_text_rect = full_screen_text.get_rect(center=Level_14.center)
screen.blit(full_screen_text, full_screen_text_rect)

pause_button = pygame.Rect(screen_width / 1.22 - 75, screen_height / 1 - 750, 250, 50)
pygame.draw.rect(screen, BLUE, pause_button)
pause_button_text = button_font.render("Pause", True, WHITE)
pause_button_text_rect = full_screen_text.get_rect(center=pause_button.center)
screen.blit(full_screen_text, full_screen_text_rect)

# Code underneath is for route 1 and route 0

import random

#Code underneath is for route 1 and route 0

#Variable for score
player_one_score_14 = 0
player_two_score_14 = 0

#variable for deck
deck_14 = []

#variable for element name
element_name = draw_text("Element", text_font, (0,0,0), 500, 500)

#Making the deck
def populate_deck_14():
    for rank_14 in range(1,15):
        deck_14.append((rank_14,element_name))

#ranking each card by their name
def printable_card_14(card_14):
    if card_14[0] == 1: rank_14 = "Dust"
    if card_14[0] == 2: rank_14 = "Wind"
    if card_14[0] == 3: rank_14 = "Ground"
    if card_14[0] == 4: rank_14 = "Rock"
    if card_14[0] == 5: rank_14 = "Fire"
    if card_14[0] == 6: rank_14 = "Water"
    if card_14[0] == 7: rank_14 = "Electric"
    if card_14[0] == 8: rank_14 = "Ice"
    if card_14[0] == 9: rank_14 = "Lava"
    if card_14[0] == 10: rank_14 = "Nuclear"
    if card_14[0] == 11: rank_14 = "Light"
    if card_14[0] == 12: rank_14 = "Dark"
    if card_14[0] == 13: rank_14 = "Demonic"
    if card_14[0] == 14: rank_14 = "God"
    fullname_14 = rank_14 + " " + card_14[1]
    return fullname_14


#printable_card_14(dshdjh)

#Drawing a card
def draw_card_player1_14(player):
    card_14 = deck_14[0]
    deck_14.remove(deck_14[0])
    #text, font, text_col, x, y
    #print(player + " drew the " + printable_card_14(card_14))
    thingToDraw = str((f"{player} drew the {printable_card_14(card_14)}"))
    draw_text(thingToDraw, text_font, (0, 0, 0), 300, 250)
    return card_14
def draw_card_player2_14(player):
    card_14 = deck_14[0]
    deck_14.remove(deck_14[0])
    thingToDraw2 = str((f"{player} drew the {printable_card_14(card_14)}"))
    #print(player + " drew the " + printable_card_14(card_14))
    draw_text(thingToDraw2, text_font, (0, 0, 0), 300, 250)
    return card_14

#make the deck
#populate_deck_14()
#shuffle the deck
#random.shuffle(deck_14)
#print("Click the deck to draw a card")













def draw_splash_screen():
    screen.blit(background, (0, 0))
    title= title_font.render("Monday", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

# Function to draw title screen
def draw_title_screen():
    screen.blit(background, (0, 0))
    title = title_font.render("Monday", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)



def draw_play_select_screen():
    screen.blit(background, (0,0))
    title = title_font.render("Choose a play type", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)


# Function to draw level selection screen
def draw_level_select():
    screen.fill(BLACK)
    title = title_font.render("Select a Level", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

# Function to draw settings screen
def draw_settings_screen():
    screen.fill(BLACK)
    title = title_font.render("Settings", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

    # Volume slider
    volume_slider = pygame.Rect(screen_width / 2 - 100, screen_height / 2 - 25, 200, 10)
    pygame.draw.rect(screen, GRAY, volume_slider)

    # Full-screen toggle button
    full_screen_button = pygame.Rect(screen_width / 2 - 75, screen_height / 2 + 50, 150, 50)
    pygame.draw.rect(screen, BLUE, full_screen_button)
    full_screen_text = button_font.render("Full Screen", True, WHITE)
    full_screen_text_rect = full_screen_text.get_rect(center=full_screen_button.center)
    screen.blit(full_screen_text, full_screen_text_rect)

def draw_text(text, font, text_col, x, y):
    img = font.render(text, True, text_col)
    screen.blit(img, (x, y))

def draw_pause_screen():
    screen.fill(BLACK)
    title = title_font.render("Pause screen", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)



make_popup = True

def doPopup(self):
    import sys
    #popup loop
    while True:
        #draw the popup
        make_popup(self)
        #check for keyboard or mouse events
        for event in pygame.event.get():
            if event.type == "QUIT":
                pygame.quit()
                sys.exit()
            elif event.type == pygame.MOUSEBUTTONDOWN:
                #update mouse position
                self.mousex, self.mousey = event.pos
            #check for left click
            elif event.type == pygame.MOUSEBUTTONDOWN and event.button == 1:
                OPTION = option_selected(self)
                if OPTION != None:
                    return OPTION
                else:
                    return None

def option_selected(self):
    popupSurf = pygame.Surface(100, 100)
    options = ['Attack', 'Talk']
    #draw up the surf, but don't blit it to the screen
    for i in range(len(options)):
        textSurf = "Arial".render(options[i], 1, BLUE)
        textRect = textSurf.get_rect()
        textRect.top = self.top
        textRect.left = self.left
        self.top += pygame.font.Font.get_linesize("Arial")
        popupSurf.blit(textSurf, textRect)
        if textSurf.collidepoint(self.mousex, self.mousey):
            return options[i]
    popupRect = popupSurf.get_rect()
    popupRect.centerx = "SCREENWIDTH"/2
    popupRect.centery = "SCREENHEIGHT"/2








def draw_play_tutorial_screen():
    screen.blit(floor, (0, 0))
    # make the deck
    populate_deck_14()
    # shuffle the deck
    random.shuffle(deck_14)
    draw_text("Click the deck to draw a card", text_font, (0,0,0), 300, 250)

    # every turn
    while True:
        player_one_score_14 = 0
        player_two_score_14 = 0
        # waiting for user input
        #for event in pygame.event.get():
           # if new_button.collidepoint(event.pos):
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False
            elif event.type == pygame.MOUSEBUTTONDOWN:
                if new_button.collidepoint(event.pos):
                    # each player draws a card
                    player_one_card_14 = draw_card_player1_14(draw_text("Player one", text_font, (0, 0, 0), 300, 250))
                    player_two_card_14 = draw_card_player2_14(draw_text("Player two", text_font, (0, 0, 0), 300, 250))
                    # compare to see who wins
                    if player_one_card_14[0] > player_two_card_14[0]:
                        winner = draw_text("Player one", text_font, (0, 0, 0), 400, 300)
                        player_one_score_14 += 1
                    elif player_one_card_14[0] < player_two_card_14[0]:
                        winner = draw_text("Player two", text_font, (0, 0, 0), 400, 300)
                        player_two_score_14 += 1
                    else:
                        winner = draw_text("no one", text_font, (0, 0, 0), 400, 300)
                    thingToDraw3 = str((f"{winner} wins"))
                    draw_text(thingToDraw3, text_font, (0, 0, 0), 300, 250)
                    draw_text(" ", text_font, (0, 0, 0), 400, 500)

                    # end the game when the deck is empty and no one can draw any more cards
                    if len(deck_14) == 0 or player_two_score_14 == 4 or player_one_score_14 == 4:
                        print("Game over")
                        print("")
                        print("Player one's final score:", player_one_score_14)
                        print("Player two's final score:", player_two_score_14)
                        if player_one_score_14 > player_two_score_14:
                            print("Player One Wins!")
                        elif player_two_score_14 > player_one_score_14:
                            print("Player Two Wins!")
                        else:
                            print("Its a Tie!")
                        break
                print("")


# Function to fit text within button
def fit_text_to_button(text, button_rect, color):
    font_size = 30
    font = pygame.font.Font(None, font_size)
    text_surface = font.render(text, True, color)

    while text_surface.get_width() > button_rect.width - 10 or text_surface.get_height() > button_rect.height - 10:
        font_size -= 1
        font = pygame.font.Font(None, font_size)
        text_surface = font.render(text, True, color)

    text_rect = text_surface.get_rect(center=button_rect.center)

    return text_surface, text_rect

def draw_level_screen_tutorial():
    screen.blit(floor, (0, 0))
    title = title_font.render("Tutorial", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_1_screen ():
    screen.blit(concrete, (0, 0))
    title = title_font.render("Level 1", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_2_screen ():
    screen.blit(floor, (0, 0))
    title = title_font.render("Level 2", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_3_screen ():
    screen.blit(ashphalt, (0, 0))
    title = title_font.render("Level 3", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_4_screen ():
    screen.blit(ashphalt, (0, 0))
    title = title_font.render("Level 4", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_5_screen ():
    screen.blit(concrete, (0, 0))
    title = title_font.render("Level 5", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_6_screen ():
    screen.blit(concrete, (0, 0))
    title = title_font.render("Level 6", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_7_screen ():
    screen.blit(grass, (0, 0))
    title = title_font.render("Level 7", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_8_screen ():
    screen.blit(grass, (0, 0))
    title = title_font.render("Level 8", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_9_screen ():
    screen.blit(concrete, (0, 0))
    title = title_font.render("Level 9", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_10_screen ():
    screen.blit(concrete, (0, 0))
    title = title_font.render("Level 10", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_11_screen ():
    screen.blit(ashphalt, (0, 0))
    title = title_font.render("Level 11", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_12_screen ():
    screen.blit(concrete, (0, 0))
    title = title_font.render("Level 12", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_13_screen ():
    screen.blit(ashphalt, (0, 0))
    title = title_font.render("Level 13", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

def draw_level_14_screen ():
    screen.blit(ashphalt, (0, 0))
    title = title_font.render("Level 14", True, WHITE)
    title_rect = title.get_rect(center=(screen_width // 2, 100))
    screen.blit(title, title_rect)

# Main game loop
def main():

    menu_screen = False
    level_select_screen = False
    settings_screen = False
    splash_screen = True

    running = True
    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False
            elif event.type == pygame.MOUSEBUTTONDOWN:
                if splash_screen:
                    #if splash_screen.collidepoint(event.pos):
                        menu_screen = True
                        splash_screen = False
                elif menu_screen:
                    if play_button.collidepoint(event.pos):
                        menu_screen = False
                        level_select_play = True
                        #level_select_screen = True
                    elif level_select.collidepoint(event.pos):
                        level_select_play = False
                        level_select_screen = True
                    elif settings_button.collidepoint(event.pos):
                        menu_screen = False
                        settings_screen = True
                    elif exit_button.collidepoint(event.pos):
                        running = False
                    elif random_button.collidepoint(event.pos):
                        menu_screen = False
                        splash_screen = True
                elif level_select_screen:
                    #for level in levels:
                        #if level.collidepoint(event.pos):
                           # load_level(level)

                        if tutorial.collidepoint(event.pos):
                            level_screen_tutorial = True
                            level_select_screen = False
                            pause_screen = False
                        if Level_1.collidepoint(event.pos):
                            level_screen_1 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            pause_screen = False
                        if Level_2.collidepoint(event.pos):
                            level_screen_2 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            pause_screen = False
                        if Level_3.collidepoint(event.pos):
                            level_screen_3 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            pause_screen = False
                        if Level_4.collidepoint(event.pos):
                            level_screen_4 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            pause_screen = False
                        if Level_5.collidepoint(event.pos):
                            level_screen_5 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            pause_screen = False
                        if Level_6.collidepoint(event.pos):
                            level_screen_6 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            pause_screen = False
                        if Level_7.collidepoint(event.pos):
                            level_screen_7 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            pause_screen = False
                        if Level_8.collidepoint(event.pos):
                            level_screen_8 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            pause_screen = False
                        if Level_9.collidepoint(event.pos):
                            level_screen_9 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            pause_screen = False
                        if Level_10.collidepoint(event.pos):
                            level_screen_10 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            level_screen_9 = False
                            pause_screen = False
                        if Level_11.collidepoint(event.pos):
                            level_screen_11 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            level_screen_9 = False
                            level_screen_10 = False
                            pause_screen = False
                        if Level_12.collidepoint(event.pos):
                            level_screen_12 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            level_screen_9 = False
                            level_screen_10 = False
                            level_screen_11 = False
                            pause_screen = False
                        if Level_13.collidepoint(event.pos):
                            level_screen_13 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            level_screen_9 = False
                            level_screen_10 = False
                            level_screen_11 = False
                            level_screen_12 = False
                            pause_screen = False
                        if Level_14.collidepoint(event.pos):
                            level_screen_14 = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            level_screen_9 = False
                            level_screen_10 = False
                            level_screen_11 = False
                            level_screen_12 = False
                            level_screen_13 = False
                            pause_screen = False
                if pause_button.collidepoint(event.pos):
                            pause_screen = True
                            level_select_screen = False
                            level_screen_tutorial = False
                            level_screen_1 = False
                            level_screen_2 = False
                            level_screen_3 = False
                            level_screen_4 = False
                            level_screen_5 = False
                            level_screen_6 = False
                            level_screen_7 = False
                            level_screen_8 = False
                            level_screen_9 = False
                            level_screen_10 = False
                            level_screen_11 = False
                            level_screen_12 = False
                            level_screen_13 = False
                            level_screen_14 = False
                if resume_button.collidepoint(event.pos):
                    pause_screen = False
                    level_select_screen = True
                    level_screen_tutorial = False
                    level_screen_1 = False
                    level_screen_2 = False
                    level_screen_3 = False
                    level_screen_4 = False
                    level_screen_5 = False
                    level_screen_6 = False
                    level_screen_7 = False
                    level_screen_8 = False
                    level_screen_9 = False
                    level_screen_10 = False
                    level_screen_11 = False
                    level_screen_12 = False
                    level_screen_13 = False
                    level_screen_14 = False
                if exit_button.collidepoint(event.pos):
                    running = False
                if settings_button.collidepoint(event.pos):
                    settings_screen = True
                if card_M_button.collidepoint(event.pos):
                    tutorial_level_play_screen = True
                    level_screen_tutorial = False
                    print("work")





        screen.fill(BLACK)

        if menu_screen:
            draw_title_screen()

            # Play button
            pygame.draw.rect(screen, BLUE, play_button)
            play_text = button_font.render("PLAY", True, WHITE)
            play_text_rect = play_text.get_rect()
            play_text_rect.center = play_button.center
            screen.blit(play_text, play_text_rect)

            # Settings button
            pygame.draw.rect(screen, BLUE, settings_button)
            settings_text = button_font.render("SETTINGS", True, WHITE)
            settings_text_rect = settings_text.get_rect()
            settings_text_rect.center = settings_button.center
            screen.blit(settings_text, settings_text_rect)

            # Exit button
            pygame.draw.rect(screen, BLUE, exit_button)
            exit_text = button_font.render("EXIT", True, WHITE)
            exit_text_rect = exit_text.get_rect()
            exit_text_rect.center = exit_button.center
            screen.blit(exit_text, exit_text_rect)

            # splash button
            pygame.draw.rect(screen, BLUE, random_button)
            random_text = button_font.render("Splash Screen", True, WHITE)
            random_text_rect = random_text.get_rect()
            random_text_rect.center = random_button.center
            screen.blit(random_text, random_text_rect)



        elif splash_screen:
            draw_splash_screen()

            draw_text("Creators of game", text_font, WHITE, 100, 250)
            draw_text("- Nathaniel", text_font, WHITE, 100, 300)
            draw_text("- Jacob", text_font, WHITE, 100, 350)


        elif level_select_play:
            draw_play_select_screen()

            pygame.draw.rect(screen, BLUE, level_select)
            select_text = button_font.render("level select", True, WHITE)
            select_text_rect = select_text.get_rect()
            select_text_rect.center = level_select.center
            screen.blit(select_text, select_text_rect)


        elif level_select_screen:
            draw_level_select()

            # tutorial
            pygame.draw.rect(screen, BLUE, tutorial)
            tutorial_text = button_font.render("Tutorial", True, WHITE)
            tutorial_text_rect = tutorial_text.get_rect()
            tutorial_text_rect.center = tutorial.center
            screen.blit(tutorial_text, tutorial_text_rect)

            # level 1
            pygame.draw.rect(screen, BLUE, Level_1)
            Level_1_text = button_font.render("Level 1", True, WHITE)
            Level_1_text_rect = Level_1_text.get_rect()
            Level_1_text_rect.center = Level_1.center
            screen.blit(Level_1_text, Level_1_text_rect)

            # level 2
            pygame.draw.rect(screen, BLUE, Level_2)
            Level_2_text = button_font.render("Level 2", True, WHITE)
            Level_2_text_rect = Level_2_text.get_rect()
            Level_2_text_rect.center = Level_2.center
            screen.blit(Level_2_text, Level_2_text_rect)

            # level 3
            pygame.draw.rect(screen, BLUE, Level_3)
            Level_3_text = button_font.render("Level 3", True, WHITE)
            Level_3_text_rect = Level_3_text.get_rect()
            Level_3_text_rect.center = Level_3.center
            screen.blit(Level_3_text, Level_3_text_rect)

            # level 4
            pygame.draw.rect(screen, BLUE, Level_4)
            Level_4_text = button_font.render("Level 4", True, WHITE)
            Level_4_text_rect = Level_4_text.get_rect()
            Level_4_text_rect.center = Level_4.center
            screen.blit(Level_4_text, Level_4_text_rect)

            # level 5
            pygame.draw.rect(screen, BLUE, Level_5)
            Level_5_text = button_font.render("Level 5", True, WHITE)
            Level_5_text_rect = Level_5_text.get_rect()
            Level_5_text_rect.center = Level_5.center
            screen.blit(Level_5_text, Level_5_text_rect)

            # level 6
            pygame.draw.rect(screen, BLUE, Level_6)
            Level_6_text = button_font.render("Level 6", True, WHITE)
            Level_6_text_rect = Level_6_text.get_rect()
            Level_6_text_rect.center = Level_6.center
            screen.blit(Level_6_text, Level_6_text_rect)

            # level 7
            pygame.draw.rect(screen, BLUE, Level_7)
            Level_7_text = button_font.render("Level 7", True, WHITE)
            Level_7_text_rect = Level_7_text.get_rect()
            Level_7_text_rect.center = Level_7.center
            screen.blit(Level_7_text, Level_7_text_rect)

            # level 8
            pygame.draw.rect(screen, BLUE, Level_8)
            Level_8_text = button_font.render("Level 8", True, WHITE)
            Level_8_text_rect = Level_8_text.get_rect()
            Level_8_text_rect.center = Level_8.center
            screen.blit(Level_8_text, Level_8_text_rect)

            # level 9
            pygame.draw.rect(screen, BLUE, Level_9)
            Level_9_text = button_font.render("Level 9", True, WHITE)
            Level_9_text_rect = Level_9_text.get_rect()
            Level_9_text_rect.center = Level_9.center
            screen.blit(Level_9_text, Level_9_text_rect)

            # level 10
            pygame.draw.rect(screen, BLUE, Level_10)
            Level_10_text = button_font.render("Level 10", True, WHITE)
            Level_10_text_rect = Level_10_text.get_rect()
            Level_10_text_rect.center = Level_10.center
            screen.blit(Level_10_text, Level_10_text_rect)

            # level 11
            pygame.draw.rect(screen, BLUE, Level_11)
            Level_11_text = button_font.render("Level 11", True, WHITE)
            Level_11_text_rect = Level_11_text.get_rect()
            Level_11_text_rect.center = Level_11.center
            screen.blit(Level_11_text, Level_11_text_rect)

            # level 12
            pygame.draw.rect(screen, BLUE, Level_12)
            Level_12_text = button_font.render("Level 12", True, WHITE)
            Level_12_text_rect = Level_12_text.get_rect()
            Level_12_text_rect.center = Level_12.center
            screen.blit(Level_12_text, Level_12_text_rect)

            # level 13
            pygame.draw.rect(screen, BLUE, Level_13)
            Level_13_text = button_font.render("Level 13", True, WHITE)
            Level_13_text_rect = Level_13_text.get_rect()
            Level_13_text_rect.center = Level_13.center
            screen.blit(Level_13_text, Level_13_text_rect)

            # level 14
            pygame.draw.rect(screen, BLUE, Level_14)
            Level_14_text = button_font.render("Level 14", True, WHITE)
            Level_14_text_rect = Level_14_text.get_rect()
            Level_14_text_rect.center = Level_14.center
            screen.blit(Level_14_text, Level_14_text_rect)



        elif settings_screen:
            draw_settings_screen()


        elif level_screen_tutorial:
            draw_level_screen_tutorial()

            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)

            #card
            screen.blit(scaled_M, (750, 364))

        elif level_screen_1:
            draw_level_1_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)

            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_2:
            draw_level_2_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)

            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_3:
            draw_level_3_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)

            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_4:
            draw_level_4_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_5:
            draw_level_5_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_6:
            draw_level_6_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_7:
            draw_level_7_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_8:
            draw_level_8_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_9:
            draw_level_9_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_10:
            draw_level_10_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_11:
            draw_level_11_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_12:
            draw_level_12_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_13:
            draw_level_13_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif level_screen_14:
            draw_level_14_screen()
            # pause button
            pygame.draw.rect(screen, GRAY, pause_button)
            pause_text = button_font.render("PAUSE", True, WHITE)
            pause_text_rect = pause_text.get_rect()
            pause_text_rect.center = pause_button.center
            screen.blit(pause_text, pause_text_rect)
            # card
            screen.blit(cardM, (750, 364))

        elif pause_screen:
            draw_pause_screen()

            # Settings button
            pygame.draw.rect(screen, BLUE, settings_button)
            settings_text = button_font.render("SETTINGS", True, WHITE)
            settings_text_rect = settings_text.get_rect()
            settings_text_rect.center = settings_button.center
            screen.blit(settings_text, settings_text_rect)

            # Exit button
            pygame.draw.rect(screen, BLUE, exit_button)
            exit_text = button_font.render("EXIT", True, WHITE)
            exit_text_rect = exit_text.get_rect()
            exit_text_rect.center = exit_button.center
            screen.blit(exit_text, exit_text_rect)

            pygame.draw.rect(screen, BLUE, resume_button)
            resume_text = button_font.render("RESUME", True, WHITE)
            resume_text_rect = resume_text.get_rect()
            resume_text_rect.center = resume_button.center
            screen.blit(resume_text, resume_text_rect)

        elif tutorial_level_play_screen:
            draw_play_tutorial_screen()
            pygame.draw.rect(screen, BLACK, new_button)
            #doPopup()
            #option_selected()


        pygame.display.flip()

    pygame.quit()

if __name__ == "__main__":
    main()
