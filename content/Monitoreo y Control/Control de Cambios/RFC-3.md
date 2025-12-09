# Formulario de Requerimiento de Cambio (RFC)

**RFC N°:** 003-2025  
**Estado:** APROBADO  
**Tipo de Cambio:** Estándar

---

## 1. INFORMACIÓN DEL SOLICITANTE

|Campo|Valor|
|---|---|
|Nombre|Claudia Moreno Soto|
|Área/Entidad|Administración de Bases de Datos|
|Teléfono|+56 2 2456 7890|

|Campo|Valor|
|---|---|
|Asignado a|Sebastián Torres|
|Cargo|DBA Senior Oracle|
|Correo electrónico|sebastian.torres@empresa.cl|

---

## 2. INFORMACIÓN DE MONITOREO

|Detalle de Suspensión de Monitoreo|Fecha y Hora de Inicio|Fecha y Hora de Término|¿Se debe suspender monitoreo?|
|---|---|---|---|
|Servidor: DB-CRM-PROD-01<br>Base de Datos: CRMDB<br>IP: 10.50.20.15|23:00:00|01:30:00|☑ SI ☐ NO|

---

## 3. INFORMACIÓN DE RESPALDO

|Fecha y Hora de Inicio|Fecha y Hora de Término|¿Se debe suspender el respaldo?|
|---|---|---|
|22:00:00|02:00:00|☐ SI ☑ NO|

**Nota:** Se mantendrá el respaldo programado regular para asegurar punto de recuperación antes del cambio.

---

## 4. INFORMACIÓN DE CMDB

|Detalle de Modificación CMDB|Acción|
|---|---|
|Actualizar parámetros de configuración de Oracle Database 19c<br>Modificar: tablespaces, índices, estadísticas, políticas de particionamiento<br>Actualizar documentación técnica y diagramas de capacidad|☑ MODIFICA ☐ ELIMINA ☐ CREA|

---

## 5. INFORMACIÓN GENERAL DEL CAMBIO

### Datos Básicos

|Cliente|Código del Cambio|Fecha de Requerimiento|Elementos de Configuración Afectados (CI)|
|---|---|---|---|
|Área Comercial (CRM)|CHG-2025-003|01/11/2025|DB-CRM-PROD-01, CRMDB (Oracle 19c)|

### Programación

|Fecha Ejecución de Actividades|Hora Ejecución|Tiempo Estimado (horas)|¿Genera Indisponibilidad?|
|---|---|---|---|
|27/11/2025|23:00|2.5 horas (incluye Rollback)|☑ SI ☐ NO|

**Nota sobre Indisponibilidad:** Solo para usuarios CRM. Otros sistemas no afectados. Ventana de mantenimiento en horario de bajo uso (23:00 - 01:30 hrs).

### Líneas de Servicio y Productos Afectados

|Línea de Servicio (señale con X)|Producto Afectado|
|---|---|
|Centro de Datos|Base de Datos Oracle 19c - CRMDB|
|Redes / Telecomunicaciones||
|CCC / Mesa De Ayuda||
|☑ Soporte Aplicaciones|Sistema CRM (Salesforce conectado a Oracle)|
|Soporte Infraestructura|Servidor DB-CRM-PROD-01|
|Otro||

### Urgencia del Cambio

|Baja|Media|Alta|Crítica|
|---|---|---|---|
|☑|☐|☐|☐|

**Justificación de Urgencia:** Cambio de mantenimiento preventivo para optimización de rendimiento. No hay incidentes críticos activos. Programado en ventana estándar de mantenimiento mensual.

### Antecedentes del Cambio

**¿Por qué se requiere?**

La base de datos del CRM ha presentado degradación gradual de rendimiento en los últimos 3 meses según análisis de métricas:

1. **Degradación de Performance**:
    
    - Tiempo de respuesta de consultas incrementado en 35% (de 1.2s a 1.62s promedio)
    - Queries complejas de reportes tardando hasta 45 segundos (objetivo: <15s)
    - Índices fragmentados afectando búsquedas de clientes
