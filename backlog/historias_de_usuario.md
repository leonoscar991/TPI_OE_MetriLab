# Historias de Usuario — Sistema de Inventario de Calibración

Las tres historias corresponden a las tres funciones críticas del sistema, que en el Diagrama de Gantt
de la Entrega N.º 2 se planificaron como tareas de codificación separadas (tareas 3, 4 y 5).
Cada historia se gestiona como un *issue* del repositorio y se sigue en el tablero del proyecto
(Por Hacer → En Progreso → Listo).

---

## HU-01 — Registro de equipos con identificador único

**Como** técnico de Recepción y Depósito,
**quiero** registrar cada equipo que ingresa con un identificador único, su cliente y su ubicación en el depósito,
**para** que ese registro acompañe al instrumento durante todo el circuito sin volver a cargar sus datos.

**Criterios de aceptación**
- El sistema asigna un `id_equipo` único al dar de alta el equipo.
- No se puede registrar un equipo sin cliente asociado ni con un número de serie ya existente para ese cliente.
- El estado inicial del equipo es *en espera* y queda registrada su ubicación en el depósito.

**Entidades involucradas:** EQUIPO, CLIENTE · **Tarea del Gantt:** 3

---

## HU-02 — Bloqueo de patrones con certificado vencido

**Como** técnico del Laboratorio de Calibración,
**quiero** que el sistema bloquee los patrones de referencia cuyo certificado esté vencido,
**para** no emitir certificados que no tengan trazabilidad válida.

**Criterios de aceptación**
- Al seleccionar un patrón, el sistema compara `fecha_vencimiento` con la fecha actual.
- Si el patrón está vencido, el campo `habilitado` pasa a falso y el sistema impide usarlo en la calibración.
- El sistema avisa con 30 días de anticipación los patrones próximos a vencer.

**Entidades involucradas:** PATRON, CALIBRACION · **Tarea del Gantt:** 4

---

## HU-03 — Historial de calibraciones para auditoría

**Como** Responsable de Calidad,
**quiero** consultar el historial completo de calibraciones de un equipo, con el patrón utilizado en cada servicio,
**para** responder una auditoría bajo ISO/IEC 17025 sin reconstruir la evidencia a partir de carpetas.

**Criterios de aceptación**
- Cada calibración se agrega al historial sin sobrescribir las anteriores.
- La consulta por número de serie o TAG muestra fecha, técnico, resultado, incertidumbre, certificado emitido y patrón utilizado.
- La consulta responde en menos de 5 segundos sobre una base de al menos 5.000 registros (meta 3 de la Entrega N.º 2).

**Entidades involucradas:** CALIBRACION, EQUIPO, PATRON · **Tarea del Gantt:** 5
