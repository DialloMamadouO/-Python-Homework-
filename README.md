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
Total Months: 22
Total: $19093448
Average Change: $0.0
Greatest Increase in Profits:  ($0
Greatest Decrease in profits: Jan-2010($0)


PyRamen

{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Import libraries\n",
    "from pathlib import Path\n",
    "import csv"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "ename": "NameError",
     "evalue": "name 'Path' is not defined",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[1;31mNameError\u001b[0m                                 Traceback (most recent call last)",
      "\u001b[1;32m<ipython-input-3-9bbe48ff89b7>\u001b[0m in \u001b[0;36m<module>\u001b[1;34m\u001b[0m\n\u001b[0;32m      1\u001b[0m \u001b[1;31m# Set file path\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m----> 2\u001b[1;33m \u001b[0mcsvmanupath\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0mPath\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m\"../../PyRamen/Homework_Python_PyRamen_Resources_menu_data.csv\"\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m      3\u001b[0m \u001b[0mcsvsalespath\u001b[0m \u001b[1;33m=\u001b[0m \u001b[1;33m(\u001b[0m\u001b[1;34m\"../../PyRamen/Homework_Python_PyRamen_Resources_sales_data.csv\"\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;31mNameError\u001b[0m: name 'Path' is not defined"
     ]
    }
   ],
   "source": [
    "# Set file path\n",
    "csvmanupath = Path(\"../../PyRamen/Homework_Python_PyRamen_Resources_menu_data.csv\")\n",
    "csvsalespath = (\"../../PyRamen/Homework_Python_PyRamen_Resources_sales_data.csv\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [],
   "source": [
    "#Initialize list object\n",
    "menu = []\n",
    "sales = []"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {},
   "outputs": [
    {
     "ename": "NameError",
     "evalue": "name 'csvmanupath' is not defined",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[1;31mNameError\u001b[0m                                 Traceback (most recent call last)",
      "\u001b[1;32m<ipython-input-2-b951a3ea8d08>\u001b[0m in \u001b[0;36m<module>\u001b[1;34m\u001b[0m\n\u001b[0;32m      1\u001b[0m \u001b[1;31m# Open the csv file as object\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m----> 2\u001b[1;33m \u001b[1;32mwith\u001b[0m \u001b[0mopen\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mcsvmanupath\u001b[0m\u001b[1;33m)\u001b[0m \u001b[1;32mas\u001b[0m \u001b[0mcsvmanufile\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m      3\u001b[0m     \u001b[1;31m# Pass in the csv file to the csv.reader() function and return the csvreader object\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m      4\u001b[0m     \u001b[0mcsvreader\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0mcsv\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mreader\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mcsvmanufile\u001b[0m\u001b[1;33m,\u001b[0m \u001b[0mdelimiter\u001b[0m\u001b[1;33m=\u001b[0m \u001b[1;34m','\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;31mNameError\u001b[0m: name 'csvmanupath' is not defined"
     ]
    }
   ],
   "source": [
    "# Open the csv file as object\n",
    "with open(csvmanupath) as csvmanufile:\n",
    "    # Pass in the csv file to the csv.reader() function and return the csvreader object\n",
    "    csvreader = csv.reader(csvmanufile, delimiter= ',')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Skip header\n",
    "next(reader)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "metadata": {},
   "outputs": [
    {
     "ename": "NameError",
     "evalue": "name 'reader' is not defined",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[1;31mNameError\u001b[0m                                 Traceback (most recent call last)",
      "\u001b[1;32m<ipython-input-19-e71dedcdafbe>\u001b[0m in \u001b[0;36m<module>\u001b[1;34m\u001b[0m\n\u001b[0;32m      1\u001b[0m \u001b[1;31m# Iterate over each row after the header\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m----> 2\u001b[1;33m \u001b[1;32mfor\u001b[0m \u001b[0mrow\u001b[0m \u001b[1;32min\u001b[0m \u001b[0mreader\u001b[0m\u001b[1;33m:\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m      3\u001b[0m     \u001b[0mmanu\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mappend\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0mrow\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;31mNameError\u001b[0m: name 'reader' is not defined"
     ]
    }
   ],
   "source": [
    "# Iterate over each row after the header\n",
    "for row in reader:\n",
    "    manu.append(row)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Open the csvsales file as object\n",
    "report = {}"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Initialize a row counter variable\n",
    "row_count = 0"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Loop over every row \n",
    "for row in sales \n",
    "print()\n",
    "print(row)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Line_item_Id, Date, Credit_Card_Number, Quantity, Manu_Item\n",
    "# Initialize sales data variables\n",
    "quantity = int(row[3])\n",
    "sales_item = row[4]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# If the item value is not in the report, add it as a new entry with initialize metrics\n",
    "# Keys are ordered in logical fashion count, revenue, cost, profit\n",
    "if sales_item not in report.keys():\n",
    "    report [sales_item] = {\n",
    "            '01-count':  0,\n",
    "            '02-revenue': 0,\n",
    "            '03-cost': 0,\n",
    "            '04-profit': 0,\n",
    "    }\n",
    "# for every row in the sales data, loop over the manu records to determine a match\n",
    "for records in manu:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "=# Item, Category, Description, Price, Cost\n",
    "# Initialize manu data variables\n",
    "item = record[0]\n",
    "price = float(record[3])\n",
    "cost = float(record[4])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Calculate profite of each item in the manu data\n",
    "profit = price - cost"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# If the item value in our sales data is equal to any of the items in the manu, then track metrics for that item\n",
    "if sales_item == item\n",
    "\n",
    "# Print out matching manu data\n",
    "    print(f\"Does {sales_item} equal {item}? WE HAVE A MATCH!!!)\n",
    "    print(f\" item: {item}\")\n",
    "    print(f\" price: ${peice}\")\n",
    "    print(f\" cost: ${cost}\")\n",
    "    print(f\" profit: ${profit}\")\n",
    "      "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cumilatively add up the metrics for each item key\n",
    "report[sales_ite][\"01 count\"] += quantity\n",
    "report[sales_item][\"02 revenue\"] == price*quantity\n",
    "report[sales_items][\"03 cogs\"] += cost*quantity\n",
    "report[sales_item][\"04 profit\"] += profit*quantity"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Else the sales_item does not equal to any other item in the many so no match\n",
    "else:\n",
    "    print(\"Does\" sales_item, \"rqual\", record[0], ?\" WOO HOO NO MATCH\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Increment the row counter by 1\n",
    "row_count += 1"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Print total number of records in sales data\n",
    "print()\n",
    "print(\"Total number of records:\", row_count)\n",
    "print() "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Write out report to text file\n",
    "with open(\"report,txt\", 'w') as a txt file:\n",
    "    for key, value report.items()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "line = f\"{key} {value}\\n\"\n",
    "txt_file.write(line)"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.7.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}

