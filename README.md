# student-grade-calculator
A Python program that calculates the average marks and assigns grades based on percentage. The program supports input and evaluation for multiple students.

def grade_calculator(name):
  
  subjects=['maths','english','urdu','computer','science','islamiat\\ethics','social studies']
  marks = []
  print(f"Enter marks of {name}")
  
  for subject in subjects:
    mark=int(input(f"Enter marks of {subject}: "))
    
    if mark > 100:
      print("invalid marks")
      mark=int(input(f"Enter marks of {subject}: "))
    
    marks.append(mark)
  
  print("Average: ", average(marks))
  print("Percentage: ", percentage(marks))

  per = percentage(marks)

  if per >= 90:
    print("Grade: A")
  elif per >= 80:
    print("Grade: B")
  elif per >= 70:
    print("Grade: C")
  elif per >= 60:
    print("Grade: D")
  else:
    print("Grade: F")

  return

def average(marks):
  avg=0
  count=0
  sum=0

  for mark in marks:
    sum = sum + mark
    count = count + 1
  avg = sum / count
  return int(avg)

def percentage(marks):
  per=0
  count=0
  sum=0

  for mark in marks:
    sum = sum + mark
    count = count + 1
  total = count * 100

  per = int((sum/total) * 100)
  return per

names=[]
print("Enter 'done' when there is no more students! ")
while True: 
  name=input("Enter name of student:")
  if name == 'done':
    break
  names.append(name)

for name in names:
  grade_calculator(name)
