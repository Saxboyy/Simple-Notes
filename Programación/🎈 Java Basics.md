Esto ni tiene orden ni sentido. Aquí voy añadiendo apuntes de cosas que son relevantes para mi aprendizaje. Igual salto de algo sencillo a algo complejo. 
# **Método Main**

El `main()` método es requerido y se debe de usar en todos los códigos de Java:

```java
public static void main(String[] args)
```

Básicamente, el código que se ejecuta como tal, es el que esta dentro de dicha clase. A groso modo. 

# System.out.print()

```java
public static void main(String[] args) {
  System.out.println("Hello World");
}
```

Hace un print de toda la vida en la consola. Creando un salto de linea. 

```java
public static void main(String[] args) {
  System.out.print("Hello World");
	System.out.print("Al lado xd");
}
```

Este no hace salto de linea, es decir. El siguiente print se reproduce al lado. 

**Típico, también puedes hacer funciones matemáticas directamente el print (2+2) o usar variables para ello .... 

# Variables

Sin mas. Le defines el tipo de dato al principio. 

```java
String name = "John";
System.out.println(name);
```

Ejemplo de tipo de datos 

```java
int myNum = 5;               // Integer (whole number)- 
float myFloatNum = 5.99f;    // Floating point number
char myLetter = 'D';         // Character
boolean myBool = true;       // Boolean
String myText = "Hello";     // String
``````

Se pueden añadir variables a otras variables .

```java
String firstName = "John ";
String lastName = "Doe";
String fullName = firstName + lastName;
System.out.println(fullName);
```

# Tipos de números enteros 

Cada uno tienes sus limitaciones y esta hecho para según que casos. No voy a poner los limites porque me lo debería saber de memoria. Aunque para el uso general, utilizaremos. Int. 

```java
byte myNum = 100;
System.out.println(myNum);

short myNum = 5000;
System.out.println(myNum);

int myNum = 100000;
System.out.println(myNum);

long myNum = 15000000000L;
System.out.println(myNum);

float myNum = 5.75f;
System.out.println(myNum);
```


# Booleanos 

Poca cosa ahí que decir ...

```java
boolean isJavaFun = true;
boolean isFishTasty = false;
System.out.println(isJavaFun);     // Outputs true
System.out.println(isFishTasty);   // Outputs false
```

# Argumentos

```java
public class Parametros {

    public static void main(String[] args) {
        
        // Si no hay dos argumentos de ejecucion. El Programa se cierrra y devuelve code 0
        
        if (args.length != 2.) {
            System.err.println("Por favor, introduzca dos numeros como argumentos.");
            System.exit(0);
        }
        
        // Asignando las posiciones de los parametros
        
        int num1 = Integer.parseInt(args [0]);
        int num2 = Integer.parseInt(args [1]);
        
        int suma = num1 + num2;
        
        System.err.println("La suma de los anteriores numeros es: " + suma);
        
       
        
        }
    }
```

