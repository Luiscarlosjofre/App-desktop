# App
#Aplicación de escritorio con tecnología Python, la librería Tkinter y mucho amor ;)
#Copiapo a junio de 2022 - luisjofreperez@gmail.com
def agregarcomodato():
    def agregar():
        id = idval.get()
        nombre = nombreval.get()
        apellidos = apellidosval.get() 
        run = runval.get()
        dispositivo = dispositivoval.get()
        marca = marcaval.get()
        modelo = modeloval.get()
        serie = serieval.get()
        fepre = fepreval.get()
        fedevo = fedevoval.get()
        estado = estadoval.get()
        
        addeddate = time.strftime("%d/%m/%Y")
        addedtime = time.strftime("%H:%M:%S")
        try:
            str='insert into contratos values(%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)'
            mycursor.execute(str,(id,nombre,apellidos,run,dispositivo,marca,modelo,serie,fepre,fedevo,estado,addeddate,addedtime))
            con.commit()
            res=messagebox.showinfo('Notificación','El Contrato con el id {} a nombre de {} fue agregado exitosamente.. '.format(id,nombre))
            if(res==True):
                idval.set('')
                nombreval.set('')
                apellidosval.set('')
                runval.set('')
                dispositivoval.set('')
                marcaval.set('')
                modeloval.set('')
                serieval.set('')
                fepreval.set('')
                fedevoval.set('')
                fepreval.set('')
                fedevoval.set('')
                estadoval.set('')
            addroot.destroy()
                
        except:
            messagebox.showerror('Notificación','El Contrato con el id {} ya existe!'.format(id))
        
        str='select * from contratos'
        mycursor.execute(str)
        data=mycursor.fetchall()
        tablacontratos.delete(*tablacontratos.get_children())
        for i in data:
            vv=[i[0],i[1],i[2],i[3],i[4],i[5],i[6],i[7],i[8],i[9],i[10],i[11],i[12]]
            tablacontratos.insert('',END,values=vv)
    addroot = Toplevel(master=root)
    addroot.grab_set()
    addroot.geometry('350x490+490+170')
    addroot.title('Agregar Contrato')
    addroot.config(bg='SteelBlue4')
    addroot.iconbitmap(r'C:\Users\Cliente\Desktop\System\icono.ico')
    addroot.resizable(False, False)
    idlabel = Label(addroot, text='Ingrese ID ', bg='SteelBlue4', font=('Calibri', 11), fg='white', borderwidth=2,
                    width=21, anchor='e')
    idlabel.place(x=10, y=10)
    nombrelabel = Label(addroot, text='Ingrese Nombre ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                         borderwidth=2, width=21, anchor='e')
    nombrelabel.place(x=10, y=50)
    apellidoslabel = Label(addroot, text='Ingrese Apellidos ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                           borderwidth=2, width=21, anchor='e')
    apellidoslabel.place(x=10, y=90)
    runlabel = Label(addroot, text='Ingrese Run ', bg='SteelBlue4', font=('Calibri', 11), fg='white', borderwidth=2,
                     width=21, anchor='e')
    runlabel.place(x=10, y=130)
    dispositivolabel = Label(addroot, text='Ingrese Dispositivo ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                             borderwidth=2, width=21, anchor='e')
    dispositivolabel.place(x=10, y=170)
    marcalabel = Label(addroot, text='Ingrese Marca ', bg='SteelBlue4', font=('Calibri', 11), fg='white', borderwidth=2,
                       width=21, anchor='e')
    marcalabel.place(x=10, y=210)
    modelolabel = Label(addroot, text='Ingrese Modelo ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                        borderwidth=2, width=21, anchor='e')
    modelolabel.place(x=10, y=250)
    serielabel = Label(addroot, text='Ingrese Serie ', bg='SteelBlue4', font=('Calibri', 11), fg='white', borderwidth=2,
                       width=21, anchor='e')
    serielabel.place(x=10, y=290)
    feprelabel = Label(addroot, text='Ingrese Fecha Préstamo ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    feprelabel.place(x=10, y=330)
    fedevolabel = Label(addroot, text='Ingrese Fecha Devolución ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                        borderwidth=2, width=21, anchor='e', activebackground='white', activeforeground='black')
    fedevolabel.place(x=10, y=370)
    estadolabel = Label(addroot, text='Ingrese Estado ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                        borderwidth=2, width=21, anchor='e', activebackground='white', activeforeground='black')
    estadolabel.place(x=10, y=410)
    idval = StringVar()
    nombreval = StringVar()
    apellidosval = StringVar()
    runval = StringVar()
    dispositivoval = StringVar()
    marcaval = StringVar()
    modeloval = StringVar()
    serieval = StringVar()
    fepreval = StringVar()
    fedevoval = StringVar()
    estadoval = StringVar()
    identry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=idval, justify=CENTER)
    identry.place(x=190, y=10)
    nombreentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=nombreval, justify=CENTER)
    nombreentry.place(x=190, y=50)
    apellidosentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=apellidosval, justify=CENTER)
    apellidosentry.place(x=190, y=90)
    runentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=runval, justify=CENTER)
    runentry.place(x=190, y=130)
    dispositivoentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=dispositivoval, justify=CENTER)
    dispositivoentry.place(x=190, y=170)
    marcaentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=marcaval, justify=CENTER)
    marcaentry.place(x=190, y=210)
    modeloentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=modeloval, justify=CENTER)
    modeloentry.place(x=190, y=250)
    serieentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=serieval, justify=CENTER)
    serieentry.place(x=190, y=290)
    fepreentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=fepreval, justify=CENTER)
    fepreentry.place(x=190, y=330)
    fedevoentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=fedevoval, justify=CENTER)
    fedevoentry.place(x=190, y=370)
    estadoentry = Entry(addroot, font=('Calibri',10),width=20, bd=2, textvariable=estadoval, justify=CENTER)
    estadoentry.place(x=190, y=410)
    submitbtn = Button(addroot, text='Agregar Contrato', font=('Calibri', 10,'bold'),fg='white', width=16, bd=2, activebackground='black',
                       activeforeground='white', bg='SteelBlue4', command=agregar)
    submitbtn.place(x=110, y=450)
    submitbtn2 = Button(addroot, text='Imprimir PDF', font=('Calibri', 10,'bold'),fg='white', width=16, bd=2, activebackground='black',
                       activeforeground='white', bg='SteelBlue4')
    submitbtn2.place(x=210, y=15)
    identry.focus_set()
    identry.bind('<Return>', lambda _: agregar(""))
    addroot.mainloop()
