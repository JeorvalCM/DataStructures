from IPython.display import clear_output
import time
class queue:
    #initializer
    def __init__(self, item = None):
        try:
            self.items = flattener(item)
        except:
            self.items = item
            
        if self.items == None:
            self.items = []
            
    #check if the stack is empty
    def empty(self):
        return self.items == []
    
    #adding a new element at the end
    def push(self, item):
        try:
            if(len(item)) >0:
                for i in item:
                    self.items.append(i)
                return
        except:
            return self.items.append(item)
    
    #eliminating the last itam
    def pop(self):
        return self.items.pop(0)
    
    #check the stack´s size
    def size(self):
        return len(self.items)
    
    #print the content of the stack
    def content(self):
        return self.items
#during the whole game it will be the operation 10*(y-1)+(x-1) that is to avoid the use of list of list, this make a vector

#Function that impress the boat
def inicio():
    for i in range(0,15):
        print("* " *i)
    for i in range(0,4):
        print("      *")
    for i in range(-40,-30):
        print("*"*-i)
 #instructions        
def comojugar():
    print("\nYou have to input a value for x -axis and y -axis ")
    
def flattener(lista):
    #return a list of one dimension
    return [principal for sub in lista for principal in sub]
    
#rules    
def reglas():
    print("It is by turn, so each player will have a turn to drop 1 bomb")
    print("You have nine boats, one of 4x1, one of 3x1, one of 2x1 and one of 1x1")
    print("If you hit one boat you will have another bomb, but if you miss, the another play will drop it")
    print("If * changes into a + you hit water, but if changes into ° you hit a boat")
    
#Print the board of the positions, parameters a list where are the asteristics and other characters, a strinf  
def board(tablero,name):
    #variable declaration that it is the number that gets the y-axis
    j=1
    print("\n {}".format(name))
    #print the x-axis
    for i in range(1,11):
        print("\t",i,end='')
    #When the loop finish print a space bar
    print()
    for i in range(0,100):
        #print y-axis; the numbers of this axis
        if i==0:
            print(j,end='')
            j+=1
            #print the asterics, basically the coordinates
        if i%10==0 and i!=0:
            print()
            print(j,end='')
            j+=1
        print("\t",tablero[i],end='')
 
 #Function for waiting 5 seconds and then clear the output
def tiempo():
    #delay
    time.sleep(1)
    #clear output
    clear_output()
        
 #It says where the boat cannot go , parameters: x and y are int inputs, i is an int from a for, listarest is an array    
def restricciones(x,y,i,listarest):
    restric = []
    if i>1:
        #when does not have enough spaces to go left that word gets forbidden
        if x<i or x==1 or ((10*(y-1)+(x-1-(i-1))) in listarest) == True:
            print("\nYou cannot go left")
            restric.append("left")
            #when does not have enough spaces to go right that word gets forbidden
        if x>(11-i) or x==10 or ((10*(y-1)+(x-1+(i-1))) in listarest) == True:
            print("\nYou cannot go right")
            restric.append("right")
            #when does not have enough spaces to go forwards that word gets forbidden
        if y<i or y==1 or ((10*(y-1-(i-1))+(x-1)) in listarest) == True:
            print("\nYou cannot go forwards")
            restric.append("forwards")
            #when does not have enough spaces to go backwards that word gets forbidden
        if y>(11-i) or y==10 or ((10*(y-1+(i-1))+(x-1)) in listarest) == True:
            print("\nYou cannot go backwards")
            restric.append("backwards")
    return restric

    #Function to introduce where you want to your boat go
    """
    parameters: tablero is an array the save the coordinates for the game, a is an array that contains the restirc words
    x and y int inputs 
    i is the size of the boat from the loop to gets the boat
    """
def direccion(tablero,a,x,y,i): 
    ans=' '
    b = []
    #save the coodinate already given
    b.append(10*(y-1)+(x-1))
    if i>1:
        #ask the direction for your boat
        print("\nYou have four directions: right, left, forwards and backwards")
        while True:
            ans = input("\nWhere do you want to go(Only valid directions): ")
            ans = ans.lower()
            """
            the if check the side it wants to go and if the value  is not repited
            the loops gets the new coordinates when it gets a side
            in the part of tablero assing x to the new coordinate
            and in b.append adds the coordinates to the list to then pass it to repit list
            the breaks to finish the While True
            """
            if ans == "right" and (ans in a) == False:
                for i in range(1,i):
                    tablero[10*(y-1)+(x+i-1)] = 'x'
                    b.append(10*(y-1)+(x+i-1))
                break
            elif ans == "left" and (ans in a) ==  False:
                for i in range(1,i):
                    tablero[10*(y-1)+(x-i-1)] = 'x'
                    b.append(10*(y-1)+(x-i-1))
                break
            elif ans == "forwards" and (ans in a) == False:
                for i in range(1,i):
                    tablero[10*(y-i-1)+(x-1)] = 'x'
                    b.append(10*(y-i-1)+(x-1))
                break
            elif ans =="backwards" and (ans in a) == False:
                for i in range(1,i):
                    tablero[10*(y+i-1)+(x-1)] = 'x'
                    b.append(10*(y+i-1)+(x-1))
                break
            #return the list that has the coordinate of the boat
        return b
    else:
        #return the list that has the coordinate of the boat
        return b

    #function to get the coordinates, parameters an array where coordinates are used