2. **Crecimiento de Datos**:
    
    - Base de datos creció de 850 GB a 1.2 TB en últimos 6 meses
    - Tablas históricas sin particionamiento adecuado
    - 3.5 millones de registros nuevos por mes
3. **Análisis de AWR Reports**:
    
    - Top Wait Events: db file sequential read (28% del tiempo)
    - Buffer cache hit ratio: 89% (objetivo: >95%)
    - Estadísticas desactualizadas en 45 tablas críticas
    - 23 índices con >30% de fragmentación
4. **Planificación de Crecimiento**:
    
    - Proyección: llegada a 2 TB en próximos 8 meses
    - Necesidad de implementar estrategia de archivado
    - Optimización de espacio para evitar expansión prematura de storage
5. **Quejas de Usuarios**:
    
    - Equipo comercial reporta lentitud en búsqueda de clientes (tickets: #12453, #12567, #12789)
    - Reportes gerenciales demorando excesivamente
    - Timeouts ocasionales en operaciones de actualización masiva

### Beneficios del Cambio

**Beneficios o consecuencias de no realizarlo:**

**BENEFICIOS:**

- Mejora de 40-50% en tiempo de respuesta de consultas (objetivo: <1s promedio)
- Reducción de uso de espacio en 15-20% mediante reorganización
- Actualización de estadísticas mejorará planes de ejecución del optimizador
- Particionamiento de tablas facilitará mantenimiento futuro y archivado
- Mejor experiencia de usuario para equipo comercial (250 usuarios)
- Liberación de espacio en storage (ahorro estimado: no requerir expansión por 12 meses)
- Base para implementar estrategia de archivado en 2026

**CONSECUENCIAS DE NO REALIZAR:**

- Continuará degradación de performance (proyección: +20% adicional en 3 meses)
- Aumento de quejas de usuarios y frustración del equipo comercial
- Posible pérdida de productividad (tiempo perdido en esperas)
- Necesidad de expansión prematura de storage ($8.000.000 aproximadamente)
- Riesgo de incidentes de performance en períodos críticos (cierre de mes, campañas)
- Dificultad creciente para implementar optimizaciones (mayor tamaño = mayor complejidad)

---

## 6. PLANES ASOCIADOS AL CAMBIO

### Plan de Implementación

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Verificar backup full de la base de datos|22:30|27/11/2025 22:45|Claudia Moreno|+56 9 8901 2345|
|Exportar estadísticas actuales del optimizador|22:45|27/11/2025 22:55|Sebastián Torres|+56 9 7890 1234|
|Detener aplicación CRM y cerrar conexiones|23:00|27/11/2025 23:05|Paula Jiménez|+56 9 6789 0123|
|Ejecutar script de análisis y rebuild de índices|23:05|27/11/2025 23:50|Sebastián Torres|+56 9 7890 1234|
|Reorganizar tablespaces y coalesce|23:50|28/11/2025 00:10|Claudia Moreno|+56 9 8901 2345|
|Implementar particionamiento en 5 tablas grandes|00:10|28/11/2025 00:40|Sebastián Torres|+56 9 7890 1234|
|Actualizar estadísticas del optimizador|00:40|28/11/2025 01:00|Claudia Moreno|+56 9 8901 2345|
|Ajustar parámetros de SGA y PGA|01:00|28/11/2025 01:05|Sebastián Torres|+56 9 7890 1234|
|Reiniciar instancia de base de datos|01:05|28/11/2025 01:10|Claudia Moreno|+56 9 8901 2345|

### Plan de Pruebas

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Verificar conectividad y apertura de BD|01:10|28/11/2025 01:15|Sebastián Torres|+56 9 7890 1234|
|Validar integridad de datos (checksum tablas)|01:15|28/11/2025 01:25|Claudia Moreno|+56 9 8901 2345|
|Ejecutar suite de 20 queries críticas y medir tiempos|01:25|28/11/2025 01:40|Sebastián Torres|+56 9 7890 1234|
|Probar conexión desde aplicación CRM|01:40|28/11/2025 01:45|Paula Jiménez|+56 9 6789 0123|
|Validar operaciones CRUD en interfaz CRM|01:45|28/11/2025 01:55|Laura Vega|+56 9 5678 9012|
|Verificar generación de reportes estándar|01:55|28/11/2025 02:05|Laura Vega|+56 9 5678 9012|
|Revisar alertlog y trace files por errores|02:05|28/11/2025 02:10|Claudia Moreno|+56 9 8901 2345|

### Plan de Respaldo (Rollback)

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Detener operaciones y declarar rollback|Según necesidad|+5 minutos|Claudia Moreno|+56 9 8901 2345|
|Apagar instancia de base de datos|Según necesidad|+3 minutos|Sebastián Torres|+56 9 7890 1234|
|Restaurar backup RMAN full|Según necesidad|+45 minutos|Claudia Moreno|+56 9 8901 2345|
|Recuperar database hasta momento pre-cambio|Según necesidad|+20 minutos|Sebastián Torres|+56 9 7890 1234|
|Restaurar estadísticas del optimizador|Según necesidad|+10 minutos|Claudia Moreno|+56 9 8901 2345|
|Validar integridad y abrir base de datos|Según necesidad|+10 minutos|Sebastián Torres|+56 9 7890 1234|
|Reiniciar aplicación CRM y validar|Según necesidad|+10 minutos|Paula Jiménez|+56 9 6789 0123|

**Tiempo Total de Rollback Estimado:** 103 minutos (~1h 45min)

**Criterios para Activar Rollback:**

- Más de 10% de queries críticas con tiempo >15 segundos
- Errores de integridad en validación de datos
- Imposibilidad de completar particionamiento en tiempo estimado
- Cualquier error ORA- crítico en alertlog

---

## 7. COMUNICACIONES

### Comunicación Antes del Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Usuarios CRM (250 personas)|20/11/2025 14:00|Anuncio de mantenimiento programado - mejoras de rendimiento|
|Teams|Gerentes Comerciales|25/11/2025 11:00|Reunión breve explicando beneficios del cambio|
|Email Recordatorio|Usuarios CRM|27/11/2025 17:00|Recordatorio: sistema no disponible 23:00-01:30 hrs|
|Banner en CRM|Todos los usuarios activos|27/11/2025 18:00|Mensaje en sistema durante las últimas 5 horas|

### Comunicación Durante el Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Teams - Canal DBA|Equipo técnico (5 personas)|Continuo|Coordinación técnica|
|WhatsApp|Gerente Comercial|Cada hito|Actualizaciones de progreso|
|Email|Jefe de TI|Al inicio y al final|Notificación de inicio y cierre|

### Comunicación Después del Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Usuarios CRM|28/11/2025 02:15|Sistema disponible - Mejoras implementadas exitosamente|
|Teams|Gerentes Comerciales|28/11/2025 09:00|Resumen de mejoras y métricas de performance|
|Portal Intranet TI|Todos|28/11/2025 10:00|Nota técnica sobre optimizaciones realizadas|
|Email a Comité|Comité de Cambios|29/11/2025 11:00|Reporte post-implementación con métricas|

---

## 8. APROBACIONES

|Rol|Nombre|Firma|Fecha|
|---|---|---|---|
|Solicitante|Claudia Moreno Soto|___________________|01/11/2025|
|Jefe de DBA|Ricardo Valdivia|___________________|04/11/2025|
|Jefe de Desarrollo CRM|Paula Jiménez|___________________|05/11/2025|
|Gerente Comercial|Andrés Muñoz|___________________|06/11/2025|
|Gerente de TI|Fernando Castillo|___________________|07/11/2025|
|Comité de Cambios|CAB - Sesión 46/2025|___________________|08/11/2025|

**Decisión del CAB:** APROBADO  
**Condiciones:**

- Realizar prueba completa del proceso en ambiente de desarrollo
- Validar tiempos de rollback en laboratorio
- Coordinar con usuarios clave para validación post-cambio
- Documentar mejoras de performance para justificar futuras optimizaciones

---

## 9. EJECUCIÓN Y CIERRE

### Resultado de la Implementación

|Estado|Fecha/Hora Inicio|Fecha/Hora Fin|Observaciones|
|---|---|---|---|
|☑ Exitoso ☐ Fallido ☐ Parcial|27/11/2025 23:00|28/11/2025 02:10|Optimización completada exitosamente. Todas las pruebas superaron objetivos. Mejoras de performance superiores a lo estimado.|

**Desviaciones del Plan:**

- Rebuild de índices tomó 5 minutos adicionales (índice CUST_NAME_IDX más fragmentado de lo previsto)
- Particionamiento de tabla ORDER_HISTORY completado en 20 minutos (10 min menos que estimado)
- Pruebas extendidas 15 minutos para validación exhaustiva de todas las funcionalidades
- Tiempo total: 3h 10min (40 minutos más de lo estimado, principalmente por pruebas exhaustivas)

**Métricas de Performance - Antes vs Después:**

|Métrica|Antes|Después|Mejora|
|---|---|---|---|
|Tiempo promedio de consultas|1.62 s|0.85 s|47.5% ↓|
|Query más lenta (reporte mensual)|45 s|12 s|73.3% ↓|
|Buffer cache hit ratio|89%|96.5%|7.5 pp ↑|
|Espacio utilizado|1.2 TB|1.01 TB|190 GB liberados|
|Índices fragmentados|23|0|100% ↓|
|CPU usage promedio|68%|52%|16 pp ↓|

### Lecciones Aprendidas

**Aspectos Positivos:**

- Planificación detallada permitió ejecución sin contratiempos mayores
- Scripts de automatización funcionaron perfectamente (inversión en preparación valió la pena)
- Coordinación con equipo de aplicaciones fue excelente
- Backup y estrategia de rollback bien definidos generaron confianza
- Mejoras de performance superaron expectativas (47.5% vs 40% estimado)
- Usuarios notaron mejora inmediatamente en primer uso del día siguiente

**Aspectos Técnicos Destacables:**

- Particionamiento por fecha en tablas históricas resultó muy efectivo
- Reorganización de tablespaces liberó más espacio del esperado (190 GB vs 150 GB)
- Nuevas estadísticas mejoraron drásticamente los planes de ejecución
- Ajustes de SGA/PGA tuvieron impacto positivo inmediato

**Oportunidades de Mejora:**

- Considerar 15 minutos adicionales para rebuild de índices en futuras optimizaciones
- Automatizar recolección de métricas "antes/después" para comparaciones más precisas
- Implementar monitoreo proactivo de fragmentación de índices (alerta en 20%)
- Crear playbook más detallado para particionamiento de tablas

**Recomendaciones para el Futuro:**

- Realizar este tipo de optimización cada 6 meses (calendario: mayo y noviembre)
- Implementar archivado de datos históricos >3 años para siguiente ventana
- Considerar upgrade a Oracle 21c en Q2 2026 (mejoras de performance adicionales)
- Establecer política de mantenimiento preventivo automático semanal
- Capacitar a equipo de desarrollo en queries optimizadas para reducir impacto futuro

**Feedback de Usuarios (primeros 3 días):**

- 15 emails de agradecimiento por mejora de velocidad
- Equipo comercial reporta reducción de 40% en tiempo de búsqueda de clientes
- Reportes gerenciales generándose en tiempo aceptable
- Cero incidentes relacionados con performance
- NPS de satisfacción con CRM subió de 7.2 a 8.5

**Próximos Pasos:**

- Monitorear performance durante 2 semanas para confirmar estabilidad
- Generar reportes semanales de métricas clave
- Planificar fase 2: archivado de datos históricos (Q1 2026)
- Documentar lecciones aprendidas en base de conocimiento
- Presentar resultados a gerencia para justificar optimizaciones periódicas

**Fecha de Cierre:** 30/11/2025  
**Cerrado por:** Claudia Moreno Soto - Administración de Bases de Datos  
**Aprobación de Cierre:** Ricardo Valdivia - Jefe de DBA

**Nota Final:** Este cambio es un ejemplo de mantenimiento preventivo bien planificado que resultó en mejoras significativas para el negocio. Se recomienda como caso de estudio para futuras optimizaciones de bases de datos.