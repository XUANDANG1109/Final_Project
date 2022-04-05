# Final_Project
Covertor
ASSIGNMENT 5 - GROUP 1
FINAL PROJECT
Date 04/04/2022
Member:
Cong Minh Nguyen
Linh Nguyen
Xuan Dang Thi Linh
Convertor
Create a program that can be used to converttemperature, length, weight, pressure.Your program should have a menu displayed for the user to choose from, where are listed the convertion options:
temperature
- fahrenheit to celsius
- celsius to fahrenheit
length
- miles to km
- km to miles
weight
- pound to kilogramms
- kg to pound
exit
The program should allow user to choose the desired convertionover and over again until user chooses to quit using it.
# Import ipywidgets for Graphical User Interface (GUI)
from ipywidgets import RadioButtons, Button, GridBox, Layout, ButtonStyle, Text, Output
​
# Define output
output = Output()
​
# Create input display screen
input_screen = Text(description = "User Input", layout=Layout(width='300px', height='50px'))
display(input_screen)
​
# Create result display screen
result_screen = Text(description = "Result", disabled=True, layout=Layout(width='300px', height='50px'))
display(result_screen)
​
​
rButton = RadioButtons(
    options=['Km->Mile', 'Mile->Km', 'Kg->Pound', 'Pound->Kg', '°F->°C ', '°C->°F'],
    description='Type:',
    disabled=False
)
display(rButton)
​
clear  = Button(description='Clear',
                 layout=Layout(width='300px', height='50px'),
                 style=ButtonStyle(button_color='gray'))
display(clear)
​
convert  = Button(description='CONVERSION',
                 layout=Layout(width='300px', height='50px'),
                 style=ButtonStyle(button_color='Darkorange'))
​
display(convert)
​
def bclear(b):
    input_screen.value = ""
    result_screen.value = ""
           
clear.on_click(bclear)
​
# define convert fomular
def convt(b):
    x = float(input_screen.value)
    if rButton.value == "Km->Mile":
        x = float(input_screen.value)
        input_screen.value = input_screen.value + "  Km"
        y = x * 0.62137
        result_screen.value = str(round(y, 2)) + "  Miles"
    elif rButton.value == "Mile->Km":
        x = float(input_screen.value)
        input_screen.value = input_screen.value + "  Miles"
        y = x / 0.62137
        result_screen.value = str(round(y, 2)) + "  Km"
    elif rButton.value == "Kg->Pound":
        x = float(input_screen.value)
        input_screen.value = input_screen.value + "  Kg"
        y = x * 2.2
        result_screen.value = str(round(y, 2)) + "  Pounds"
    elif rButton.value == "Pound->Kg":
        x = float(input_screen.value)
        input_screen.value = input_screen.value + "  Pounds"
        y = x / 2.2
        result_screen.value = str(round(y, 2)) + "  Kg"
    elif rButton.value == "°F->°C ":
        x = float(input_screen.value)
        input_screen.value = input_screen.value + "  °F"
        y = 5/9 * (x - 32)
        result_screen.value = str(round(y, 2)) + " °C "
    elif rButton.value == "°C->°F":
        x = float(input_screen.value)
        input_screen.value = input_screen.value + "  °F"
        y = (x * 9/5) + 32
        result_screen.value = str(round(y, 2)) + " °C "
convert.on_click(convt)