def buscarcomodato():
    def buscar():
        id = idval.get()
        nombre = nombreval.get()
        apellidos = apellidosval.get()
        run = runval.get()
        dispositivo = dispositivoval.get()
        marca = marcaval.get()
        modelo = modeloval.get()
        serie = serieval.get()
        fepre = fepreval.get()
        fedevo = fedevoval.get()
        estado = estadoval.get()
        addeddate = time.strftime("%d/%m/%Y")
        if (id != ''):
            strr = 'select *from contratos where id=%s'
            mycursor.execute(strr, (id))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif(nombre !=''):
            strr='select *from contratos where nombre=%s'
            mycursor.execute(strr,(nombre))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9],i[10],i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (apellidos != ''):
            strr = 'select *from contratos where apellidos=%s'
            mycursor.execute(strr, (apellidos))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (run != ''):
            strr = 'select *from contratos where run=%s'
            mycursor.execute(strr, (run))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (dispositivo != ''):
            strr = 'select *from contratos where dispositivo=%s'
            mycursor.execute(strr, (dispositivo))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (marca != ''):
            strr = 'select *from contratos where marca=%s'
            mycursor.execute(strr, (marca))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (modelo != ''):
            strr = 'select *from contratos where modelo=%s'
            mycursor.execute(strr, (modelo))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (serie != ''):
            strr = 'select *from contratos where serie=%s'
            mycursor.execute(strr, (serie))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (fepre != ''):
            strr = 'select *from contratos where fepre=%s'
            mycursor.execute(strr, (fepre))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (fedevo != ''):
            strr = 'select *from contratos where fedevo=%s'
            mycursor.execute(strr, (fedevo))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (estado != ''):
            strr = 'select *from contratos where estado=%s'
            mycursor.execute(strr, (estado))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        elif (addeddate != ''):
            strr = 'select *from contratos where addeddate=%s'
            mycursor.execute(strr, (addeddate))
            data = mycursor.fetchall()
            tablacontratos.delete(*tablacontratos.get_children())
            for i in data:
                vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
                tablacontratos.insert('', END, values=vv)
        buscarroot.destroy()
        
    buscarroot = Toplevel(master=root)
    buscarroot.grab_set()
    buscarroot.geometry('350x570+450+150')
    buscarroot.title('Buscar Contrato')
    buscarroot.config(bg='SteelBlue4')
    buscarroot.iconbitmap(r'C:\Users\Cliente\Desktop\System\icono.ico')
    buscarroot.resizable(False, False)
    idlabel = Label(buscarroot, text='Ingrese ID ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    idlabel.place(x=10, y=10)
    nombrelabel = Label(buscarroot, text='Ingrese Nombre ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    nombrelabel.place(x=10, y=50)
    apellidoslabel = Label(buscarroot, text='Ingrese Apellidos ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    apellidoslabel.place(x=10, y=90)
    runlabel = Label(buscarroot, text='Ingrese Run ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    runlabel.place(x=10, y=130)
    dispositivolabel = Label(buscarroot, text='Ingrese Dispositivo ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    dispositivolabel.place(x=10, y=170)
    marcalabel = Label(buscarroot, text='Ingrese Marca ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    marcalabel.place(x=10, y=210)
    modelolabel = Label(buscarroot, text='Ingrese Modelo ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    modelolabel.place(x=10, y=250)
    serielabel = Label(buscarroot, text='Ingrese Serie ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    serielabel.place(x=10, y=290)
    feprelabel = Label(buscarroot, text='Ingrese Fecha Préstamo ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    feprelabel.place(x=10, y=330)
    fedevolabel = Label(buscarroot, text='Ingrese Fecha Devolución ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    fedevolabel.place(x=10, y=370)
    estadolabel = Label(buscarroot, text='Ingrese Estado ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    estadolabel.place(x=10, y=410)
    fechalabel = Label(buscarroot, text='Ingrese Fecha ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    fechalabel.place(x=10, y=450)
    horalabel = Label(buscarroot, text='Ingrese Hora ', bg='SteelBlue4', font=('Calibri', 11), fg='white',borderwidth=2, width=21, anchor='e')
    horalabel.place(x=10, y=490)
    
    idval = StringVar()
    nombreval = StringVar()
    apellidosval = StringVar()
    runval = StringVar()
    dispositivoval = StringVar()
    marcaval = StringVar()
    modeloval = StringVar()
    serieval = StringVar()
    fepreval = StringVar()
    fedevoval = StringVar()
    estadoval = StringVar()
    dateval = StringVar()
    timeval = StringVar()
    identry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=idval, justify=CENTER)
    identry.place(x=190, y=10)
    nombreentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=nombreval, justify=CENTER)
    nombreentry.place(x=190, y=50)
    apellidosentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=apellidosval, justify=CENTER)
    apellidosentry.place(x=190, y=90)
    runentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=runval, justify=CENTER)
    runentry.place(x=190, y=130)
    dispositivoentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=dispositivoval, justify=CENTER)
    dispositivoentry.place(x=190, y=170)
    marcaentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=marcaval, justify=CENTER)
    marcaentry.place(x=190, y=210)
    modeloentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=modeloval, justify=CENTER)
    modeloentry.place(x=190, y=250)
    serieentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=serieval, justify=CENTER)
    serieentry.place(x=190, y=290)
    fepreentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=fepreval, justify=CENTER)
    fepreentry.place(x=190, y=330)
    fedevoentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=fedevoval, justify=CENTER)
    fedevoentry.place(x=190, y=370)
    estadoentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=estadoval, justify=CENTER)
    estadoentry.place(x=190, y=410)
    dateentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=dateval, justify=CENTER)
    dateentry.place(x=190, y=450)
    timeentry = Entry(buscarroot, font=('Calibri',10),width=20, bd=2, textvariable=timeval, justify=CENTER)
    timeentry.place(x=190, y=490)
    submitbtn = Button(buscarroot, text='Buscar Contrato', font=('Calibri', 10,'bold'),fg='white', width=16, bd=2, activebackground='black',
                       activeforeground='white', bg='SteelBlue4', command=buscar)
    
    submitbtn.place(x=110, y=530)
    identry.focus_set()
    identry.bind('<Return>', lambda _: buscar())
    buscarroot.mainloop()
