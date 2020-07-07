# -Python-Homework-
PyBank                               

# Creating a Python script that analyses the records to calculate each of the following

# Import the pathlib and csv library
from pathlib import Path

import csv

# Set the file path
csvpath = Path("../PyBank/PyBank_Resources_budget_data.csv")

csvfile_to_output = Path("../PyBank/main.txt")

# Initialize racords

total_months = 0

month_of_change = []

net_change_list = []

greatest_increase = ["", 0]

greatest_decrease = ["", 999999]

total_net = 0


# Open the csv file as object

with open(csvpath, 'r') as csvfile:

# Pass in the csv file to the csv.reader() function and return the csvreader object
   
   reader = csv.reader(csvfile, delimiter=',')
   
  # Read the header row
    header = next(reader)
    
    # Extract first row
    first_row = next(reader)
    total_months = total_months + 1
    total_net = total_net + int(first_row[1])
    prev_net = int(first_row[1])
      
    # Total
    total_months = total_months + 1
    total_net = total_net + int(first_row[1])
        
        # Net Change
    net_change = int(first_row[1]) - prev_net
    prev_net = int(first_row[1])
    net_change_list = net_change_list + [net_change]
    month_of_change = month_of_change + [first_row[0]]
        
        # Greatest increase
    if net_change > greatest_increase[1]:
        greatest_increase[0] = int(first_row[0])
        greatest_increase[1] = net_change
            
        # Greatest decrease
    if net_change < greatest_decrease[1]:
        greatest_decrease[0] = first_row[0]
        greatest_decrease[1] = net_change
            
        # Average change
net_monthly_average = round(sum(net_change_list) / len(net_change_list) , 2)

# Export the results to text file 
with open(csvfile_to_output, "w+") as csvfile:
    csvfile.write(f"PyBank/main.ipynb\n")
    csvfile.write(f"PyBank/main.ipynb\n")
    csvfile.write(f"Total Months: {total_months}\n")
    csvfile.write(f"Total: ${total_net}\n")
    csvfile.write(f"Average Change: ${net_monthly_average}\n")
    csvfile.write(f"Greatest Increase in Profits: {greatest_increase[0]} (${greatest_increase[1]}\n")
    csvfile.write(f"Greatest Decrease in profits: {greatest_decrease[0]}(${greatest_decrease[1]})\n")
 

PyBank/main.ipynb

PyBank/main.ipynb

Total Months: 6

Total: $5207304

Average Change: $0.0

Greatest Increase in Profits:  ($0

Greatest Decrease in profits: Jan-2010($0)
