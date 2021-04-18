# Water-Snake-Gun-Game
#Pyhton program For Random Choice Game
# Water Snake Gun Game Using Random Slection 
import random
list1=["S","W","G"]

try:
    process="Y"
    # _random=random.choice(list1)
    # # print(_random)
    while(process=="Y"):
        computer_Points=0
        human_point=0
        tie=0
        chance=int(input("How many chnaces You Want 1 to 10 : "))
        print(f"\t\tSnake Water Gun Game .. Good Luck for Ur Luck ..\n \t\t\t\t You Got {chance} Chances")
        while(chance!=0):
            _random=random.choice(list1)
            user_input=input("\n\t1 Or S for Snake\n\t2 Or W for Water\n\t3 Or G for Gun :  ").capitalize()
            if (user_input=="1" or user_input=="S"):user_input="S"
            elif(user_input=="2" or user_input=="W"):user_input="W"
            elif(user_input=="3" or user_input=="G"):user_input="G"
            else:
                print("\tWorng Input !! Try Again ")
                continue
            if(_random==user_input):
                tie += 1
                print("\tMatch Tie !! Try Again.")
            elif(_random=="S" and user_input=="G"):
                print("\t*****You Win","Your Gun killed Snake.*****")# _random)
                human_point += 1
            elif(_random=="S" and user_input=="W"):
                print("\t*****You Lose !! Snake Drinks all the Water ..*****")
                computer_Points += 1
            elif(_random=="G" and user_input=="S"):
                print("\t****You Lose !! Gun killed ur Snake..****")
                computer_Points += 1
            elif(_random=="G" and user_input=="W"):
                print("\t*****You Win!! Gun Drpped into ur Water ..*****")
                human_point += 1
            elif(_random=="W" and user_input=="S"):
                print("\t*****You Win !! Your Snake drank all the Water ..*****")
                human_point += 1
            elif(_random=="W" and user_input=="G"):
                print("\t*****You Lose !! Your Gun Sanked into the Water ..*****")
                computer_Points += 1
            # else:
            #     print("Wrong Input .. Try Again ..")
            #     continue    
            chance -= 1
            print("\t",chance," Chances Left.. ")
        if(computer_Points>human_point):
            print(f"\t\n********************\n\tComputer Won by {computer_Points} Scores.Yours Score was{human_point}\n\t And Match tie = {tie} Times\n\t**********************")
        elif(computer_Points<human_point):
            print(f"\n\t**********************\n\tYou won by {human_point} Scores. Computer Score was {computer_Points}\n\t And Match tie = {tie} Times\n\t***************")
        else:
            print(f"\n\t*********************\n\tMatch Tie ... Your Point {human_point} = Computer Points {computer_Points}\n\t*********************")            
        process=input(" \n\t\tDo you Want To Play Again Press 'Y' for Yes /Any key for No : ").capitalize()

except Exception as e:
    print("Error is : ",e)    

