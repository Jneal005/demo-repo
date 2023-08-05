
import random 
import time

def type_out_word(word, typing_speed):
    for char in word:
        print(char, end='', flush=True)  # Print the character without a newline
        time.sleep(typing_speed)  # Introduce a delay to control typing speed
    print()  # Print a newline after typing out the word

typing_speed = 0.05  # Adjust this value to control the typing speed



def type_fast_game():
    count = 0 #default count = 3 change if you hashtag out user options
    lives = user_lives #default lives 3 change if you hashtag out user options
    while True:
        time_limit = user_timelimit #default limit is 5 change if you hashtag out user options
        start_time = time.time()
      
        # Game loop
        running = True
        while True:
            time_limit = user_timelimit #default limit is 5 change if you hashtag out user options
            start_time = time.time()
            running = True
            
            if lives == 0:
                print("YOU LOSE!")
                exit()
            if count == user_count: #default count = 3 change if you hashtag out user options
                print("YOU WIN!")
                exit()


                
            random_num = random.randint(0,8)
            hacker_vocab = "Main Frame", "Data Base", "Encryption","Malware","Spoofing","Denial of Service", "Phishing", "Ransomware", "Back Door"
            coding_vocab =  "Variable", "Function", "Method", "Class", "Array", "Loop", "Condition", "Boolean", "Object", "Interface", "Recursion"
            computer_vocab = "Kernel", "File System", "Cache", "Compiler", "Interpreter", "Algorithm", "Data Structure", "Binary", "Bit", "Byte", "Protocol"
            
            if topic_choice == "Hacker":
                topic = hacker_vocab
            elif topic_choice == "Coder":
                topic = coding_vocab
            elif topic_choice == "Computing":
                topic = computer_vocab
            else:
                topic = hacker_vocab

        
            print("  ---------------  ")
            random_word = topic[random_num]
            print("|   ", random_word , "   |")
            print("  ---------------  ")
            type_word = input("Type the word as fast as you can: ") 
            
            elapsed_time = time.time() - start_time
            if elapsed_time >= time_limit:
                running = False
                
            if type_word == random_word:
                if type_word == random_word and running == False:
                    print()
                    print("you took too long to answer")
                    print()
                    print("Answers Right: ", count)
                    lives = lives - 1
                    print("Lives: ", lives)
                    break
                    
                print("")
                print("Correct!")
                count += 1
                
            if type_word != random_word:
                if lives < 1:
                    exit()
                else:   
                    "That was incorrect"
                    lives = lives - 1
                    print()
                    print("Lives: ", lives)
                    print()
            #Checking if the time limit matched up

introduction = """The rules of the game are simple type in the word displayed as fast as you can, if you don't type it in time
then you will loose a life, you have 5 seconds per word. In order to win you must get 3 words within the timeframe."""
type_out_word(introduction, typing_speed)


print("")
print("Topics - Hacker(Hard), Coder(Medium), Computing(Easy)")

topic_choice = input("Choose a topic to play: ")
user_lives = int(input("How many lives do you want: "))
user_count = int(input("Whats the word limit: "))
user_timelimit = int(input("Whats your time limit: "))
user_ready = input("Are you ready (y/n): ")

if user_ready == "y":
    print("Okay then")

else:
    while user_ready != "y":
        print("Type 'y' when you're ready")
        user_ready = input("")
        
print("3")
time.sleep(1)
print("2")
time.sleep(1)
print("1")
time.sleep(1)
print("Go!")
type_fast_game()






