case study
http://localhost:8888/notebooks/Case%20study.ipynb



from tkinter import *

root = Tk()
root.title("Staff Managerment System")
root.geometry('1000x700+0+0')
title = Label(root, text="Staff Managerment System", font=("arial",30,"bold"), fg="white", bg="blue")
title.pack(side=TOP, fill=X)   
root.configure(background='orange')


def add():
    global name, nameVar
    name.append(entry.get())
    name.append(entry2.get())
    name.append(entry3.get())
    nameVar.set(name)
    entry.delete(0, END)
    entry2.delete(0, END)
    entry3.delete(0, END)

def clear():
    global name, nameVar
    name = []
    nameVar.set(name)
    entry.delete(3, END)
    entry.focus()

    

label = Label(root, text='enter a name:')
label2 = Label(root, text='Tuổi tác:')
label3 = Label(root, text='Chức vụ:')

entry = Entry(root, width=20)
entry2 = Entry(root,width=20)
entry3 = Entry(root,width=20)

b1 = Button(root, text='Add', padx=13, pady=10, command=add)
b2 = Button(root, text='Clear', padx=11, pady=10, command=clear)

name = []
nameVar = StringVar(value=name)
lst = Listbox(root, listvariable=nameVar, height=20,width=100)

label.place(x=47, y=60)
label2.place(x=47,y=130)
label3.place(x=47,y=200)
entry.place(x=47,y=100)
entry2.place(x=47,y=170)
entry3.place(x=47,y=240)

lst.place(x=700, y=400)

b1.place(x=50, y=300)
b2.place(x=50, y=400)


root.mainloop()
