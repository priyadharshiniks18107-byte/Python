Question 1:
import numpy as np

marks = np.array(list(map(int, input("Enter 5 marks: ").split())))

print("Average:", np.mean(marks))
print("Highest:", np.max(marks))
print("Lowest:", np.min(marks))

Input: 78 65 92 55 84
Output:
Average: 74.8
Highest: 92
Lowest: 55

Question 2:
import numpy as np

temp = np.array(list(map(int, input("Enter temperature values: ").split())))

temp[temp < 0] = 0

print("Modified temperatures:", temp)

Input: 25 -3 28 -1 30 27 -5
Output: Modified temperatures: [25  0 28  0 30 27  0]

Question 3:
import numpy as np

test1 = np.array(list(map(int, input("Enter Test 1 marks: ").split())))
test2 = np.array(list(map(int, input("Enter Test 2 marks: ").split())))

students = np.where(test2 > test1)[0]

print("Students improved:", students)

Input: import numpy as np

test1 = np.array(list(map(int, input("Enter Test 1 marks: ").split())))
test2 = np.array(list(map(int, input("Enter Test 2 marks: ").split())))

students = np.where(test2 > test1)[0]

print("Students improved:", students)

Output: Students improved: [0 2 4]

Question 4:
import numpy as np

matrix = np.array([
    list(map(int, input().split())),
    list(map(int, input().split())),
    list(map(int, input().split()))
])

print("Row sums:", np.sum(matrix, axis=1))
print("Column sums:", np.sum(matrix, axis=0))

Input:
1 2 3
4 5 6
7 8 9

Output:
Row sums: [ 6 15 24]
Column sums: [12 15 18]

Question 5:
import numpy as np

rainfall = np.array(list(map(int, input("Enter rainfall for 12 months: ").split())))

total = np.sum(rainfall)
average = np.mean(rainfall)

months = np.where(rainfall > average)[0] + 1

print("Total Rainfall:", total)
print("Average Rainfall:", round(average, 2))
print("Months having rainfall above average:", months)

Input: 120 85 150 200 175 90 110 160 210 180 95 130
Output: 
Total Rainfall: 1705
Average Rainfall: 142.08
Months having rainfall above average: [ 3  4  5  8  9 10]

Question 6 :
import pandas as pd

df = pd.DataFrame({
    'Name': ['Arun', 'Bala', 'Charan', 'Divya'],
    'Python': [80, 65, 90, 75],
    'Java': [85, 70, 88, 80],
    'DBMS': [75, 60, 92, 78]
})

df['Total'] = df[['Python', 'Java', 'DBMS']].sum(axis=1)
df['Average'] = df[['Python', 'Java', 'DBMS']].mean(axis=1)

print(df[['Name', 'Total', 'Average']])

print("\nStudents with Average > 75:")
print(df.loc[df['Average'] > 75, ['Name', 'Average']])

Output:
     Name  Total  Average
0    Arun    240    80.00
1    Bala    195    65.00
2  Charan    270    90.00
3   Divya    233    77.67

Students with Average > 75:
     Name  Average
0    Arun    80.00
2  Charan    90.00
3   Divya    77.67

Question 7:
import pandas as pd

df = pd.DataFrame({
    'ID': [101, 102, 103, 104, 105],
    'Name': ['Ravi', 'Kumar', 'Anu', 'Priya', 'Manoj'],
    'Department': ['IT', 'HR', 'IT', 'HR', 'Sales'],
    'Salary': [50000, 45000, 65000, 55000, 60000]
})

result = df.loc[df.groupby('Department')['Salary'].idxmax()]

result = result.sort_values('Department')

print(result[['Department', 'Name', 'Salary']])

Output:
  Department   Name  Salary
3         HR  Priya   55000
2         IT    Anu   65000
4      Sales  Manoj   60000

Question 8:
import pandas as pd

df = pd.DataFrame({
    'Product': ['Laptop', 'Mouse', 'Keyboard', 'Mobile', 'Tablet'],
    'Category': ['Electronics', 'Accessories', 'Accessories',
                 'Electronics', 'Electronics'],
    'Quantity': [5, 20, 10, 8, 6],
    'Price': [50000, 500, 1000, 20000, 15000]
})

df['Total_Sales'] = df['Quantity'] * df['Price']

print(df[['Product', 'Total_Sales']])

print("\nCategory Total Sales:")
print(df.groupby('Category')['Total_Sales'].sum())

Output:
    Product  Total_Sales
0    Laptop       250000
1     Mouse        10000
2  Keyboard        10000
3    Mobile       160000
4    Tablet        90000

Category Total Sales:
Category
Accessories      20000
Electronics     500000
Name: Total_Sales, dtype: int64

Question 9:
import pandas as pd

df = pd.DataFrame({
    'Name': ['Arun', 'Bala', 'Charan', 'Divya'],
    'Total_Days': [50, 50, 50, 50],
    'Present_Days': [45, 38, 48, 35]
})

df['Attendance %'] = (df['Present_Days'] / df['Total_Days']) * 100

print(df[['Name', 'Attendance %']])

print("\nStudents below 80%:")
print(df.loc[df['Attendance %'] < 80, ['Name', 'Attendance %']])

Output:
     Name  Attendance %
0    Arun          90.0
1    Bala          76.0
2  Charan          96.0
3   Divya          70.0

Students below 80%:
    Name  Attendance %
1   Bala          76.0
3  Divya          70.0

Qusetion 10:
import pandas as pd

df = pd.DataFrame({
    'Product': ['Laptop', 'Mobile', 'Mouse', 'Keyboard', 'Tablet'],
    'Category': ['Electronics', 'Electronics', 'Accessories',
                 'Accessories', 'Electronics'],
    'Rating': [4.5, 4.2, 3.8, 4.6, 4.8]
})

avg = df.groupby('Category')['Rating'].mean()

print("Category Average Rating:")
print(avg)

highest = avg.idxmax()
rating = avg.max()

print("\nHighest Rated Category:")
print(highest, rating)

Output:
Category Average Rating:
Category
Accessories    4.20
Electronics    4.50
Name: Rating, dtype: float64

Highest Rated Category:
Electronics 4.5
