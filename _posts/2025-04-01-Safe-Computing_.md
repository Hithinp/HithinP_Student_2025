---

---

```python

import random

def caesar_cipher(text, shift, mode):
    result = ""
    for char in text:
        if char.isalpha():  # Encrypts only letters
            shift_amount = shift if mode == "encrypt" else -shift
            new_char = chr(((ord(char.lower()) - 97 + shift_amount) % 26) + 97)
            result += new_char.upper() if char.isupper() else new_char
        else:
            result += char  # Keeps spaces and punctuation unchanged
    return result

# Get user input
mode = input("Do you want to encrypt or decrypt? ").strip().lower()
message = input("Enter your message: ")
shift_input = input("Enter shift value (or type 'random'): ").strip().lower()

# Generate a random shift if "random" is entered
shift = random.randint(1, 25) if shift_input == "random" else int(shift_input)

print(f"Using shift value: {shift}")  # Display the shift used
output = caesar_cipher(message, shift, mode)
print(f"Result: {output}")


```