def eliminarcomodato():
        cc = tablacontratos.focus()
        content = tablacontratos.item(cc)
        pp = content['values'][0]
        strr = 'delete from contratos where id=%s'
        mycursor.execute(strr,(pp))
        con.commit()
        messagebox.showinfo('Notificación','el Contrato con el Id {}  ha sido eliminado de la Base de Datos...'.format(pp))
        strr = 'select * from contratos'
        mycursor.execute(strr)
        data = mycursor.fetchall()
        tablacontratos.delete(*tablacontratos.get_children())
        for i in data:
            vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
            tablacontratos.insert('', END, values=vv)
def editarcomodato():
    def editar():
        id = idval.get()
        nombre = nombreval.get()
        apellidos = apellidosval.get()
        run = runval.get()
        dispositivo = dispositivoval.get()
        marca = marcaval.get()
        modelo = modeloval.get()
        serie = serieval.get()
        fepre = fepreval.get()
        fedevo = fedevoval.get()
        estado = estadoval.get()
        date = dateval.get()
        time = timeval.get()
        strr = 'update contratos set nombre=%s,apellidos=%s,run=%s,dispositivo=%s,marca=%s,modelo=%s,serie=%s,fepre=%s,fedevo=%s,estado=%s,date=%s,time=%s where id=%s'
        mycursor.execute(strr,(nombre,apellidos,run,dispositivo,marca,modelo,serie,fepre,fedevo,estado,date,time,id))
        con.commit()
        messagebox.showinfo('Notificación', 'Los datos del Contrato se han modificado correctamente...'.format(id),parent=editarroot)
        strr = 'select * from contratos'
        mycursor.execute(strr)
        data = mycursor.fetchall()
        tablacontratos.delete(*tablacontratos.get_children())
        for i in data:
            vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
            tablacontratos.insert('', END, values=vv)
        editarroot.destroy()
        
    editarroot = Toplevel(master=root)
    editarroot.grab_set()
    editarroot.geometry('350x560+490+140')
    editarroot.title('Modificar Contrato')
    editarroot.config(bg='SteelBlue4')
    editarroot.iconbitmap(r'C:\Users\Cliente\Desktop\System\icono.ico')
    editarroot.resizable(False, False)
    idlabel = Label(editarroot, text='Ingrese ID ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    idlabel.place(x=10, y=10)
    nombrelabel = Label(editarroot, text='Ingrese Nombre ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    nombrelabel.place(x=10, y=50)
    apellidoslabel = Label(editarroot, text='Ingrese Apellidos ', bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    apellidoslabel.place(x=10, y=90)
    runlabel = Label(editarroot, text='Ingrese Run ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    runlabel.place(x=10, y=130)
    dispositivolabel = Label(editarroot, text='Ingrese Dispositivo ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    dispositivolabel.place(x=10, y=170)
    marcalabel = Label(editarroot, text='Ingrese Marca ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    marcalabel.place(x=10, y=210)
    modelolabel = Label(editarroot, text='Ingrese Modelo ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    modelolabel.place(x=10, y=250)
    serielabel = Label(editarroot, text='Ingrese Serie ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    serielabel.place(x=10, y=290)
    feprelabel = Label(editarroot, text='Ingrese Fecha Préstamo ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    feprelabel.place(x=10, y=330)
    fedevolabel = Label(editarroot, text='Ingrese Fecha Devolución ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    fedevolabel.place(x=10, y=370)
    estadolabel = Label(editarroot, text='Ingrese Estado',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    estadolabel.place(x=10, y=410)
    datelabel = Label(editarroot, text='Ingrese Fecha ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    datelabel.place(x=10, y=450)
    timelabel = Label(editarroot, text='Ingrese Hora ',  bg='SteelBlue4', font=('Calibri', 11), fg='white',
                       borderwidth=2, width=21, anchor='e')
    timelabel.place(x=10, y=490)
    idval = StringVar()
    nombreval = StringVar()
    apellidosval = StringVar()
    runval = StringVar()
    dispositivoval = StringVar()
    marcaval = StringVar()
    modeloval = StringVar()
    serieval = StringVar()
    fepreval = StringVar()
    fedevoval = StringVar()
    estadoval = StringVar()
    fechaval = StringVar()
    dateval = StringVar()
    timeval = StringVar()
    identry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=idval, justify=CENTER)
    identry.place(x=190, y=10)
    nombreentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=nombreval, justify=CENTER)
    nombreentry.place(x=190, y=50)
    apellidosentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=apellidosval, justify=CENTER)
    apellidosentry.place(x=190, y=90)
    runentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=runval, justify=CENTER)
    runentry.place(x=190, y=130)
    dispositivoentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=dispositivoval, justify=CENTER)
    dispositivoentry.place(x=190, y=170)
    marcaentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=marcaval, justify=CENTER)
    marcaentry.place(x=190, y=210)
    modeloentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=modeloval, justify=CENTER)
    modeloentry.place(x=190, y=250)
    serieentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=serieval, justify=CENTER)
    serieentry.place(x=190, y=290)
    fepreentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=fepreval, justify=CENTER)
    fepreentry.place(x=190, y=330)
    fedevoentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=fedevoval, justify=CENTER)
    fedevoentry.place(x=190, y=370)
    estadoentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=estadoval, justify=CENTER)
    estadoentry.place(x=190, y=410)
    dateentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=dateval, justify=CENTER)
    dateentry.place(x=190, y=450)
    timeentry = Entry(editarroot, font=('Calibri',10),width=20, bd=2, textvariable=timeval, justify=CENTER)
    timeentry.place(x=190, y=490)
    submitbtn = Button(editarroot, text='Modificar Contrato', font=('Calibri', 10,'bold'),fg='white', width=16, bd=2, activebackground='black',
                       activeforeground='white', bg='SteelBlue4', command=editar)
    submitbtn.place(x=110, y=525)
    identry.focus_set()
    identry.bind('<Return>', lambda _: editar(""))
    cc = tablacontratos.focus()
    content = tablacontratos.item(cc)
    pp = content['values']
    if(len(pp) !=0):
        idval.set(pp[0])
        nombreval.set(pp[1])
        apellidosval.set(pp[2])
        runval.set(pp[3])
        dispositivoval.set(pp[4])
        marcaval.set(pp[5])
        modeloval.set(pp[6])
        serieval.set(pp[7])
        fepreval.set(pp[8])
        fedevoval.set(pp[9])
        estadoval.set(pp[10])
        dateval.set(pp[11])
        timeval.set(pp[12])
    editarroot.mainloop()
