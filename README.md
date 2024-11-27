# Currency-Converter
from currency_converter import CurrencyConverter
import tkinter as tk

# Initialize the currency converter
c = CurrencyConverter()

# Create the main window
window = tk.Tk()
window.geometry("500x360")
window.title("Currency Converter")

# Function to handle conversion when the button is clicked
def clicked():
    amount = int(entry1.get())
    cur1 = entry2.get()
    cur2 = entry3.get()
    try:
        # Perform the conversion
        data = c.convert(amount, cur1, cur2)
        # Display the result
        label4 = tk.Label(window, text=f"Converted Amount: {data:.2f}", font="Times 16 bold")
        label4.place(x=150, y=300)
    except Exception as e:
        # Handle invalid inputs
        error_label = tk.Label(window, text=f"Error: {e}", font="Times 16 bold", fg="red")
        error_label.place(x=150, y=300)

# Title Label
label = tk.Label(window, text="Currency Converter", font="Times 20 bold")
label.place(x=120, y=40)

# Input Labels and Entry Fields
label1 = tk.Label(window, text="Enter amount here:", font="Times 16 bold")
label1.place(x=70, y=100)
entry1 = tk.Entry(window)
entry1.place(x=270, y=105)

label2 = tk.Label(window, text="Enter currency here:", font="Times 16 bold")
label2.place(x=30, y=150)
entry2 = tk.Entry(window)
entry2.place(x=270, y=155)

label3 = tk.Label(window, text="Enter desired currency:", font="Times 16 bold")
label3.place(x=15, y=200)
entry3 = tk.Entry(window)
entry3.place(x=270, y=205)

# Convert Button
button = tk.Button(window, text="Convert", font="Times 16 bold", command=clicked)
button.place(x=220, y=250)

# Run the application
window.mainloop()
