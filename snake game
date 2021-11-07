import random# Random module is used to randomanly generate coordinates 
import math # It used to perform mathemticsl functions
import pygame # Used to help me design the game and it's objects 
import tkinter as tk # Used to generate boxes and buttons for the user 

pygame.init()#Intialises the pygame module
width = 700#Establishes the width of the window
height = 700#Estbalishes the height of the window
window = pygame.display.set_mode((width,height))#Creates a gaming window
pygame.display.set_caption("Snake Game")#Caption of the window
clock = pygame.time.Clock()#Uses to help keep track of time within the game
font = pygame.font.SysFont(None,25)# establishes the font that will be used in the game 
snake_list = []# A list that stores the x and y postion of the snake 

class Snake(object):# This class defines the variables that will be used throughout my game 
    def __init__(self,direction_x,direction_y,width,height,velocity,snake_x,snake_y):
        self.direction_x = 0
        self.direction_y = 1
        self.velocity_x = 0
        self.velocity_y = 0
        self.width = 20
        self.height = 20
        self.snake_x = 300
        self.snake_y = 300
        self.food_width = 20 
        self.food_height = 20
        self.score = 0
        self.length = 0
        self.red = (255,0,0)
        self.green = (0,255,0)
        self.white = (255,255,255)
        self.entry = ''
        self.root = ''
        self.box = ''
        self.Exit = False
        self.endgame = False
        self.answer = ''
        self.num1 = ''
        self.num2 = ''
       

    def snake_head(self):# This method is used to generate a new block for the snake when the food has been eaten 
        for xny in snake_list:
            snake = pygame.draw.rect(window,self.red,(xny[0],xny[1],self.width,self.height))

            
    def message(self,msg,colour):# This method is displays a message when the user has touched itself or the boundaries of the window
        text = font.render(msg, True, colour)
        window.blit(text, (self.snake_x/3, self.snake_y/3))

    def score_text(self,text, color, x,y):# This method displays the user's score
        screen_text = font.render(text, True, color)
        window.blit(screen_text, [x,y])
        

    def length_text(self,text,color_2, y,x):# This method displays the length of the snake
        word = font.render(text, True, color_2)
        window.blit(word, [x,y])
        

    

    
    def question(self):# This method creates the question box and displays a question for the user to answer
        self.root = tk.Tk()
        window = self.root
        window.title('Question')

        self.box = tk.Canvas(self.root, width = 400, height = 300,  relief = 'raised')
        self.box.pack()

        self.num1 = random.randint(1,50)
        self.num2 = random.randint(1,50)
        self.answer = (self.num1)+(self.num2)
        
        title = tk.Label(self.root, text='"What is ' +str(self.num1)+ '+' +str(self.num2)+'?') 
        title.config(font=('arial', 20))
        self.box.create_window(200, 25, window=title)

        subtitle = tk.Label(self.root, text='Please enter the correct number')
        subtitle.config(font=('arial', 15))
        self.box.create_window(200, 100, window=subtitle)

        self.entry = tk.Entry (self.root) 
        self.box.create_window(200, 140, window=self.entry)

        button = tk.Button(text='Enter', command=self.check, bg='red', fg='white', font=('helvetica', 9, 'bold'))
        self.box.create_window(200, 180, window=button)

        self.root.mainloop()

    def check(self):# This method checks if the user has enter the correct answer or not
        user_input = self.entry.get()
        if user_input == str(self.answer):
            self.root.destroy()
        elif user_input == '':
            label2 = tk.Label(self.root, text= 'you must enter something!', font=('arial', 10))
            self.box.create_window(200, 210, window=label2)
        elif user_input != self.answer:
            label3 = tk.Label(self.root, text= ('Incorrect! Please try again'))
            self.box.create_window(200, 210, window=label3)

       
            
        
          

    def movement(self):# This method allows the user to move, eat the food
        snake_x = 300
        snake_y = 300
        food_x = int(random.randint(0,width+100)/2)
        food_y = int(random.randint(0,height+100)/2)
        
        
        
        while not self.Exit:
            while self.endgame == True:
                window.fill((0,0,0))
                mysnake = Snake(335,325,20,20,5,300,300)
                mysnake.message("You lose! Please press space to continue or press Q to exit",self.red) 
                pygame.display.update()

                for event in pygame.event.get():
                    if event.type == pygame.KEYDOWN:
                        if event.key == pygame.K_q:
                            self.Exit = True
                            self.endgame = False
                            pygame.quit()

                        if event.key == pygame.K_SPACE:
                             mysnake = Snake(335,325,20,20,5,300,300)
                             mysnake.movement()

                        
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    self.Exit = True
                    

                if event.type == pygame.KEYDOWN:
                    if event.key == pygame.K_RIGHT:
                        self.velocity_x = 20
                        self.velocity_y = 0

                    elif event.key == pygame.K_LEFT:
                        self.velocity_x = -20
                        self.velocity_y = 0


                    elif event.key == pygame.K_UP:
                        self.velocity_x = 0
                        self.velocity_y = -20


                    elif event.key == pygame.K_DOWN:
                        self.velocity_x = 0
                        self.velocity_y = 20

            self.snake_x = self.snake_x + self.velocity_x
            self.snake_y = self.snake_y + self.velocity_y

            if (self.snake_x - food_x) < 5 and (self.snake_y - food_y)<5:
                food_x = int(random.randint(0,width)/2)
                food_y = int(random.randint(0,height)/2)
                self.score += 1
                self.length += 1
                mysnake = Snake(335,325,20,20,5,300,300)
                mysnake.question()

         

            window.fill((0,0,0))
            mysnake = Snake(335,325,20,20,5,300,300)
            snake = pygame.draw.rect(window,self.red,(self.snake_x,self.snake_y,self.width,self.height))
            snack = pygame.draw.rect(window,self.green,(food_x,food_y,self.food_width,self.food_height))
            mysnake.snake_head()
            mysnake.score_text("Score: " + str(self.score * 10),self.red,5,5)
            mysnake.length_text("Length "+ str(self.length+1),self.red,5,620)

            head = []
            head.append(self.snake_x)
            head.append(self.snake_y)
            snake_list.append(head)

            if self.snake_x>width or self.snake_x < 0 or self.snake_y >=height or self.snake_y < 0:
                self.endgame=True

            if len(snake_list)> self.length:
                del snake_list[0]

            if head in snake_list[:-1]:
                self.endgame = True

            mysnake = Snake(335,325,20,20,5,300,300)
            mysnake.snake_head()
            clock.tick(10)
            pygame.display.update()

            

def main():#This calls all the methods used in the game 
    mysnake = Snake(335,325,20,20,5,300,300)
    mysnake.snake_head()
    mysnake.movement()
    

if __name__ == '__main__': # this condition is used to call the main method 
    main()
