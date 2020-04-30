# EV1
EV1 ESTRUCTURA DE DATOS Y SU PROCESAMIENTO
import pandas as pd
import numpy as np

 

Alumnos = {"Hugo" : {}, "Sergio" : {}, "Mario" : {}, "Kevin" : {}, "Alberto" :{}, \
           "Felipe" : {}, "Cristian" : {}, "Luis" : {}, "Angel" : {}, "Adamaris" : {}, \
           "Mariana" : {}, "Elena" : {}, "Cristal" : {}, "Cristina" : {}, "Karla" : {}, \
           "Lizbeth" : {}, "Fernanda" :{}, "Aracely" : {}, "Ilena" : {}, "Norma" : {}, \
           "Janeth": {}, "Erick" :{}, "Daniel" : {}, "Juan" : {}, "Ivan" : {}, \
           "Brenda": {}, "Rubi" : {}, "Kate" : {}, "Alma" : {}, "Gignac" : {}}
  
  
diccionario_materia= {"Programación" : {}, "Base De Datos": {}, "Creatividad": {}, "Contabilidad" :{}, "Economía" :{}}

 


x=Alumnos.keys()
Alumnoskeys = pd.DataFrame(x)
framematerias = pd.DataFrame(diccionario_materia)
framealumnos = pd.DataFrame(Alumnoskeys)
concatenacion = pd.concat([framealumnos, framematerias], axis=0)

 

diccionarioc1 = []
diccionarioc2 = []
diccionarioc3 = []
diccionarioc4 = []
diccionarioc5 = []

 

Numero1=0
Numero2=0

 


Proceso=True
while Proceso == True:
    print("1 para ver a los usuarios")
    print("2 para subir calificaciones")
    print("3 para ver la estadistica descriptiva de las materias")
    print("4 para ver a los alumnos reprobados")
    print("5 para salir")

 

    Proceso2= int(input("¿Que quieres realizar?:"))
   
    if Proceso2 == 1:
        print(concatenacion.iloc[:,0])
    
    
    elif Proceso2 == 2:
        for i in range(3):
            Nombres=Alumnoskeys.iloc[Numero2, 0]
            c1= int(input("Dime la calificacion en Base De Datos: "))
            c2= int(input("Dime la calificacion en Contabilidad: "))
            c3= int(input("Dime la calificacion en Creatividad: "))
            c4= int(input("Dime la calificacion en Economia: "))
            c5= int(input("Dime la calificacion en Programacion: "))
            
            concatenacion.loc[Numero1] = [Nombres, c1, c2, c3, c4, c5]
            Numero1 = Numero1+1
            Numero2 = Numero2+1
            print(concatenacion)
            if c1 < 70:
                diccionarioc1.append(c1)
            if c2 < 70:
                diccionarioc2.append(c2)
            if c3 < 70:
                diccionarioc3.append(c3)
            if c4 < 70:
                diccionarioc4.append(c4)
            if c5 < 70:
                diccionarioc5.append(c5)
                

 


    elif Proceso2 == 3:
        print(concatenacion.describe())
    
    
    elif Proceso2 == 4:
        print(f"Calificaciones reprobatorias de Base de Datos {diccionarioc1}")
        print(f"Calificaciones reprobatorias de Contabilidad {diccionarioc2}")
        print(f"Calificaciones reprobatorias de Creatividad {diccionarioc3}")
        print(f"Calificaciones reprobatorias de Economía {diccionarioc4}")
        print(f"Calificaciones reprobatorias de Programación{diccionarioc5}")
                
    
    
    elif Proceso2 == 5:
        print("Fin del programa")
        break
 
