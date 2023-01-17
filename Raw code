"""This program asks the user what drink they want. The user then inputs the cost, and the program processes the payment. 
A refund is given if funds are insufficient or more than the cost. User is asked if they want another drink, unless user 
types 'off' which shuts the machine off. If report is the input, the program outputs current resources and profit. """

MENU = {
    "espresso": {
        "ingredients": {
            "water": 50,
            "coffee": 18,
        },
        "cost": 1.5,
    },
    "latte": {
        "ingredients": {
            "water": 200,
            "milk": 150,
            "coffee": 24,
        },
        "cost": 2.5,
    },
    "cappuccino": {
        "ingredients": {
            "water": 250,
            "milk": 100,
            "coffee": 24,
        },
        "cost": 3.0,
    }
}
profit = 0
resources = {
    "water": 300,
    "milk": 200,
    "coffee": 100,
  
}


coin_quarters = 0.25
coin_dimes = 0.10
coin_nickles = 0.05
coin_pennies = 0.01

def check_ingredients(ingredients_order):
  """Compares the values in the dictionary called 'resources'
  to the values in the user's drink choice to determine if
  there is enough ingredients to make the drink"""
  for item in ingredients_order:
    if ingredients_order[item] >= resources[item]:
      print(f'Sorry. There is not enough {item}.')
      return False
  return True
  

def process_coins():
  """Returns the total of the coins inserted"""
  print('Please enter coins.')
  total = int(input('How many quarters?: ')) * coin_quarters
  total += int(input('How many dime?: ')) * coin_dimes
  total += int(input('How many nickels?: ')) * coin_nickles
  total += int(input('How many pennies?: ')) * coin_pennies
  return total

def is_payment_approved(money_given, cost):
  """Return true for accepted payment and false if money isnt enough."""
  if money_given >= cost:
    change = round(money_given - cost, 2)
    print(f'Thank you for your order. Here is ${change} in change.')
    global profit
    profit += cost
    return True
  else:
    print('That is not enough money. Here is your money back.')
    return False 


def make_coffee(drink_choice, ingredients_order):
  """Deduct the required ingredients from the resources"""
  for item in ingredients_order:
    resources[item] -= ingredients_order[item]
  print(f'Here is your {drink_choice}!☕️')
    
  
    

machine = True

while machine:
    choice = input("What would you like?(espresso/latte/cappuccino) ")
    if choice == "report":
      print(f"Water: {resources['water']} ml")
      print(f"Milk: {resources['milk']} ml")
      print(f"Coffee: {resources['coffee']} ml")
      print(f"Money: ${profit:.2f}")
    elif choice == "off":
        print("Machine turned off.")
        machine = False
    else:
      drink = MENU[choice]
      if check_ingredients(drink["ingredients"]):
        payment = process_coins()
        cost = drink['cost']
        if is_payment_approved(payment, cost):
          make_coffee(choice, drink["ingredients"])
        
        
     
      

      





