# container

container:-
we are making product on the blow modling after some time we can check the given below dimensions.
form sample is given below:-


                                                      reading 1                              reading 2                      reading 3


major axis ,
 minor axis , 
height, 
thickness 
neck dia 
internal dia
tesnile strenght
compression strenght


given below are thye hints for the above data to file or document:

First create the data
# import openpyxl module
import openpyxl

# Give the location of the file
path = "gfg.xlsx"

# To open the workbook
# workbook object is created
wb_obj = openpyxl.load_workbook(path)

# Get workbook active sheet object
# from the active attribute
sheet_obj = wb_obj.active

cell_obj = sheet_obj.cell(row=1, column=1)

print(cell_obj.value)


import openpyxl

# Give the location of the file
path = "gfg.xlsx"

wb_obj = openpyxl.load_workbook(path)

sheet_obj = wb_obj.active

row = sheet_obj.max_row
column = sheet_obj.max_column

print("Total Rows:", row)
print("Total Columns:", column)

print("\nValue of first column")
for i in range(1, row + 1):
    cell_obj = sheet_obj.cell(row=i, column=1)
    print(cell_obj.value)

print("\nValue of first row")
for i in range(1, column + 1):
    cell_obj = sheet_obj.cell(row=2, column=i)
    print(cell_obj.value, end=" ")

# import openpyxl module
import openpyxl

wb = openpyxl.Workbook()

sheet = wb.active

c1 = sheet.cell(row=1, column=1)

# writing values to cells
c1.value = "Hello"

c2 = sheet.cell(row=1, column=2)
c2.value = "World"

c3 = sheet['A2']
c3.value = "Welcome"

# B2 means column = 2 & row = 2.
c4 = sheet['B2']
c4.value = "Everyone"

wb.save("sample.xlsx")


# import openpyxl module 
import openpyxl 

wb = openpyxl.load_workbook("sample.xlsx") 

sheet = wb.active 

c = sheet['A3'] 
c.value = "New Data"

wb.save("sample.xlsx")














Import the data

Then print and save it



# import openpyxl module
import openpyxl

# import BarChart class from openpyxl.chart sub_module
from openpyxl.chart import BarChart, Reference

wb = openpyxl.Workbook()

sheet = wb.active

# write o to 9 in 1st column of the active sheet
for i in range(10):
    sheet.append([i])

# create data for plotting
values = Reference(sheet, min_col=1, min_row=1,
                   max_col=1, max_row=10)

# Create object of BarChart class
chart = BarChart()

# adding data to the Bar chart object
chart.add_data(values)

# set the title of the chart
chart.title = " BAR-CHART "

# set the title of the x-axis
chart.x_axis.title = " X_AXIS "

# set the title of the y-axis
chart.y_axis.title = " Y_AXIS "

sheet.add_chart(chart, "E2")

# save the file
wb.save("sample.xlsx")



# import openpyxl module
import openpyxl

# import LineChart class from openpyxl.chart sub_module
from openpyxl.chart import LineChart, Reference

wb = openpyxl.Workbook()
sheet = wb.active

# write o to 9 in 1st column of the active sheet
for i in range(10):
    sheet.append([i])

values = Reference(sheet, min_col=1, min_row=1,
                   max_col=1, max_row=10)

# Create object of LineChart class
chart = LineChart()

chart.add_data(values)

# set the title of the chart
chart.title = " LINE-CHART "

# set the title of the x-axis
chart.x_axis.title = " X-AXIS "

# set the title of the y-axis
chart.y_axis.title = " Y-AXIS "
sheet.add_chart(chart, "E2")

# save the file
wb.save("sample.xlsx")



