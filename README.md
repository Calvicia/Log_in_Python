# Log_in_Python
from Tkinter import *
import tkMessageBox

raiz = Tk()
nom = ""
passw = ""

#---DEF------BotóEntrar------------------------------------------

def codigoBoton():
    if cuadroNombre.get() == "Juan" and cuadroPass.get() == "hola":
        tkMessageBox.showinfo("Correcto", "Te has logeado correctamente")
    else:
        tkMessageBox.showinfo("Mal", "Te has logeado incorrectamente, revista contrasenya o nombre")

#---DEF------BotóRegistre------------------------------------------

def Registre():
  
    a = Tk()
    aFrame = Frame(a,width=0,height=0)
    aFrame.pack()

    cuadroNom = StringVar()
    cuadroPas = Entry(aFrame)

    nombreLabel = Label(aFrame, text = "Nuevo nombre:")
    nombreLabel.grid(row = 0, column = 0, sticky="e", padx=5, pady= 5)

    cuadroNom = Entry(aFrame, textvariable=nom)
    cuadroNom.grid(row=0, column = 1, padx=5, pady= 5)
    cuadroNom.config(fg="Black", justify = "left")

    pasLabel = Label(aFrame, text = "Nueva password:")
    pasLabel.grid(row = 1, column = 0, sticky="e", padx=5, pady= 5)

    cuadroPas.grid(row=1, column = 1, padx=5, pady= 5)

    botonAc = Button(a, text = "Aceptar", command = Aceptar)
    botonAc.grid(row = 1, column = 2, padx=5, pady= 5)
    botonAc.pack()
    
    
    
    a.mainloop()
#---DEF------Aceptar Registro------------------------------------

def Aceptar():
    global nom
    global passw
    global cuardoNom
    global cuadroPas

       
    nom = cuadroNom.get()
    passw = cuadroPas.get()

    print nom
    print passw
#------------Frames/var------------------------------------
miFrame = Frame(raiz, width = 500, height = 500)
miFrame.pack()

minombre = StringVar()
cuadroPass = Entry(miFrame)

#-------------Nom--------------------------------------------

nombreLabel = Label(miFrame, text = "Nombre:")
nombreLabel.grid(row = 0, column = 0, sticky="e", padx=5, pady= 5)

cuadroNombre = Entry(miFrame, textvariable=minombre)
cuadroNombre.grid(row=0, column = 1, padx=5, pady= 5)
cuadroNombre.config(fg="Black", justify = "left")

#------------Password-------------------------------------------

passLabel = Label(miFrame, text = "Password:")
passLabel.grid(row = 1, column = 0, sticky="e", padx=5, pady= 5)

cuadroPass.grid(row=1, column = 1, padx=5, pady= 5)


#---------BotoRegistre-------------------------------------

botonRegistre = Button(raiz, text = "Registre", command = Registre)
botonRegistre.grid(row = 0, column = 2, padx=5, pady= 5)
botonRegistre.pack()

#----------BotóLogIn----------------------------------------

botonEnvio = Button(raiz, text = "Enviar", command = codigoBoton)
botonEnvio.grid(row = 1, column = 2, padx=5, pady= 5)
botonEnvio.pack()



raiz.mainloop()
