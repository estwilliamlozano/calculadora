import math

print ('Calculadora Pythoon')

while True:
    print ('[1] Función Suma')
    print ('[2] Función Resta')
    print ('[3] Función Multiplicación')
    print ('[4] Función División')
    print ('[5] Función Seno')
    print ('[6] Función Coseno')
    print ('[7] Función Tangente')
    print ('[8] Función Raíz enésima')
    print ('[9] Función Potencia enésima')
    print ('[10] Función Factorial')
    print ('[11] Función Fibonacci')
    print ('[12] Función Mínimo Común Múltiplo de 2 números')
    print ('[13] Función Máximo Común Divisor de 2 números')
    print ('[14] Función IVA')
    print ('[15] Función Total IVA')

    x = int (input('Digite una de las opciones: '))

    match x:
        case 0:
            print('Programa finalizado')
        case 1:
            a = int (input('Digite el primer número: '))
            b = int (input('Digite el segundo número: '))
            suma = a + b 
            print ('El resultado de la suma es: ', suma)
        case 2:
            a = int (input('Digite el primer número: '))
            b = int (input('Digite el segundo número: '))
            resta = a - b
            print ('El resultado de la resta es: ', resta)
        case 3:
            a = int (input('Digite el primer número: '))
            b = int (input('Digite el segundo número: '))
            multiplicar = a * b
            print ('El resultado de la multiplicación es: ', multiplicar)
        case 4:
            a = int (input('Digite el primer número: '))
            b = int (input('Digite el segundo número: '))
            dividir = a / b
            if b>0:
                print ('El resultado de la división es: ', dividir)
            else:
                print ('No se puede dividir entre 0')
        case 5:
            a = int (input('Digite el número del cual quiere hallar la función seno: '))
            seno = math.sin(a)
            print ('El resultado es: ', seno)
        case 6:
            a = int (input('Digite el número del cual quiere hallar la función coseno: '))
            coseno = math.cos(a)
            print ('El resultado es: ', coseno)
        case 7:
            a = int (input('Digite el número del cual quiere hallar la función tangente: '))
            tangente = math.tan(a)
            print ('El resultado es: ', tangente)
        case 8:
            a = int (input('Digite el número del cual quiere hallar la raíz: '))
            b = int (input('Digite el índice de la raíz: '))
            raiz = a**(1/b)
            print ('El resultado de la raíz enésima de ' , a , ' es: ', raiz)
        case 9:
            a = int (input('Digite el número del cual quiere hallar la potencia: '))
            b = int (input('Digite la potencia a la cual quiere elevar el número: '))
            potencia = a**b
            print ('El resultado de la potencia enésima de ' , a , ' es: ', potencia)
        case 10:
            a = int(input('Digite el número del cual quiere hallar su factorial: '))
            fact = 1
            i = 1
            while i<=a:
                    fact = fact * i
                    i = i + 1
                    print ('El factorial de ', a, ' es: ', fact)
        case 11:
            n = int(input('Digite la cantidad de términos de la serie Fibonacci: '))
            a = 0
            b = 1
            i = 1
            print('Serie de Fibonacci: ')
            while i<=n:
                print (a, end='') 
                c = a + b
                a = b 
                b = c 
                i = i + 1
                print ()
        case 12:
            a = int (input('Digite el primer número: '))
            b = int (input('Digite el segundo número: '))
            mcm = max (a, b)
            while True:
                if mcm % a == 0 and mcm % b == 0:
                    break
                mcm += 1
            print('El Mínimo Común Múltiplo es: ', mcm)
        case 13:
            a = int (input('Digite el primer número: '))
            b = int (input('Digite el segundo número: '))
            while b != 0:
                c = a % b
                a = b 
                b = c 
            print('El Máximo Común Divisor es: ', a)
        case 14:
            valor = float(input('Digite el valor del producto: '))
            iva = float(input('Digite el porcentaje del IVA: '))
            valor_iva = valor * (iva/100)
            print('El valor del IVA es: ', valor_iva)
        case 15:
            valor = float(input('Digite el valor del producto: '))
            iva = float(input('Digite el porcentaje del IVA: '))
            total = valor + (valor * iva / 100)
            print('El valor total con IVA es: ', total)
        case _:
            print('El dato es inválido')
    final=input("¿Desea volveral menu? si/no: ")
    if final=="no":
        print("finalizado")
        break
