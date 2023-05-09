---
title: Year 9 Math Investigation
---

## Year 9 Math Investigation

#### Task PDF
<iframe src="/shanmeis-notes/assets/Year 9 Mathematics Investigation - Computational Algorithms for Modeling Compound Interest.pdf"></iframe>

#### Code
```py
Table = { # Start of the table
   'day': { #Define day and its conversions
      'day': 1, #the following is how many of this in a day
      'week': 1/7,
      'month': 1/30,
      'quarter': 1/90,
      'year': 1/365,
      'hour': 24,
      '10 minutes': 144,
   },
      'week': { #Define week and its conversions
      'day': 7, #How many of this in a week
      'week': 1,
      'month': 7/30,
      'quarter': 7/90,
      'year': 1/52,
      'hour': 268,
      '10 minutes': 1008,
   },
      'month': { #||
      'day': 30,
      'week': 30/7,
      'month': 1,
      'quarter': 1/3,
      'year': 30/365,
      'hour': 720,
      '10 minutes': 4320,
   },
      'quarter': {
      'day': 90,
      'week': 90/7,
      'month': 3,
      'quarter': 1,
      'year': 365/90,
      'hour': 2160,
      '10 minutes': 12960,
   },
   'year': {
      'day': 365,
      'week': 52,
      'month': 365/30,
      'quarter': 365/90,
      'year': 1,
      'hour': 8760,
      '10 minutes': 52560,
   },
}

def sectionOne():
   print("≿━━━━༺❀༻━━━━≾")
   print('I am going to help you compare a simple interest (si) to a compound interest (ci) account') #Introduction
   print("≿━━━━༺❀༻━━━━≾")
   print("SIMPLE INTEREST ACCOUNT") #SI account
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #Starts of the while loop
   while userCorrect == False: #While userCorrect is false
      siPrincipal = input("Enter the principal amount in $: ") #Prompts user to enter principal
      try: #try and except fuction, to test if the value inputted is a float - error handling
         siPrincipal = float(siPrincipal) #the program tries to do this
         userCorrect = True #if the above is successfuly done, this breaks the while loop
      except: #if the floating is not successfully done
         print('The value you entered is not a number, please try again.') #Tells the user that it is an invalid time, doesn't break the while loop and brings user back to line 44
   userCorrect = False #Sets usercorrect to false
   while userCorrect == False: #while the usercorrect is false
      siInterest = input("Enter the interest rate (enter 5% as 5): ") #Asks for input
      try: #error handling
         siInterest = float(siInterest)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False #Sets usercorrect to false
   while userCorrect == False: #while the usercorrect is false
      siInterestRate = input("Enter the interest rate time unit (year, quarter, month, week, day): ") #asks for the unit input
      if siInterestRate == "year": #if year is inputted
         userCorrect = True #breaks loop
      elif siInterestRate == "quarter": #if quarter is inputted
         userCorrect = True #breaks loop
      elif siInterestRate == "month": #etc
         userCorrect = True
      elif siInterestRate == "week":
         userCorrect = True
      elif siInterestRate == "day":
         userCorrect = True
      else: #if the user did not input the above
         print('The value you entered is not a time unit, please try again.') #tells user there is an error and brings them back to line 60
   print("COMPOUND INTEREST ACCOUNT") #CI account
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #usercorrect business
   while userCorrect == False:
      ciPrincipal = input("Enter the principal amount in $: ")
      try:
         ciPrincipal = float(ciPrincipal)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False #etc
   while userCorrect == False:
      ciInterest = input("Enter the interest rate (enter 5% as 5): ")
      try:
         ciInterest = float(ciInterest)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False #etc
   while userCorrect == False:
      ciInterestRate = input("Enter the interest rate time unit (year, quarter, month, week, day): ")
      if ciInterestRate == "year":
         userCorrect = True
      elif ciInterestRate == "quarter":
         userCorrect = True
      elif ciInterestRate == "month":
         userCorrect = True
      elif ciInterestRate == "week":
         userCorrect = True
      elif ciInterestRate == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False #sets usercorrect to false
   while userCorrect == False: #asks for compounding unit
      compoundingRate = input("Enter the compounding period time unit (year, quarter, month, week, day, custom): ") #asks for input
      if compoundingRate == "year": #error handling process
         userCorrect = True
      elif compoundingRate == "quarter":
         userCorrect = True
      elif compoundingRate == "month":
         userCorrect = True
      elif compoundingRate == "week":
         userCorrect = True
      elif compoundingRate == "day":
         userCorrect = True
      elif compoundingRate == "custom": #if the user enters custom as their compounding unit
         customCheck = "Pend" #sets a different version of "usercorrect," namely "customcheck." "Pend" is used as the "boolean"
         while customCheck =="Pend": #if the customcheck is set to pend
            ciCustomCompoundingRate = input("Enter the number of compounding periods per interest rate time unit: ") #asks for how many compounding periods there are
            try: #error handling
               compoundingRate = float(ciCustomCompoundingRate)
               customCheck = "Done" #checks customcheck
               userCorrect = True #checks usercorrect
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   print("Future projection timeframe for both accounts:") #tells user they are going to enter data regarding projection timeframes
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #error handling
   while userCorrect == False:
      projectionTime = input("Enter the amount of time to project into the future: ")
      try:
         projectionTime = float(projectionTime)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      projectionUnit = input("Enter the projection time unit (year, quarter, month, week, day): ")
      if projectionUnit == "year":
         userCorrect = True
      elif projectionUnit == "quarter":
         userCorrect = True
      elif projectionUnit == "month":
         userCorrect = True
      elif projectionUnit == "week":
         userCorrect = True
      elif projectionUnit == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   print("≿━━━━༺❀༻━━━━≾")
   print(f"SI Account: P = {siPrincipal}, r = {siInterest}% per {siInterestRate}") #prints the stats of the si account
   print(f"CI Account: P = {ciPrincipal}, r = {ciInterest}% per {ciInterestRate}, Compounding Frequency = {compoundingRate}") #prints the stats of the ci account
   print(f"Projection timeframe: {projectionTime} {projectionUnit}") #prints the projection stats
   print("≿━━━━༺❀༻━━━━≾")
   #the program now attempts to figure out the simple interest
   if projectionUnit == siInterestRate: #if the projection unit is equivalent to the interest rate
      siProjectedInterest = siPrincipal*(siInterest/100)*(projectionTime) #uses the si formula, Prn, to solve the interest
      siProjectedAmount = siPrincipal+siProjectedInterest #adds the new interest to the principal to find out the total amount earned.
   else: #if the projection unit is unfortunately not equivalent to the interest rate
      siNewInterest = (Table[projectionUnit][siInterestRate])*siInterest #retrieves info from the conversions table.
      siProjectedInterest = siPrincipal*(siNewInterest/100)*projectionTime # uses the simple interest formula
      siProjectedAmount = siProjectedInterest+siPrincipal #||
   print(f"SI Account projected amount: ${round(siProjectedAmount, 2)}, Interest earned: ${round(siProjectedInterest, 2)}") #prints the simple interest values
   #program now attempts to figure out compound interest
   if projectionUnit == compoundingRate: #if the projection unit is equal to the compounding rate
      ciProjectedAmount = ciPrincipal*(1 + (ciInterest/100))**(projectionTime) #uses the ci formula to find the total amount
      ciProjectedInterest = ciProjectedAmount-ciPrincipal #new total minus principal to find interest
   else: #if the projection unit is unfortunately not eqal to the compounding rate
      ciNewInterest = ciInterest/(Table[ciInterestRate][compoundingRate]) #retrieves info from the conversion table
      ciNewProjection = (Table[projectionUnit][compoundingRate])*projectionTime #figures out the new projecting unit
      ciProjectedAmount = ciPrincipal*(1+(ciNewInterest/100))**ciNewProjection #uses the ci formula
      ciProjectedInterest = ciProjectedAmount-ciPrincipal #find the interest by minusing the principal from the new total
   print(f"CI Account projected amount: ${round(ciProjectedAmount, 2)}, Interest earned: ${round(ciProjectedInterest, 2)}") #prints the ci stats
   userCorrect = False #sets usercorrect to false
   print("≿━━━━༺❀༻━━━━≾")
   while userCorrect == False: #while usercorrect is false
      menuQuestion = input("Would you like to quit, repeat the module or return to main menu? (quit/repeat/menu): ") #asks the user if they want to quit, restart or return to main menu.
      if menuQuestion == "quit": #if the user chooses quit
         userCorrect = True #checks usercorrect
         exit() #exits code
      elif menuQuestion == "repeat": #if the user chooses repeat
         userCorrect = True #checks usercorrect
         sectionOne() #goes back to section 1
      elif menuQuestion == "menu": #if the user chooses menu
         userCorrect = True #checks usercorrect
         mainMenu() #goes to main menu
      else: #if none of these values were entered
         print("The value you entered did not correspond to the options, please try again.") #prompts the user to try again.

def sectionTwo():
   print("≿━━━━༺❀༻━━━━≾")
   print('I will help your CI account reach a target amount.') #tells the user
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #error handling
   while userCorrect == False:
      ciPrincipal = input("Enter the principal amount in $: ")
      try:
         ciPrincipal = float(ciPrincipal)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False #etc
   while userCorrect == False:
      ciInterest = input("Enter the interest rate (enter 5% as 5): ")
      try:
         ciInterest = float(ciInterest)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False #etc
   while userCorrect == False:
      ciInterestRate = input("Enter the interest rate time unit (year, quarter, month, week, day): ")
      if ciInterestRate == "year":
         userCorrect = True
      elif ciInterestRate == "quarter":
         userCorrect = True
      elif ciInterestRate == "month":
         userCorrect = True
      elif ciInterestRate == "week":
         userCorrect = True
      elif ciInterestRate == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False #etc
   while userCorrect == False:
      compoundingRate = input("Enter the compounding period time unit (year, quarter, month, week, day, custom): ")
      if compoundingRate == "year":
         userCorrect = True
      elif compoundingRate == "quarter":
         userCorrect = True
      elif compoundingRate == "month":
         userCorrect = True
      elif compoundingRate == "week":
         userCorrect = True
      elif compoundingRate == "day":
         userCorrect = True
      elif compoundingRate == "custom":
         customCheck = "Pend"
         while customCheck =="Pend":
            ciCustomCompoundingRate = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               compoundingRate = float(ciCustomCompoundingRate)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      ciTargetAmount = input("Enter target amount $: ")
      try:
         ciTargetAmount = float(ciTargetAmount)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   print("≿━━━━༺❀༻━━━━≾")
   print(f"CI Account: P = ${str(ciPrincipal)}, r = {str(ciInterest)}% per {str(ciInterestRate)}, Compounding frequency = {str(compoundingRate)}, Target amount = ${str(ciTargetAmount)}") #prints the info of the ci account
   ciTester = 0 #sets the number of n to 0, for testing for goal
   appender = float(0) #sets the appender, which will add values to the projection, to 0
   projection = [ciPrincipal] #sets the projection list as "ciPrincipal"
   userCorrect = False #sets userCorrect to false
   while userCorrect == False: #while the usercorrect is false
      if float(appender) < float(ciTargetAmount): #if the target amount is larger than the appender
         ciTester = ciTester+1 #add one to the ci testor
         appender = ciPrincipal*(1 + (ciInterest/100))**(ciTester) #sets the appender using the ci interest formula and the ci tester
         appender = round(appender, 2) #rounds appender to 2 dp
         projection.append(appender) #appends the appender into the projection list
      else: #if the appender is larger than the target amount
         userCorrect = True #break the while loop
   print("≿━━━━༺❀༻━━━━≾")
   print(f"Forward projection: {projection}") #prints the forward projection
   print(f"Time taken: {len(projection) - 1} {compoundingRate}") #prints how long many units it took to reach the target amount by finding the length of the list minus 1
   userCorrect = False #main menu options
   print("≿━━━━༺❀༻━━━━≾")
   while userCorrect == False:
      menuQuestion = input("Would you like to quit, repeat the module or return to main menu? (quit/repeat/menu): ")
      if menuQuestion == "quit":
         userCorrect = True
         exit()
      elif menuQuestion == "repeat":
         userCorrect = True
         sectionTwo()
      elif menuQuestion == "menu":
         userCorrect = True
         mainMenu()
      else:
         print("The value you entered did not correspond to the options, please try again.")

def sectionThree():
   print("≿━━━━༺❀༻━━━━≾")
   print('I will help you compare two CI accounts') #Tells the user that they are going to be comparing two ci accounts
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #taken from section 1 and doubled and pasted.
   while userCorrect == False:
      ci1Principal = input("Enter the first principal amount in $: ")
      try:
         ci1Principal = float(ci1Principal)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False
   while userCorrect == False:
      ci2Principal = input("Enter the second principal amount in $: ")
      try:
         ci2Principal = float(ci2Principal)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False 
   while userCorrect == False:
      ci1Interest = input("Enter the first interest rate (enter 5% as 5): ")
      try:
         ci1Interest = float(ci1Interest)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False
   while userCorrect == False:
      ci2Interest = input("Enter the second interest rate (enter 5% as 5): ")
      try:
         ci2Interest = float(ci2Interest)
         userCorrect = True
      except:
         print('The value you entered is not a number, please try again.')
   userCorrect = False 
   while userCorrect == False:
      ci1InterestRate = input("Enter the first interest rate time unit (year, quarter, month, week, day): ")
      if ci1InterestRate == "year":
         userCorrect = True
      elif ci1InterestRate == "quarter":
         userCorrect = True
      elif ci1InterestRate == "month":
         userCorrect = True
      elif ci1InterestRate == "week":
         userCorrect = True
      elif ci1InterestRate == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      ci2InterestRate = input("Enter the second interest rate time unit (year, quarter, month, week, day): ")
      if ci2InterestRate == "year":
         userCorrect = True
      elif ci2InterestRate == "quarter":
         userCorrect = True
      elif ci2InterestRate == "month":
         userCorrect = True
      elif ci2InterestRate == "week":
         userCorrect = True
      elif ci2InterestRate == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      compounding1Rate = input("Enter the first compounding period time unit (year, quarter, month, week, day, custom): ")
      if compounding1Rate == "year":
         userCorrect = True
      elif compounding1Rate == "quarter":
         userCorrect = True
      elif compounding1Rate == "month":
         userCorrect = True
      elif compounding1Rate == "week":
         userCorrect = True
      elif compounding1Rate == "day":
         userCorrect = True
      elif compounding1Rate == "custom":
         customCheck = "Pend"
         while customCheck =="Pend":
            ci1CustomCompoundingRate = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               compounding1Rate = float(ci1CustomCompoundingRate)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      compounding2Rate = input("Enter the second compounding period time unit (year, quarter, month, week, day, custom): ")
      if compounding2Rate == "year":
         userCorrect = True
      elif compounding2Rate == "quarter":
         userCorrect = True
      elif compounding2Rate == "month":
         userCorrect = True
      elif compounding2Rate == "week":
         userCorrect = True
      elif compounding2Rate == "day":
         userCorrect = True
      elif compounding2Rate == "custom":
         customCheck = "Pend"
         while customCheck =="Pend":
            ci2CustomCompoundingRate = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               compounding2Rate = float(ci2CustomCompoundingRate)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      projection1Time = input("Enter the amount of time to project into the future for your first account: ")
      try:
         projection1Time = float(projection1Time)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      projection2Time = input("Enter the amount of time to project into the future for your second account: ")
      try:
         projection2Time = float(projection2Time)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      projection1Unit = input("Enter the first projection time unit (year, quarter, month, week, day): ")
      if projection1Unit == "year":
         userCorrect = True
      elif projection1Unit == "quarter":
         userCorrect = True
      elif projection1Unit == "month":
         userCorrect = True
      elif projection1Unit == "week":
         userCorrect = True
      elif projection1Unit == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      projection2Unit = input("Enter the second projection time unit (year, quarter, month, week, day): ")
      if projection2Unit == "year":
         userCorrect = True
      elif projection2Unit == "quarter":
         userCorrect = True
      elif projection2Unit == "month":
         userCorrect = True
      elif projection2Unit == "week":
         userCorrect = True
      elif projection2Unit == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   ci1Tester = float(0) #figuring out ci interest and principals
   appender1 = float(0)
   projection1 = [ci1Principal]
   userCorrect = False
   while userCorrect == False:
      if float(ci1Tester) < projection1Time:
         ci1Tester = ci1Tester+1
         appender1 = ci1Principal*(1 + (ci1Interest/100))**(ci1Tester)
         appender1 = round(appender1, 2)
         projection1.append(appender1)
      else:
         userCorrect = True
   ci2Tester = float(0)
   appender2 = float(0)
   projection2 = [ci2Principal]
   userCorrect = False
   while userCorrect == False:
      if float(ci2Tester) < float(projection2Time):
         ci2Tester = ci2Tester+1
         appender2 = ci2Principal*(1 + (ci2Interest/100))**(ci2Tester)
         appender2 = round(appender2, 2)
         projection2.append(appender2)
      else:
         userCorrect = True
   print("≿━━━━༺❀༻━━━━≾")
   print(f"CI Account One: P = ${str(ci1Principal)}, r = {str(ci1Interest)}% per {str(ci1InterestRate)}, Compounding frequency = {str(compounding1Rate)}, Projection rate = {projection1Time} {projection1Unit}")
   print(f"CI Account Two: P = ${str(ci2Principal)}, r = {str(ci2Interest)}% per {str(ci2InterestRate)}, Compounding frequency = {str(compounding2Rate)}, Projection rate = {projection2Time} {projection2Unit}")
   print("≿━━━━༺❀༻━━━━≾")
   print(f"Forward projection for Account 1 {projection1}")
   print(f"Forward projection for Account 2 {projection2}")
   userCorrect = False #main menu options
   print("≿━━━━༺❀༻━━━━≾")
   while userCorrect == False:
      menuQuestion = input("Would you like to quit, repeat the module or return to main menu? (quit/repeat/menu): ")
      if menuQuestion == "quit":
         userCorrect = True
         exit()
      elif menuQuestion == "repeat":
         userCorrect = True
         sectionThree()
      elif menuQuestion == "menu":
         userCorrect = True
         mainMenu()
      else:
         print("The value you entered did not correspond to the options, please try again.")

def sectionFour():
   print("≿━━━━༺❀༻━━━━≾")
   print("Compound Interest account with regular deposits") #tells the user the program is going to help them with deposits
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #inputs with error handling
   while userCorrect == False:
      principal = input("Enter the principal amount in $: ")
      try:
         principal = float(principal)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      interest = input("Enter the interest rate (enter 5% as 5): ")
      try:
         interest = float(interest)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      interestUnit = input("Enter the interest rate time unit (year, quarter, month, week, day): ")
      if interestUnit == "year":
         userCorrect = True
      elif interestUnit == "quarter":
         userCorrect = True
      elif interestUnit == "month":
         userCorrect = True
      elif interestUnit == "week":
         userCorrect = True
      elif interestUnit == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      compoundingUnit = input("Enter the compounding period time unit (year, quarter, month, week, day, custom): ")
      if compoundingUnit == "year":
         userCorrect = True
      elif compoundingUnit == "quarter":
         userCorrect = True
      elif compoundingUnit == "month":
         userCorrect = True
      elif compoundingUnit == "week":
         userCorrect = True
      elif compoundingUnit == "day":
         userCorrect = True
      elif compoundingUnit == "custom":
         customCheck = "Pend"
         while customCheck == "Pend":
            customCompoundingUnit = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               compoundingUnit = float(customCompoundingUnit)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      depositAmount = input("Enter the regular deposit amount per compounding period $: ") #asks the user for their depositing amount
      try: #error handling
         depositAmount = float(depositAmount)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      projectionAmount = input("Enter the dollar amount to project to (if you enter 0, you will be asked for the amount of time to project for): ") #asks for the dollar amount they want to project to (the user's goal)
      try: 
         projectionAmount = float(projectionAmount) #tries to float the amount
         if projectionAmount == float(0): #if the float amount is 0
            customCheck = "Pend" #then enact customCheck process
            while customCheck == "Pend":
               projectionTime = input("In that case, enter the amount of time to project for: ") # asks them for the amount of time they want to project for, since they entered 0
               try: #second set of error handling
                  projectionTime = float(projectionTime) #tries to float the projection time
                  customCheck = "done" #ticks customcheck
                  userCorrect = True #ticks usercorrect
               except: #if it is not a number
                  print("The value you entered is not a number, please try again.") #if the value they entered for projection time was not a float, then it would prompt the user to retry
         else: #if the float is not 0
            userCorrect = True #checks usercorrect
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False #continuing with the normal processes
   while userCorrect == False:
      projectionUnit = input("Enter the projection time unit (year, quarter, month, week, day, custom): ")
      if projectionUnit == "year":
         userCorrect = True
      elif projectionUnit == "quarter":
         userCorrect = True
      elif projectionUnit == "month":
         userCorrect = True
      elif projectionUnit == "week":
         userCorrect = True
      elif projectionUnit == "day":
         userCorrect = True
      elif projectionUnit == "custom":
         customCheck = "Pend"
         while customCheck == "Pend":
            projectionUnitRate = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               projectionUnit = float(projectionUnitRate)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   print("≿━━━━༺❀༻━━━━≾")
   openingAmountList = [] #sets the opening list to the principal
   interestList = [] #sets the interest list to the current interest
   regularDepositList = [] #sets depo list of currect depo
   closingAmountList = [] #sets closing list to the above closing amount
   counter = 0
   appender = principal #sets the first appender to the principle. the first appender is the principal + interest
   appender2 = principal #sets second appender to the principal (the new principal tester). This is the result which gets carried fromt he closing amount to the next opening
   appender3 = principal #sets third appender (the new principal tester 2). This is the appender that saves the old principal
   interestAppend = 0 #makes an interest appender exist
   if projectionAmount == 0: #if the projection amount was 0
      if projectionUnit == compoundingUnit: #if the projection unit is equal to the compounding rate 
         while counter < projectionTime: #if the counter (used as n) is smaller than the projection time
            counter = counter + 1 #adds one to the counter
            appender3 = appender2 #sets the "new principle" to the appender
            appender = appender2*(1 + (interest/100))**1 #uses the ci formula to find the total amount, with the counter
            appender = round(appender, 2) #rounds the appender to 2 dp
            openingAmountList.append(appender2) #appends the second appender (new principal)
            interestAppend = appender - appender3 #finds the interest but taking the appender 3 from the appender
            interestList.append(round(interestAppend, 2)) #appends the interest
            regularDepositList.append(depositAmount) #appends the deposit amount
            appender2 = appender + depositAmount #sets the appender two to appender (with interest) + deposit
            closingAmountList.append(appender2)
      else: #if the projection unit is unfortunately not eqal to the compounding rate
         newInterest = (Table[projectionUnit][compoundingUnit])*projectionTime #figures out the new projecting unit
         while counter < projectionTime: #continues
            counter = counter + 1
            appender3 = appender
            appender = appender2*(1+(newInterest/100))**1
            appender = round(appender, 2)
            openingAmountList.append(appender2)
            interestAppend = appender - appender3
            interestList.append(round(interestAppend, 2))
            regularDepositList.append(depositAmount)
            appender2 = appender + depositAmount
            closingAmountList.append(appender2)
   else:
      if projectionUnit == compoundingUnit: #if the projection unit is equal to the compounding rate
         while appender2 < projectionAmount: #does same functions as above
            counter = counter + 1
            appender3 = appender
            appender = principal*(1 + (interest/100))**(counter)
            appender = round(appender, 2)
            openingAmountList.append(appender)
            interestAppend = appender - appender3
            interestList.append(round(interestAppend, 2))
            regularDepositList.append(depositAmount)
            appender2 = appender + depositAmount
            closingAmountList.append(appender2)
      else:
         newInterest = (Table[projectionUnit][compoundingUnit])*projectionTime #figures out the new projecting unit
         while appender2 < projectionTime: #etc
            counter = counter + 1
            appender = principal*(1+(newInterest/100))**counter #uses the ci formula
            appender = round(appender, 2)
            openingAmountList.append(appender)
            interestList.append(interest)
            regularDepositList.append(depositAmount)
            appender2 = appender + depositAmount
            closingAmountList.append(appender2)
   zippedLists = zip(openingAmountList, interestList, regularDepositList, closingAmountList) #zips all the lists. Makes it so a list is made with the first val of each list, then the second, and etc
   print("Column Headings: Opening amount, Interest, Deposit, Final amount") #prints the titles of the zipped list columns
   for row in list(zippedLists): #for every list in the zipped lists
      print(row) #print each list as a row
   userCorrect = False #main menu options
   print("≿━━━━༺❀༻━━━━≾")
   while userCorrect == False:
      menuQuestion = input("Would you like to quit, repeat the module or return to main menu? (quit/repeat/menu): ")
      if menuQuestion == "quit":
         userCorrect = True
         exit()
      elif menuQuestion == "repeat":
         userCorrect = True
         sectionFour()
      elif menuQuestion == "menu":
         userCorrect = True
         mainMenu()
      else:
         print("The value you entered did not correspond to the options, please try again.")

def sectionFive():
   print("≿━━━━༺❀༻━━━━≾")
   print("Modelling missed loan payments in compound interest") #tells the user that they are going to be helped with modelling missed loan payments
   print("≿━━━━༺❀༻━━━━≾")
   userCorrect = False #does the inputting and error handling system
   while userCorrect == False:
      principal = input('Enter the principal amount in $: ')
      try:
         principal = float(principal)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      interest = input("Enter the interest rate (enter 5% as 5): ")
      try:
         interest = float(interest)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      interestUnit = input("Enter the interest rate time unit (year, quarter, month, week, day): ")
      if interestUnit == "year":
         userCorrect = True
      elif interestUnit == "quarter":
         userCorrect = True
      elif interestUnit == "month":
         userCorrect = True
      elif interestUnit == "week":
         userCorrect = True
      elif interestUnit == "day":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      compoundingUnit = input("Enter the compounding period time unit (year, quarter, month, week, day, custom): ")
      if compoundingUnit == "year":
         userCorrect = True
      elif compoundingUnit == "quarter":
         userCorrect = True
      elif compoundingUnit == "month":
         userCorrect = True
      elif compoundingUnit == "week":
         userCorrect = True
      elif compoundingUnit == "day":
         userCorrect = True
      elif compoundingUnit == "custom":
         customCheck = "Pend"
         while customCheck == "Pend":
            customCompoundingUnit = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               compoundingUnit = float(customCompoundingUnit)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      projectionTime = input("Enter the amount of time to project into the future: ")
      try:
         projectionTime = float(projectionTime)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      projectionUnit = input("Enter the projection time unit (year, quarter, month, week, day, custom): ")
      if projectionUnit == "year":
         userCorrect = True
      elif projectionUnit == "quarter":
         userCorrect = True
      elif projectionUnit == "month":
         userCorrect = True
      elif projectionUnit == "week":
         userCorrect = True
      elif projectionUnit == "day":
         userCorrect = True
      elif projectionUnit == "custom":
         customCheck = "Pend"
         while customCheck == "Pend":
            projectionUnitRate = input("Enter the number of compounding periods per interest rate time unit: ")
            try:
               projectionUnit = float(projectionUnitRate)
               customCheck = "Done"
               userCorrect = True
            except:
               print("The value you entered is not a number, please try again.")
      else:
         print('The value you entered is not a time unit, please try again.')
   userCorrect = False
   while userCorrect == False:
      missedProjectionNumber = input("At which projection was the loan payment missed: ") #asks the user for which projection the loan was missed
      try: #error handling
         missedProjectionNumber = float(missedProjectionNumber)
         userCorrect = True
      except:
         print("The value you entered is not a number, please try again.")
   userCorrect = False
   while userCorrect == False:
      missedProjectionUnit = input("At which unit has your lender decided to compound to (year/quarter/month/week/day/hour/10 minutes): ") #asks user what the lender has decided to push the compounding rate to
      if missedProjectionUnit == "day": #error handling
         userCorrect = True
      elif missedProjectionUnit == "hour":
         userCorrect = True
      elif missedProjectionUnit == "10 minutes":
         userCorrect = True
      elif missedProjectionUnit == "year":
         userCorrect = True
      elif missedProjectionUnit == "quarter":
         userCorrect = True
      elif missedProjectionUnit == "month":
         userCorrect = True
      elif missedProjectionUnit == "week":
         userCorrect = True
      else:
         print('The value you entered is not a time unit, please try again.')
   openingAmountList = [] #sets the opening list to the principal
   interestList = [] #sets the interest list to the current interest
   closingAmountList = [] #sets the closing list to the principal
   counter = 0 #sets the counter to 0
   appender = principal #sets the first appender to the principle. the first appender is the principal + interest
   appender2 = principal #sets second appender to the principal (the new principal tester). This is the result which gets carried fromt he closing amount to the next opening
   appender3 = principal #sets third appender (the new principal tester 2). This is the appender that saves the old principal
   set1 = missedProjectionNumber - 1 #the variable for 1 minus missed projection number. This is needed because of how the counter is counter in the middle of the while loop, we still want the missed projection to be whatever the user specifies. 
   if projectionUnit == compoundingUnit: #if the projection unit is equal to the compounding unit
      while counter < projectionTime: # while the counter is smaller than the projection time
         while counter < set1: #while the counter is smaller than the set 1
            counter = counter + 1 #does the same function as section 4, without the depositing
            appender3 = appender 
            appender = appender2*(1 + (interest/100))**1 #uses the ci formula to find the total amount, with the counter
            appender = round(appender, 3)
            openingAmountList.append(appender2)
            interestAppend = appender - appender3
            interestList.append(round(interestAppend, 3))
            appender2 = appender
            closingAmountList.append(appender2)
         while counter == set1: #when the counter is the same as set1
            counter = counter + 1 #sets the counter to 1
            appender3 = appender #sets appender 3 to appender
            openingAmountList.append(appender2) #appending appender two to opening amount lists
            interestList.append(0) #appending 0 to the interest liste (since there was no interest earned by the lender)
            closingAmountList.append(appender2) #appending append 2 to closing amount list
         newProjectionUnit = (Table[interestUnit][missedProjectionUnit])*interest #searches for the conversion between the interests.
         counter = counter + 1 #adds one to the counter
         appender3 = appender #does the same thing
         appender = appender2*(1 + (newProjectionUnit/100))**1
         appender = round(appender, 3)
         openingAmountList.append(appender2)
         interestAppend = appender - appender3
         interestList.append(round(interestAppend, 3))
         appender2 = appender
         closingAmountList.append(appender2)
   else:
      interest = (Table[interestUnit][compoundingUnit])*interest #finds the conversion
      while counter < projectionTime: #does the same function
         while counter < set1:
            counter = counter + 1 
            appender3 = appender
            appender = appender2*(1 + (interest/100))**1 
            appender = round(appender, 3)
            openingAmountList.append(appender2)
            interestAppend = appender - appender3
            interestList.append(round(interestAppend, 3))
            appender2 = appender
            closingAmountList.append(appender2)
         while counter == set1:
            counter = counter + 1
            appender3 = appender
            openingAmountList.append(appender2)
            interestList.append(0)
            closingAmountList.append(appender2)
         newProjectionUnit = (Table[interestUnit][missedProjectionUnit])*interest
         counter = counter + 1
         appender3 = appender
         appender = appender2*(1 + (newProjectionUnit/100))**1
         appender = round(appender, 3)
         openingAmountList.append(appender2)
         interestAppend = appender - appender3
         interestList.append(round(interestAppend, 3))
         appender2 = appender
         closingAmountList.append(appender2)
   zippedLists = zip(openingAmountList, interestList, closingAmountList) #zips the 3 lists
   print("Column Headings: Opening amount, Interest, Final amount") #titles the columns
   for row in list(zippedLists): #for every row in the zipped lists
      print(row) #print the lists
   userCorrect = False
   print("≿━━━━༺❀༻━━━━≾")
   while userCorrect == False: #main menu options
      menuQuestion = input("Would you like to quit, repeat the module or return to main menu? (quit/repeat/menu): ")
      if menuQuestion == "quit":
         userCorrect = True
         exit()
      elif menuQuestion == "repeat":
         userCorrect = True
         sectionFive()
      elif menuQuestion == "menu":
         userCorrect = True
         mainMenu()
      else:
         print("The value you entered did not correspond to the options, please try again.")

def mainMenu():
   print("≿━━━━༺❀༻━━━━≾")
   print("This program has five modules. Choose a module by typing its number.\n(1) Compare simple and compound interest savings accounts\n(2) Calculate the time for a CI savings account to reach a target amount\n(3) Compare two Compound Interest savings accounts\n(4) Model a CI savings account with regular deposits\n(5) Model a loan with missed interest payments") #tells the user of the program options. In this case, "\n" means line break
   userCorrect = False #sets usercorrect to false
   while userCorrect == False: #while usercorrect is false
      menu = input("Enter 1 to 5, or 6 to quit: ") #sets the menu input
      if menu == "1": #if user chooses one
         userCorrect = True #checks usercorrect
         sectionOne() #goes to section 1
      elif menu == "2": #etc
         userCorrect = True
         sectionTwo()
      elif menu == "3":
         userCorrect = True
         sectionThree()
      elif menu == "4":
         userCorrect = True
         sectionFour()
      elif menu == "5":
         userCorrect = True
         sectionFive()
      elif menu == "6": #if user chooses 6
         userCorrect = True #checks usercorrect
         exit() #exists the program
      else: #if none of these values were inputted
         print("The value you entered was did not correspond to a module, please try again.") #prompts the user of the mistake and asks them to try again

print("Welcome to the simple and compound interest calculator, made by Shan-Mei") #welcome the user into the code in a decently friendly way :)
mainMenu() #goes to main menu
```
