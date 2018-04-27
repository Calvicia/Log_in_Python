# This code opens one frame that shows the LOG IN page,
# There we find two buttons, one for Log in and another for Sign in
# If you Log in correctly you will see a message that says "You log in correctly"
# If not you will se a message that says "You log in incorrectly, revise your user and password"
# The sign in button opens a new frame were you can establish new value to User and Password

  
     
    from Tkinter import *
    import tkMessageBox

    raiz = Tk()
    nom = "09l90on"   # 09109on is for making a initial user
    passw = "098.87"  # 098.87 is for making a initial password

    #---DEF------Log in--------------------------------------------

    def ButtonCode():
        if cuadroNombre.get() == nom and cuadroPass.get() == passw:
            tkMessageBox.showinfo("Correct", "You log in correctly")
            raiz.destroy()
        
        else:
            tkMessageBox.showinfo("Wrong", "You log in incorrectly, revise your user and password")

    #---DEF------Sign in------------------------------------------

    def signin():
  
        a = Tk()
        aFrame = Frame(a,width=0,height=0)
        aFrame.pack()

        cuadroNom = StringVar()
        cuadroPas = Entry(aFrame)

        def accept():
            global nom
            global passw
       
            nom = cuadroNom.get()
            passw = cuadroPas.get()

            a.destroy()

            print nom
            print passw

        nombreLabel = Label(aFrame, text = "New name:")
        nombreLabel.grid(row = 0, column = 0, sticky="e", padx=5, pady= 5)

        cuadroNom = Entry(aFrame, textvariable=nom)
        cuadroNom.grid(row=0, column = 1, padx=5, pady= 5)
        cuadroNom.config(fg="Black", justify = "left")

        pasLabel = Label(aFrame, text = "New password:")
        pasLabel.grid(row = 1, column = 0, sticky="e", padx=5, pady= 5)

        cuadroPas.grid(row=1, column = 1, padx=5, pady= 5)

        botonAc = Button(a, text = "Aceptar", command = accept)
        botonAc.grid(row = 1, column = 2, padx=5, pady= 5)
        botonAc.pack()
       
    
        a.mainloop()
        
        
    #------------Frames/var------------------------------------
    miFrame = Frame(raiz, width = 500, height = 500)
    miFrame.pack()

    minombre = StringVar()
    cuadroPass = Entry(miFrame)

    #-------------Name--------------------------------------------

    nombreLabel = Label(miFrame, text = "Nombre:")
    nombreLabel.grid(row = 0, column = 0, sticky="e", padx=5, pady= 5)
  
    cuadroNombre = Entry(miFrame, textvariable=minombre)
    cuadroNombre.grid(row=0, column = 1, padx=5, pady= 5)
    cuadroNombre.config(fg="Black", justify = "left")

    #------------Password-------------------------------------------

    passLabel = Label(miFrame, text = "Password:")
    passLabel.grid(row = 1, column = 0, sticky="e", padx=5, pady= 5)

    cuadroPass.grid(row=1, column = 1, padx=5, pady= 5)


    #---------Sign in Button-------------------------------------

    signinButton = Button(raiz, text = "Sign in", command = signin)
    signinButton.grid(row = 0, column = 2, padx=5, pady= 5)
    signinButton.pack()

    #----------Log in Button----------------------------------------

    sendButton = Button(raiz, text = "Enviar", command = ButtonCode)
    sendButton.grid(row = 1, column = 2, padx=5, pady= 5)
    sendButton.pack()


    raiz.mainloop() 
