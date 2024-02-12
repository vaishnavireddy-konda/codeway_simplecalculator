# codeway_simplecalculator
import tkinter as tk

def calculate():
    num1 = float(entry_num1.get())
    num2 = float(entry_num2.get())
    operation = operation_var.get()

    if operation == "Add":
        result = num1 + num2
    elif operation == "Subtract":
        result = num1 - num2
    elif operation == "Multiply":
        result = num1 * num2
    elif operation == "Divide":
        if num2 == 0:
            result = "Cannot divide by zero!"
        else:
            result = num1 / num2

    result_label.config(text="Result: " + str(result))

root = tk.Tk()
root.title("Simple Calculator")
root.configure(bg="red")


entry_num1 = tk.Entry(root, width=10)
entry_num1.grid(row=0, column=0, padx=5, pady=5)

operation_var = tk.StringVar(root)
operation_var.set("Add")
operation_menu = tk.OptionMenu(root, operation_var, "Add", "Subtract", "Multiply", "Divide")
operation_menu.grid(row=0, column=1, padx=5, pady=5)

entry_num2 = tk.Entry(root, width=10)
entry_num2.grid(row=0, column=2, padx=5, pady=5)

result_label = tk.Label(root, text="Result: ", bg="#f0f0f0")
result_label.grid(row=1, columnspan=3, padx=5, pady=5)

calculate_button = tk.Button(root, text="Calculate", command=calculate, width=20, bg="#008080", fg="white")
calculate_button.grid(row=2, columnspan=3, padx=5, pady=5)

root.mainloop()
