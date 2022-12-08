#Importes a library assets from PrettyTable used to build the table!
from prettytable import PrettyTable
from stringcolor import *
from memory_profiler import profile


print(cs(" \n \n Welcome To Jirays Industry! \n \n", "#FF00547"))
#orders table
orders = PrettyTable(["Orders", "P1", "P2", "P3", "P4", "P5",])


#order rows
orders.add_row(["01", "0001", "0002", "0003", "0004","0005",])
orders.add_row(["02", "0006", "0007", "0008", "0009","0010",])
orders.add_row(["03", "0011", "0012", "0013", "0014","0015",])
orders.add_row(["04", "0016", "0017", "0018", "0019","0020",])
orders.add_row(["05", "0021", "0022", "0023", "0024","0025",])


#sort's row's number, the order of the rows matter so if not in sequence index number will be diferent
orders.sortby = "Orders"
print(orders)


##@profile                  note: delete the # and indent the code to run memory_profiler 
##def memoryruntest():


Parts = False
while Parts == False:
    
#Ask the user to intruduce a between C, D, M or Q to proceed or quit the program: 
    choice = input(cs("\n Select:\n \n --------------- c To Create --------------- \n --------------- d To Delete --------------- \n --------------- m To Modify --------------- \n --------------- q to  Exit  --------------- \n  \nEnter Here: " , "#FF00547"))   # explain
    choice = choice.lower() # Tells the program to accept both capital and lower letters

    
    #Creates a new order by user inputing item numbers and order number 
    if choice == "c":
    
    
        print("Your Choose Create!")
    
    #Variable "Parts" tells the program to loop until the user put integer numbers while parts == False then "try:" input integer numbers, if the user input intengers numbers...
    # then Parts = True allowing the user to proceed...


        
        loopinputc = False
        while loopinputc == False:
        
            Orders = input("Input order number: ")
            P1 = input("Input part number 1: ")
            P2 = input("Input part number 2: ")
            P3 = input("Input part number 3: ")
            P4 = input("Input part number 4: ")
            P5 = input("Input part number 5: ")
            
            #convert strings from table "P1, P2, P3, P4, ,P5" to integer numbers. 
            try:
                Orders = int(Orders)
                P1 = int(P1)
                P2 = int(P2)
                P3 = int(P3)
                P4 = int(P4)
                P5 = int(P5)
                loopinputc = True

                
                orders.add_row([str(Orders), str(P1), str(P2), str(P3), str(P4), str(P5)]) #if true then adds a new row
                print(orders) #print the orders
                print('You Have Successfuly created a New Order! \n')   # display this message if the values are intruduced correctly
                
            
            except:
                print('Invalid Digits Please Try Again!') # if user introduce no integer numbers or any other type of data "float numbers, strings... it will print Invalid Digits Please Try Again! " 
                break #tells the program to stop this algorithm
    
    

    #Deletes an order by user selecting wich index number to delete  
    elif choice == "d":
       
        delinput = False
        while delinput == False: 
            
            try:
                
                delete_index = int(input("Choose wich index number to delete: "))#Only integer numbers are allowed on the function input.
                orders.del_row(delete_index)#for deleting an index number now it is used the function del_row
                print(orders) #prints the table 
                print("You Have Succesfuly Deleted The Order!")
                delinput = True
            
            except:
                print("Index Number Not Found Please Try Again!")
                print(orders) #prints the updated table 
            break #tells the program to stop this algorithm

    elif choice == "m":
            

            
            Modifyloop = False
            while Modifyloop == False:

                try:
                    
                    #Deletes the row selected by choosing the index number from the table
                    delete_index = int(input("Choose wich index number to modify: "))
                    orders.del_row(delete_index)
                    
                    
                    #asks the user to input the order details 
                    Orders = input("Input order number: ")
                    P1 = input("Input part number 1: ")
                    P2 = input("Input part number 2: ")
                    P3 = input("Input part number 3: ")
                    P4 = input("Input part number 4: ")
                    P5 = input("Input part number 5: ")
                
                    
                    
                    #tells the program to convert the data to intenger numbers
                    Orders = int(Orders)
                    P1 = int(P1)
                    P2 = int(P2)
                    P3 = int(P3)
                    P4 = int(P4)
                    P5 = int(P5)
                        
                    Modifyloop = True
                    

                
                    #Tells the Program convert the integer numbers back to strings and hold the data on the table
                    orders.add_row([str(Orders), str(P1), str(P2), str(P3), str(P4), str(P5)])
                    print("You Have Succesfuly Modified your Order Number \n ")
                    print(orders) #print the updated orders table

                except:
                    print('Please Input Only Numbers or Index Number Do not Exist Try Again! \n')
                    print(orders) 
                break

    #tells to close the program if we choose q option!  
    elif choice == "q":
        print("See You Soon! \n")
        break
        

    #Else the choosen inputs are not C - D - M or Q loops back and displays invalid please try again! 
    else: 
        print("invalid please try again!")
                        
    ##memoryruntest() delete the # and indent the code to run memory_profiler 
