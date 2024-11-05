# highestNumber.py
This is the code I used to get the highest integer out of a number of integers in class. 11/05/2024
SENTINEL = -1
LOW_VALUE = 0

def main():
    newValue = 0
    lowestValue = 0
    highestValue = 0

    message = f"Enter number > {LOW_VALUE}. Enter {SENTINEL} to quit: "

    newValue = getValidNumber(message)  # priming read
    if newValue != SENTINEL:
        highestValue = newValue
        lowestValue = newValue

        while (newValue != SENTINEL):
            if newValue > highestValue:
                highestValue = newValue
            if newValue < lowestValue:
                lowestValue = newValue
            
            newValue = getValidNumber(message)
        

        print("Highest value = ", highestValue)
        print("Lowest value = ", lowestValue)
    else:
        print("No numbers entered.")
    

# The One-Function Input Validation Routine
        
def getValidNumber(msg):
    newValue = 0
    newValue = getInteger(msg)

    # loop while the input value is invalid

    while newValue < LOW_VALUE and newValue != SENTINEL:
        print("Invalid Value")
        newValue = getInteger(msg)
    

    return newValue

# make sure the input is an integer otherwise an exception is thrown
def getInteger(msg):
    myInt = input(msg)  # this prompts the user for an integer > LOW_VALUE and not SENTINEL

    try:
        return int(myInt)
    except ValueError: 
        print(myInt, "is not a valid integer. Please try again.")
        return getInteger(msg)

main()
