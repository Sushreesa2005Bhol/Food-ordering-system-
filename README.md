# Food-ordering-system-

menu = {
    "Burger": 80,
    "Pizza": 150,
    "Dosa": 70,
    "Coffee": 40
}

order = {}

def show_menu():
    for item, price in menu.items():
        print(item, "- Rs.", price)

def add_order():
    item = input("Enter food item: ").title()

    if item not in menu:
        print("Item not available!")
        return

    quantity = int(input("Enter quantity: "))

    if quantity <= 0:
        print("Invalid quantity!")
        return

    order[item] = order.get(item, 0) + quantity
    print("Order added successfully!")

def show_bill():
    total = 0

    for item, quantity in order.items():
        cost = menu[item] * quantity
        print(item, "x", quantity, "=", cost)
        total += cost

    print("Total Bill: Rs.", total)

while True:
    print("\n1. Show Menu")
    print("2. Add Order")
    print("3. Show Bill")
    print("4. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        show_menu()
    elif choice == "2":
        add_order()
    elif choice == "3":
        show_bill()
    elif choice == "4":
        break
    else:
        print("Invalid choice!")
        
