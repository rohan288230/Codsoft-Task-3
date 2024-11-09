# Codsoft-Task-3
import random
import string

# Function to generate a random password
def generate_password(length=12):
    # Define the characters that can be used in the password
    characters = string.ascii_letters + string.digits + string.punctuation
    
    # Randomly choose characters from the defined set to form the password
    password = ''.join(random.choice(characters) for _ in range(length))
    
    return password

# Main function to interact with the user
def main():
    print("Welcome to the Password Generator!")
    
    # Get password length from the user
    while True:
        try:
            length = int(input("Enter the length of the password (minimum 8 characters): "))
            if length < 8:
                print("Password length should be at least 8 characters. Please try again.")
            else:
                break
        except ValueError:
            print("Invalid input. Please enter a valid number.")

    # Generate and display the password
    password = generate_password(length)
    print(f"Your generated password is: {password}")

if __name__ == "__main__":
    main()
