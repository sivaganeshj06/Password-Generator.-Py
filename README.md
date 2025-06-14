#import random
import string

def generate_password(length=12, use_digits=True, use_special_chars=True):
    characters = string.ascii_letters  # a-z + A-Z
    
    if use_digits:
        characters += string.digits     # 0-9
    if use_special_chars:
        characters += string.punctuation  # !@#$%^&*() etc.
    
    if not characters:
        raise ValueError("No characters available to generate a password.")

    password = ''.join(random.choice(characters) for _ in range(length))
    return password

# Example usage:
if __name__ == "__main__":
    length = int(input("Enter desired password length: "))
    include_digits = input("Include digits? (y/n): ").lower() == 'y'
    include_special = input("Include special characters? (y/n): ").lower() == 'y'
    
    password = generate_password(length, include_digits, include_special)
    print("Generated password:", password) Password-Generator.-Py
