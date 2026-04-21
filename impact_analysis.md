## 1. Cambio solicitado 

Implementar un contador de horas de juego, el cual no debe ser manipulado por el jugador solamente por el desarrollador.

## 2. Nuevas historias de usuario 

 ### US-01: Sistema de reconocimiento 

Como usuario, 
quiero obtener reconocimiento del tiempo invertido, 
para incentivar la lealtad del juego.

Criterios de aceptación:

- CA1: Dado que el contador de horas esta activo, cuando el valor alcanza un tiempo determinado, entonces el sistema debe marcar el logro como "completado" internamente.
- CA2: Dado que el tiempo es controlado por el desarrollador, cuando se intenta modificar manualmente el archivo de guardado, entonces el sistema debe validar para evitar fraudes en las recompensas.

### US-02: Retención de usuario.

Como desarrollador, 
quiero implementar un contador de tiempo de juego persistente, 
para analizar la retención del usuario.

Criterios de aceptación:

- CA1: Dado que el jugador abre el menú de pausa, cuando la acción de juego se detiene, entonces el contador debe suspenderse inmediatamente para no inflar las estadísticas.
- CA2: Dado que el jugador cierra la aplicación, cuando se detecta el evento de cierre, entonces el sistema debe guardar el tiempo acumulado.

## 3. Impacto en requisitos extrafuncionales 

Indicar si el cambio altera la prioridad de algún REF o introduce nuevos. 
Trazar cambios de prioridad que motiven cambios en decisiones de arquitectura. 

| REF ID | Descripción                    | Prioridad anterior | Prioridad nueva | Cambio / Motivo           | 
|--------|--------------------------------|--------------------|-----------------|---------------------------| 
| REF-01 | Eficiencia                  | Alta               | Alta            | Sin cambio                | 
| REF-02 | Fiabilidad / Disponibilidad  | Media               | Media            | Sin cambio              | 
| REF-03 | Seguridad                  | Media              | Alta            | El cambio lo hace crítico | 
| REF-04 | Compatibilidad  | Media               | Media            | Sin cambio              | 
| REF-05 | Aforo / Soporte | Media               | Media            | Sin cambio              | 
| REF-06 | Recuperabilidad | Baja                  | Alta            | El cambio lo hace crítico   | 
| REF-07 | Capacidad de interacción  | Baja               | Baja            | Sin cambio              | 
| REF-08 | Calidad de rendimiento | Alta                  | Alta            | Sin cambio           | 
| REF-09 | Mantenibilidad | Alta                 | Media            | El requisito se va dirigido al cambio  | 
| REF-10 | Testabilidad | Media | Alta            | El cambio lo hace crítico           | 
 

## 4. Impacto en entidades del dominio 

[Nuevas entidades, atributos o relaciones afectadas] + Diagrama acutalizado 

 

## 5. Impacto en mockups 

[Mockups afectados y descripción de cambios necesarios] 

 

## 6. Impacto en arquitectura 

### 6.1 ¿Cambia el estilo arquitectónico? 

No cambia, ya que se mantiene el formato de capas (3), ya que el contador viviría en la capa de servicios, se mostraría en la capa de presentación y se almacenaría de forma segura en la capa de datos.

### 6.2 Relación REF (repriorizado) con decisiones de arquitectura 

| REF ID | Prioridad nueva | Decisión de arquitectura que lo aborda         | 
|--------|-----------------|------------------------------------------------| 
| REF-01 | Alta            | El sistema debe respoder en menos de 2 segundos.  | 
| REF-03 | Alta            | Se necesita evitar fraudes en el sistema de recompensas.    | 
| REF-06 | Alta            | Resguardar y proteger los datos que se necesitan almacenar.   | 
| REF-08 | Alta            | El contador no debe afectar en el rendimiento del juego.  | 
| REF-10 | Alta            | El contador se debe adaptar bien a lo ya previamente establecido.        | 

## 7. Impacto en módulos 

 
| Módulo             | Tipo de impacto    | Responsabilidad actualizada        | Ofrece a otros (actualizado)   | 
|--------------------|--------------------|------------------------------------|--------------------------------| 
| [Módulo existente] | modificado         | [descripción actualizada]          | [interfaces actualizadas]      | 
| [Módulo nuevo]     | nuevo              | [responsabilidad]                  | [qué expone]                   | 
| [Módulo eliminado] | eliminado          | —                                  | —                              | 

 
Fundamentación de cambios modulares: 

[Justificar por qué se agregan, modifican o eliminan módulos en función del 
cambio de requerimientos y/o la repriorización de REF.] 

 

## 8. Nuevas decisiones de diseño 

 

### Decisión 1 

- Decisión: [qué se decide] 

- Motivación: [por qué, referenciando REF repriorizado si aplica] 

- Alternativas consideradas: [opciones evaluadas] 

- Impacto: [en qué módulos o REF afecta] 

 
## 9. Trazabilidad actualizada 

 
| Historia | REF relacionado | Módulo     | Mockup  | 
|----------|-----------------|------------|---------| 
| US-XX    | REF-XX          | [módulo]   | [ref]   | 

 

## 10. Justificación global y trade-offs 

[Por qué la solución propuesta es coherente con el sistema. 
Qué trade-offs se asumieron, especialmente ante cambios de prioridad en REF. 

Qué se gana y qué se sacrifica con las decisiones tomadas.] 
