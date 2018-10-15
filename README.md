import random

def calculation(oper, temp_num_1, temp_num_2):
  if oper == '+':
    num = temp_num_1 + temp_num_2
  elif oper == '-':
    num = temp_num_1 - temp_num_2
  elif oper == '*':
    num = temp_num_1 * temp_num_2
  elif oper == '/':
    num = temp_num_1 / temp_num_2

  return num

card_deck = [100, 5, 5, 4, 2]
oper_list = ['+', '-', '*', '/']
oper_list_no_div = ['+', '-', '*']
count = 0
a = card_deck[0]
b = card_deck[1]
c = card_deck[2]
d = card_deck[3]
e = card_deck[4]

i = 0
answer_list = [i]

while i < 100:
  oper1 = random.choice(oper_list)
  oper2 = random.choice(oper_list)
  oper3 = random.choice(oper_list)
  oper4 = random.choice(oper_list)
  
  if a % b != 0:
    oper1 = random.choice(oper_list_no_div)
    
  if (calculation(oper1, num1, b)) % c != 0:
    oper2 = random.choice(oper_list_no_div)
    
  if (calculation(oper1, num2, c)) % d != 0:
    oper3 = random.choice(oper_list_no_div)

  if (calculation(oper1, num3, d)) % e != 0:
    oper4 = random.choice(oper_list_no_div)

  num1 = calculation(oper1, a, b)
  num2 = calculation(oper2, num1, c)
  num3 = calculation(oper3, num2, d)
  finalnum = calculation(oper4, num3, e)

  if isinstance(finalnum, int) and finalnum > 100 and finalnum < 1000 and not finalnum in answer_list:
    answer_list.append(finalnum)
    print (oper1 + oper2 + oper3 + oper4)
    print (finalnum)
    count += 1
    print (count)
    i += 1
 


  
