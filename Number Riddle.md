# python
import random
from tkinter import *

ifc= Tk()
ifc.title("Akanksha's Game")
ifc.geometry('600x400')
ifc.config(bg="#666699")
var = IntVar()
st=StringVar()
hs= StringVar()

global eNo
eNo = random.randint(1,100)
global attempt
attempt =6

def hints():
    global eNo
    if (eNo>1 or eNo==1 or eNo==10 or eNo<10):
        msd = (f"hint: This number when multiplied by 5 gives: {eNo*5}")
    elif(eNo>11 or eNo==11 or eNo<20 or eNo==20):
        msd = (f"Hint: This number gives an addition of {eNo+8} when 8 is added to it")
    elif(eNo>21 or eNo==21 or eNo<30 or eNo==30):
        msd = (f"Hint: This number when divided by 9 gives the result as '{eNo/9}'")
    elif(eNo>31 or eNo==31 or eNo<40 or eNo==40):
        msd = "Hint: This number can be between 31 to 40"
    elif(eNo>41 or eNo==41 or eNo<45 or eNo==45):
        msd = "Hint: This number is greater than 41"
    elif(eNo>45 or eNo==45 or eNo<50 or eNo==50):
        msd = "hint: This number is less than 50 but greater than 45"
    elif(eNo>51 or eNo==51 or eNo<60 or eNo==60):
        msd = f"Hint: When 8 is subtracted from {eNo+8} this is the number you get"
    elif(eNo>61 or eNo==61 or eNo<70 or eNo==70):
        msd = "Hint: Oh boy! you're in 60s"
    elif(eNo>71 or eNo==71 or eNo<80 or eNo==80):
        msd = "Hint: A number I know begins from '7', it is afraid of being ate and so stays away from '8'"
    elif(eNo>81 or eNo==81 or eNo<90 or eNo==90):
        msd = "Hint: This is the score you wish you had in school...oh wait not talking above 91"
    elif(eNo>91 or eNo==91 or eNo<100 or eNo==100):
        msd = "Hint: Damnn!! You're heading towards a century"
    print(msd)
    hs.set(msd)

def wingame():
    global eNo
    global attempt
    go = var.get()
    if attempt > 0:
        if go == eNo:
            op_msg = f"You Won! Playaaa"
        else :
            attempt -= 1
            op_msg = f'You have {attempt} attempt left.'
    else:
        op_msg = f'Out of attempts! You Loose!!!!.'

    st.set(op_msg)


label = Label(ifc, text="Numbers and Riddles", font=('sans-serif',30), relief= SOLID, padx=10, pady=10, bg='#00ff00')
label.pack(pady=(10,0))

bt1 = Button(ifc, text = "Start", font=('sans-serif', 18), command=hints)
bt1.pack(pady=(10,0)) 

lb= Label(ifc, textvariable=hs, bg="#666699", font=('sans-serif', 14))
lb.pack(pady=(20,0))

ent = Entry(ifc, textvariable=var, font=('sans-serif', 18))
ent.pack(pady=(20,10))

bt = Button(ifc, text = "Submit Guess", font=('sans-serif', 18), command=wingame)
bt.pack()


lb1= Label(ifc, textvariable=st, bg="#666699", font=('sans-serif', 14))
lb1.pack(pady=(20,0))

ifc.mainloop()