def mostrartodo():
    strr = 'select * from contratos'
    mycursor.execute(strr)
    data = mycursor.fetchall()
    tablacontratos.delete(*tablacontratos.get_children())
    for i in data:
        vv = [i[0], i[1], i[2], i[3], i[4], i[5], i[6], i[7], i[8], i[9], i[10], i[11], i[12]]
        tablacontratos.insert('', END, values=vv)
def exportardatos():
    ff = filedialog.asksaveasfilename()
    gg = tablacontratos.get_children()
    id,nombre,apellidos,run,dispositivo,marca,modelo,serie,fepre,fedevo,estado,fecha,hora=[],[],[],[],[],[],[],[],[],[],[],[],[]
    for i in gg:
        content = tablacontratos.item(i)
        pp = content['values']
        id.append(pp[0]),nombre.append(pp[1]),apellidos.append(pp[2]),run.append(pp[3]),dispositivo.append(pp[4]),marca.append(pp[5]),modelo.append(pp[6]),serie.append(pp[7]),fepre.append(pp[8]),fedevo.append(pp[9]),estado.append(pp[10]),fecha.append(pp[11]),hora.append(pp[12])
    dd = ['Id','Nombre','Apellidos','Run','Dispositivo','Marca','Modelo','Serie','Fecha Préstamo','Fecha Devolución','Estado','Fecha','Hora']
    df = pandas.DataFrame(list(zip(id,nombre,apellidos,run,dispositivo,marca,modelo,serie,fepre,fedevo,estado,fecha,hora)),columns=dd)
    if gg:
        paths = r'{}.csv'.format(ff)
        df.to_csv(paths,index=False)
        messagebox.showinfo('Notificación', 'El archivo .csv se guardó en la siguiente dirección {}'.format(paths))
    else:
        messagebox.showerror('Notificación', 'No ha ingresado un nombre para guardar el archivo .csv')
        
