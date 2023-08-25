# Explorando Principios de "Clean Code" 🕹️

## Título: Instrucciones Switch 🔦

**Pagina: 67-69**

### Definición: 
La instrucción switch es una estructura de control que permite seleccionar una de varias opciones basadas en el valor de una expresión. Cada opción se define en una cláusula case y se ejecuta el bloque de código correspondiente a la opción seleccionada.

### Resultado: 
La instrucción switch permite una forma más clara y legible de manejar múltiples opciones en lugar de usar múltiples declaraciones if-else. Además, puede mejorar el rendimiento del código al evitar la evaluación repetida de la misma expresión en múltiples declaraciones if-else.

### Ejemplo Práctico: 
Un ejemplo práctico de uso de instrucciones switch en Java podría ser un programa que clasifica los días de la semana según su número. 

### El código sería el siguiente:

```java
int dia = 3;
String nombreDia;

switch (dia) {
    case 1:
        nombreDia = "Lunes";
        break;
    case 2:
        nombreDia = "Martes";
        break;
    case 3:
        nombreDia = "Miércoles";
        break;
    case 4:
        nombreDia = "Jueves";
        break;
    case 5:
        nombreDia = "Viernes";
        break;
    case 6:
        nombreDia = "Sábado";
        break;
    case 7:
        nombreDia = "Domingo";
        break;
    default:
        nombreDia = "Día inválido";
        break;
}

System.out.println("El día " + dia + " es " + nombreDia);
```
En este ejemplo, la variable "dia" contiene el número del día de la semana que se desea clasificar. La instrucción switch evalúa el valor de "dia" y selecciona la opción correspondiente en la cláusula case. Si "dia" es igual a 3, se ejecutará el bloque de código correspondiente a la opción "case 3", que asigna el valor "Miércoles" a la variable "nombreDia". Finalmente, se imprime el resultado por consola.

----
<br>

## Título: Comentarios de Calidad 🤐

**Pagina: 90-94**

### Definición: 
Los comentarios de calidad son aquellos que se utilizan en el código para explicar su funcionamiento y facilitar su comprensión. Estos comentarios deben ser claros, concisos y estar escritos en un lenguaje comprensible para cualquier desarrollador que lea el código.

En mi opinión, los puntos más importantes son los siguientes:

- **Comentarios Legales**

- **Comentarios Informativos**

- **Explicar la Intencion**

- **Advertir las Consecuencias**

### Resultado: 
La inclusión de comentarios de calidad mejora la legibilidad y mantenibilidad del código, permitiendo que otros desarrolladores comprendan más fácilmente su propósito y lógica. Además, ayuda a detectar errores y problemas en el código, lo que facilita su corrección y mejora la calidad del software en general.


### Ejemplo Práctico: 
Un ejemplo práctico de un comentario de calidad en Java podría ser el siguiente:

```java
/**
 * Calcula el promedio de los elementos de la lista.
 * @param lista La lista de números a promediar.
 * @return El promedio de los elementos de la lista.
 */
public double calcularPromedio(List<Double> lista) {
    double suma = 0;
    for (Double numero : lista) {
        suma += numero;
    }
    double promedio = suma / lista.size();
    return promedio;
}
```

En este ejemplo, se utiliza un comentario de calidad para explicar la función de un método que calcula el promedio de los elementos de una lista de números. El comentario incluye una descripción clara y concisa de lo que hace el método, así como información adicional sobre los parámetros y el valor de retorno. Esto ayuda a otros desarrolladores a entender rápidamente qué hace el método y cómo utilizarlo correctamente.

----
<br>

## Título: Usar primero la instrucción try-catch-finally 🛑

**Pagina: 149-150**

### Definición: 
Esta práctica se refiere a colocar primero la estructura try-catch-finally al manejar excepciones en el código. Esto implica envolver el código que puede generar una excepción dentro de un bloque try, capturar y manejar la excepción en uno o varios bloques catch, y finalmente ejecutar el código que debe ejecutarse sin importar si se produce una excepción en el bloque finally.

### Resultado: 
Al utilizar esta práctica, se mejora la legibilidad y organización del código, ya que el manejo de excepciones está claramente separado del resto de la lógica. Además, garantiza que el código en el bloque finally se ejecute, lo que es útil para realizar tareas de limpieza o liberación de recursos, incluso si se produce una excepción.

### Ejemplo Práctico: 
Un ejemplo práctico de uso de la instrucción try-catch-finally en Java podría ser el siguiente:

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ManejoArchivo {
    public static void main(String[] args) {
        BufferedReader reader = null;
        try {
            reader = new BufferedReader(new FileReader("archivo.txt"));
            String linea;
            while ((linea = reader.readLine()) != null) {
                System.out.println(linea);
            }
        } catch (IOException e) {
            System.out.println("Error al leer el archivo: " + e.getMessage());
        } finally {
            try {
                if (reader != null) {
                    reader.close();
                }
            } catch (IOException e) {
                System.out.println("Error al cerrar el archivo: " + e.getMessage());
            }
        }
    }
}
```
En este ejemplo, se utiliza la instrucción try-catch-finally para manejar la lectura de un archivo. El código que puede generar una excepción, en este caso, la lectura de líneas del archivo, se coloca dentro del bloque try. Si se produce una excepción de tipo IOException, se captura y se maneja en el bloque catch, donde se muestra un mensaje de error. En el bloque finally, se asegura de que el archivo se cierre correctamente, incluso si se produce una excepción durante la lectura. Esto garantiza que los recursos se liberen adecuadamente y se eviten posibles fugas de memoria.

----
<br>

## Cita Relevante 🔥

La siguiente cita considero que es fundamental para todos los que programamos código:

<br>

**Original**
>"Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer's intent but rather is full of crisp abstractions and straightforward lines of control."

<br>

**Traduccion: "Español"**
>"El código limpio es simple y directo. El código limpio se lee como una prosa bien escrita. El código limpio nunca oculta la intención del diseñador, sino que está lleno de abstracciones precisas y líneas de control directas."

<br>

Esta cita refleja un consejo fundamental para escribir código limpio porque resalta la importancia de la simplicidad y la claridad en el código. El código limpio debe ser fácil de entender, como una buena prosa, y nunca debe ocultar la intención del diseñador. Más bien, debe estar lleno de abstracciones claras y líneas de control directas.

Esta cita se aplica en el contexto del desarrollo de software al recordarnos que el objetivo principal al escribir código no es solo hacer que la computadora lo entienda, sino también facilitar que otros desarrolladores (y nosotros mismos en el futuro) lo comprendan y modifiquen. Cuando el código es simple, directo y claro, es mucho más fácil para otros colaboradores trabajar en él, identificar problemas, agregar nuevas funcionalidades y corregir errores.

La cita enfatiza la importancia de la comunicación efectiva a través del código. Los desarrolladores pasan más tiempo leyendo y manteniendo código que escribiéndolo desde cero. Por lo tanto, priorizar la legibilidad y la comprensión del código es esencial para un desarrollo exitoso y eficiente a lo largo del tiempo.