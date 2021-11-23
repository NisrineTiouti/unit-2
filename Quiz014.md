## Quiz 14:

```.py

#14: Given 3 integers where one is the largest, one is medium and the other is the smallest.
# Check if they're all evenely spaced, and output TRUE. If not output FALSE

def evenlyspaced(num1, num2, num3):
  if num1>num2 and num1>num3:
    largest = num1
  elif num2>num3: 
    largest = num2
  else:
    largest = num3

  if num1<num2 and num1<num3:
    smallest = num1
  elif b<c:
    smallest = num2
  else: 
    smallest = num3 

  if num1>num2:
    if num1<num3:
        median= num1
    elif num2>num3:
        median= num2
    else:
        median= num3
  else:
    if num1>num3:
        median= num1
    elif num2<num3:
        median= num2
    else:
        median= num3

  if largest - median == median - smallest or largest - smallest == smallest - median:
    answer = True 
  else: 
    answer = False

  return answer

test1 =evenlyspaced(6,4,2) 
test2 = evenlyspaced(4,3,8)
print(test1)
print(test2) 
--------------------------------------------------------------------------------------------
True
False

