# OpenTwin EXO — especificaciones técnicas de alto nivel

Versión propuesta 0.1 · 10 octubre 2026 · Base: `eedebad5ea331001c57d187ae16162d4a004bd68`.

## Alcance y estado

Refactorización documental de la ingeniería de requisitos para el concepto OpenTwin EXO / H2FLY. Todos los requisitos HL son **propuestos, pendientes de aprobación y verificación**. La ilustración aporta intención visual, no dimensiones, prestaciones, integración funcional ni certificación. No hay CAD paramétrico, planos dimensionados, lista de materiales ni resultados de ensayo en la base revisada. H2FLY es una etiqueta del concepto: no demuestra relación comercial o técnica externa.

Se conserva el catálogo general de arquitectura del README y los diagramas CAS existentes. Esta especificación concentra el alcance del traje y sus módulos; no refactoriza software ejecutable. La aeronave del fondo constituye contexto visual: no se derivan requisitos de vuelo, propulsión ni integración aeronáutica.

## Fuentes y trazabilidad

- S1: [imagen de concepto v3](../../MBSE/CAD/h2fly-opentwin-exo-modular-expedition-suit-concept-v3.jpg): traje y módulos de construcción, pesca, caza, camping, gastronomía y asistencia profesional; indica diseño conceptual y validación pendiente.
- S2: [README](../../README.md): contratos canónicos, seguridad determinista, separación CAD/descripción robótica y ciclo MBSE → CAD → CAM → CAS.
- S3: [diagrama de datos experimentales](../../MBSE/CAS/Drawio/human-exoskeleton-control-simulation.drawio): contiene únicamente un nodo Experimental Data; no establece un lazo de control completo.
- S4: [método de modelado](../../MBSE/CAS/Drawio/mechatronicuml-development-method.drawio): proceso preliminar de requisitos y diseño de software.
- S5: [contexto regulatorio existente](../regulations/peru-hunting-licensing-and-restricted-areas.md): referencia contextual con limitaciones explícitas; no se adopta como autorización operativa.

## Descomposición del concepto

| Elemento | Evidencia visual | Traducción propuesta a ingeniería |
| --- | --- | --- |
| Traje corporal | Casco, torso, brazos, piernas, articulaciones y mochila | Interfaz humana, estructura, asistencia, sensado y seguridad; tecnología de actuadores y fuente de energía pendientes |
| Construcción | Taladro, atornillador y corte | Interfaces y aislamiento de accesorios; capacidades no verificadas |
| Pesca deportiva | Miniarpón; pulso eléctrico expresamente no validado | Inventario e interfaces pasivas; desarrollo funcional fuera de esta propuesta |
| Caza deportiva | Rifle, arco y flechas | Inventario y transporte conceptual; sin automatización de accionamiento |
| Camping | Refugio, descanso e iluminación | Montaje, transporte y balance energético |
| Gastronomía | Cocina, utensilios y conservación | Compatibilidad y aislamiento térmico |
| Asistencia profesional | Botiquín y módulo clínico | Segregación de funciones y validación especializada pendiente |

## Necesidades y requisitos

N-01: adaptar el conjunto a usos y usuarios definidos → HL-01, HL-02, HL-08, HL-12.
N-02: proporcionar asistencia física controlada → HL-03 a HL-07 y HL-09.
N-03: evaluar configuraciones de forma reproducible → HL-10, HL-11, HL-17.
N-04: incorporar accesorios según alcance aprobado → HL-13 a HL-16.
Estas necesidades son una interpretación editorial de S1/S2 y requieren revisión del responsable de producto.

La tabla CSV adjunta es la matriz completa de trazabilidad. Enunciados y criterios describen obligaciones propuestas; parámetros TBD impiden declarar aceptación cuantitativa hasta su cierre.

