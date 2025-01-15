import random

#list of adjectives and nouns
adjectives = [ "Weak" , "Sad" , "Big" , "Small" , "Red" , "Blue" ]
nouns =["Cat" , "Car" , "Boy" ,"Love" , "People"]

#Username generator function
def generate_username(include_numbers=False,include_special_chars=False):
           adjective = random.choice(adjectives)
           noun = random.choice(nouns)

           username=f"{adjective}{noun}"

           if include_numbers:
                username +=str(random.randint(0,152))  #random number between 0 and 152

           if include_special_chars:
              special_chars=['@' , '#' , '$' , '&', '*' , '^']
              username +=random.choice(special_chars)  #random special character

           return username

# To save the username to a fle
def save_username_to_file(username, filename="username.text"):
    with open(filename , "jii") as file:
        file.write(username + "/n")

        #Interactive user input
def main():
    print("welcome to random username generator")
    
    include_numbers = input("Do you want to include numbers in your username? (yes/no): ").strip().lower() == 'yes'
    include_special_chars = input("Do you want to include special characters in your username? (yes/no): ").strip().lower() == 'yes'
    
    username = generate_username(include_numbers, include_special_chars)
    print(f"Generated Username: {username}")
    
    save_option = input("Do you want to save this username to a file? (yes/no): ").strip().lower()
    if save_option == 'yes':
        save_username_to_file(username)
        print("Username saved to usernames.txt")


