# PRODIGY_CS_01
Here I have Implemented Caesar Cipher by Creating a Python program that can encrypt and decrypt text using the Caesar Cipher algorithm. It Allows users to input a message and a shift value to perform encryption and decryption.
So, Here is my Project check below :

def caesar_cipher(text, shift, encrypt=True):
    result = ""
    for char in text:
        if char.isalpha():
            # Determine the shift direction based on encryption or decryption
            if encrypt:
                shifted_char = chr((ord(char) - ord('a' if char.islower() else 'A') + shift) % 26 + ord('a' if char.islower() else 'A'))
            else:
                shifted_char = chr((ord(char) - ord('a' if char.islower() else 'A') - shift) % 26 + ord('a' if char.islower() else 'A'))
            result += shifted_char
        else:
            result += char
    return result

def main():
    while True:
        choice = input("Do you want to encrypt or decrypt? (e/d): ").strip().lower()
        if choice not in ['e', 'd']:
            print("Invalid choice. Please enter 'e' for encryption or 'd' for decryption.")
            continue
        break
    
    message = input("Enter your message: ")
    shift = int(input("Enter the shift value (an integer): "))
    
    if choice == 'e':
        encrypted_message = caesar_cipher(message, shift)
        print("Encrypted message:", encrypted_message)
    else:
        decrypted_message = caesar_cipher(message, shift, encrypt=False)
        print("Decrypted message:", decrypted_message)

if __name__ == "__main__":
    main()

(This program will prompt the user to choose whether they want to encrypt or decrypt a message. Then it asks for the message and the shift value. Finally, it prints the encrypted or decrypted message based on the user's choice.) 
