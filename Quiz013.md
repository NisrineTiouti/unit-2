## Quiz 13:

![output 13](https://user-images.githubusercontent.com/89052189/143126333-eb0524a6-b3fd-4363-a511-b29344a4269c.PNG)

Here is the test proof( I wasn't able to add it after the code)
```.py
# Given a list of food and their price calculate their overall price after taxing

def total(items, amount):

  food = ["bread", "rice"]
  electronics = ["ipad", "tv"]
  liquor = ["water", "beer"]

  message = input("Do you want to add an item to the lists?: ").lower()
  if message == "yes":
    choice= input("Where do you want to add the item, food, electronics, or liquor?: ").lower()
    if choice == "food":
      new_item = input("Please enter the item: ")
      food.append(new_item) 
    elif choice == "electronics":
      new_item = input("Please enter the item: ")
      electronics.append(new_item)
    elif choice == "liquor":
      new_item = input("Please enter the item: ")
      liquor.append(new_item)

  price = 0
  for i in range(len(items)):
    current_item = items[i]
    if current_item in food:
      price += 1.1*amount[i]
    elif current_item in electronics:
      price += 1.15 * amount[i]
    elif current_item in liquor:
      price += 1.20 * amount[i]
    else: 
      print(f"Warning item {current_item} is not on the database)

  return price

items_ordered = ["bread","beer", "ipad", "pudin"]
amount_ordered = [300, 800, 3000, 700]
total_pay = total(items_ordered, amount_ordered)
print(f"Pay {total_pay}")

#END 
```.py
-----------------------------------------------------------------------------------------------------------------------------------------------------
Do you want to add an item to the lists?: yes
Where do you want to add the item, food, electronics, or liquor?: food
Please enter the item: pudin
Pay 5510.0
