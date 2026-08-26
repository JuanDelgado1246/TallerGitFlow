# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre: Juan David Delgado
- Nombre: Jeronimo Mazo Diez
- Nombre: Juan José Ortega Aguilera


## 3. Requerimientos Funcionales

### RF-01 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-02 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-03 - [Inscripción de estudiante en una tutoría]

#### Resumen
Permitir que un estudiante solicite su inscripción a una tutoría académica mediante su código estudiantil y el identificador de la tutoría.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|Código Estudiantil         | String | Identificador único del estudiante que desea inscribirse |
|Identificador tutoría      | String | Identificador único de la tutoría a la que el estudiante desea inscribirse |

#### Reglas o condiciones
-El estudiante debe encontrarse activo en la Universidad.
-La tutoría debe existir.
-La tutoría debe tener al menos un cupo disponible.
-El estudiante no debe estar previamente inscrito en la tutoría.
-Si alguna de las condiciones no se cumple, la inscripción no debe realizarse.
-Cuando la inscripción sea exitosa, se debe registrar la inscripción y disminuir en uno la cantidad de cupos disponibles.

#### Salidas

| Salida | Tipo de dato | Descripción |
|Mensaje de confirmación | String | Informa al estudiante que la inscripción fue realizada correctamente |
|Mensaje de error        | String | Informa el motivo por el cual no fue posible realizar la inscripción |
|Cantidad cupo disponible| int    | Cantidad de cupos restantes después de realizar una inscripción exitosa|


#### Resultado esperado
La inscripción del estudiante queda registrada correctamente, la cantidad de cupos disponibles de la tutoría se reduce en uno y se muestra un mensaje de confirmación. Si alguna de las condiciones requeridas no se cumple, la inscripción no se realiza y se informa al estudiante el motivo.

### RF-04 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