def salirestudiante():
    res = messagebox.askyesnocancel('Notificación', '¿Desconectar Base Datos y salir de la aplicación?')
    if (res == True):
        root.destroy()
def ConectarBD():
    def submitbd():
        global con, mycursor
        host = 'localhost'
        user = 'root'
        password = 'H.0OG6Il,i#2'
        
        try:
            con = pymysql.connect(host=host, user=user, password=password)
            mycursor = con.cursor()
        except:
            messagebox.showerror('Notificación', 'Datos incorrectos, intente nuevamente',parent=bdroot)
            return
        try:
            strr = 'create database Comodatos'
            mycursor.execute(strr)
            strr = 'use Comodatos'
            mycursor.execute(strr)
            strr = 'create table contratos(id int,nombre varchar(100),apellidos varchar(100),' \
                   'run varchar(30),dispositivo varchar(45),marca varchar(45),modelo varchar(45),' \
                   'serie varchar(45),fepre varchar(45),fedevo varchar(45),estado varchar(45))'
            mycursor.execute(strr)
            strr = 'alter table contratos modify column id int not null'
            mycursor.execute(strr)
            strr = 'alter table contratos modify column id int primary key'
            mycursor.execute(strr)
            messagebox.showinfo('Notificación', 'Base de Datos creada y se ha conectado exitosamente! ', parent=bdroot)
        except:
            strr = 'use Comodatos'
            mycursor.execute(strr)
            
        bdroot.destroy()
    bdroot = Toplevel()
    bdroot.grab_set()
    bdroot.geometry('300x150+520+280')
    bdroot.iconbitmap(r'C:\Users\Cliente\Desktop\System\icono.ico')
    bdroot.resizable(False, False)
    bdroot.config(bg="SteelBlue4")
    bdroot.title('Acceso a la Base Datos')
    img = ImageTk.PhotoImage(file="iconos.png")
    lbl_img = Label(bdroot, image=img, bg="SteelBlue4")
    lbl_img.place(x=175, y=25)
       
    userlabel = Label(bdroot, text='Estimado usuario\nUsted se ha conectado\ncorrectamente\na la Base de Datos', bg="SteelBlue4", font=('Calibri',13), fg='white', borderwidth=3,width=18, anchor='w')
    userlabel.place(x=3, y=5)
    
    img5 = ImageTk.PhotoImage(file="btnOscuro.png")
    lbl_img = Label(root, image=img5, bg="SteelBlue4")
    lbl_img.place(x=500, y=55)
   
    img4 = ImageTk.PhotoImage(file="btnVerde.png")
    lbl_img = Label(root, image=img4, bg="SteelBlue4")
    lbl_img.place(x=815, y=55)
  
    hostval = StringVar()
    userval = StringVar()
    passwordval = StringVar()
    submitbutton = Button(bdroot, text='ACEPTAR', font=('Calibri', 10,'bold'), bg='SteelBlue4', bd=2,
                          fg='white', width=11, activebackground='white', activeforeground='black', command=submitbd)
    submitbutton.place(x=40,y=110)
    
    bdroot.mainloop()
