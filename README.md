# Password Generator
This is a password generator that will generate a password of any desired length and tell you how many brute force guesses it would roughly guess to crack.

## Important
This is a very basic password generator, and the estimate of strength is not a direct indicator of pure password strength, but mere probability.

## Code

``` Python
import random

print('Hello, I see you have come for a password. We will generate a strong password for you.')

while True: #tests for int value of input
    try:
        password_length = int(input('Please enter your desired password length: '))
        if password_length <= 0:
            print("Password length must be a positive integer.")
        else:
            break  # Exit the loop if the input is valid
    except ValueError:
        print("Invalid input. Please enter a number.")
 #converts value to actual integer once check is complete
upper_case = ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z']
lower_case = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
numbers = ['0','1','2','3','4','5','6','7','8','9']
symbols = ['!', '@', '#', '$', '%', '^', '&', '*', '(', ')', '-', '_', '=', '+', '[', ']', '{', '}', '|', '\\', ':', ';', '"', '\'', '<', '>', ',', '.', '?', '/']

all_characters = upper_case + lower_case + numbers + symbols #combining all lists to form one pool for password generation

num_characters = len(all_characters)
estimated_guesses = num_characters ** password_length

random_chars = [random.choice(all_characters) for _ in range(password_length)] #defines the range for random chars

generated_password = ''.join(random_chars) #combines the random chars into string format

print(f'Your newly generated password is {generated_password}')
print(f'Your password would take roughly {estimated_guesses:,} brute force guesses to guess.')


```
