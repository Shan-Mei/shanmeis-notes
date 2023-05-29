---
title: Year 8 Coding Investigation
---

## Year 8 Coding Investigation
The coding investigation was about congruency in triangles.  

#### Task PDF
<iframe src="/shanmeis-notes/assets/Year 8 Investigation - Mathematical Modelling and Congruent Triangles - FINAL.pdf"></iframe>

#### Code

```py
import math


def checkingSides1(): #function
    userCorrect = False #while loop breaker, to prevent runtime error
    while userCorrect == False: # while there are no errors
        sides1 = input('Enter lengths AB, AC and BC in that order, separated by spaces. If there are unknown values, write "NA" in place of the value: ') # inputting sides
        global splitSides1 # allowing the function to be used throughout the code
        splitSides1 = sides1.split() # splitting sides to separate values
        global sideAB1 
        try: # if the following doesnt' work
            sideAB1 = float(splitSides1[0]) # if side AB can be made into, a float, make it a float
        except: # if it can't be made a float
            sideAB1 = str(splitSides1[0]) # make it a string
        global sideAC1
        try:
            sideAC1 = float(splitSides1[1])
        except:
            sideAC1 = str(splitSides1[1])
        global sideBC1
        try:
            sideBC1 = float(splitSides1[2])
        except:
            sideBC1 = str(splitSides1[2])
        global floatCountSides1
        floatCountSides1 = 0 # counting the number of floats in the list. starts with 0 floats and will count up
        if isinstance(sideAB1, float): # if sideAB1 is a float
            floatCountSides1 = floatCountSides1 + 1 # add 1 to the float count
        if isinstance(sideAC1, float):
            floatCountSides1 = floatCountSides1 + 1
        if isinstance(sideBC1, float):
            floatCountSides1 = floatCountSides1 + 1
        if floatCountSides1 == 0: # if the float count is 0
            print("I'm sorry but if you do not input any sides, we are unable to check congruence. If you want to check congruence of a triangle, there must be at least 1 side inputted.") # then repeats the function, because we have not added userCorrect = True
        elif floatCountSides1 == 3: # if there are 3 floats:
            splitSides1.sort(reverse=False) # split the sides, and sort in decending order
            global biggestSide1
            biggestSide1 = max(splitSides1) # getting the biggest value
            biggestSide1 = float(biggestSide1) # making the value a float
            global mediumSide1
            mediumSide1 = float(splitSides1[1]) # getting the middle value
            mediumSide1 = float(mediumSide1)
            global smallestSide1
            smallestSide1 = min(splitSides1) # getting the smallest value
            smallestSide1 = float(smallestSide1)
            if (mediumSide1 + smallestSide1) <= biggestSide1: # if the sum of the medium and smallest value is equal or less than the biggest value
                print('These sides do not make up a valid triangle. The biggest side must be less than the lengths of the two smaller sides to be a triangle.') # identifies an error and restarts the code
            if (mediumSide1 + smallestSide1) >= biggestSide1: # if the triangle is valid
                userCorrect = True # breaks the loop
        elif floatCountSides1 == 1: # if there is only 1 side
            userCorrect = True # breaks the loop
        elif floatCountSides1 == 2:
            userCorrect = True

def checkingAngles1(): # function for first set of angles
    userCorrect = False
    while userCorrect == False:
        angles1 = input('Enter angles BAC, ABC and ACB in that order, separated by spaces. If there are unknown values, write "NA" in place of the value: ') #inputting angles
        global splitAngles1 #below is same process as the side splitting and trial-error
        splitAngles1 = angles1.split()
        global angleBAC1
        angleBAC1 = splitAngles1[0]
        try:
            angleBAC1 = float(angleBAC1)
        except:
            angleBAC1 = str(angleBAC1)
        global angleABC1
        angleABC1 = splitAngles1[1]
        try:
            angleABC1 = float(angleABC1)
        except:
            angleABC1 = str(angleABC1)
        global angleACB1
        angleACB1 = splitAngles1[2]
        try:
            angleACB1 = float(angleACB1)
        except:
            angleACB1 = str(angleACB1)
        global countingAngles1
        countingAngles1 = 0 # below is counting how many floats there are
        if isinstance(angleBAC1, float):
            countingAngles1 = countingAngles1 + 1
        if isinstance(angleABC1, float):
            countingAngles1 = countingAngles1 + 1
        if isinstance(angleACB1, float):
            countingAngles1 = countingAngles1 + 1
        if countingAngles1 == 0: # if there are no angles given
          if floatCountSides1 == 3: # if there were 3 values in the sides
            userCorrect = True # break loop
          elif floatCountSides1 == 2: # if there are only 2 sides
            error2 = input('You did not input any angles, and you only have 2 sides. You need at least 1 side if you inputted 2 sides. If you would like to go back to inputting your sides again, please type "sides". If you would like to reinput angles, please type "angles". If you would like to quit, enter "quit". ') #identifies error and prompts user for what they want to do.
            if error2 == "sides": # if the user inputted sides
              checkingSides1() # input sides again
            elif error2 == "angles": # if the user inputted angles
              checkingAngles1() # try this step again
            elif error2 == "quit": # if the user wants to stop
                exit() # exits the code completely
            else: # if the user didn't type anything or write something else
                print('There was an error, program aborted xP') # identify error
                exit() # exits code.
          if floatCountSides1 == 1: # if only 1 side inputted
            error2 = input('You did not input any angles, and you only have 2 sides. You need at least 1 side if you inputted 2 sides. If you would like to go back to inputting your sides again, please type "sides". If you would like to reinput angles, please type "angles". If you would like to quit, enter "quit". ') #runs code again
            if error2 == "sides":
              checkingSides1()
            elif error2 == "angles":
              checkingAngles1()
            elif error2 == "quit":
                exit()
            else:
                print('There was an error, program aborted xP')
                exit()
        elif countingAngles1 == 1: # if the user only inputted 1 angle
          if floatCountSides1 == 1: # if there is only one angle given
            error1 = input('You only inputted 1 angle and 1 side. We are unable to draw any congruency tests with this. If you would like to go back to inputting your sides again, please type "sides". If you would like to reinput angles, please type "angles". If you would like to quit, enter "quit". ') # identifies error and gives options
            if error1 == "sides": # directory below
              checkingSides1()
            elif error1 == "angles":
              checkingAngles1()
            elif error1 == "quit":
                exit()
            else:
                print('There was an error, program aborted xP')
                exit()
          if floatCountSides1 == 2: #if number of sides is 2
            userCorrect = True # break loop
        elif countingAngles1 == 2: # if there are 2 angles given
          if isinstance(angleBAC1, float):
            if isinstance(angleABC1, float):
              angleACB1 = 180 - (angleBAC1 + angleABC1) # finds missing angle
            elif isinstance(angleACB1, float): # tests with more combinations
              angleABC1 = 180 - (angleBAC1 + angleACB1)
          elif isinstance(angleABC1, float):
            if isinstance(angleACB1, float):
              angleBAC1 = 180 - (angleABC1 + angleACB1)
          if floatCountSides1 == 2: # if there were 2 sides given
            userCorrect = True
          elif floatCountSides1 == 1: # if there was 1 side given
            userCorrect = True
          elif floatCountSides1 == 3: # if there were 3 sides given
            userCorrect = True
        elif countingAngles1 == 3: # if there were 3 angles given
            angleSummary = angleABC1 + angleACB1 + angleBAC1 # sees the sum of the angles
            if angleSummary == 180: # if the sum is 180
                userCorrect = True # breaks loop
            else: # if not
                error180 = input('If you would like to go back to inputting your sides again, please type "sides". If you would like to reinput angles, please type "angles". If you would like to quit, enter "quit". ') # identifies error and gives options
                if error180 == "sides": # directory below
                    checkingSides1()
                elif error180 == "angles":
                    checkingAngles1()
                elif error180 == "quit":
                    exit()
                else:
                    print('There was an error, program aborted xP')
                    exit()
        userCorrect = True

def checkingSides2(): # this function is basically the same as the other sides one
    userCorrect = False
    while userCorrect == False:
        sides2 = input('Enter lengths PQ, PR and QR in that order, separated by spaces, where PQ = AB, PR = AC, QR = BC. If there are unknown values, write "NA" in place of the value: ')
        global splitSides2
        splitSides2 = sides2.split()
        global sidePQ
        try: 
            sidePQ = float(splitSides2[0])
        except:
            sidePQ = str(splitSides2[0])
        global sidePR
        try:
            sidePR = float(splitSides2[1])
        except:
            sidePR = str(splitSides2[1])
        global sideQR
        try:
            sideQR = float(splitSides2[2])
        except:
            sideQR = str(splitSides2[2])
        global countingSides2
        countingSides2 = 0
        if isinstance(sidePQ, float):
            countingSides2 = countingSides2 + 1
        if isinstance(sidePR, float):
            countingSides2 = countingSides2 + 1
        if isinstance(sideQR, float):
            countingSides2 = countingSides2 + 1
        if countingSides2 == 0:
            print("I'm sorry but if you do not input any sides, we are unable to check congruence. If you want to check congruence of a triangle, there must be at least 1 side inputted.")
        elif countingSides2 == 3:
            splitSides2.sort(reverse=False)
            global biggestSide2
            biggestSide2 = max(splitSides2)
            biggestSide2 = float(biggestSide2)
            global mediumSide2
            mediumSide2 = float(splitSides2[1])
            mediumSide2 = float(mediumSide2)
            global smallestSide2
            smallestSide2 = min(splitSides2)
            smallestSide2 = float(smallestSide2)
            if (mediumSide2 + smallestSide2) <= biggestSide2:
                print('These sides do not make up a valid triangle. The biggest side must be less than the lengths of the two smaller sides to be a triangle.')
            if (mediumSide2 + smallestSide2) >= biggestSide2:
                userCorrect = True
        elif countingSides2 == 1:
            userCorrect = True
        elif countingSides2 == 2:
            userCorrect = True

def checkingAngles2(): # basically the same as the last angles ones
    userCorrect = False
    while userCorrect == False:
        angles2 = input('Enter angles QPR, PQR and PRQ in that order, separated by spaces, where QPR = BAC, PQR = ABC, PRQ = ACB. If there are unknown values, write "NA" in place of the value: ')
        global splitAngles2
        splitAngles2 = angles2.split()
        global angleQPR1
        angleQPR1 = splitAngles2[0]
        try:
            angleQPR1 = float(angleQPR1)
        except:
            angleQPR1 = str(angleQPR1)
        global anglePQR1
        anglePQR1 = splitAngles2[1]
        try:
            anglePQR1 = float(anglePQR1)
        except:
            anglePQR1 = str(anglePQR1)
        global anglePRQ1
        anglePRQ1 = splitAngles2[2]
        try:
            anglePRQ1 = float(anglePRQ1)
        except:
            anglePRQ1 = str(anglePRQ1)
        global countingAngles2
        countingAngles2 = 0
        if isinstance(angleQPR1, float):
            countingAngles2 = countingAngles2 + 1
        if isinstance(anglePQR1, float):
            countingAngles2 = countingAngles2 + 1
        if isinstance(anglePRQ1, float):
            countingAngles2 = countingAngles2 + 1
        if countingAngles2 == 0:
            if countingSides2 == 3:
                userCorrect = True
            elif countingSides2 == 2:
                error2 = input('You did not input any angles, and you only have 2 sides. You need at least 1 side if you inputted 2 sides. If you would like to go back to inputting your first set of sides again, please type "restart". If you would like to reinput angles for the first time, please type "first angles". If you would like to enter your second set of sides again, please type "sides". If you would like to input angles for the second time again, please type "second angles". If you would like to quit, enter "quit". ')
                if error2 == "restart":
                    checkingSides1()
                elif error2 == "first angles":
                    checkingAngles1()
                elif error2 == "sides":
                    checkingSides2()
                elif error2 == "second angles":
                    checkingAngles2()
                elif error2 == "quit":
                    quit()
                else:
                    print('There was an error. The program aborted xP')
                    quit()
        elif countingAngles2 == 1:
          if countingSides2 == 1:
            error1 = input('You only inputted 1 angle and 1 side. We are unable to draw any congruency tests with this. If you would like to go back to inputting your first set of sides again, please type "restart". If you would like to reinput angles for the first time, please type "first angles". If you would like to enter your second set of sides again, please type "sides". If you would like to input angles for the second time again, please type "second angles". If you would like to quit, enter "quit". ')
            if error1 == "restart":
              checkingSides1()
            elif error1 == "first angles":
              checkingAngles1()
            elif error1 == "sides":
                checkingSides2()
            elif error1 == "second angles":
                checkingAngles2()
            elif error1 == "quit":
                exit()
            else:
                print('There was an error, program aborted xP')
                quit()
          if countingSides2 == 2:
            userCorrect = True
        elif countingAngles2 == 2: # if there are 2 angles given
          if isinstance(angleQPR1, float):
            if isinstance(anglePQR1, float):
              anglePRQ1 = 180 - (angleQPR1 + anglePQR1) # finds missing angle
            elif isinstance(anglePRQ1, float): # tests with more combinations
              anglePQR1 = 180 - (angleQPR1 + anglePRQ1)
          elif isinstance(anglePQR1, float):
            if isinstance(anglePRQ1, float):
              angleQPR1 = 180 - (anglePQR1 + anglePRQ1)
          if floatCountSides1 == 2: # if there were 2 sides given
            userCorrect = True
          elif floatCountSides1 == 1: # if there was 1 side given
            userCorrect = True
          elif floatCountSides1 == 3: # if there were 3 sides given
            userCorrect = True
        elif countingAngles2 == 3: # if there were 3 angles given
            angleSummary = anglePQR1 + anglePRQ1 + angleQPR1 # sees the sum of the angles
            if angleSummary == 180: # if the sum is 180
                userCorrect = True # breaks loop
            else: # if not
                error180 = input('The angles do not equal to a valid triangle. If you would like to go back to inputting your first set of sides again, please type "restart". If you would like to reinput angles for the first time, please type "first angles". If you would like to enter your second set of sides again, please type "sides". If you would like to input angles for the second time again, please type "second angles". If you would like to quit, enter "quit". ') # identifies error and gives options
                if error180 == "restart": # directory below
                    checkingSides1()
                elif error180 == "first angles":
                    checkingAngles1()
                elif error180 == "sides":
                    checkingSides2()
                elif error180 == "second angles":
                    checkingAngles2
                elif error180 == "quit":
                    exit()
                else:
                    print('There was an error, program aborted xP')
                    exit()

def pythagTheorum(a, b): # this assists witht he pythag() function that is upcoming
    global pythagTheorumVar
    pythagTheorumVar = math.sqrt((a*a) - (b*b)) # finding the missing side in a right angled triangle. Square of hypotenuse minus square of value is square of second value.
    print(pythagTheorumVar)

def arcPythagTheorum(a, b): # formula to find hypotenuse. the arc means that it's the reverse of the first pythag I used
    global arcPythagTheorumVar
    arcPythagTheorumVar = math.sqrt((a*a) + (b*b)) # square of value 1 + square of value 2 = square of hypotenuse.

def pythag(): # putting the pythag theorum into action
    global sideBC1
    global sideAB1
    global sideAC1
    global sidePQ
    global sidePR
    global sideQR
    global angleABC1
    global angleACB1
    global anglePQR1
    global anglePQR1
    global anglePRQ1
    global angleQPR1
    if angleABC1 == 90: # this is the beginning of brute forcing the pythag theorum possibilities. If ABC equals 90:
        if isinstance(sideAC1, float): # if AC is float
            if isinstance(sideAB1, float): # if AB is float
                sideBC1 = pythagTheorum(sideAC1, sideAB1) # store BC
            elif isinstance(sideBC1, float): # if BC is a float
                sideAB1 = pythagTheorum(sideAC1, sideBC1) # store AB
        elif isinstance(sideAC1, str): # if hypotenuse is unknown
            if isinstance(sideAB1,float): # if AB is a float
                if isinstance(sideBC1, float): # and if BC is a float too
                    sideAC1 = arcPythagTheorum(sideAB1, sideBC1) # store AC.
    elif angleACB1 == 90: # from here, the code repeats. 
        if isinstance(sideAB1, float):
            if isinstance(sideAC1,float):
                sideBC1 = pythagTheorum(sideAB1, sideAC1)
            elif isinstance(sideBC1, float):
                sideAC1 = pythagTheorum(sideAB1, sideBC1)
        elif isinstance(sideAB1, str):
            if isinstance(sideAC1, float):
                if isinstance(sideBC1, float):
                    sideAB1 = arcPythagTheorum(sideAC1, sideBC1)
    elif angleBAC1 == 90: # repeat
        if isinstance(sideBC1, float):
            if isinstance(sideAB1, float):
                sideAC1 = pythagTheorum(sideBC1, sideAB1)
            elif isinstance(sideAC1, float):
                sideAB1 = pythagTheorum(sideBC1, sideAC1)
        elif isinstance(sideBC1, str):
            if isinstance(sideAC1, float):
                if isinstance(sideAB1, float):
                    sideBC1 = arcPythagTheorum(sideAC1, sideAB1)
    elif anglePQR1 == 90: # set for the PQR triangle
        if isinstance(sidePR, float):
            if isinstance(sidePQ, float):
                sideQR = pythagTheorum(sidePR, sidePQ)
            elif isinstance(sideQR, float):
                sidePQ = pythagTheorum(sidePR, sideQR)
        elif isinstance(sidePR, str):
            if isinstance(sidePQ, float):
                if isinstance(sideQR, float):
                    sidePR = arcPythagTheorum(sidePQ, sideQR)
    elif anglePRQ1 == 90:
        if isinstance(sidePQ, float):
            if isinstance(sidePR, float):
                sideQR = pythagTheorum(sidePQ, sidePR)
            elif isinstance(sideQR, float):
                sidePR = pythagTheorum(sidePQ, sideQR)
        elif isinstance(sidePQ, str):
            if isinstance(sidePR, float):
                if isinstance(sideQR, float):
                    sidePQ = arcPythagTheorum(sidePR, sideQR)
    elif angleQPR1 == 90:
        if isinstance(sideQR, float):
            if isinstance(sidePR, float):
                sidePQ = pythagTheorum(sideQR, sidePR)
            elif isinstance(sidePQ, float):
                sidePR = pythagTheorum(sideQR, sidePQ)
        elif isinstance(sideQR, str):
            if isinstance(sidePR, float):
                if isinstance(sidePQ, float):
                    sideQR = arcPythagTheorum(sidePQ, sidePR)

def dictionaries(): # getting dictionaries
    global triangleABC # making the dictionary accessible everywhere
    triangleABC = { # the variable name
        'name':'Triangle ABC', # the triangle name
        'sides':{'AB':sideAB1, 'AC':sideAC1, 'BC':sideBC1}, # information threaded to the sides
        'angles':{'BAC':angleBAC1, 'ABC':angleABC1, 'ACB':angleACB1}, # information for angles
    }
    global trianglePQR # reoeat
    trianglePQR = {
        'name':'Triangle PQR',
        'sides':{'PQ':sidePQ, 'PR':sidePR, 'QR':sideQR},
        'angles':{'QPR':angleQPR1, 'PQR':anglePQR1, 'PRQ':anglePRQ1}
    }

def addingValues(): # function for if the user wants to update their triangles
    global sideBC1
    global sideAB1
    global sideAC1
    global sidePQ
    global sidePR
    global sideQR
    global angleABC1
    global angleACB1
    global angleBAC1
    global anglePQR1
    global anglePRQ1
    global angleQPR1
    global countingAngles1
    global floatCountSides1
    global countingAngles2
    global countingSides2
    while True: # while the loop isn't broken
        update = input("Would you like to update any value of either triangle? [Y/N]: ") # asking if the user wants to input anything new
        if update.upper() == 'N': # if they don't
            break # break the loop
        elif update.upper() == 'Y': # if they do want to change something
            triangle = input("Which triangle would you like to update? [ABC/PQR]: ") # asking for which triangle to update
            if triangle.upper() == 'ABC': # it it is ABC
                angleSide = input("Do you want to update: angle or side? [angles/sides]: ") # checking for which dimention
                if angleSide.lower() == 'angles': # if they want to update an angle
                    angle = input('Which angle do you want to update? [ACB/ABC/BAC]: ') # which angle to update
                    newValue = input("What is the new value?: ") # what to change the value to
                    triangleABC[angleSide][angle.upper()] = newValue # updates the dictionary
                    countingAngles1 = countingAngles1 + 1 # adds 1 to the angles count
                    if angle.upper() == 'ACB': # the below doens't do anything, just there for reference
                        angleACB1 = newValue
                    elif angle.upper() == 'ABC':
                        angleABC1 = newValue
                    elif angle.upper() == 'BAC':
                        angleBAC1 = newValue
                elif angleSide.lower() == 'sides': # if the user wants to update sides
                    side = input('Which side do you want to update? [AB/AC/BC]: ') # which sides to update
                    newValue = input("What is the new value?: ") # which value to change the side to
                    triangleABC[angleSide][side.upper()] = newValue # updates dictionary
                    floatCountSides1 = floatCountSides1 + 1 # adds 1 to side count
                    if side.upper() == "AB":
                        sideAB1 = newValue
                    elif side.upper() == 'AC':
                        sideAC1 = newValue
                    elif side.upper() == 'BC':
                        sideBC1 = newValue
                else: # if the user didn't enter anything or entered somthing else
                    print('There was an error, program aborted xP') # identify error
                    quit() # abort the whole program
            elif triangle.upper() == 'PQR': # if the want to update the PQR triangle
                angleSide = input("Do you want to update: angle or side? [angles/sides]: ") # the following is a repeat of what is above
                if angleSide.lower() == 'angles': 
                    angle = input('Which angle do you want to update? [PRQ/PQR/QPR]: ')
                    newValue = input("What is the new value?: ")
                    trianglePQR[angleSide][angle.upper()] = newValue
                    countingAngles2 = countingAngles2 + 1
                    if angle.upper() == 'PRQ':
                        anglePRQ1 = newValue
                    elif angle.upper() == 'PQR':
                        anglePQR1 = newValue
                    elif angle.upper() == 'QPR':
                        angleQPR1 = newValue
                elif angleSide.lower() == 'sides': 
                    side = input('Which side do you want to update? [PQ/PR/QR]: ')
                    newValue = input("What is the new value?: ")
                    trianglePQR[angleSide][side.upper()] = newValue
                    countingSides2 = countingSides2 + 1
                    if side.upper() == "PQ":
                        sidePQ = newValue
                    if side.upper() == 'PR':
                        sidePR = newValue
                    if side.upper() == 'QR':
                        sideQR = newValue
                else:
                    print('There was an error, program aborted xP')
                    quit()
            else:
                print('There was an error, program aborted xP')
                quit()
        else:
            print('There was an error, program aborted xP')
            quit()

def convertingDictionary(): # putting tha values back into variables
    global sideAB1
    global sideBC1
    global sideAC1
    global sidePQ
    global sidePR
    global sideQR
    global angleABC1
    global angleACB1
    global angleBAC1
    global anglePQR1
    global anglePRQ1
    global angleQPR1
    global floatCountSides1
    global countingSides2
    sideAB1 = triangleABC['sides']['AB'] # taking a value from the dictionary
    try: # try and except in making every value a float
        sideAB1 = float(sideAB1)
    except:
        sideAB1 = str(sideAB1)
    sideAC1 = triangleABC['sides']['AC'] # repeats
    try:
        sideAC1 = float(sideAC1)
    except:
        sideAC1 = str(sideAC1)
    sideBC1 = triangleABC['sides']['BC']
    try:
        sideBC1 = float(sideBC1)
    except:
        sideBC1 = str(sideBC1)
    sidePQ = trianglePQR['sides']['PQ']
    try:
        sidePQ = float(sidePQ)
    except:
        sidePQ = str(sidePQ)
    sidePR = trianglePQR['sides']['PR']
    try:
        sidePR = float(sidePR)
    except:
        sidePR = str(sidePR)
    sideQR = trianglePQR['sides']['QR']
    try:
        sideQR = float(sideQR)
    except:
        sideQR = str(sideQR)
    angleABC1 = triangleABC['angles']['ABC']
    try:
        angleABC1 = float(angleABC1)
    except:
        angleABC1 = str(angleABC1)
    angleACB1 = triangleABC['angles']['ACB']
    try:
        angleACB1 = float(angleACB1)
    except:
        angleACB1 = str(angleACB1)
    angleBAC1 = triangleABC['angles']['BAC']
    try:
        angleBAC1 = float(angleBAC1)
    except:
        angleBAC1 = str(angleBAC1)
    anglePQR1 = trianglePQR['angles']['PQR']
    try:
        anglePQR1 = float(anglePQR1)
    except:
        anglePQR1 = str(anglePQR1)
    angleQPR1 = trianglePQR['angles']['PRQ']
    try:
        angleQPR1 = float(angleQPR1)
    except:
        angleQPR1 = str(angleQPR1)
    angleQPR1 = trianglePQR['angles']['QPR']
    try:
        angleQPR1 = float(angleQPR1)
    except:
        angleQPR1 = str(angleQPR1)
    if isinstance(sideAB1, float): # checking for 3 sides, just in case the last one didn't work. Sometimes it will work, sometimes it wont, not too sure why, but it's there jsut to make sure
        if isinstance(sideAC1, float):
            if isinstance(sideBC1, float):
                floatCountSides1 = 3
    if isinstance(sidePQ, float):
        if isinstance(sidePR, float):
            if isinstance(sideQR, float):
                countingSides2 = 3

def sssCongruence(): # tests for sss congruency
    global sssCorrect
    sssCorrect = False # stores boolean for later function
    if sideAB1 != 'NA' and sideAC1 != 'NA' and sideBC1 != 'NA' and sidePQ != 'NA' and sideQR != 'NA' and sideQR != 'NA': # if all sides are given
        if sideAB1 == sidePQ: # if the corresponding sides equal
            if sideAC1 == sidePR:
                if sideBC1 == sideQR:
                    print('The triangles are SSS congruent.') # conclude congruency
                    print('AB = PQ') # providing evidence
                    print('''AC = PR
BC = QR''')
                    sssCorrect = True # changes boolean to true, stores for later

def sasCongruence(): # sas tests
    global sasCorrect
    sasCorrect = False
    sideAC1 = triangleABC['sides']['AC'] # getting side AC again, there were issues with getting this side before for an unknown reason
    try:
        sideAC1 = float(sideAC1)
    except:
        sideAC1 = str(sideAC1)
    if sideAB1 != 'NA' and sidePQ != 'NA' and sideAC1 != 'NA' and sidePR != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA': # if these values are floats
        if float(sideAB1) == float(sidePQ) and float(sideAC1) == float(sidePR): # checking corresponding sides
            if angleBAC1 == angleQPR1: # checking angles
                print('''The triangles are SAS congruent. 
AB = PQ
AC = PR
BAC = QPR''') # concluding statement
                sasCorrect = True # makes statement true
    elif sideAC1 != 'NA' and sidePR != 'NA' and sideBC1 != 'NA' and sideQR != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA': # basically repeats
        if sideAC1 == sidePR and sideBC1 == sideQR:
            if angleACB1 == anglePRQ1:
                print('''The triangles are SAS congruent.
AC = PR
BC = QR
ACB = PRQ''')
                sasCorrect = True
    elif sideBC1 != 'NA' and sideQR != 'NA' and sideAB1 != 'NA' and sidePQ != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA':
        if sideBC1 == sideQR and sideAB1 == sidePQ:
            if angleABC1 == anglePQR1:
                print('''The triangles are SAS congruent.
BC = QR
AB = PQ
ABC = PQR''')
                sasCorrect = True

def asaCongruence(): # asa tests
    global asaCorrect
    asaCorrect = False
    if sideAB1 != 'NA' and sidePQ != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA': #if these values are not NA'd
        if float(sideAB1) == float(sidePQ): # if the sides are equal
            if float(angleABC1) == float(anglePQR1) and float(angleACB1) == float(anglePRQ1): # if these angles are equal
                print('''The triangles are ASA congruent
AB = PQ
ABC = PQR
ACB = PRQ''') #congruency statement
                asaCorrect = True
    elif sideAB1 != 'NA' and sidePQ != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA': # repeat for the same side with different angle combination
        if float(sideAB1) == float(sidePQ):
            if float(angleABC1) == float(anglePQR1) and float(angleBAC1) == float(angleQPR1):
                print('''The triangles are ASA congruent
AB = PQ
ABC = PQR
BAC = QPR''')
                asaCorrect = True
    elif sideAB1 != 'NA' and sidePQ != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA':
        if float(sideAB1) == float(sidePQ):
            if float(angleACB1) == float(anglePRQ1) and float(angleBAC1) == float(angleQPR1):
                print('''The triangles are ASA congruent
AB = PQ
ACB = PRQ
BAC = QPR''')
                asaCorrect = True
    elif sideAC1 != 'NA' and sidePR != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA': # for a different side now
        if float(sideAC1) == float(sidePR):
            if float(angleABC1) == float(anglePQR1) and float(angleACB1) == float(anglePRQ1):
                print('''The triangles are ASA congruent
AC = PR
ABC = PQR
ACB = PRQ''')
                asaCorrect = True
    elif sideAC1 != 'NA' and sidePR != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA':
        if float(sideAC1) == float(sidePR):
            if float(angleABC1) == float(anglePQR1) and float(angleBAC1) == float(angleQPR1):
                print('''The triangles are ASA congruent
AC = PR
ABC = PQR
BAC = QPR''')
                asaCorrect = True
    elif sideAC1 != 'NA' and sidePR != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA':
        if float(sideAB1) == float(sidePQ):
            if float(angleACB1) == float(anglePRQ1) and float(angleBAC1) == float(angleQPR1):
                print('''The triangles are ASA congruent
AB = PQ
ACB = PRQ
BAC = QPR''')
                asaCorrect = True
    elif sideBC1 != 'NA' and sideQR != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA':
        if float(sideAC1) == float(sideQR): # next set of sides and angles
            if float(angleABC1) == float(anglePQR1) and float(angleACB1) == float(anglePRQ1): 
                print('''The triangles are ASA congruent
BC = QR
ABC = PQR
ACB = PRQ''')
                asaCorrect = True
    elif sideBC1 != 'NA' and sideQR != 'NA' and angleABC1 != 'NA' and anglePQR1 != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA':
        if float(sideBC1) == float(sideQR):
            if float(angleABC1) == float(anglePQR1) and float(angleBAC1) == float(angleQPR1):
                print('''The triangles are ASA congruent
BC = QR
ABC = PQR
BAC = QPR''')
                asaCorrect = True
    elif sideBC1 != 'NA' and sideQR != 'NA' and angleACB1 != 'NA' and anglePRQ1 != 'NA' and angleBAC1 != 'NA' and angleQPR1 != 'NA':
        if float(sideAB1) == float(sideQR):
            if float(angleACB1) == float(anglePRQ1) and float(angleBAC1) == float(angleQPR1):
                print('''The triangles are ASA congruent
BC = QR
ACB = PRQ
BAC = QPR''')
                asaCorrect = True
                
def rhsCongruence(): # rhs tests
    global rhsCorrect
    rhsCorrect = False
    if angleABC1 == 90: # if there is a 90 degree angle at the angle
        if isinstance(sideAC1, float): # if AC is float
            if isinstance(sideAB1, float): # if AB is float
                if anglePQR1 == 90: # if the other triangle's corresponding angle is also 90 degrees
                    if isinstance(sidePR, float): # if PR is float
                        if isinstance(sidePQ, float): # if PQ is float
                            print('''The triangles are RHS congruence.
ABC and PQR = 90 degrees
Hypotenuses AC and PR are equal
AB = PQ''') # congruency statement
                            rhsCorrect = True
            elif isinstance(sideBC1, float): # if instead, this angle is float
                if anglePQR1 == 90: # redo of angle check
                    if isinstance(sidePR, float): # if hypotenuse is float
                        if isinstance(sideQR, float): # if the "side" is float
                            print('''The triangles are RHS congruence.
ABC and PQR = 90 degrees
Hypotenuses AC and PR are equal
BC = QR''') # conclude congruence
                            rhsCorrect = True
    elif angleACB1 == 90: # repeat for all 3 angles
        print(angleACB1)
        if isinstance(sideAB1, float):
            if isinstance(sideAC1, float):
                if anglePRQ1 == 90:
                    if isinstance(sidePQ, float):
                        if isinstance(sidePR, float):
                            print('''The triangles are RHS congruence.
ACB and PRQ = 90 degrees
Hypotenuses AB and PQ are equal
AC = PR''')
                            rhsCorrect = True
            elif isinstance(sideBC1, float):
                if anglePRQ1 == 90:
                    if isinstance(sidePQ, float):
                        if isinstance(sideQR, float):
                            print('''The triangles are RHS congruence.
ACB and PRQ = 90 degrees
Hypotenuses AB and PQ are equal
BC = QR''')
                            rhsCorrect = True
    elif angleBAC1 == 90:
        print(angleBAC1)
        if isinstance(sideBC1, float):
            if isinstance(sideAB1, float):
                if angleQPR1 == 90:
                    if isinstance(sideQR, float):
                        if isinstance(sidePQ, float):
                            print('''The triangles are RHS congruence.
BAC and QPR = 90 degrees
Hypotenuses BC and QR are equal
AB = PQ''')
                            rhsCorrect = True
            elif isinstance(sideAC1, float):
                if angleQPR1 == 90:
                    if isinstance(sideQR, float):
                        if isinstance(sidePR, float):
                            print('''The triangles are RHS congruence.
ACB and PRQ = 90 degrees
Hypotenuses AB and PQ are equal
AC = PR''')
                            rhsCorrect = True
        
def finalStatements(): # testing for any congruency
    if sssCorrect == False: # if there are absolutely no congruence statements drawn
        if sasCorrect == False:
            if asaCorrect == False:
                if rhsCorrect == False:
                    print('Your triangles are not congruent or do not have enough information to conclude congruence') # state lack of congruency.

# the following is when I call the functions into the code. 
checkingSides1()
checkingAngles1()
checkingSides2()
checkingAngles2()
pythag()
dictionaries()
addingValues()
convertingDictionary()
sssCongruence()
sasCongruence()
asaCongruence()
rhsCongruence()
finalStatements()
```
