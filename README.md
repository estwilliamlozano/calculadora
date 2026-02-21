import math
class Calculadora:
    def __init__(self):
        self.valor1 = 0.0
        self.valor2 = 0.0

    def sumar(self):
        self.valor1 = float(input('Digite el primer número: '))
        self.valor2 = float(input('Digite el segundo número: '))
        print('El resultado de la suma es:', self.valor1 + self.valor2)

    def restar(self):
        self.valor1 = float(input('Digite el primer número: '))
        self.valor2 = float(input('Digite el segundo número: '))
        print('El resultado de la resta es:', self.valor1 - self.valor2)

    def multiplicar(self):
        self.valor1 = float(input('Digite el primer número: '))
        self.valor2 = float(input('Digite el segundo número: '))
        print('El resultado de la multiplicación es:', self.valor1 * self.valor2)

    def dividir(self):
        self.valor1 = float(input('Digite el primer número: '))
        self.valor2 = float(input('Digite el segundo número: '))
        if self.valor2 == 0:
                print("No se puede dividir entre 0")
        else:
            print('El resultado de la división es:', self.valor1 / self.valor2)

    def seno(self):
        self.valor1 = float(input('Digite el número del cual quiere hallar la función seno: '))
        print('El resultado es:', math.sin(self.valor1))

    def coseno(self):
        self.valor1 = float(input('Digite el número del cual quiere hallar la función coseno: '))
        print('El resultado es:', math.cos(self.valor1))

    def tangente(self):
        self.valor1 = float(input('Digite el número del cual quiere hallar la función tangente: '))
        print('El resultado es:', math.tan(self.valor1))

    def raizEnesima(self):
        self.valor1 = float(input('Digite el número del cual quiere hallar la raíz: '))
        self.valor2 = float(input('Digite el índice de la raíz: '))
        if self.valor2 == 0:
                print("El índice no puede ser 0")
        else:
                raiz = self.valor1 ** (1 / self.valor2)
                print("El resultado de la raíz enésima de", self.valor1, "es:", raiz)

    def potenciaEnesima(self):
        self.valor1 = float(input('Digite el número del cual quiere hallar la potencia: '))
        self.valor2 = float(input('Digite la potencia a la cual quiere elevar el número: '))
        print('El resultado de la potencia enésima de', self.valor1, 'es:', self.valor1 ** self.valor2)

    def factorial(self):
        self.valor1 = int(input('Digite el número del cual quiere hallar su factorial: '))
        if self.valor1 < 0:
                print("No existe factorial de números negativos")
        else:
                fact = 1
                for i in range(1, self.valor1 + 1):
                    fact *= i
                print("El factorial de", self.valor1, "es:", fact)
        

    def fibonacci(self):
        n = int(input("Digite la cantidad de términos de la serie Fibonacci: "))
        if n <= 0:
            print("La cantidad debe ser mayor que 0")
        else:
            a, b = 0, 1
            print("Serie de Fibonacci:")
            for _ in range(n):
                print(a, end=" ")
                a, b = b, a + b
            print()
            
    def mcm(self):
        self.valor1 = int(input('Digite el primer número: '))
        self.valor2 = int(input('Digite el segundo número: '))
        mcm = max(self.valor1, self.valor2)
        while True:
            if mcm % self.valor1 == 0 and mcm % self.valor2 == 0:
                break
            mcm += 1
        print('El Mínimo Común Múltiplo es:', mcm)

    def mcd(self):
        self.valor1 = int(input('Digite el primer número: '))
        self.valor2 = int(input('Digite el segundo número: '))
        while self.valor2 != 0:
            self.valor1, self.valor2 = self.valor2, self.valor1 % self.valor2
        print("El Máximo Común Divisor es:", self.valor1)
        
    def calcularIVA(self):
        valor = float(input("Digite el valor del producto: "))
        iva = float(input("Digite el porcentaje del IVA: "))
        valor_iva = valor * (iva / 100)
        print("El valor del IVA es:", valor_iva)

    def totalIVA(self):
        valor = float(input("Digite el valor del producto: "))
        iva = float(input("Digite el porcentaje del IVA: "))
        total = valor + (valor * iva / 100)
        print("El valor total con IVA es:", total)


class Menu:
    def __init__(self):
        self.opcion = 0
        self.__calculadora = Calculadora()   
        
    def mostrarMenu(self):
        print('\nCalculadora Python')
        print('[1]  Función Suma')
        print('[2]  Función Resta')
        print('[3]  Función Multiplicación')
        print('[4]  Función División')
        print('[5]  Función Seno')
        print('[6]  Función Coseno')
        print('[7]  Función Tangente')
        print('[8]  Función Raíz enésima')
        print('[9]  Función Potencia enésima')
        print('[10] Función Factorial')
        print('[11] Función Fibonacci')
        print('[12] Función Mínimo Común Múltiplo')
        print('[13] Función Máximo Común Divisor')
        print('[14] Función IVA')
        print('[15] Función Total IVA')

    def ejecutarOpcion(self):
        match self.opcion:
            case 1:  self.__calculadora.sumar()
            case 2:  self.__calculadora.restar()
            case 3:  self.__calculadora.multiplicar()
            case 4:  self.__calculadora.dividir()
            case 5:  self.__calculadora.seno()
            case 6:  self.__calculadora.coseno()
            case 7:  self.__calculadora.tangente()
            case 8:  self.__calculadora.raizEnesima()
            case 9:  self.__calculadora.potenciaEnesima()
            case 10: self.__calculadora.factorial()
            case 11: self.__calculadora.fibonacci()
            case 12: self.__calculadora.mcm()
            case 13: self.__calculadora.mcd()
            case 14: self.__calculadora.calcularIVA()
            case 15: self.__calculadora.totalIVA()
            case _:  print('El dato es inválido')

    def iniciar(self):
        while True:
            self.mostrarMenu()
            self.opcion = int(input('Digite una de las opciones: '))
            self.ejecutarOpcion()
            final = input('¿Desea volver al menú? si/no: ')
            if final == 'no':
                print('Programa finalizado')
                break            
menu = Menu()
menu.iniciar()
