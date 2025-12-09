# Informe Final de Proyecto

## Sistema de Monitoreo de Desempeño Estudiantil

## Instituto Técnico Profesional Crecer Más

**Versión:** 1.0  
**Fecha:** 03 de diciembre de 2025

---

## Historia de Revisiones

|Fecha|Versión|Descripción|Autor|
|---|---|---|---|
|26/08/2025|0.1|Creación del Acta de Constitución del Proyecto|Ignacio Beltrán|
|15/09/2025|0.2|Ajustes iniciales en el cronograma y presupuesto|Patricio Núñez|
|20/10/2025|0.3|Implementación de cambios en requerimientos funcionales|Sebastián Bravo|
|15/11/2025|0.4|Validación de entregables del sistema de alertas|Comité de Proyecto|
|03/12/2025|1.0|Finalización del Informe Final de Proyecto|Equipo de Proyecto|

---

## Contenido

1. [Resumen Ejecutivo](#resumen-ejecutivo)
2. [Mediciones de Tamaño](#mediciones-de-tama%C3%B1o)
3. [Mediciones de Esfuerzo](#mediciones-de-esfuerzo)
4. [Estimaciones vs. Reales](#estimaciones-vs-reales)
5. [Desarrollo del Proyecto](#desarrollo-del-proyecto)
6. [Desviaciones Ocurridas](#desviaciones-ocurridas)
7. [Riesgos Ocurridos](#riesgos-ocurridos)
8. [Riesgos No Identificados](#riesgos-no-identificados)
9. [Evaluación Final](#evaluaci%C3%B3n-final)

---

## Resumen Ejecutivo

El proyecto **Sistema de Monitoreo de Desempeño Estudiantil** fue ejecutado exitosamente para el Instituto Técnico Profesional Crecer Más entre agosto y diciembre de 2025. El sistema integra información académica de SIGAA y Moodle, proporcionando herramientas de visualización, análisis predictivo con inteligencia artificial y alertas automatizadas para mejorar el seguimiento estudiantil y reducir la deserción.

### Datos Principales del Proyecto

|Aspecto|Detalle|
|---|---|
|**Duración**|16 semanas (26/08/2025 - 03/12/2025)|
|**Presupuesto**|$110.000.000 CLP|
|**Costo Final**|$108.500.000 CLP (1.4% bajo presupuesto)|
|**Estado**|Completado exitosamente|
|**Equipo**|12 profesionales|

### Resultados Destacados

- ✅ **100%** de entregables completados según especificaciones
- ✅ **87%** de precisión en predicción de deserción (objetivo: 85%)
- ✅ **86%** de satisfacción de usuarios (objetivo: 80%)
- ✅ **99.7%** de disponibilidad del sistema (objetivo: 99.5%)
- ✅ **95%** de adopción por coordinadores de carrera (objetivo: 90%)

---

## Mediciones de Tamaño

Esta sección contiene las mediciones de tamaño en LOC (Lines of Code) correspondientes a cada componente liberado, distinguiendo entre el tamaño del producto entregado y el tamaño de la implementación realizada.

### Fase de Análisis y Diseño

**Tamaño de Documentación Generada:**

- Especificación de Requisitos: 2,500 líneas
- Documentos de Diseño Técnico: 3,200 líneas
- Casos de Uso: 1,800 líneas
- **Total Documentación:** 7,500 líneas

### Fase de Desarrollo - Iteración I

**Tamaño del Producto Desarrollado:**

|Componente|LOC Desarrolladas|Descripción|
|---|---|---|
|**Dashboard de Visualización**|4,500|Interfaz principal con componentes React, gráficos y visualizaciones|
|**Backend APIs REST**|3,200|Servicios de consulta de datos académicos y reportes|
|**Sistema de Alertas**|2,800|Motor de reglas de negocio y notificaciones|
|**Integración SIGAA**|1,500|Conectores y transformadores de datos|
|**Base de Datos**|800|Scripts de creación y procedimientos almacenados|

**Tamaño Total de Implementación Iteración I:**

- Código Productivo: 12,800 LOC
- Pruebas Unitarias: 3,200 LOC (25% del código productivo)
- Documentación de Código: 1,600 LOC
- **Total Iteración I:** 17,600 LOC

### Fase de Desarrollo - Iteración II

**Tamaño del Producto Desarrollado:**

|Componente|LOC Desarrolladas|Descripción|
|---|---|---|
|**Motor de IA Predictiva**|5,200|Algoritmos ML, entrenamiento y API de predicción|
|**Dashboard de IA**|2,300|Visualización de métricas del modelo|
|**Integración Moodle**|1,800|Conectores con plataforma Moodle|
|**Sistema de Notificaciones**|2,100|Email templates y notificaciones web|
|**Middleware ETL**|1,900|Procesos de extracción, transformación y carga|

**Tamaño Total de Implementación Iteración II:**

- Código Productivo: 13,300 LOC
- Pruebas Unitarias: 3,325 LOC (25% del código productivo)
- Pruebas de Integración: 2,100 LOC
- Documentación de Código: 1,800 LOC
- **Total Iteración II:** 20,525 LOC

### Fase de Transición

**Tamaño del Producto en Transición:**

|Componente|LOC Ajustadas|Descripción|
|---|---|---|
|Scripts de Migración|1,200|Migración de datos históricos 2020-2025|
|Configuraciones de Producción|600|Archivos de configuración y despliegue|
|Scripts de Monitoreo|400|Herramientas de monitoreo operativo|
|Documentación de Usuario|3,500|Manuales y guías de usuario|

**Total Fase de Transición:** 5,700 LOC/líneas

### Resumen Total del Proyecto

|Fase|Código Productivo|Pruebas|Documentación|Total|
|---|---|---|---|---|
|Análisis y Diseño|-|-|7,500|7,500|
|Iteración I|12,800|3,200|1,600|17,600|
|Iteración II|13,300|5,425|1,800|20,525|
|Transición|2,200|-|3,500|5,700|
|**TOTAL**|**28,300**|**8,625**|**14,400**|**51,325**|

---

## Mediciones de Esfuerzo

Esta sección contiene las mediciones de esfuerzo (en horas) por fase, disciplina, rol e integrante del equipo.

### Esfuerzo por Fase del Proyecto

|Fase|Duración|Horas Totales|Promedio Semanal|
|---|---|---|---|
|**Fase Inicial**|2 semanas|320 horas|160 h/semana|
|**Fase de Elaboración**|3 semanas|480 horas|160 h/semana|
|**Fase de Construcción - Iteración I**|5 semanas|1,000 horas|200 h/semana|
|**Fase de Construcción - Iteración II**|4 semanas|960 horas|240 h/semana|
|**Fase de Transición**|2 semanas|400 horas|200 h/semana|
|**TOTAL**|**16 semanas**|**3,160 horas**|**197.5 h/semana**|

### Esfuerzo por Disciplina

|Disciplina|Fase Inicial|Elaboración|Construcción I|Construcción II|Transición|Total|%|
|---|---|---|---|---|---|---|---|
|**Gerencia de Proyecto**|80|120|200|160|80|640|20.3%|
|**Análisis de Requisitos**|120|180|120|80|40|540|17.1%|
|**Diseño y Arquitectura**|40|100|160|120|20|440|13.9%|
|**Desarrollo**|40|40|320|400|80|880|27.8%|
|**QA y Pruebas**|20|20|120|120|80|360|11.4%|
|**DevOps**|20|20|80|80|100|300|9.5%|
|**TOTAL**|**320**|**480**|**1,000**|**960**|**400**|**3,160**|**100%**|

### Esfuerzo por Rol

|Rol|Cantidad|Horas Totales|Promedio por Persona|% del Total|
|---|---|---|---|---|
|**Gerente de Proyecto**|1|640|640|20.3%|
|**Product Owner**|1|340|340|10.8%|
|**Analista de Requisitos**|2|540|270|17.1%|
|**Arquitecto de Software**|1|440|440|13.9%|
|**Desarrollador Full-Stack**|3|880|293|27.8%|
|**Ingeniero de QA**|2|360|180|11.4%|
|**Ingeniero DevOps**|1|300|300|9.5%|
|**Especialista en IA/ML**|1|280|280|8.9%|
|**TOTAL**|**12**|**3,780**|**315**|**119.7%***|

_* El porcentaje supera 100% debido a roles simultáneos de algunos miembros del equipo._

### Esfuerzo Total por Integrante del Equipo

|Nombre|Rol(es)|Horas Totales|Promedio Semanal|
|---|---|---|---|
|Ignacio Beltrán|Gerente de Proyecto|640|40|
|Patricio Núñez|Product Owner|340|21|
|Carolina Méndez|Analista de Requisitos|280|17.5|
|Ricardo Silva|Analista de Requisitos|260|16.25|
|Sebastián Bravo|Arquitecto de Software|440|27.5|
|Andrés Rojas|Desarrollador Full-Stack (Lead)|320|20|
|Fernanda López|Desarrolladora Full-Stack|280|17.5|
|Martín Vega|Desarrollador Full-Stack|280|17.5|
|Paula Contreras|Ingeniera de QA|180|11.25|
|Jorge Soto|Ingeniero de QA|180|11.25|
|Luis Herrera|Ingeniero DevOps|300|18.75|
|Daniela Campos|Especialista en IA/ML|280|17.5|

---

## Estimaciones vs. Reales

### Comparación de Tamaño

Durante la planificación del proyecto, se estimó el tamaño del desarrollo en líneas de código (LOC). A continuación, se presentan las comparaciones entre estimaciones y valores reales:

|Componente|Tamaño Estimado (LOC)|Tamaño Real (LOC)|Diferencia|Variación %|
|---|---|---|---|---|
|Dashboard de Visualización|4,000|4,500|+500|+12.5%|
|Backend APIs REST|3,000|3,200|+200|+6.7%|
|Sistema de Alertas|2,500|2,800|+300|+12.0%|
|Motor de IA Predictiva|5,000|5,200|+200|+4.0%|
|Dashboard de IA|2,000|2,300|+300|+15.0%|
|Integración SIGAA|1,400|1,500|+100|+7.1%|
|Integración Moodle|1,600|1,800|+200|+12.5%|
|Sistema de Notificaciones|2,000|2,100|+100|+5.0%|
|Middleware ETL|1,800|1,900|+100|+5.6%|
|Base de Datos y Scripts|1,000|2,000|+1,000|+100.0%|
|**TOTAL**|**24,300**|**27,300**|**+3,000**|**+12.3%**|

#### Análisis de Resultados - Tamaño

**Dashboard de Visualización (+12.5%):** El incremento se debió a la incorporación de funcionalidades adicionales solicitadas durante el desarrollo, como filtros avanzados y vistas personalizables por usuario.

**Motor de IA Predictiva (+4.0%):** Las estimaciones fueron precisas. El ligero aumento corresponde a mejoras en la optimización del modelo y validaciones adicionales.

**Base de Datos y Scripts (+100%):** Variación significativa debido a la complejidad no anticipada de los scripts de migración de datos históricos y procedimientos almacenados para optimización de consultas.

**Conclusión:** Las diferencias entre los tamaños estimados y reales fueron razonables y justificadas por mejoras en requisitos y complejidad técnica descubierta durante el desarrollo. Esto permitió entregar un producto más robusto y alineado con las expectativas.

### Comparación de Esfuerzo

|Fase|Esfuerzo Estimado (horas)|Esfuerzo Real (horas)|Diferencia|Variación %|
|---|---|---|---|---|
|Fase Inicial|300|320|+20|+6.7%|
|Elaboración|450|480|+30|+6.7%|
|Construcción I|950|1,000|+50|+5.3%|
|Construcción II|900|960|+60|+6.7%|
|Transición|400|400|0|0.0%|
|**TOTAL**|**3,000**|**3,160**|**+160**|**+5.3%**|

#### Análisis por Disciplina

|Disciplina|Esfuerzo Estimado (horas)|Esfuerzo Real (horas)|Diferencia|Variación %|
|---|---|---|---|---|
|Gerencia de Proyecto|600|640|+40|+6.7%|
|Análisis de Requisitos|500|540|+40|+8.0%|
|Diseño y Arquitectura|420|440|+20|+4.8%|
|Desarrollo|850|880|+30|+3.5%|
|QA y Pruebas|350|360|+10|+2.9%|
|DevOps|280|300|+20|+7.1%|
|**TOTAL**|**3,000**|**3,160**|**+160**|**+5.3%**|

#### Análisis de Resultados - Esfuerzo

**Elaboración (+6.7%):** La diferencia se atribuye a iteraciones adicionales en el levantamiento de requisitos y validaciones con stakeholders para asegurar claridad en el alcance.

**Construcción I y II (+5.3% y +6.7%):** Incremento moderado debido a ajustes en los módulos de dashboard y motor de IA para cumplir con requisitos de rendimiento y usabilidad identificados durante pruebas tempranas.

**Transición (0.0%):** Se logró optimizar la fase de transición gracias a una planificación detallada y capacitación anticipada del personal.

**Disciplina - Gerencia de Proyecto (+6.7%):** La supervisión constante, gestión de cambios y coordinación con múltiples stakeholders incrementaron ligeramente el esfuerzo.

**Disciplina - Desarrollo (+3.5%):** El esfuerzo adicional incluyó optimización de código y manejo de incidencias durante las pruebas de integración.

**Conclusión:** El esfuerzo real se mantuvo dentro de rangos muy aceptables respecto a las estimaciones iniciales (variación de solo 5.3%), reflejando una planificación adecuada y un manejo eficiente de los recursos. Los incrementos fueron justificados por la necesidad de adaptarse a requisitos emergentes y asegurar la calidad del producto.

---

## Desarrollo del Proyecto

### Fases e Iteraciones

#### Comparación entre la Duración Planificada y Real

|Fase / Iteración|Duración Planificada|Duración Real|Diferencia|Variación %|
|---|---|---|---|---|
|**Fase Inicial**|2 semanas|2 semanas|0|0.0%|
|**Fase de Elaboración**|3 semanas|3 semanas|0|0.0%|
|**Construcción - Iteración I**|5 semanas|5 semanas|0|0.0%|
|**Construcción - Iteración II**|4 semanas|4 semanas|0|0.0%|
|**Fase de Transición**|2 semanas|2 semanas|0|0.0%|
|**TOTAL**|**16 semanas**|**16 semanas**|**0**|**0.0%**|

#### Análisis de Resultados

**Fase Inicial:** Se completó según lo planificado. La definición clara del alcance y objetivos permitió un inicio ordenado del proyecto.

**Fase de Elaboración:** Cumplió con los plazos establecidos. Los workshops con stakeholders y la definición detallada de requisitos fueron eficientes.

**Iteraciones de Construcción I y II:** Ambas iteraciones se completaron en el tiempo planificado, beneficiándose de un equipo experimentado y una gestión ágil efectiva.

**Fase de Transición:** Se ejecutó exitosamente en el tiempo establecido gracias a una planificación detallada, migración de datos bien estructurada y capacitación anticipada del personal.

**Conclusión:** El proyecto se ejecutó exactamente según el cronograma planificado, demostrando una planificación precisa, gestión eficiente de riesgos y coordinación efectiva del equipo. No se registraron retrasos en ninguna fase del proyecto.

---

## Desviaciones Ocurridas

### Descripción de las Desviaciones y sus Causas

Durante la ejecución del proyecto, se identificaron las siguientes desviaciones con respecto a la planificación inicial:

|Actividad/Componente|Desviación|Causa Principal|Impacto|
|---|---|---|---|
|**Integración de APIs SIGAA**|Complejidad técnica adicional|El API de SIGAA tenía documentación incompleta, requiriendo ingeniería inversa|Incremento de 30 horas de desarrollo|
|**Modelo de IA - Entrenamiento**|Iteraciones adicionales de optimización|Precisión inicial del modelo era 78%, requiriendo ajustes en features y hiperparámetros|Incremento de 40 horas de trabajo del especialista IA|
|**Dashboard - UX/UI**|Ajustes de diseño solicitados|Feedback de usuarios piloto requirió mejoras en usabilidad|Incremento de 25 horas de desarrollo frontend|
|**Base de Datos - Migración**|Complejidad de datos históricos|Inconsistencias en datos históricos de SIGAA requirieron limpieza adicional|Incremento de 50 horas de ETL y validación|
|**Capacitación de Usuarios**|Mayor demanda de sesiones|Usuarios solicitaron sesiones adicionales y personalizadas|Incremento de 20 horas de capacitación|

### Análisis de las Causas

**Integración con SIGAA:** Durante el desarrollo, se identificó que la documentación del API de SIGAA era incompleta y contenía inconsistencias. Esto requirió trabajo adicional de análisis mediante ingeniería inversa y pruebas exhaustivas para garantizar la correcta integración.

**Modelo de Inteligencia Artificial:** Las pruebas iniciales del modelo predictivo mostraron una precisión del 78%, por debajo del objetivo del 85%. Se requirieron iteraciones adicionales de feature engineering, selección de variables y ajuste de hiperparámetros para alcanzar la precisión final del 87%.

**Interfaz de Usuario:** Los usuarios piloto (3 coordinadores de carrera) proporcionaron feedback valioso durante las pruebas de aceptación, solicitando ajustes en la disposición de elementos y simplificación de flujos de navegación para mejorar la experiencia de usuario.

**Migración de Datos:** Los datos históricos en SIGAA (periodo 2020-2025) presentaban inconsistencias en formatos de fechas, valores nulos no documentados y registros duplicados. Esto requirió desarrollo de scripts adicionales de limpieza y validación de datos.

### Cumplimiento de los Entregables

A pesar de estas desviaciones, todos los entregables principales se completaron satisfactoriamente, cumpliendo con los requisitos establecidos y dentro del presupuesto total aprobado. Las desviaciones representaron un incremento del 5.3% en el esfuerzo total, que fue absorbido dentro del buffer de contingencia del proyecto.

Los ajustes realizados durante el proyecto permitieron no solo mitigar los impactos, sino mejorar la calidad del producto final, resultando en una precisión del modelo de IA superior a lo planificado y una interfaz de usuario con mejor usabilidad.

---

## Riesgos Ocurridos

### Riesgos Identificados y su Gestión

Durante el proyecto, se materializaron algunos riesgos previamente identificados en el Plan de Gestión de Riesgos. A continuación se detallan los riesgos que ocurrieron y las estrategias implementadas:

|Riesgo|Probabilidad|Impacto|Descripción|Estrategia Implementada|Resultado|
|---|---|---|---|---|---|
|**Cambios en Requisitos**|Media|Alto|Solicitudes de ajustes en funcionalidades durante el desarrollo|Proceso ágil de validación de cambios con Product Owner. Cambios priorizados y evaluados|3 cambios menores aprobados sin impacto en cronograma|
|**Calidad de Datos Históricos**|Alta|Alto|Inconsistencias en datos históricos de SIGAA afectando entrenamiento del modelo|Scripts de limpieza y validación de datos. Trabajo conjunto con área académica|Migración exitosa con 98.5% de integridad de datos|
|**Disponibilidad de Usuarios Clave**|Media|Medio|Coordinadores con limitada disponibilidad para validaciones|Sesiones de validación programadas con 2 semanas de anticipación. Prototipos funcionales|Validaciones completadas sin retrasos|
|**Rendimiento del Sistema**|Baja|Alto|Consultas complejas con tiempos de respuesta elevados|Optimización de queries SQL. Implementación de caché en Redis|Tiempos de respuesta 2.1 seg (objetivo: 3 seg)|

### Gestión Detallada de Riesgos

#### 1. Cambios en los Requisitos

**Descripción:** Durante la fase de construcción, se recibieron 5 solicitudes de cambios en funcionalidades por parte de la Dirección Académica.

**Gestión Implementada:**

- Se implementó un proceso ágil de evaluación de cambios
- Comité de control de cambios (CCB) evaluó cada solicitud
- Se priorizaron cambios según valor de negocio e impacto técnico
- 3 cambios menores fueron aprobados e implementados
- 2 cambios fueron diferidos para fase de mejoras futuras

**Resultado:** Los cambios aprobados se implementaron sin impacto en el cronograma principal, gracias a la flexibilidad del enfoque ágil y a la correcta priorización.

#### 2. Calidad de Datos Históricos

**Descripción:** Durante la fase de análisis de datos para el entrenamiento del modelo de IA, se descubrieron inconsistencias significativas en los datos históricos de SIGAA (2020-2025).

**Gestión Implementada:**

- Se formó un equipo conjunto entre TI y área académica
- Se desarrollaron scripts automatizados de limpieza de datos
- Se implementó un proceso de validación con reglas de negocio
- Se documentaron las transformaciones aplicadas

**Resultado:** Se logró migrar 98.5% de los datos históricos con integridad completa. El 1.5% restante correspondía a registros inconsistentes que fueron excluidos con aprobación del área académica.

#### 3. Disponibilidad de Usuarios Clave

**Descripción:** Los coordinadores de carrera, usuarios clave para validaciones, tenían agendas muy ocupadas durante el periodo académico.

**Gestión Implementada:**

- Programación de sesiones con 2 semanas de anticipación
- Uso de prototipos funcionales para validación rápida
- Sesiones de validación de máximo 1 hora
- Documentación visual para facilitar feedback

**Resultado:** Todas las sesiones de validación se completaron sin retrasos. Los prototipos facilitaron feedback rápido y preciso.

#### 4. Rendimiento del Sistema

**Descripción:** Consultas iniciales para reportes complejos mostraban tiempos de respuesta de hasta 8 segundos, excediendo el objetivo de 3 segundos.

**Gestión Implementada:**

- Análisis de performance de queries SQL
- Optimización de índices en base de datos
- Implementación de caché con Redis para consultas frecuentes
- Paginación de resultados extensos

**Resultado:** Tiempos de respuesta reducidos a 2.1 segundos promedio, superando el objetivo establecido.

### Influencia en el Avance del Proyecto

A pesar de los riesgos materializados, las estrategias de mitigación y contingencia implementadas permitieron cumplir con los entregables clave, mantener el cronograma y completar el proyecto dentro del presupuesto con una desviación mínima del 1.4%.

La gestión proactiva de riesgos y la respuesta ágil del equipo fueron factores determinantes para el éxito del proyecto.

---

## Riesgos No Identificados

### Descripción de los Riesgos No Identificados

Durante el proyecto, surgieron algunos riesgos que no habían sido previstos en la planificación inicial. Estos fueron gestionados de manera reactiva pero efectiva:

|Riesgo|Momento de Ocurrencia|Descripción|Estrategia de Respuesta|Impacto Final|
|---|---|---|---|---|
|**Actualización de SIGAA**|Semana 10|Actualización no planificada de SIGAA cambió estructura de algunas tablas|Ajuste urgente de ETL y consultas SQL. Coordinación con proveedor de SIGAA|15 horas adicionales de desarrollo|
|**Cambio de Servidor**|Semana 13|Servidor original presentó fallas de hardware, requiriendo migración|Migración a servidor de respaldo. Reconfiguración de ambiente|20 horas de trabajo DevOps. 1 día de retraso recuperado|
|**Sobrecarga de Red**|Semana 15|Sincronización masiva de Moodle generó congestión de red|Implementación de sincronización programada en horarios de baja demanda|Sin impacto significativo. Optimización implementada|
|**Resistencia al Cambio**|Semana 14-16|Algunos docentes mostraron resistencia al uso del nuevo sistema|Sesiones de capacitación adicionales. Apoyo personalizado|20 horas de capacitación extra. Adopción final del 95%|

### Gestión Detallada de Riesgos No Identificados

#### 1. Actualización de SIGAA

**Contexto:** En la semana 10, el proveedor de SIGAA implementó una actualización de mantenimiento que modificó la estructura de algunas tablas de la base de datos sin notificación previa al instituto.

**Impacto Inicial:** El ETL dejó de funcionar correctamente, generando errores en la sincronización de datos.

**Respuesta Implementada:**

- Detección inmediata mediante monitoreo automatizado
- Análisis de cambios en la estructura de SIGAA
- Ajuste de scripts ETL y queries SQL
- Coordinación con proveedor para obtener documentación actualizada
- Implementación de validaciones adicionales para futuras actualizaciones

**Resultado:** El problema fue resuelto en 2 días. Se implementaron mecanismos de detección temprana de cambios en sistemas externos.

#### 2. Cambio de Servidor

**Contexto:** En la semana 13, el servidor físico destinado para el proyecto presentó fallas intermitentes en el subsistema de almacenamiento, poniendo en riesgo la estabilidad del sistema.

**Impacto Inicial:** Preocupación sobre cumplimiento de cronograma y disponibilidad del sistema.

**Respuesta Implementada:**

- Activación del servidor de respaldo disponible en TI
- Migración urgente de ambiente de pruebas y desarrollo
- Reconfiguración de servicios y certificados SSL
- Pruebas de estabilidad y rendimiento en nuevo servidor

**Resultado:** La migración se completó exitosamente. El nuevo servidor demostró mejor rendimiento. El retraso de 1 día fue recuperado mediante trabajo paralelo en otras actividades.

#### 3. Sobrecarga de Red

**Contexto:** Durante las pruebas de sincronización masiva con Moodle, se detectó congestión de red que afectaba otros servicios institucionales.

**Impacto Inicial:** Quejas de usuarios sobre lentitud en otros sistemas durante horarios laborales.

**Respuesta Implementada:**

- Análisis de patrones de uso de la red institucional
- Implementación de sincronización programada en horarios de baja demanda (22:00-06:00)
- Optimización de consultas para reducir transferencia de datos
- Implementación de sincronización incremental en lugar de completa

**Resultado:** Se eliminó el impacto en la red institucional. La sincronización se realiza de manera eficiente en horarios no laborales.

#### 4. Resistencia al Cambio

**Contexto:** Durante la fase de transición, algunos docentes (aproximadamente 15% del total) mostraron resistencia al uso del nuevo sistema, prefiriendo los métodos tradicionales de seguimiento estudiantil.

**Impacto Inicial:** Riesgo de baja adopción del sistema y no alcanzar el objetivo del 90%.

**Respuesta Implementada:**

- Identificación de usuarios con mayor resistencia
- Sesiones de capacitación personalizadas
- Apoyo one-on-one durante las primeras semanas
- Comunicación de beneficios tangibles y casos de éxito
- Incentivos para early adopters

**Resultado:** La adopción final alcanzó el 95%, superando el objetivo. Los docentes resistentes terminaron siendo promotores del sistema al experimentar sus beneficios.

### Influencia en el Proyecto

Estos riesgos no identificados causaron ajustes en el esfuerzo y la planificación operativa, pero fueron gestionados efectivamente sin comprometer los objetivos principales del proyecto. La capacidad de respuesta del equipo y la flexibilidad de la metodología ágil permitieron absorber estos imprevistos.

La experiencia adquirida en la gestión de estos riesgos no identificados se ha documentado en las lecciones aprendidas para futuros proyectos similares.

---

## Evaluación Final

### Resumen General del Proyecto

El proyecto **Sistema de Monitoreo de Desempeño Estudiantil** cumplió exitosamente con sus objetivos principales, entregando una plataforma integral que integra información académica de SIGAA y Moodle, proporciona análisis predictivo mediante inteligencia artificial y genera alertas tempranas para reducir la deserción estudiantil.

El sistema ha sido implementado en ambiente de producción, está operando de manera estable y ha sido aceptado formalmente por los stakeholders clave: Dirección Académica, Rectoría y Dirección de TI.

### Aspectos Positivos

#### 1. Cumplimiento de Objetivos

✅ **Todos los entregables planificados fueron completados exitosamente**

- 100% de los componentes del sistema implementados y operativos
- Todas las funcionalidades especificadas en los requisitos están operativas
- Documentación técnica y de usuario completa y entregada

✅ **Superación de objetivos cuantitativos**

- Precisión del modelo de IA: 87% (objetivo: 85%)
- Satisfacción de usuarios: 86% (objetivo: 80%)
- Adopción del sistema: 95% (objetivo: 90%)
- Disponibilidad del sistema: 99.7% (objetivo: 99.5%)
- Tiempo de respuesta: 2.1 seg (objetivo: 3 seg)

✅ **Beneficios tangibles entregados**

- Reducción del 65% en tiempo de generación de reportes académicos
- Detección temprana de 34 estudiantes en riesgo durante el primer mes
- Mejora del 40% en tiempos de respuesta a situaciones académicas críticas

#### 2. Gestión del Proyecto

✅ **Cumplimiento de plazos**

- Proyecto completado exactamente según el cronograma (16 semanas)
- Ninguna fase experimentó retrasos
- Gestión efectiva de riesgos y contingencias

✅ **Gestión eficiente de recursos**

- Desviación presupuestaria de solo -1.4% (bajo presupuesto)
- Desviación de esfuerzo de solo +5.3% (muy controlada)
- Optimización de recursos humanos y técnicos

✅ **Gestión de riesgos proactiva**

- 4 riesgos identificados gestionados exitosamente
- 4 riesgos no identificados resueltos sin impacto significativo
- Ningún riesgo crítico materializado

#### 3. Calidad del Producto

✅ **Alta calidad técnica**

- Arquitectura escalable y mantenible
- Código bien documentado (25% de cobertura de pruebas)
- Cumplimiento de estándares de seguridad y protección de datos

✅ **Experiencia de usuario excepcional**

- Interfaz intuitiva con curva de aprendizaje corta (1.5 horas)
- Feedback muy positivo de usuarios piloto
- Accesibilidad desde dispositivos móviles y de escritorio

✅ **Rendimiento superior**

- Tiempos de respuesta por debajo del objetivo
- Capacidad de usuarios concurrentes superada (250 vs 200)
- Disponibilidad superior al objetivo

#### 4. Colaboración del Equipo

✅ **Compromiso y profesionalismo**

- Alto nivel de compromiso del equipo de proyecto
- Comunicación efectiva entre áreas técnicas y stakeholders
- Resolución colaborativa de problemas

✅ **Gestión del cambio efectiva**

- 95% de adopción del sistema por usuarios finales
- Capacitación exitosa de 23 coordinadores y 45 docentes
- Transferencia de conocimiento completada

### Desafíos Encontrados

#### 1. Desafíos Técnicos

⚠️ **Integración con SIGAA**

- Documentación del API incompleta requirió ingeniería inversa
- Actualización no planificada de SIGAA durante el proyecto
- **Impacto:** 30 horas adicionales de desarrollo

⚠️ **Calidad de datos históricos**

- Inconsistencias en datos históricos de SIGAA (2020-2025)
- Requirió limpieza y validación extensiva
- **Impacto:** 50 horas adicionales de ETL

⚠️ **Optimización del modelo de IA**

- Precisión inicial del 78%, requirió iteraciones adicionales
- **Impacto:** 40 horas adicionales de optimización

#### 2. Desafíos Organizacionales

⚠️ **Resistencia al cambio**

- 15% de docentes mostró resistencia inicial al sistema
- Requirió capacitación personalizada y apoyo adicional
- **Impacto:** 20 horas de capacitación extra (superado exitosamente)

⚠️ **Disponibilidad de usuarios clave**

- Coordinadores con agendas muy ocupadas para validaciones
- Requirió planificación anticipada y uso de prototipos
- **Impacto:** Ninguno (gestionado efectivamente)

#### 3. Desafíos de Infraestructura

⚠️ **Falla de hardware del servidor**

- Servidor original presentó fallas, requirió migración
- **Impacto:** 1 día de retraso (recuperado posteriormente)

⚠️ **Congestión de red**

- Sincronización masiva con Moodle afectó otros servicios
- **Impacto:** Ninguno (implementada sincronización en horarios de baja demanda)

### Lecciones Aprendidas Principales

1. **Validación temprana de integraciones:** Las integraciones con sistemas externos (SIGAA, Moodle) requieren pruebas de concepto tempranas para identificar limitaciones de documentación.
    
2. **Calidad de datos es crítica para IA:** El modelo de IA requiere datos de alta calidad. La limpieza y validación de datos históricos debe ser una actividad planificada con tiempo suficiente.
    
3. **Gestión del cambio desde el inicio:** La resistencia al cambio debe abordarse desde las fases tempranas del proyecto, involucrando a usuarios en el diseño y validación.
    
4. **Prototipos funcionales aceleran validación:** Los prototipos funcionales son más efectivos que documentos para obtener feedback de usuarios.
    
5. **Monitoreo proactivo previene problemas:** El monitoreo automatizado de integraciones permitió detectar y resolver problemas rápidamente.
    
6. **Flexibilidad en metodología ágil:** El enfoque ágil permitió absorber cambios y riesgos no identificados sin comprometer el cronograma.
    

### Recomendaciones para Proyectos Futuros

#### 1. Planificación

📋 **Integración con sistemas externos:**

- Realizar pruebas de concepto (POC) de integraciones críticas antes de iniciar el proyecto
- Solicitar acceso a ambientes de sandbox de proveedores
- Documentar detalladamente las APIs y sus limitaciones
- Establecer canales de comunicación directa con proveedores

📋 **Gestión de datos:**

- Incluir fase explícita de análisis y limpieza de datos históricos
- Asignar recursos específicos para data quality
- Establecer reglas de validación desde el inicio

📋 **Gestión del cambio:**

- Elaborar plan de gestión del cambio desde la fase de planificación
- Identificar early adopters y champions del cambio
- Incluir tiempo para sesiones de capacitación personalizadas

#### 2. Ejecución

🔧 **Desarrollo ágil:**

- Continuar con sprints cortos (2 semanas) para feedback rápido
- Usar prototipos funcionales para validación temprana
- Implementar entregas incrementales para reducir riesgos

🔧 **Calidad:**

- Mantener cobertura de pruebas mínima del 25%
- Implementar integración continua (CI/CD) desde el inicio
- Realizar code reviews obligatorios

🔧 **Comunicación:**

- Mantener reuniones semanales con stakeholders clave
- Usar dashboards visuales para reportar avance
- Documentar decisiones importantes en actas

#### 3. Cierre y Transición

🎯 **Soporte post-implementación:**

- Establecer periodo de hipercare (soporte intensivo) de 1 mes
- Asignar recursos dedicados para soporte durante primeras semanas
- Crear base de conocimiento con FAQs y solución de problemas comunes

🎯 **Mejora continua:**

- Programar revisiones post-implementación a los 3, 6 y 12 meses
- Recopilar feedback continuo de usuarios
- Planificar roadmap de mejoras futuras

### Conclusión Final

El proyecto **Sistema de Monitoreo de Desempeño Estudiantil** se considera un **éxito total** en términos de alcance, calidad, tiempo, costo y satisfacción del cliente.

**Logros destacados:**

- ✅ 100% de entregables completados
- ✅ 0% de desviación en cronograma
- ✅ -1.4% de desviación presupuestaria (bajo presupuesto)
- ✅ Superación de todos los objetivos cuantitativos clave
- ✅ 86% de satisfacción de usuarios
- ✅ 95% de adopción del sistema

El sistema está operativo, estable y generando valor tangible para el Instituto Técnico Profesional Crecer Más. La detección temprana de estudiantes en riesgo durante el primer mes de operación (34 casos) demuestra que el sistema está cumpliendo su objetivo principal de reducir la deserción estudiantil.

Las lecciones aprendidas durante este proyecto proporcionan una base sólida para la mejora continua en futuros proyectos de transformación digital en la organización. El éxito de este proyecto posiciona al instituto para continuar con los otros tres módulos de la iniciativa de "Transformación Digital Crecer Más".

---

**Documento elaborado por:** Equipo de Proyecto - Sistema de Monitoreo de Desempeño Estudiantil  
**Gerente de Proyecto:** Ignacio Beltrán, Director de Proyectos  
**Fecha de elaboración:** 03 de diciembre de 2025  
**Versión:** 1.0  
**Estado:** APROBADO

---

_Instituto Técnico Profesional Crecer Más_  
_Subdirección de Diseño Instruccional_  
_2025_