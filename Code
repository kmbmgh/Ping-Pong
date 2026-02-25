from pygame import *
win_height = 700
win_width = 900
win = display.set_mode((win_width, win_height))
display.set_caption('Пинг-Понг')

clock = time.Clock()
FPS = 60
game = True
speed = 10

class GameSptite(sprite.Sprite):
    def __init__(self, player_image, player_x, player_y, size_x, size_y, player_speed):
        super().__init__()
        self.image = transform.scale(image.load(player_image), (size_x, size_y))
        self.speed = player_speed
        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y
    def reset(self):
        win.blit(self.image, (self.rect.x, self.rect.y))


class Player(GameSptite):
    def update_r(self):
        keys = key.get_pressed()
        if keys[K_UP] and self.rect.y > 5:
            self.rect.y -= self.speed
        if keys[K_DOWN] and self.rect.y < 625:
            self.rect.y += self.speed

    def update_l(self):
        keys = key.get_pressed()
        if keys[K_w] and self.rect.y > 5:
            self.rect.y -= self.speed
        if keys[K_s] and self.rect.y < 625:
            self.rect.y += self.speed

class Ball(GameSptite):
    def update(self):
        self.rect.y += self.speed
        # global lost
        if self.rect.y > win_height:
            self.rect.x = randint(80, win_width - 80)
            self.rect.y = 0
            # lost = lost + 1
            

racket1 = Player('racket.png',100, win_height - 200, 80, 200, 10)
racket2 = Player('racket.png',800, win_height - 200, 80, 200, 10)
ball = Ball('tennis_ball.png',450, win_height - 350, 80, 80,10)
while game:
    for e  in event.get():
        if e.type == QUIT:
            game = False
            

    display.update()
    clock.tick(FPS)
