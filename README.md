import random

def randomGenerator():
    loopo = True
    file1 = 0
    while loopo == True:
        while True:
            listLength = input("enter the current length of the list you are using")
            if listLength.isnumeric() == True:
                print("list length accepted")
                break
            else:
                print("invalid input")

        while True:
            upperBound = input("enter the highest spot on the list you want the roulette to be")
            lowerBound = input("enter the lowest spot on the list you want the roulette to be")
            if upperBound.isnumeric() == True and lowerBound.isnumeric() == True:
                if int(lowerBound) < int(upperBound) or (int(upperBound) + 99) > int(lowerBound):
                    print("invalid input, lower bound must be at least 100 spots below upper bound and list length must be at least 100")
                else:    
                    print("bounds accepted")
                    loopo = False
                    break
            else:
                print("invalid input, enter only numbers")
                
    lowerBound = int(lowerBound)
    upperBound = int(upperBound)
        



    file1 = open('demonRoulette.txt', 'w+')
    for i in range(0,int(listLength)):
        randomThing = random.randint(upperBound,lowerBound)
        theBigOne = file1.read()
        if str(randomThing) in theBigOne:
            print("ckoc")
            var = var + 1
        else:
            file1.write(str(randomThing))
            file1.write("\n")

    file1.close() 



def roulette():
    listArray = []
    file1 = open('demonRoulette.txt', 'r')

    for line in file1:
        listArray.append(line.rstrip())
    while True:
        position = input("enter position on the roulette you are at")
        if position.isdigit() == True:
            break
        else:
            print("invalid input")

    for i in range(int(position), 101):
        print(listArray[i-1])
        print(i,"%")
        print("\n")
        misc = input("press enter when finished level")

while True:
    choice = input("do you want to generate a new list or continue last one? Enter 1 or 2 accordingly")
    if choice == "1":
        randomGenerator()
        print("generated new roulette")
    elif choice == "2":
        roulette()
        break
    else:
        print("invalid input")
        


    