def tick():
    time_string = time.strftime("%H:%M:%S")
    date_string = time.strftime("%d/%m/%Y")
    clock.config(text='Fecha: ' + date_string + "    Hora: " + time_string, bg='SteelBLue4', fg='white')
    clock.after(200, tick)
    clock.place(x=520, y=42)
import time
from tkinter import *
from tkinter import Toplevel, messagebox,filedialog
from tkinter import ttk
from tkinter.ttk import Treeview
import pymysql
import pandas
from PIL import Image, ImageTk

root = Tk()
root.title('Gestión y Administración de Comodato')
root.config(bg='SteelBlue4')
root.geometry('1350x730+0+0')
root.iconbitmap(r'C:\Users\Cliente\Desktop\System\icono.ico')
root.resizable(False, False)
img = ImageTk.PhotoImage(file="icono.png")
lbl_img = Label(root, image=img, bg="SteelBlue4")
lbl_img.place(x=25, y=5)

img2 = ImageTk.PhotoImage(file="btnNegro.png")
lbl_img = Label(root, image=img2, bg="SteelBlue4")
lbl_img.place(x=815, y=55)
img3 = ImageTk.PhotoImage(file="btnRojo.png")
lbl_img = Label(root, image=img3, bg="SteelBlue4")
lbl_img.place(x=500, y=55)

