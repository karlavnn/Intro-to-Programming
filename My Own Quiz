# My Own Quiz

# To write this code I've searched to several different websites such as
# stackoverflow, thepythonguru.com, Udacity's Forum, pythontutor.com, python.org, pythonforbeginners.com, ....


# Global Variables
introduction = (
'''\n ** Quiz: Fill In The Blanks ** \n
\n In this quiz you can choose how many guesses you'll have and your difficulty level.\n
\n (Attention: Use lowercase for all of your answers.)\n''')

blank = ["__1__","__2__","__3__","__4__","__5__"]

easy_paragraph =(
'''\n If you'd like to learn a new __1__ language you should study __2__,
 it is easier to read and requires less effort to write than C++ and Java.
 While other __3__ use ";" to indicate a block of code, Python uses __4__,
 which is crucial to make the program runs properly. In order to output a string,
 you only need to type: __5__ 'string'.''')

medium_paragraph =(
'''\n Locations that are used to store references to the objects in memory are named __1__.
 Some data types in Python are: numbers, strings, __2__, tuple and dictionary.
 You can use index operator ( [ ] ) to access individual elements in the list.
 List's __3__ starts from __4__. A list common method is " + " that __5__ two lists, i.e.:
  \nlist1 = [1,2,3] \nlist2 = [4,5] \nlist3 = list1 + list2 \nprint list3 \n[1,2,3,4,5,6]''')

hard_paragraph =(
'''\n When you write code you should always avoid __1__, and __2__ is one of the tools
 used for that. Python has only two: __3__ and while. Another way to have an
 organized and reusable code to perform a set of actions is using __4__.
 They simplify the coding process, prevent redundant logic, and make code easier to follow.
 To define __4__ the statement most common is __5__.''')

easy_answer = ['program','python','languages','indentation','print']

medium_answer = ['variables','lists','index','zero','concatenates']

hard_answer = ['repetition','loop','for', 'functions', 'def']

correct = ['\n Yep! You got it!','\n Great!', '\n Keep killing it!', '\n Yes! Just one more.', '\n You just finished! Yay! This is the complete paragraph: ']

wrong = "\n Not really... Guesses left: "

guess_list = range(1,11)

def quiz():
    '''
    * Input:    None
    
    * Output:   play_quiz function
    
    * Behavior: Player will choose number of guesses and difficulty level, than all respectives
                arguments for play_quiz function will be defined and returned.
    '''
    print introduction
    guesses = guess_choice()
    while True:
        level = raw_input(" Please choose your level: easy, medium, hard: ")
        if level not in ('easy', 'medium', 'hard'):
            print(" Not an appropriate choice.")
        elif level == "easy":
            print "\n You've chosen easy! Good luck!!"
            return play_quiz(easy_paragraph, easy_answer, blank, guesses)
        elif level == "medium":
            print "\n You've chosen medium! Good luck!!"
            return play_quiz(medium_paragraph, medium_answer, blank, guesses)
        else:
            print "\n You've chosen hard! Good luck!!"
            return play_quiz(hard_paragraph, hard_answer, blank, guesses)

def guess_choice():
    '''
    * Input:    None
    
    * Output:   Variable "guesses"
    
    * Behavior: Player will provide the number of guesses, and there are two validations:
                1) it has to be a number
                2) the number needs to be from 1 to 10
                
                If it does not pass validation, an error will be prompted and the user will be 
                continually requested to provide the correct value.
                If the value provided is validated it will be stored in a variable called "guesses".
    '''
    while True:
        try:
            guesses = int(raw_input("\n How many guesses would you like to have for each question? Enter a number from 1 to 10. \n"))
        except ValueError:
            print "It has to be a number."
            continue
        else:
            if guesses not in guess_list:
                print "Not an appropriate choice. Please choose between numbers 1 - 10."
            elif guesses == 1:
                print "\n OK, you will have: " + str(guesses) + " guess.\n"
                return guesses
            else:
                print "\n OK, you will have: " + str(guesses) + " guesses.\n"
                return guesses

def play_quiz(paragraph, answer, blank, guesses):
    '''
    * Input:    The arguments defined at quiz() function
    
    * Output:   There are two possible outputs in this function:
                1) an element from list called "correct", and the paragraph with blank(s) filled.
                2) an element from list called "wrong", and current number of guesses left.
                
    * Behavior: play_quiz will loop through each blank list element's index and request an answer.
                If the answer matches the element's index in answers list, it will return the respective blank filled 
                and ask for the next answer until all blanks are correctly filled.
                
                For every mistake made the number stored in guess_number will be decreased, if its value is equal 0: 
                Game Over! However, if user makes mistakes and than gets the correct answer, the guess_number is 
                reseted, and he has the total of his guesses back to try the next answer.
    '''
    count = 0
    guess_number = guesses
    while count <= len(blank):
        if count == len(blank):
            return paragraph
        else:
            print paragraph
            word = raw_input("\n What is the word for: " + blank[count] + "?\n")
            if word == answer[count]:
                print correct[count]
                paragraph = paragraph.replace(blank[count], answer[count])
                count += 1
                guess_number = guesses
            else:
                guess_number -= 1
                print wrong + str(guess_number)
                if guess_number == 0:
                    return "\n Game Over!"

print quiz()
