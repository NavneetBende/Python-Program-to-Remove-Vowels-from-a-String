Program to remove the vowels
The string is built with 2 different types of alphabets grouped as vowels and consonants. In this python program, we will be searching for each alphabet that belongs to the group of vowels and will delete it and print the strings with remaining consonants. As we know String is un-mutable in python so we will initialize a new string and concatenate alphabets that don’t belong to the group of vowels and print it.

Program to remove vowels
We will look at the following methods –

Method 1 – Simple iteration on string using for loop
Method 2 – Iterate on individual char of string
Method 3 – Uses replace method
Method 4 – Longer but more clear implementation
Method 5 – One line iterator and join method
Method 6 – Using regex
Method 7 – Using slicing
Method 1
The following method uses
A for loop to iterate on the input string
Characters are not vowels are added to the result string
Run
string = "PrepInsta"

vowels = ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U']
result = ""

for i in range(len(string)):
    if string[i] not in vowels:
        result = result + string[i]

print("\nAfter removing Vowels: ", result)
Output
Enter the String : PrepInsta
After removing Vowels:  Prpnst
Method 2
The following method uses –
Iterator to iterate on each character of the input string
Unlike the previous method where we use string[i] we directly iterate on char of whole string
Run
string = "PrepInsta"

vowels = ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U']
result = ""

for char in string:
    if char not in vowels:
        result = result + char

print("\nAfter removing Vowels: ", result)
Output
After removing Vowels:  Prpnst
Method 3
The following method uses –
Creating a copy for Input string called as result
Iterate on the whole string char one by one
Use an internal replace method that replaces all occurrences of a character in the whole result string
Run
input_string = "PrepInsta"
result = input_string

vowels = ('a', 'e', 'i', 'o', 'u')

for x in input_string.lower():
    if x in vowels:
        result = result.replace(x, "")

print('After removing vowels : ', result)
Output
After removing vowels :  PrpInst
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Toggle each character in a string

Find the ASCII value of a character

Length of the string without using strlen() function

Method 4
This method is a little longer but simple implementation of the same.

Run
#take user input
String = "PrepInsta"

#initialize new empty string
result = str()
String = String.lower()

for i in String:
    #check condition if alphabet belong to group of vowels
    if i == 'a' or i == 'e' or i == 'i' or i == 'o' or i == 'u':
        pass
    else:
        result = result + i

#check for if the result is not null
if len(result) == 0:
    print('No vowel found in ' + String)
else:
    print('After removing vowels : ' + result)
Output
After removing vowels : prpnst
Note
The time complexity of above code is O(n) as in the above code we are looping through the sting once.
Method 5
This method uses one line for iterator and join method to join individual list characters.
Run
def remove_vowel(string):
    vowels = ['a','e','i','o','u']
    
    # result will become : ['P', 'r', 'p', 'n', 's', 't'] after below step
    result = [letter for letter in string if letter.lower() not in vowels]
    
    # result will become Prpnst, i.e. we joined strings in this
    result = ''.join(result)
    print(result)
 
# Driver program
string = "PrepInsta"
print(string)
remove_vowel(string)
Output
PrepInsta
Prpnst
Method 6
The below solution is using regex :-

Run
# import the module for regular expression (re)
import re
def rem_vowel(string):
    return (re.sub("[aeiouAEIOU]","",string))           

# Driver program
string = "Prepinsta"
print(rem_vowel(string))
Prpnst
Method 7
The following method uses slicing. Advantage we can remove the vowels without needing another variable.
Run
str = "PrepInsta"

vowels = ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U']
i = 0
for c in str:
    if c in vowels:
        str = str[:i] + str[i+1:]
        i = i-1
    i = i+1

print("After removing Vowels : ", str)
Output
After removing Vowels :  Prpnst
