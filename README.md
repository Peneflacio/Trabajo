import re

print("Password meets the requirements to be considered secure")
password = input("Enter your password:")

#The following allows us to set some boolean values that we will change whether the password meets the requirement or not.
lenght = False
capital_letter = True
lowercase_letters = True
number = True
special = True

if  8 <= len(password):
    lenght = True
    if not re.search(r"[A-Z]", password): #Find capital letters
        capital_letter = False
        print("Password must contain at least one capital letter.")
    if not re.search(r"[a-z]", password): #Find lowercase letters
        lowercase_letters = False
        print("Password must contain at least one lowercase letter.")
    if not re.search(r"\d", password): #Find some number
        number = False
        print("The password must contain at least one number.")
    if not re.search(r"[!@#\$%\^&\*\(\),\.\?\\:\{\}\|<>\[\]/]", password): #Search for special characters
        special = False
        print("The password must contain at least one special character.")
        
else:
    print("The password is too short. It must be at least 8 characters.")
    
#It will be displayed when all the above characteristics are true
if lenght and capital_letter and lowercase_letters and number and special == True: 
    print("The password is secure")
