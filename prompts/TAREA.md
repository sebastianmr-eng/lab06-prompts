# Tarea: Mi prompt profesional

## Funcionalidad elegida

Registro de clientes

## Version 1: prompt basico

```text
Crea un programa en Java para registrar usuarios con correo y contraseña.
```

Se usó una instrucción muy general y directa sin parámetros. Sirve como punto de partida para identificar la falta de estructura en la respuesta del LLM. Finalmente, generó un código funcional básico en consola, pero sin interfaz gráfica, sin modularización clara y sin validaciones de seguridad.

## Version 2

```text
Actúa como un desarrollador Senior en Java. Crea un sistema de registro de usuarios utilizando una interfaz gráfica con Swing. Debe solicitar correo y contraseña, y validar que los datos no estén vacíos.
```

Agregué un rol (desarrollador Senior), especificué la tecnología visual (Swing) y añadí una validación simple (no vacíos). Para evitar que el código sea de consola y empezar a dar contexto técnico. Finalmente, la respuesta ya incluye código GUI con JFrame, pero sigue careciendo de un formato estructurado de salida, explicaciones técnicas organizadas y restricciones estrictas de librerías.

## Version 3: prompt final

```text
Actúa como un Desarrollador Java Senior experto en Swing y arquitectura de software.

Tu tarea es escribir un módulo completo de registro de usuarios en Java usando la librería javax.swing. El sistema debe solicitar correo electrónico y contraseña, realizar validaciones de formato de correo y longitud de contraseña, y mostrar mensajes contextuales al usuario.

Contexto: Este código formará parte de un proyecto educativo para estudiantes universitarios, por lo que el código debe estar altamente documentado con comentarios explicativos, organizado en clases independientes (separando la GUI de la lógica de validación) y listo para ejecutarse sin configuraciones complejas.

Ejemplo de entrada/salida esperada en la validación:
- Entrada: correo = "usuario.com", contraseña = "123"
- Salida esperada: Error de validación -> "El correo no tiene un formato válido" y "La contraseña debe tener al menos 6 caracteres".

Formato de respuesta:
1. Breve explicación conceptual de la estructura de clases utilizada.
2. Código fuente completo organizando cada clase en su propio bloque de código Markdown.
3. Breve guía de ejecución.

Restricciones:
- No uses librerías externas (utiliza únicamente el JDK estándar y javax.swing / java.awt).
- La contraseña debe enmascararse mediante JPasswordField.
```

Incorporé los 5 componentes principales (Rol, Instrucción, Contexto, Ejemplo, Formato) y restricciones explícitas. Para obtener una respuesta exacta, profesional, modular y alineada al objetivo sin ambigüedades. Finalmente, el código modular estructurado en clases (UserRegistrationForm.java, Validator.java), manejo correcto de componentes Swing, comentarios educativos completos y salida en el formato exacto requerido.

## Componentes del prompt final

| Componente  | Texto de mi prompt                                                                                                                                                                                                                                                                                               |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Rol         | Actúa como un Desarrollador Java Senior experto en Swing y arquitectura de software.                                                                                                                                                                                                                             |
| Instruccion | Tu tarea es escribir un módulo completo de registro de usuarios en Java usando la librería javax.swing. El sistema debe solicitar correo electrónico y contraseña, realizar validaciones de formato de correo y longitud de contraseña, y mostrar mensajes contextuales al usuario.                              |
| Contexto    | Este código formará parte de un proyecto educativo para estudiantes universitarios, por lo que el código debe estar altamente documentado con comentarios explicativos, organizado en clases independientes (separando la GUI de la lógica de validación) y listo para ejecutarse sin configuraciones complejas. |
| Ejemplo     | Entrada: correo = "usuario.com", contraseña = "123". Salida esperada: Error de validación -> "El correo no tiene un formato válido" y "La contraseña debe tener al menos 6 caracteres".                                                                                                                          |
| Formato     | Breve explicación conceptual de la estructura de clases utilizada. Código fuente completo organizando cada clase en su propio bloque de código Markdown. Breve guía de ejecución.                                                                                                                                |

## Evaluacion del resultado

| Qué revisar                                            | Cumple (Sí / No) |
| ------------------------------------------------------ | ---------------- |
| ¿Está escrito en Java y usa Swing?                     | Si               |
| ¿Pide correo y contraseña?                             | Si               |
| ¿Explica el funcionamiento antes o después del código? | Si               |
| ¿El código está organizado en clases?                  | Si               |
| ¿Valida los datos que ingresa el usuario?              | Si               |

## Errores que evite

1. Ser demasiado general: En la versión v1 solo pedí "un programa en Java", lo que generaba un script plano de consola. Lo evité delimitando en el prompt final el framework exacto (javax.swing), las variables a capturar y la arquitectura deseada.
2. No indicar el formato de salida: En iteraciones previas la IA entregaba explicaciones largas mezcladas con el código. Lo evité estableciendo una lista numerada en la sección Formato, separando la explicación teórica, el código modular y la guía de ejecución.
