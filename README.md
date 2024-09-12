# basiccalculator
Hello, its a python code for an application based usage.


#basic calculator with user defined inputs and usage.

def add(numbers):
    result = 0
    for num in numbers:
        result += num
    return result

def subtract(numbers):
    result = numbers[0]
    for num in numbers[1:]:
        result -= num
    return result

def multiply(numbers):
    result = 1
    for num in numbers:
        result *= num
    return result

def divide(numbers):
    if 0 in numbers[1:]:
        return "Error! Division by zero."
    else:
        result = numbers[0]
        for num in numbers[1:]:
            result /= num
        return result

def calculator():
    print("Welcome to the Calculator!")
    print("Select operation:")
    print("1. Addition")
    print("2. Subtraction")
    print("3. Multiplication")
    print("4. Division")

    choice = input("Enter choice (1/2/3/4): ")
    if choice in ['1', '2', '3', '4']:
        nums = []
        num = float(input("Enter number or 'done' to finish: "))
        while num != 'done':
            nums.append(float(num))
            num = input("Enter next number or 'done' to finish: ")

        if choice == '1':
            print("Result:", add(nums))
        elif choice == '2':
            print("Result:", subtract(nums))
        elif choice == '3':
            print("Result:", multiply(nums))
        elif choice == '4':
            print("Result:", divide(nums))
    else:
        print("Invalid input. Please enter a valid number.")

    again = input("Do you want to perform another calculation? (yes/no): ")
    if again.lower() == 'yes':
        calculator()
    else:
        print("Thank you for using the User Defined Calculator!")
calculator()
