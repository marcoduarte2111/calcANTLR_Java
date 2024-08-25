# Calculadora Implementada con ANTLR y Java

Este proyecto implementa una calculadora utilizando ANTLR y Java. La calculadora es capaz de manejar operaciones aritméticas básicas, así como variables y asignaciones. A continuación, se detallan los pasos para ejecutar el código y la descripción de cómo se implementó.

## Implementación de la Calculadora

### 1. Consulta del Capítulo 4

- El diseño y la implementación de la calculadora se basan en el Capítulo 4 del material de estudio.
- Se implementaron las siguientes funcionalidades:
  - Definición de gramática para operaciones aritméticas y asignación de variables.
  - Implementación de un visitante para evaluar las expresiones y manejar variables.

### 2. Descripción de la Implementación

- **Gramática ANTLR (`LabeledExpr.g4`)**:
  - Define la sintaxis para operaciones aritméticas, asignaciones y variables.
  - Permite manejar expresiones como `a + b * 2` y `(1 + 2) * 3`.

- **Clases Generadas por ANTLR**:
  - `LabeledExprLexer.java`: Lexer para dividir el texto en tokens.
  - `LabeledExprParser.java`: Parser para analizar la estructura del texto según la gramática.
  - `LabeledExprBaseVisitor.java` y `LabeledExprVisitor.java`: Clases base para implementar el visitante.

- **Visitor (`LabeledExprVisitorImpl.java`)**:
  - Implementa la lógica para evaluar expresiones y manejar variables.
  - Utiliza un `Map` para almacenar el valor de las variables y realiza cálculos según la expresión dada.

## Ejecución del Proyecto

### 1. Preparación del Entorno

1. **Instala ANTLR**:
   - Descarga el archivo JAR de ANTLR desde [la página de ANTLR](https://www.antlr.org/download.html).

2. **Prepara la Gramática**:
   - Crea un archivo llamado `LabeledExpr.g4` con el contenido de la gramática proporcionada.

### 2. Generar Clases con ANTLR

Utiliza el siguiente comando para generar los archivos de lexer, parser, y visitor:

```bash
java -jar /usr/local/bin/antlr-4.13.2-complete.jar -visitor LabeledExpr.g4
