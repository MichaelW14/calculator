# calculator
import tkinter

button_list = {"C": {"row": "1",
                     "column": "0"},
               "CE": {"row": "1",
                      "column": "1"},
               "7": {"row": "2",
                     "column": "0"},
               "8": {"row": "2",
                     "column": "1"},
               "9": {"row": "2",
                     "column": "2"},
               "+": {"row": "2",
                     "column": "3"},
               "0": {"row": "5",
                     "column": "0"},
               "1": {"row": "4",
                     "column": "0"},
               "2": {"row": "4",
                     "column": "1"},
               "3": {"row": "4",
                     "column": "2"},
               "4": {"row": "3",
                     "column": "0"},
               "5": {"row": "3",
                     "column": "1"},
               "6": {"row": "3",
                     "column": "2"},
               "-": {"row": "3",
                     "column": "3"},
               "*": {"row": "4",
                     "column": "3"},
               "/": {"row": "5",
                     "column": "3"},
               "=": {"row": "5",
                     "column": "1"}
               }

mainWindow = tkinter.Tk()

mainWindow.title("Calculator")
mainWindow.geometry('640x480-8-200')
mainWindow['padx'] = 8

calculator_input = tkinter.Entry(mainWindow)
calculator_input.grid(row=0, column=0, sticky='nsew', columnspan=4)

calculator_button_frame = tkinter.Frame(mainWindow)
calculator_button_frame.grid(row=1, column=0, sticky='nsew')

for x in button_list:
    if x == '=':
        calculator_buttons = tkinter.Button(mainWindow, text=x)
        calculator_buttons.grid(row=button_list[x]["row"], column=button_list[x]["column"], sticky='new', columnspan=2)
    else:
        calculator_buttons = tkinter.Button(mainWindow, text=x)
        calculator_buttons.grid(row=button_list[x]["row"], column=button_list[x]["column"], sticky='new')

mainWindow.update()
mainWindow.minsize(calculator_button_frame.winfo_width() + 200, calculator_input.winfo_height() +
                   calculator_button_frame.winfo_height())
mainWindow.maxsize(calculator_button_frame.winfo_width() + 200, calculator_input.winfo_height() + 200 +
                   calculator_button_frame.winfo_height())

tkinter.mainloop()
