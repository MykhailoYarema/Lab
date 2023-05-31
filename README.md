# Lab_5
Код програми:

from num2words import num2words

def main():
    name = input("What is your name? ")
    print(f"Hello, {name}!")

    while True:
        try:
            number = int(input("Enter a number: "))
            break
        except ValueError:
            print("Invalid input. Please enter a number.")

    words = num2words(number)
    print(words)

if __name__ == '__main__':
    main()
