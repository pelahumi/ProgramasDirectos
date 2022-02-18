# ProgramasDirectos

La dirección de este repositorio es: [GitHub](https://github.com/pelahumi/ProgramasDirectos)

## Ejercicio 8
```
Algoritmo Precio

    //Definimos las variables
    Definir precio Como Entero
    Definir iva Como Real
    Escribir "Introduce el precio sin impuestos: "
    Leer precio, iva

    impuestos = precio * iva
    precio_impuestos = precio + impuestos

    //Escribimos el resultado
    Escribir "El precio total es: ",precio_impuestos," euros"

FinAlgoritmo

Algoritmo Intereses_generados

    //Definimos las variables
    Definir capital, interes Como Real
    Definir tiempo Como Entero
    Escribir "Introduce el capital invertido: "
    Leer capital, interes, tiempo

    intereses_generados = capital * interes * tiempo

    //Escribimos el resultado
    Escribir "Los intereses generados durante ",tiempo," meses es: ",intereses_generados," con un interés del: ",interes

FinAlgoritmo
```

## Ejercicio 9
```
Algorimo Media_aritmetica

    //Definimos las variables
    Definir a, b, c Como Enteros
    Leer a, b, c

    media = (a + b +c) / 3

    //Escribimos el resultado
    Escribir "La media aritmética es: ", media

FinAlgoritmo

Algoritmo Media_ponderada

    //Definimos las variables números
    Definir a, b, c Como Enteros
    //Definimos las variables coeficientes de ponderación
    Definir x, y, z Como Reales

    media = (a * x) + (b * y) + (c * z)

    //Escribimos el resultado
    Escribir "La media ponderada de los tres números es: ", media

FinAlgoritmo
```

## Ejercicio 10
```
Algoritmo Area_triangulo
    
    //Definimos las variables
    Definir lado, altura Como Enteros
    Leer lado, altura

    area = (lado * altura)/ 2

    //Escribimos el resultado
    Escribir "El área del triángulo es: ", area

FinAlgoritmo

Algoritmo Area_triangulo_rectangulo

    //Definimos las variables
    Definir lado1, lado2 Como Enteros
    Leer lado1, lado2

    //Uno de los dos lados perpendiculares será la altura del triángulo

    Area_triangulo(lado1, lado2)

    FinArea_triangulo

FinAlgoritmo
```




    