def coordenadas(listarepetidas):
    #ask for the coordinates until gets a value that is not repited
    while True:
        #declaration variable and gets 0 each time to gets in the other loops
        x=0
        y=0
        #loop to get a valid x-axis coordinate
        while True:
            try:
                x = int(input("\nCoordinate of the x-axis of boat: "))
                if x<=10 and x>=1:
                    break
            except:
                print("Unvalid")
        #loop to get a valid y-axis coordinate
        while True:
            try:
                y = int(input("\nCoordinate of the y-axis: "))
                if y<=10 and y>=1:
                    break
            except:
                print("Unvalid")
            #when there is not lisf of repited yet
        if len(listarepetidas)==0:
            #break to finish the While True
            break
        else:    
            #when are coordinates that are not repited
            if ((10*(y-1)+(x-1)) in listarepetidas) == False:
                #break to finish the While True
                break
    #when x and y are valid are return it
    return x,y    
    
    
    
#function to hide boats before the attack starts
    """
    Parameters: tablero is an array that has the coordinates or rather asteriscs, name is a string input
    """

def esconderbarcos(tablero, name):
    #list declaration
    c=[]
    boats = queue()
    boats.push([1,2,3,4])
    print("\t\t\tWhere dou you want to save your boats?\nWrite the coordinates of one corner of the boat")
    #function to get all the boats from since 1 up to 4
    while True:
        tamaño_barco = boats.pop()
        print("\nThe next boat occupies {} squares".format(tamaño_barco))
        #print board
        board(tablero,name)
        #c are the  coordinates where the boats are saves, and gets in the function boat
        c.append(barcos(tablero,flattener(c),tamaño_barco,name))
        tiempo()
        if boats.empty() == True:
            break
        #return the list that has the coordinates of the boat
    return c

  #function to introduce boats 
    """
    parameters: tablero is an array that has the coordinates or rather asteriscs, c is a vector where are the values of 
    the coordinates, tamaño it is to know the size of the boat, name string input
    """
def barcos(tablero,c,tamaño,name):
    a=[]
    b = []
    print("\nyou will input one corner of your boat")
    x,y = coordenadas(c)
    tablero[10*(y-1)+(x-1)] = 'x'
    tiempo()
    board(tablero,name)
    #gets the restrictions
    a = restricciones(x,y,tamaño,c)
    #gets the coordinates where the boats area saved
    b = direccion(tablero,a,x,y,tamaño)
    return b

#function for the gamen itself
    """
    parameters:tablero 1 and tablero 2 are arrays that contains characters used in the game
    a and b are array,vectors, where are saved the coordinates of the boats of each player
    name1 and name2 string input
    """
def juego(tablero1,tablero2,a,b,name1,name2):
    #variable declaration
    vidas1=10
    vidas2=10
    usados1=[]
    usados2=[]
    while True:
        #player one turn
        print("Player ONE Turn")
        #it gets into the attack
        vidas2 = jugador(tablero1,b,vidas2,usados1,name1)
        #if for player 1 winning
        if vidas2==0:
            print("Player 1 won")
            tiempo()
            break
        tiempo()
        print("Player TWO turn")
        #it gets into the attack
        vidas1 = jugador(tablero2,a,vidas1,usados2,name2)
        #if for player 2 winning
        if vidas1==0:
            print("You won")
            tiempo() 
            break
        tiempo()
    
    #function for the player attacking
    """
    parameters: tablero array that contains characters used in the game
    listadehits an array, vector where are saved the coordinates of the boats hidden
    vidas: int thatare lifes of the player
    usados: an arrray, vector, where are saved coordinates of boats already hit
    name is an string input
    """
def jugador(tablero,listadehits,vidas,usados,name):
    while True:
    #print the both or ratter the remaining lifes of enemy
        print("Lifes remainings  of your enemy: {}".format(vidas))
        tiempo()
        #print the board
        board(tablero,name)
        #while true to gets valid x and y coordinates
        while True:
            x=0
            y=0
            while True:
                try:
                    x = int(input("\nCoordinate of the x-axis of your boat(valid operators a non-repited positions): "))
                    if x<=10 and x>=1:
                        break
                except:
                    print("Unvalid")
            while True:
                try:
                    y = int(input("\nCoordinate of the y-axis(valid operators a non-repited positions): "))
                    if y<=10 and y>=1:
                        break
                except:
                    print("Unvalid")
                #check if that coordinates have been used
            if ((10*(y-1)+(x-1)) in usados) == False:
                #finish the loop because it is a valid coordinate
                break
        #it it is a not repited coordinate gets into usados to not repit in next rounds
        usados.append(10*(y-1)+(x-1))
        #check if that coordinates has hit a boat
        if ((10*(y-1)+(x-1)) in listadehits)==True:
            print("You hit a boat")
            vidas= vidas-1
            #assigns a ° to the coordinate when you hit a boat
            tablero[10*(y-1)+(x-1)]='°'
            #when the player destroy all the boat it is a if to finish the function
            if vidas==0:
                #return the life remaining
                return vidas
            #when hits water
        else:
            print("You hit water")
            #assigns a + to the coordinate when you hit water
            tablero[10*(y-1)+(x-1)]='+'
            board(tablero,name)
            tiempo()
            #return the life remaining
            return (vidas)
    
 
 #variable declaration
tablero1 = ['*' for x in range(0,100)]
tablero2 = ['*' for x in range(0,100)]
tablero3 = ['*' for x in range(0,100)]
tablero4 = ['*' for x in range(0,100)]
inicio()
reglas()
comojugar()
tiempo()
print("Player 1 Turn")
jug1 = input("Introduce your name: ")
#it gest coordinates of boats from player 1
a = flattener(esconderbarcos(tablero3,jug1))
tiempo()
print("Player 2 Turn")
jug2 = input("Introduce your name: ")
#it gest coordinates of boats from player 2
b = flattener(esconderbarcos(tablero4,jug2))
tiempo()
juego(tablero1,tablero2,a,b,jug1,jug2)