SliderLabel = Label(root, text='Gestión y Administración de Comodato', font=('Calibri', 25), fg='white',
                    bg='SteelBlue4')
SliderLabel.place(x=410, y=0)
SliderLabel2 = Label(root,
                     text='Proyecto de Mejora "Gestión y Administración de Comodato". Práctica Laboral de la Carrera Técnico de Nivel Superior en Informática Instituto de las Artes y Ciencias de la Comunicación IACC. Diseñado con Python y la Librería Tkinter. Luis Jofré Pérez - Copiapó junio 2022',
                     font=('Calibri', 8), fg='white', bg='SteelBlue4')
SliderLabel2.place(x=40, y=710)
connectbutton = Button(root, text='Conectar BD', command=ConectarBD, font=('Calibri', 10, 'bold'),
                       fg='white', bg='SteelBlue4', width=16,  )
connectbutton.place(x=1070, y=90)
btnagregar = Button(root, text='Configurar PDF', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                    bg='SteelBlue4', activebackground='white', activeforeground='black')
btnagregar.place(x=170, y=50)
btnagregar = Button(root, text='Agregar Contrato', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                    bg='SteelBlue4', activebackground='white', activeforeground='black', command=agregarcomodato)
btnagregar.place(x=170, y=90)
btnbuscar = Button(root, text='Buscar Contrato', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                   bg='SteelBlue4', activebackground='white', activeforeground='black', command=buscarcomodato)
btnbuscar.place(x=320, y=90)
btneliminar = Button(root, text='Eliminar Contrato', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                     bg='SteelBlue4', activebackground='white', activeforeground='black')
btneliminar.place(x=470, y=90)
btneditar = Button(root, text='Editar Contrato', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                   bg='SteelBlue4', activebackground='white', activeforeground='black', command=editarcomodato)
btneditar.place(x=620, y=90)
btnmostrar = Button(root, text='Mostrar todo', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                    bg='SteelBlue4', activebackground='white', activeforeground='black', command=mostrartodo)
btnmostrar.place(x=770, y=90)
btnexportar = Button(root, text='Exportar vista', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2,
                     bg='SteelBlue4', activebackground='white', activeforeground='black', command=exportardatos)
