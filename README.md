# importing csv module
import csv
#import pandas as pd

# csv file name
filename = "p.csv"

# initializing the titles and rows list
fields = []
rows = []

# reading csv file
with open("p.csv", 'r') as csvfile:
    # creating a csv reader object
    csvreader = csv.reader(csvfile,dialect='excel')

    # extracting field names through first row
    fields = csvreader.next()

    # extracting each data row one by one
    for row in csvreader:
        rows.append(row)

    # get total number of rows
    print("Total no. of rows: %d"%(csvreader.line_num))

# printing the field names
print('Field names are:' + ', '.join(field for field in fields))

#  printing first 5 rows
print('\nFirst 5 rows are:\n')
for row in rows[:20]:
    # parsing each column of a row
    for col in row:
        num = col
        print("%10s"%num),
        print("%10s"%col),
    print('\n')
