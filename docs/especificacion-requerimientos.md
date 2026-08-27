# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre: Juan David Delgado
- Nombre: Jeronimo Mazo Diez
- Nombre: Juan José Ortega Aguilera


## 3. Requerimientos Funcionales

### RF-01 - [registro-tutoria]

#### Resumen
El sistema deberá permitir que un profesor registre una nueva tutoría académica, proporcionando la información necesaria para que posteriormente los estudiantes puedan consultarla e inscribirse.
#### Entradas

| Entrada                        | Tipo de dato | Descripción                                                       |
| ------------------------------ | ------------ | ----------------------------------------------------------------- |
| Código del profesor            | String       | Código que identifica al profesor que ofrece la tutoría.          |
| Tema de la tutoría             | String       | Tema o contenido académico que será tratado en la tutoría.        |
| Fecha                          | Date         | Fecha en la que se realizará la tutoría.                          |
| Hora de inicio                 | Time         | Hora en la que comenzará la tutoría.                              |
| Cantidad máxima de estudiantes | Integer      | Número máximo de estudiantes que podrán participar en la tutoría. |


#### Reglas o condiciones
La fecha de la tutoría no puede ser anterior a la fecha actual.
La cantidad máxima de estudiantes debe estar entre 1 y 10.
El sistema deberá asignar automáticamente un identificador único a la tutoría.
El registro solo se realizará si todas las condiciones son válidas.
#### Salidas

| Salida                      | Tipo de dato   | Descripción                                                  |
| --------------------------- | -------------- | ------------------------------------------------------------ |
| Identificador de la tutoría | Integer/String | Identificador único asignado a la tutoría.                   |
| Mensaje de confirmación     | String         | Informa al profesor que la tutoría fue creada correctamente. |


#### Resultado esperado
La tutoría queda registrada correctamente en el sistema con un identificador único y el profesor recibe un mensaje de confirmación.

### RF-02 - [consulta-tutorías]

#### Resumen
El sistema deberá permitir a los estudiantes consultar las tutorías disponibles para una fecha determinada y, opcionalmente, filtrar los resultados por asignatura o tema de interés.
#### Entradas

| Entrada           | Tipo de dato | Descripción                                                                            |
| ----------------- | ------------ | -------------------------------------------------------------------------------------- |
| Fecha de consulta | Date         | Fecha para la cual el estudiante desea consultar las tutorías.                         |
| Asignatura o tema | String       | Criterio opcional utilizado para filtrar las tutorías según el interés del estudiante. |


#### Reglas o condiciones
La fecha de consulta es obligatoria.
La asignatura o tema es opcional.
Si se proporciona un tema, solo deberán mostrarse las tutorías que correspondan con este.
Solo deberán mostrarse tutorías que correspondan con los criterios de búsqueda.
Si no existen tutorías que coincidan con la búsqueda, el sistema deberá informar al estudiante.
#### Salidas

| Salida                   | Tipo de dato   | Descripción                                                          |
| ------------------------ | -------------- | -------------------------------------------------------------------- |
| Identificador de tutoría | Integer/String | Identificador de la tutoría encontrada.                              |
| Tema                     | String         | Tema de la tutoría.                                                  |
| Profesor responsable     | String         | Profesor encargado de la tutoría.                                    |
| Fecha                    | Date           | Fecha de realización de la tutoría.                                  |
| Hora                     | Time           | Hora de inicio de la tutoría.                                        |
| Cupos disponibles        | Integer        | Cantidad de estudiantes que aún pueden inscribirse.                  |
| Mensaje                  | String         | Informa si no se encontraron tutorías que coincidan con la búsqueda. |


#### Resultado esperado
El estudiante recibe una lista de las tutorías disponibles que coinciden con los criterios de búsqueda, mostrando su información y los cupos disponibles. Si no existen coincidencias, recibe un mensaje informativo


### RF-03 - [inscripcion-tutoria]

#### Resumen
El sistema deberá permitir que un estudiante solicite su inscripción a una tutoría utilizando su código estudiantil y el identificador de la tutoría.
#### Entradas

| Entrada                  | Tipo de dato   | Descripción                                                                 |
| ------------------------ | -------------- | --------------------------------------------------------------------------- |
| Código estudiantil       | String         | Código que identifica al estudiante que desea inscribirse.                  |
| Identificador de tutoría | Integer/String | Identificador único de la tutoría a la que el estudiante desea inscribirse. |


#### Reglas o condiciones
El estudiante debe encontrarse activo en la Universidad.
La tutoría debe existir.
La tutoría debe tener al menos un cupo disponible.
El estudiante no debe encontrarse previamente inscrito en la tutoría.
Si alguna condición no se cumple, la inscripción no deberá realizarse.
Cuando la inscripción sea exitosa, se deberá disminuir en uno la cantidad de cupos disponibles.
#### Salidas

| Salida                   | Tipo de dato | Descripción                                                                 |
| ------------------------ | ------------ | --------------------------------------------------------------------------- |
| Estado de la inscripción | Boolean      | Indica si la inscripción fue realizada correctamente.                       |
| Mensaje                  | String       | Confirma la inscripción o informa el motivo por el cual no pudo realizarse. |
| Cupos disponibles        | Integer      | Cantidad actualizada de cupos disponibles después de la inscripción.        |


#### Resultado esperado
El estudiante queda inscrito correctamente en la tutoría, se registra la inscripción, se actualizan los cupos disponibles y se muestra un mensaje de confirmación. Si alguna condición no se cumple, no se realiza la inscripción y se informa el motivo

### RF-04 - [cancelacion-inscripcion]

#### Resumen

Permitir que un estudiante que se encuentre inscrito en una tutoría pueda cancelar su participación.

#### Entradas
| Entrada                  | Tipo de dato   | Descripción                                                              |
| ------------------------ | -------------- | ------------------------------------------------------------------------ |
| Código estudiantil       | String         | Código que identifica al estudiante que desea cancelar su participación. |
| Identificador de tutoría | Integer/String | Identificador único de la tutoría en la que el estudiante está inscrito. |



#### Reglas o condiciones

- El estudiante debe tener una inscripción previa en la tutoría.
- La tutoría debe existir.
- La tutoría no debe haber comenzado.
- Si alguna de las condiciones no se cumple, la cancelación no deberá realizarse.

#### Salidas
| Salida                   | Tipo de dato | Descripción                                                                   |
| Estado de la cancelación | Boolean      | Indica si la cancelación fue realizada correctamente.                         |
| Mensaje                  | String       | Confirma la cancelación o informa el motivo por el cual no pudo realizarse.   |
| Cupos disponibles        | Integer      | Cantidad actualizada de cupos disponibles después de cancelar la inscripción. |

#### Resultado esperado

La inscripción del estudiante es eliminada, se libera nuevamente el cupo correspondiente de la tutoría y se informa al estudiante que la cancelación fue realizada correctamente.


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
