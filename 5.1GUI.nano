import RPi.GPIO as GPIO
import tkinter as tk

# Set up GPIO
GPIO.setmode(GPIO.BCM)
GPIO.setup(17, GPIO.OUT)  # Red LED
GPIO.setup(18, GPIO.OUT)  # Green LED
GPIO.setup(27, GPIO.OUT)  # Blue LED

# Function to turn on selected LED and turn off others
def select_led(led_pin):
    GPIO.output(17, GPIO.LOW)  # Turn off red LED
    GPIO.output(18, GPIO.LOW)  # Turn off green LED
    GPIO.output(27, GPIO.LOW)  # Turn off blue LED

    GPIO.output(led_pin, GPIO.HIGH)  # Turn on selected LED

# Function to exit the GUI and clean up GPIO
def exit_gui():
    GPIO.cleanup()
    root.destroy()

# Create GUI
root = tk.Tk()
root.title("LED Controller")
root.configure(bg="lightblue")

# Create radio buttons
led_var = tk.StringVar()

red_radio = tk.Radiobutton(root, text="Red LED", variable=led_var, value="red", command=lambda: select_led(17), font=("Arial", 12), bg="lightgray")
red_radio.pack(pady=5)

green_radio = tk.Radiobutton(root, text="Green LED", variable=led_var, value="green", command=lambda: select_led(18), font=("Arial", 12), bg="lightgray")
green_radio.pack(pady=5)

blue_radio = tk.Radiobutton(root, text="Blue LED", variable=led_var, value="blue", command=lambda: select_led(27), font=("Arial", 12), bg="lightgray")
blue_radio.pack(pady=5)

# Create exit button
exit_button = tk.Button(root, text="Exit", command=exit_gui, font=("Arial", 12, "bold"), bg="red", fg="white", width=10)
exit_button.pack(pady=10)

# Center the GUI window on the screen
win_width = 300
win_height = 200
screen_width = root.winfo_screenwidth()
screen_height = root.winfo_screenheight()
x = (screen_width - win_width) // 2
y = (screen_height - win_height) // 2
root.geometry(f"{win_width}x{win_height}+{x}+{y}")

root.mainloop()
