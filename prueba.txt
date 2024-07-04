import csv 
import msvcrt
import os 
import time

Estudiantes=[]

def registrar_estudiante():
    alumno=input("Ingrese su nombre: ")
    rut=float(input("Ingrese su rut: "))
    nota1=float(input("Ingrese su nota 1: "))
    nota2=float(input("Ingrese su nota 2: "))
    nota3=float(input("Ingrese su nota 3: "))
    nota4=float(input("Ingrese su nota 4: "))
    final_nota=nota1*0.3 + nota2*0.3 + nota3*0.3+ nota4*0.1/4
    nota_presentacion=nota1*0.3 + nota2*0.3 + nota3*0.3+ nota4*0.1/4
    print("Alumno Registrado con exito.")
    time.sleep(0.5)
    print(f"Su nota de presentacion es {nota_presentacion}")
    time.sleep(0.7)
    os.system('cls')
    Estudiantes.append([alumno , rut , nota1 , nota2 , nota3 , nota4 , final_nota , nota_presentacion])
    return
    
def comprobar_rut():
    while True:
        if not registrar_estudiante() !='0':
            time.sleep(0.5)
            print("Rut no ingresado en el sistema.")
            
            return

def mostrar_estudiantes():
    for alumno in Estudiantes:
        print(f"""      
                {alumno}
""")
        time.sleep(4.5)
        os.system('cls')
        return

def buscar_estudiante():
    buscar_rut=input("Ingrese el rut del estudiante: ")
    if buscar_rut== alumno:
        for alumno in Estudiantes:
            print(f"{alumno}")
        return
    elif buscar_rut!=alumno:
        print("No hay alumno registrado.")



def exportar_csv():
    with open("Estudiantes.csv", "w", newline='') as f:
        writer=csv.writer(f)
        writer.writerow(['alumno' , 'rut' , 'nota1' , 'nota2' , 'nota3' , 'nota4' ])
        for alumno in Estudiantes:
         writer.writerow(f" {alumno} ")
        time.sleep(0.5)
        os.system('cls')
        return


def main():
        while True:
            opcion=int(input("""
                            1.Registrar Estudiante.
                            2.Comprobar que el rut.
                            3.Mostrar estudiantes. 
                            4.Buscar estudiante por rut.
                            5.Exportar a csv.
                            0.Salir.
                             Seleccione una Opcion:  """))
            if opcion ==1:
                registrar_estudiante()
            elif opcion == 2:
                comprobar_rut()
            elif opcion == 3:
                mostrar_estudiantes()
            elif opcion == 4:
                buscar_estudiante()
            elif opcion ==5:
                exportar_csv()
            elif opcion ==0:
                print("Saliendo del sistema...")
                os.system('cls')
                break
            else:
                print("Opcion Invalida. Presione un Boton para Continuar. ")
                msvcrt.getch()

if __name__=="__main__":
    main()