| ID | Especificación propuesta | Asignación | Verificación / aceptación | Pendiente |
| --- | --- | --- | --- | --- |
| HL-01 | **Configuración modular.** El sistema deberá identificar cada módulo y su revisión, y rechazar configuraciones incompatibles antes de habilitar asistencia. | Gestor de configuración | Revisión de matriz de compatibilidad y ensayo de módulo desconocido: habilitación rechazada. | TBD-01 |
| HL-02 | **Ajuste e interfaz humana.** El diseño deberá documentar envolventes antropométricas, alineación articular, zonas de contacto y procedimiento de colocación y liberación. | Interfaz humana / CAD | Inspección del CAD y protocolo de ajuste contra envolvente aprobada; liberación demostrada en banco. | TBD-02 |
| HL-03 | **Estructura y carga.** El diseño deberá declarar casos de carga, masa total, centro de gravedad y factores de diseño para cada configuración. | Estructura / CAD | Análisis estructural y ensayo de banco contra límites aprobados, sin fallo ni deformación fuera de tolerancia. | TBD-03 |
| HL-04 | **Cinemática y asistencia.** El sistema deberá declarar articulaciones, grados de libertad, rangos y límites de velocidad, esfuerzo y potencia por articulación. | Actuación / control | Comparación CAD-modelo y pruebas de saturación: comandos fuera de límites rechazados. | TBD-04 |
| HL-05 | **Seguridad determinista.** El sistema deberá aplicar límites y enclavamientos independientes de las decisiones de IA y registrar sus intervenciones. | Supervisor de seguridad | Inyección de órdenes inválidas y fallo de política: ningún comando evita el supervisor. | TBD-05 |
| HL-06 | **Estado seguro.** El sistema deberá definir y alcanzar un estado seguro ante parada, pérdida de comunicaciones, alimentación o sensores críticos, considerando soporte del usuario. | Supervisor / energía | Ensayos de fallo en banco: transición dentro del tiempo aprobado y evidencia de soporte mecánico seguro. | TBD-05 |
| HL-07 | **Energía.** El sistema deberá presupuestar consumo, autonomía y disipación por configuración, e impedir conexión energética incompatible. | Energía | Revisión de balance y ensayo con carga representativa contra presupuesto aprobado; conexión incompatible bloqueada. | TBD-06 |
| HL-08 | **Interfaz de módulos.** Cada interfaz deberá especificar fijación, bloqueo, carga admisible, conexiones, identificación y condiciones de intercambio. | Interfaz mecánica / eléctrica / datos | Inspección del documento de interfaz y ensayo de bloqueo, montaje y desconexión segura. | TBD-01 |
| HL-09 | **Sensado y calibración.** El sistema deberá documentar sensores requeridos, calibración, unidades, marcos, calidad y detección de datos vencidos. | Sensado | Reproducción de datos calibrados y datos vencidos: detección y transición de seguridad según perfil. | TBD-07 |
| HL-10 | **Gemelo digital.** Cada configuración deberá vincular CAD, descripción cinemática, masas, inercias, colisiones y revisiones mediante un manifiesto trazable. | Modelo / CAS | Revisión de manifiesto y comparación de marcos, unidades, masas e inercias con tolerancias aprobadas. | TBD-08 |
| HL-11 | **Interoperabilidad.** La integración deberá separar contratos de robot, observación, acción y simulación de sus implementaciones, e incluir unidades, tiempo y versionado. | Adaptadores / software | Prueba de contrato con dos adaptadores de ensayo: entradas y salidas conservan semántica y rechazan versión incompatible. | TBD-07 |
| HL-12 | **Entorno y mantenimiento.** El diseño deberá declarar condiciones de operación, transporte, limpieza, inspección y sustitución de módulos. | Integración / mantenimiento | Inspección de procedimientos y ensayos ambientales contra perfil aprobado. | TBD-09 |
| HL-13 | **Módulos de trabajo.** Los accesorios de construcción deberán declarar modos permitidos, interfaces y condiciones de aislamiento y almacenamiento. | Módulos de trabajo | Revisión de peligros y banco de interfaces; solo configuraciones aprobadas habilitan conexión. | TBD-10 |
| HL-14 | **Campamento y gastronomía.** Los módulos de refugio, iluminación, cocina y conservación deberán declarar compatibilidad, transporte y aislamiento térmico y energético. | Módulos auxiliares | Inspección y ensayo de montaje y temperatura contra perfil aprobado. | TBD-10 |
| HL-15 | **Accesorios restringidos.** Los accesorios de pesca y caza del concepto deberán permanecer fuera de la habilitación automática y limitarse al inventario e interfaces pasivas hasta revisión específica. | Configuración / gobernanza | Revisión de configuración: no existen comandos de accionamiento automático ni funciones habilitadas sin revisión. | TBD-11 |
| HL-16 | **Asistencia profesional.** El módulo clínico deberá quedar segregado del perfil general y sin habilitación de funciones clínicas hasta definición y aprobación de alcance y validación especializada. | Gobernanza / módulos | Inspección de perfil y prueba de acceso: perfil general no habilita funciones clínicas. | TBD-12 |
| HL-17 | **Evidencia y cambios.** Cada requisito deberá vincular fuente, responsable, diseño, revisión y evidencia; todo cambio de CAD deberá evaluar impacto sobre interfaces y pruebas. | Ingeniería de requisitos | Auditoría de trazabilidad: ningún requisito aprobado carece de diseño, criterio o evidencia identificable. | TBD-13 |

