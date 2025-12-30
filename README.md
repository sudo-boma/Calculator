```
import tkinter as tk
import math

class Calculator:
    def __init__(self, master):
        self.master = master
        master.title("Calculator")
        master.geometry("400x500")
        master.resizable(False, False)

        self.total = tk.StringVar()

        self.entry = tk.Entry(master, textvariable=self.total, font=("Arial", 20),
                              justify='right', bd=10, relief=tk.SUNKEN)
        self.entry.grid(row=0, column=0, columnspan=5, sticky="nsew", padx=10, pady=10)
        self.create_buttons()

        master.grid_rowconfigure(0, weight=1, minsize=80)
        for row in range(1, 6):
            master.grid_rowconfigure(row, weight=1)
        for col in range(5):
            master.grid_columnconfigure(col, weight=1)

    def create_buttons(self):
        button_list = [
            ['sin', 'cos', 'tan', '^2', '10^x'],
            ['7', '8', '9', '/', 'log(x)'],
            ['4', '5', '6', '*', '1/x'],
            ['1', '2', '3', '-', 'x!'],
            ['0', 'C', '=', '+', 'sqrt']
        ]

        for i, row in enumerate(button_list):
            for j, button_text in enumerate(row):
                button = tk.Button(
                    self.master, text=button_text, width=5, height=3,font=("Arial", 16),
                    command=lambda text=button_text: self.click(text),
                    padx=10, pady=10, bd=3, relief=tk.RAISED
                )
                button.grid(row=i + 1, column=j, sticky="nsew", padx=2, pady=2)
                
                for row in range(6):
                    self.master.grid_rowconfigure(row, weight=1)
                for col in range(5):
                    self.master.grid_columnconfigure(col, weight=1)
        

    def click(self, button_text):
        current_text = self.entry.get()
        if button_text == '=':
            try:
                expression = current_text
                expression = expression.replace('^', '**')
                result = eval(expression)
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == 'C':
            self.total.set("")
        elif button_text == 'sin':
            try:
                result = math.sin(math.radians(float(current_text)))
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == 'cos':
            try:
                result = math.cos(math.radians(float(current_text)))
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == 'tan':
            try:
                result = math.tan(math.radians(float(current_text)))
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == '^2':
            try:
                result = float(self.entry.get()) **2
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == 'log(x)':
            try:
                result = math.log10(float(current_text))
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == '1/x':
            try:
                result = 1 / float(current_text)
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == 'x!':
            try:
                result = math.factorial(int(current_text))
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == '10^x':
            try:
                result = 10 ** float(current_text)
                self.total.set(result)
            except:
                self.total.set("Error")
        elif button_text == 'sqrt':
            try:
                result = math.sqrt(float(current_text))
                self.total.set(result)
            except:
                self.total.set("Error")
        else:
            self.total.set(current_text + button_text)

if __name__ == '__main__':
    root = tk.Tk()
    my_calculator = Calculator(root)
    root.mainloop()
```
