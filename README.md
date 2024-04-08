def caesar_cipher(text, shift, mode):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            if char.islower():
                shifted_char = chr((ord(char) - 97 + shift * mode) % 26 + 97)
            else:
                shifted_char = chr((ord(char) - 65 + shift * mode) % 26 + 65)
        else:
            shifted_char = char
        encrypted_text += shifted_char
    return encrypted_text

def main():
    while True:
        print("\nCaesar Cipher")
        print("1. Encrypt")
        print("2. Decrypt")
        print("3. Exit")
        choice = input("Enter your choice: ")

        if choice == "1":
            message = input("Enter the message to encrypt: ")
            shift = int(input("Enter the shift value: "))
            encrypted_message = caesar_cipher(message, shift, 1)
            print("Encrypted message:", encrypted_message)
        elif choice == "2":
            message = input("Enter the message to decrypt: ")
            shift = int(input("Enter the shift value: "))
            decrypted_message = caesar_cipher(message, shift, -1)
            print("Decrypted message:", decrypted_message)
        elif choice == "3":
            print("Exiting program...")
            break
        else:
            print("Invalid choice. Please enter 1, 2, or 3.")

if __name__ == "__main__":
    main()