btnexportar.place(x=920, y=90)
btnsalir = Button(root, text='Salir', width=16, font=('Calibri', 10, 'bold'), fg='white', bd=2, bg='SteelBlue4',
                  activebackground='white', activeforeground='black', command=salirestudiante)
btnsalir.place(x=1218, y=90)
frameC = Frame(root, bg='gray80', borderwidth=5)
frameC.place(x=10, y=132, width=1330, height=580)
style = ttk.Style()
style.configure('Treeview.Heading', font=('Book Antiqua', 13,'bold'), bg='SteelBlue4',foreground='black')
style.configure('Treeview', font=('Calibri', 12), background='gray80', foreground='black')
scroll_X = Scrollbar(frameC, orient=HORIZONTAL)
scroll_y = Scrollbar(frameC, orient=VERTICAL)
tablacontratos = Treeview(frameC, columns=('Id', 'Nombre', 'Apellidos', 'Run', 'Dispositivo',
                                            'Marca', 'Modelo', 'Serie', 'F Préstamo', 'F Devolución','Estado', 'Fecha','Hora'),
                           yscrollcommand=scroll_y.set,xscrollcommand=scroll_X.set)
scroll_X.pack(side=BOTTOM, fill=X)
scroll_y.pack(side=RIGHT, fill=Y)
scroll_X.config(command=tablacontratos.xview)
scroll_y.config(command=tablacontratos.yview)
tablacontratos.heading('Id', text='Id')
tablacontratos.heading('Nombre', text='Nombre')
tablacontratos.heading('Apellidos', text='Apellidos')
tablacontratos.heading('Run', text='Run')
tablacontratos.heading('Dispositivo', text='Dispositivo')
tablacontratos.heading('Marca', text='Marca')
tablacontratos.heading('Modelo', text='Modelo')
tablacontratos.heading('Serie', text='Serie')
tablacontratos.heading('F Préstamo', text='F Préstamo')
tablacontratos.heading('F Devolución', text='F Devolución')
tablacontratos.heading('Estado', text='Estado')
tablacontratos.heading('Fecha', text='Fecha')
tablacontratos.heading('Hora', text=' Hora')
tablacontratos['show'] = "headings"
tablacontratos.column('Id', width=40)
tablacontratos.column('Nombre', width=200)
tablacontratos.column('Apellidos', width=200)
tablacontratos.column('Run', width=150)
tablacontratos.column('Dispositivo', width=150)
tablacontratos.column('Marca', width=100)
tablacontratos.column('Modelo', width=120)
tablacontratos.column('Serie', width=170)
tablacontratos.column('F Préstamo', width=130)
tablacontratos.column('F Devolución', width=130)
tablacontratos.column('Estado', width=130)
tablacontratos.column('Fecha', width=110)
tablacontratos.column('Hora', width=110)
tablacontratos.pack(fill=BOTH, expand=1)
clock = Label(root, font=('Calibri', 14), borderwidth=4, bg='#3b8cde')
clock.place()
tick()
root.mainloop()
