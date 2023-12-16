import pygame


pygame.init()

screen_width = 800
screen_height = 600

screen = pygame.display.set_mode((screen_width, screen_height))

font = pygame.font.SysFont("Kristen ITC", 50)
font2 = pygame.font.SysFont("Kristen ITC", 30)

hero_img = pygame.image.load("kartinki/images.jpg")
hero_img = pygame.transform.scale(hero_img, (120,120))

fon_img = pygame.image.load("kartinki/b17c0a3ce5dd6a23dfb6fe1147e6b34ec8f20p.jpeg")
fon_img = pygame.transform.scale(hero_img, (800,600))


x,y = 140, 40
x1,y1 = 140, 80
x2,y2 = 140, 120
x3,y3 = 140,120
speed = 0.1
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            quit()


    screen.blit(fon_img, (0,0))
    text = font.render("Welcome to game!!", True, (0, 0, 100))
    screen.blit(text, (x, y))
    text2 = font2.render("Welcome to game2!!", True, (110, 10, 100))
    screen.blit(text2, (x1, y1))
    textadsf = font.render("Welcome to game3!!", True, (110, 110, 100))
    screen.blit(textadsf, (x2, y2))

    keys = pygame.key.get_pressed()
    if keys[pygame.K_d]:
        x3 += speed
    if keys[pygame.K_w]:
        y3 -= speed
    if keys[pygame.K_s]:
        y3 += speed
    if keys[pygame.K_a]:
        x3 -= speed



    screen.blit(hero_img, (x3, y3))


    pygame.display.update()