## Contratos de interfaz propuestos

- IF-01 Humano–traje: envolvente corporal, alineación, contactos, colocación y liberación; HL-02/03/06.
- IF-02 Traje–módulo: geometría de fijación, bloqueo, cargas, identificación, alimentación y datos; HL-01/07/08/13–16.
- IF-03 CAD–gemelo: unidades SI, marcos y orientación, articulaciones, masas, inercias, colisiones, formato de exportación y revisión; HL-04/10.
- IF-04 Control–seguridad: comandos propuestos, permisos, límites, estado y eventos; el supervisor puede vetar la ejecución; HL-05/06/09/11.
- IF-05 Ensayo–evidencia: configuración y hashes, versión de simulador, calibración, escenarios, métricas, resultados y responsable; HL-10/17.

Los nombres de subsistemas y contratos son arquitectura propuesta, no interfaces implementadas. La IA propone acciones; la autorización local y los límites deterministas preceden a la actuación.

## Registro de decisiones pendientes

| ID | Definición requerida | Rol propuesto para cierre |
| --- | --- | --- |
| TBD-01 | Catálogo, compatibilidad e interfaces | Arquitectura |
| TBD-02 | Población objetivo, tallas, contacto y liberación | Ergonomía |
| TBD-03 | Carga, masa, centro de gravedad, materiales y factores | Mecánica |
| TBD-04 | DOF, rangos, velocidad, esfuerzo y potencia | Control / mecánica |
| TBD-05 | Peligros, estados seguros, tiempos y cobertura de fallos | Seguridad |
| TBD-06 | Fuente energética, tensión, autonomía y temperaturas | Energía |
| TBD-07 | Sensores, tasas, latencia, reloj y contratos | Software / control |
| TBD-08 | Formatos, tolerancias y correlación del modelo | CAD / simulación |
| TBD-09 | Temperatura, humedad, protección y mantenimiento | Integración |
| TBD-10 | Alcance y aceptación de accesorios de trabajo y campamento | Producto |
| TBD-11 | Alcance permitido de accesorios restringidos | Gobernanza |
| TBD-12 | Uso previsto y evaluación del módulo clínico | Responsable especializado |
| TBD-13 | Responsables, aprobadores y repositorio de evidencias | Proyecto |

## Verificación y puertas de madurez

| Puerta | Entregables y condición de salida |
| --- | --- |
| G0 — requisitos | Uso previsto, necesidades, requisitos, riesgos y todos los TBD del alcance de la siguiente etapa aprobados; responsables nombrados |
| G1 — concepto CAD | CAD paramétrico, interfaces, configuración, masas y casos de carga disponibles; revisión de ajuste y coherencia del modelo |
| G2 — CAS / simulación | Descripción robótica y escenarios reproducibles; límites y fallos probados; correlación y tolerancias documentadas |
| G3 — CAM / banco | Planos, materiales y montaje trazables; inspección y ensayos mecánicos, eléctricos y de estado seguro contra límites aprobados |
| G4 — evaluación supervisada | Evidencias revisadas y autorización específica para el uso previsto; alcances clínicos o restringidos requieren su propia revisión |

Estas puertas son criterios propuestos, no resultados alcanzados. Simulación aprobada no equivale a aptitud para uso humano. Las primeras pruebas se planifican en simulación y banco; la evaluación con personas depende de G4.

## Gestión de configuración

Cada configuración deberá mantener `config_id`, revisión, lista de módulos, revisión CAD, revisión de modelo, perfil de límites, requisitos aplicables y evidencia. Cada informe de verificación identificará requisito, procedimiento y versión, configuración, parámetros aprobados, resultado esperado y observado, desviaciones y responsable. Estados: propuesto → aprobado → verificado, o rechazado/retirado con justificación. Cambios de geometría, masa, interfaz o control requieren análisis de impacto y repetición de verificaciones afectadas.

## Diagrama y entregables

[Draw.io editable de cuatro páginas](../../MBSE/CAS/Drawio/opentwin-exo-high-level-requirements.drawio): contexto, asignación de requisitos, interfaces y ciclo de verificación. Flechas expresan relaciones propuestas; no representan funciones implementadas. [Matriz CSV](opentwin-exo-traceability.csv) con 17 requisitos.
