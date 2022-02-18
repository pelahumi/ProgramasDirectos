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

## Ejercicio 11
```
Algoritmo horas_extra

Entrada
    Definir salario_mensual_bruto Como Real
    Definir horas_ext Como Entero

Precondición
    salario_mensual_bruto > 0
    horas_ext >= 0

Constante
    cantidad_horas_max_1 : Entero <- 8
    precio_1 : Real <- 1,25
    precio_2 : Real <- 1,5

Variable
    horas_ext_1 : Entero
    horas_ext_2 : Entero
    precio_hora : Real

Realización
    cálculo del precio_hora de la remuneración bruta de base precio hora <- precio_hora_bruto(salario_mensual_bruto)

    cálculo de la cantidad de horas de cada categoría
    horas_ext_1 <- inf(horas_ext, cantidad_horas_max_1)
    horas_ext_2 <- sup(horas_ext - cantidad_horas_max_1, 0)

    cálculo de la remuneración de las horas extra
    Resultado <- precio_hora * (horas_ext_1 * precio_1 + horas_ext_2 * precio_2)
Fin horas_extra

Definición de la función precio_hora_bruto

precio_hora_bruto(salario_mensual_bruto : Real) : Real

Precondición
    salario_mensual_bruto > 0 

Constante
    cantidad_semanas : Entero <- 52
    cantidad_horas_semana : Entero <-35

Realización
    cálculo del precio_hora de la remuneración bruta de la base
    Resultado <- salario_mensual_bruto * 12/(Real(cantidad_horas_semana) * Real(cantidad_semanas))

Postcondición
    Resultado = salario_mensual_bruot * 12,0 / Real(35 * 52)

Fin precio_horas_bruto
```

## Ejercicio 12.1
### Tipo datos de cuenta
```
tipo Cuenta estructura
    saldo : Real
    invariante
        //El descubierto no está autorizado
        saldo >= 0
Fin Cuenta
```

### Operaciones aplicables
```
Algoritmo abrir_cuenta
    abrir(c : Cuenta; saldo_inicial : Real)
Precondición
    saldo_inicial > 0
Realización
    c.descubrimiento <- 0 
    c.saldo <- saldo_inicial
Postcondicion
    c.descubierto = 0
    //El descubierto no está autorizado
    antiguo(saldo_inicial) = saldo_inicial
    c,saldo = saldo_inicial
Fin abrir_cuenta

Algoritmo abonar_cuenta
Precondición 
    c.saldo =! 0
    credito =! 0
Realización
    c.saldo <- c.saldo + credito
Postcondición
    //El descubierto autorizado y el importe del credito no se modifican
    antiguo(c).descubierto = descubierto
    antiguo(c).credito = credito
    //El saldo de la cuenta aumenta con el credito
    c.saldo = antiguo(c).saldo + credito
Fin abonar_cuenta

Algoritmo cargar_cuenta
Precondición
    c.saldo =! 0
    debito =! 0
    c.saldo + c.descubierto >= debito >= 0
Realización
    abonar(c, -debito)
Postcondición
    //El descubierto autorizado y el importe del debito no se modifican
    antiguo(c).descubierto = descubierto
    antiguo(debito) = debito

    //Al saldo se le resta el debito
    c.saldo = antiguo(c).saldo - debito
Fin cargar_cuenta

Algoritmo consultar_cuenta
    consultar(c : Cuenta) : Real
Precondición
    c.saldo =! 0
Realización
    Resultado <- c.saldo
Postcondición
    Resultado = c.saldo
Fin consultar_cuenta

Algoritmo es_acreedora
    es_acreedora(c : Cuenta) : Booleano
Precondición
    c.saldo =! 0
Realización
    Resultado <- (c.saldo > 0)
Postcondición
    Resultado = (c.saldo > 0)
Fin es_acreedora

Algoritmo es_deudora
    es_deudora (c : Cuenta) : Booleano
Precondición
    c.saldo =! 0
Realización
    Resultado <- (-c.descubierto <= c.saldo <= 0)
Postcondición
    Resultado = (-c.descubierto <= c.saldo <= 0)
Fin es_deudora
```

## Ejercicio 12.2
### Tipo de cuenta
```
tipo Cuenta estructura
    saldo : Real
    invariante 
        //El descubierto está autorizado
        descubierto >= 0 
        //El saldo debe ser superior al descubierto autorizado
        saldo >= -descubierto
Fin Cuenta
```
### Abrir cuenta
```
Algoritmo abrir_cuenta
    abrir(c : Cuenta; saldo_inicial : Real; descubierto_Max : Real)
Precondicion
    saldo_inicial > 0
    descubierto_Max >= 0
Realización
    c.descubierto <- descubierto_Max
    c.saldo <- saldo_inicial
Postcondición
    c.descubierto = descubierto_Max
    c.saldo = saldo_inicial
Fin abrir_cuenta



    
