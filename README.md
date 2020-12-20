# Weather Station
### ETR 107 Final Project
#### Weatherbit for Microbit
This is a project that I thouroghly enjoyed.  I wanted to create a interface from my computer using tkinter and allow communication to the weather;bit extension on my microbit.
The measurements I am taking is for Windspeed, Temperature, Barometric Pressure, Humidity, Sunlight Level, and altitude.  The following is my Python code for the serial interface to the microbit/weatherbit extension.

   ```# Python serial interface to a micro:bit
   
   import serial
   import tkinter as tk

   # Send a command to the micro:bit and show the response
   def myfunc(action):
   print ("Requested action: ",action)
   out = action + "\n"
   out2 = out.encode('utf_8')
   ser.write(out2)   
   lstatus.config(text = ser.readline())

   # configure the serial connections
   ser = serial.Serial(
    port='COM11',
    baudrate=115200
   )

   root = tk.Tk()
   root.title("Weather Station")

   # Button for temperature 
   bt_T = tk.Button(root, width=25,text= "Temperature",bg='silver' ,
   command = lambda: myfunc("T"),relief="raised")
   bt_T.grid(row = 1,column = 1)

   # Button for light sensor 
   bt_L = tk.Button(root, width=25,text= "Light Level",bg='silver' ,
   command = lambda: myfunc("L"),relief="raised")
   bt_L.grid(row = 1,column = 2)

   # Button for humidity
   bt_1 = tk.Button(root, width=25,text= "Humidity",bg='silver' ,
   command = lambda: myfunc("H"),relief="raised")
   bt_1.grid(row = 2,column = 1)

   # Button for Barometric Pressure
   bt_0 = tk.Button(root, width=25,text= "Barometric Pressure",bg='silver' ,
   command = lambda: myfunc("P"),relief="raised")
   bt_0.grid(row = 2,column = 2)

   # Button for Wind Speed
   bt_0 = tk.Button(root, width =25, text= "Wind Speed",bg='silver' ,
   command = lambda: myfunc("W"),relief="raised")
   bt_0.grid(row = 3,column = 1)

   # Button for Altitude
   bt_0 = tk.Button(root, width =25, text= "Altitude",bg='silver' ,
   command = lambda: myfunc("A"),relief="raised")
   bt_0.grid(row = 3,column = 2)


   # Label to show results
   lstatus = tk.Label(root, width= 50, text= "                 ", relief="raised")
   lstatus.grid(row = 4,column = 1,  columnspan = 2)

   root.mainloop()```
   
   
