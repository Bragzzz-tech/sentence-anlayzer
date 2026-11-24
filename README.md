# sentence-anlayzer
import string

def get_word_count(sentence: str) -> int:
"""Returns the total number of words in the sentence."""
words = sentence.split()
return len(words)

def get_longest_word(sentence: str) -> str:
"""Returns the longest word in the sentence (ignoring punctuation)."""
words = sentence.split()
if not words:
return "None"

# Strip punctuation from each word before comparing lengths  
clean_words = [word.strip(string.punctuation) for word in words]  
return max(clean_words, key=len)

def reverse_sentence(sentence: str) -> str:
"""Returns the sentence reversed character by character."""
return sentence[::-1]

def is_prime(number: int) -> bool:
"""Returns True if the given integer is a prime number, False otherwise."""
if number <= 1:
return False
for i in range(2, int(number**0.5) + 1):
if number % i == 0:
return False
return True

def main():
# 1. Read inputs from the user
sentence = input("Enter a sentence: ")

while True:  
    try:  
        num = int(input("Enter an integer to check if it is prime: "))  
        break  
    except ValueError:  
        print("Invalid input. Please enter a whole number.")  

# 2. Process results using dedicated functions  
word_count = get_word_count(sentence)  
longest_word = get_longest_word(sentence)  
reversed_text = reverse_sentence(sentence)  
prime_status = is_prime(num)  

# 3. Print clean, labelled output  
print("\n--- Analysis Results ---")  
print(f"Word Count     : {word_count}")  
print(f"Longest Word   : {longest_word}")  
print(f"Reversed Text  : {reversed_text}")  
print(f"Is {num} Prime? : {'Yes' if prime_status else 'No'}")

if name == "main":
main()
