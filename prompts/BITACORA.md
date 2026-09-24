# Bitacora de prompts

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: (Gemini)

## Ejercicio 2: Tokens y ventana de contexto

| Texto                              | Caracteres | Tokens |
| ---------------------------------- | ---------- | ------ |
| Los estudiantes programan en Java. | 37         | 8      |
| The students program in Java.      | 29         | 6      |
| desafortunadamente                 | 18         | 4      |

En los pasos 4 y 5, la herramienta respondió correctamente gracias al contexto previo del chat. Al abrir una nueva ventana, la conversación se reinicia sin historial, por lo que no reconoce el proyecto y solicita información adicional.

## Ejercicio 3: Temperatura

| Temperatura | % de BiblioTec | Nombres en los 5 intentos                                 |
| ----------- | -------------- | --------------------------------------------------------- |
| 0           | 100.0%         | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec     |
| 0.5         | 65.3%          | BiblioTec, BiblioTec, BiblioTec, LibroYa, BiblioTec       |
| 1           | 44.5%          | LibroYa, BiblioTec, LibroYa, BiblioTec, LibroYa           |
| 1.8         | 32.2%          | PrestaLibro, NubeDeTinta, PrestaLibro, BiblioTec, LibroYa |

Al subir la temperatura, el modelo elige opciones menos probables y más variadas entre las alternativas disponibles. Sin embargo, nunca inventa un nombre nuevo porque la temperatura solo cambia la probabilidad de elección, no el conocimiento o vocabulario del modelo.

## Ejercicio 4: Prompt vago vs estructurado

| Criterio                            | Prompt vago | Prompt estructurado |
| ----------------------------------- | ----------- | ------------------- |
| Menciona el objetivo del sistema    | Si          | Si                  |
| Menciona a los usuarios principales | Si          | Si                  |
| Tiene exactamente 3 funcionalidades | No          | Si                  |
| Esta en 3 parrafos                  | No          | Si                  |
| Lo usaria en un informe real        | No          | Si                  |

## Ejercicio 5: Anatomia de un prompt

| Componente  | Texto de mi prompt                                                             |
| ----------- | ------------------------------------------------------------------------------ |
| Rol         | Actua como desarrollador Java                                                  |
| Instruccion | ...usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto    | Crea un programa en Java para gestionar los productos de una tienda.           |
| Ejemplo     | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio).       |
| Formato     | ...Explica primero la estructura de la clase y luego presenta el codigo Java.  |

## Ejercicio 6: Del prompt basico al profesional

| Qué revisar                                            | Cumple (Sí / No) |
| ------------------------------------------------------ | ---------------- |
| ¿Está escrito en Java y usa Swing?                     | Si               |
| ¿Pide correo y contraseña?                             | Si               |
| ¿Explica el funcionamiento antes o después del código? | Si               |
| ¿El código está organizado en clases?                  | Si               |
| ¿Valida los datos que ingresa el usuario?              | Si               |

```text
Actua como desarrollador Java. Crea un ejemplo de login para una aplicacion de escritorio utilizando Swing. El usuario debe ingresar correo y contrasena. Explica brevemente el funcionamiento y presenta
el codigo organizado por clases.
Mejora el codigo anterior con estas restricciones: no uses librerias externas, valida que el correo contenga @ y que la contrasena tenga al menos 8 caracteres, y muestra los mensajes con JOptionPane.
```
