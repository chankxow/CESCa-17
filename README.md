# CESCa17
ค่ายเยาวชนวิศวกรรมคอมพิวเตอร์ภาคฤดูร้อนครั้งที่ 17 (CESCa 17)

> #### CESCa17!
```
def check_balance(add_money):
    global wallet
    wallet += add_money
    return wallet

def price_order(user_need):
    global my_order
    for item in my_order.keys():
      if user_need == item:
        price = my_order[item]
        return price
      
def get_order():
    global my_order
    for menu in my_order.keys():
        print(menu, end=" : ")
        print(my_order[menu])

    return my_order

def get_user():
    user_call = input("Type Y to order, Type C to check balance, Type X to exit the program Would you like to have an order? [Y/C/X] : ")
    user_call = user_call.upper()
    return user_call

#valid = False
my_order = {"Mocha" : 60, "Americano" : 60, "Espresso" : 70, "Late" : 65}

wallet = 10000
add_money = 0

while True:

    user_call = get_user()
    if user_call == "X":
        print("Bye!")
        break

    elif user_call == "Y":
        user_name = input("What is your name? ")
        while True:
            get_order()
            user_need = input("I would like to order : ")
            user_need = user_need[0].upper() + user_need[1:]
            #print(user_need)

            if user_need in my_order:
                print("%s your of %s is ready!" % (user_name, user_need))
                print("Thank you for purchasing!")
                # add money
                add_money = price_order(user_need)
                check_balance(add_money)
                break
            else:
                print("Please enter order again.")
                

        # add_money = price_order(user_need)

    elif user_call == "C":
        print("Current balance is %s THB" % wallet)
```

> Mocha : 60
> Americano : 60
> Espresso : 70
> Late : 65
>> Chankxow your of Late is ready!
>>Thank you for purchasing!
> Mocha : 60
> Americano : 60
> Espresso : 70
>Late : 65
>> Kanom your of Americano is ready!
>> Thank you for purchasing!
>>> Current balance is 10125 THB
>> Bye!
