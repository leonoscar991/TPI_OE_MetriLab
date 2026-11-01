# Sistema de Inventario de Calibración — MetriLab S.R.L.

**Trabajo Práctico Integrador y Progresivo (TPI) — Organización Empresarial**
Tecnicatura Universitaria en Programación a Distancia — Universidad Tecnológica Nacional
Comisión 13 · Docente tutora: Prof. Laureana Gangge

**Integrante:** Oscar Hernán Leon Oyarzo (trabajo individual)

---

## Descripción del proyecto

MetriLab S.R.L. es un laboratorio de calibración e instrumentación (organización ficticia, construida a
partir del funcionamiento real de este tipo de laboratorios) que presta servicios a la industria del
petróleo y gas en la Patagonia, bajo la norma ISO/IEC 17025.

El proyecto propone un **Sistema de Inventario de Calibración** que centraliza el registro de los
instrumentos, el control de vencimientos de los patrones de referencia y la trazabilidad de los
certificados emitidos. Hoy esa información está repartida entre planillas, carpetas en papel y el
conocimiento de cada técnico.

## Enlaces

- **Repositorio:** https://github.com/leonoscar991/TPI_OE_MetriLab
- **Tablero del proyecto (GitHub Projects):** https://github.com/users/leonoscar991/projects/1/views/1
- **Historias de usuario (issues):** pestaña *Issues* de este repositorio

## Contenido del repositorio

| Carpeta | Contenido |
|---|---|
| `docs/` | Entregas N.º 1, 2 y 3 y el PDF final consolidado |
| `diagramas/` | Diagrama BPMN del proceso de calibración y su descripción |
| `backlog/` | Historias de usuario con criterios de aceptación |
| `control/` | Indicadores de control y estándares de desempeño |

## Recorrido del TPI

1. **Entrega 1:** la organización como sistema abierto (TGS) y elección del módulo de software.
2. **Entrega 2:** FODA del proyecto, objetivo general, metas cuantitativas y Diagrama de Gantt.
3. **Entrega 3:** organigrama piramidal y diccionario de datos (CLIENTE, EQUIPO, PATRON, CALIBRACION).
4. **Entrega 4:** proceso en BPMN, gestión con Git y GitHub, backlog ágil e indicadores de control.

## Flujo de trabajo con Git

Cada parte de la Entrega 4 se desarrolló en una rama propia y se integró a `main` mediante un
Pull Request revisado antes del merge:

- `docs/entregas-anteriores` — incorporación de las Entregas 1, 2 y 3.
- `docs/bpmn` — diagrama BPMN y su descripción.
- `docs/backlog-y-control` — historias de usuario e indicadores de control.

---

## Declaración de Uso de IA

Durante todo el TPI utilicé un asistente de IA generativa (**Claude**, de Anthropic). La IA se usó para
ordenar y redactar, y para diseñar las figuras. Las decisiones sobre el caso, los datos y el proceso
salieron de mi experiencia profesional en calibración e instrumentación para petróleo y gas.

### Prompts principales y para qué se usaron

| Entrega | Prompt (resumido) | Uso |
|---|---|---|
| 1 | "Ayudame a modelar un laboratorio de calibración de petróleo y gas como sistema abierto según la TGS" | Ordenar entradas, procesos, salidas y contexto |
| 2 | "Armá un FODA enfocado solo en la viabilidad del proyecto de software" | Clasificar los factores en los cuatro cuadrantes |
| 3 | "Proponé un diccionario de datos con al menos tres entidades para el inventario de calibración" | Primera versión de las entidades y sus campos |
| 4 | "Diagramá en BPMN el proceso de calibración con pools, lanes y compuertas para las excepciones" | Primera versión del diagrama y de las historias de usuario |
| 1–4 | "Generá la figura con el mismo estilo que las anteriores" | Diseño gráfico de los diagramas |

### Correcciones humanas sobre los resultados de la IA

- **Patrones de referencia:** la primera versión trataba a los patrones como si pertenecieran al cliente.
  Los corregí: son propiedad del laboratorio y su trazabilidad depende de la entidad certificadora
  externa, por eso la entidad PATRON tiene `entidad_certificadora` y `numero_certificado`.
- **Periodicidad de calibración:** la IA la ubicaba como una política del cliente. La corregí: depende
  del punto de aplicación del equipo (24 meses en separadores, 12 meses en salida de estación por su
  incidencia en la transferencia de custodia), así que es un atributo del EQUIPO.
- **Vigencia calculada:** decidí calcular la vigencia del equipo a partir de la última calibración en
  lugar de almacenarla, para que un cambio de periodicidad no obligue a corregir registros.
- **Responsable de Calidad como staff:** lo ubiqué fuera de la línea de Operaciones Técnicas porque la
  norma exige independencia respecto de las áreas que audita.
- **FODA:** agregué un antecedente real de digitalización parcial del laboratorio, que la IA no podía
  conocer, y que aparece como oportunidad y como amenaza.
- **Formulaciones genéricas:** descarté en todas las entregas las frases que no se ajustaban a cómo
  funciona realmente un laboratorio de este tipo.

Asumo la responsabilidad intelectual por la veracidad y la coherencia del contenido presentado.
