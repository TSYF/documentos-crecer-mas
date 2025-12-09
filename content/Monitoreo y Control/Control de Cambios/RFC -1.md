# Formulario de Requerimiento de Cambio (RFC)

**RFC N°:** 001-2025  
**Estado:** PENDIENTE DE APROBACIÓN  
**Tipo de Cambio:** Normal

---

## 1. INFORMACIÓN DEL SOLICITANTE

|Campo|Valor|
|---|---|
|Nombre|María González Rodríguez|
|Área/Entidad|Dirección de Sistemas ERP|
|Teléfono|+56 2 2345 6789|

|Campo|Valor|
|---|---|
|Asignado a|Carlos Mendoza|
|Cargo|Especialista ERP Senior|
|Correo electrónico|carlos.mendoza@empresa.cl|

---

## 2. INFORMACIÓN DE MONITOREO

|Detalle de Suspensión de Monitoreo|Fecha y Hora de Inicio|Fecha y Hora de Término|¿Se debe suspender monitoreo?|
|---|---|---|---|
|Servidores: ERP-PROD-01, ERP-PROD-02, ERP-APP-01<br>IPs: 10.20.30.45, 10.20.30.46, 10.20.30.47|22:00:00|02:00:00|☑ SI ☐ NO|

---

## 3. INFORMACIÓN DE RESPALDO

|Fecha y Hora de Inicio|Fecha y Hora de Término|¿Se debe suspender el respaldo?|
|---|---|---|
|21:30:00|02:30:00|☑ SI ☐ NO|

---

## 4. INFORMACIÓN DE CMDB

|Detalle de Modificación CMDB|Acción|
|---|---|
|Actualizar versión de software SAP ERP de 6.0 EHP7 a 6.0 EHP8<br>Modificar dependencias de módulos FI, CO, MM|☑ MODIFICA ☐ ELIMINA ☐ CREA|

---

## 5. INFORMACIÓN GENERAL DEL CAMBIO

### Datos Básicos

|Cliente|Código del Cambio|Fecha de Requerimiento|Elementos de Configuración Afectados (CI)|
|---|---|---|---|
|Área Financiera y Operaciones|CHG-2025-001|15/11/2025|ERP-PROD-01, ERP-PROD-02, ERP-APP-01, ERP-DB-01|

### Programación

|Fecha Ejecución de Actividades|Hora Ejecución|Tiempo Estimado (horas)|¿Genera Indisponibilidad?|
|---|---|---|---|
|23/11/2025|22:00|4 horas (incluye Rollback)|☑ SI ☐ NO|

### Líneas de Servicio y Productos Afectados

|Línea de Servicio (señale con X)|Producto Afectado|
|---|---|
|Centro de Datos|SAP ERP - Módulos FI, CO, MM, SD|
|Redes / Telecomunicaciones||
|CCC / Mesa De Ayuda||
|☑ Soporte Aplicaciones|Sistema de Gestión Empresarial|
|Soporte Infraestructura||
|Otro||

### Urgencia del Cambio

|Baja|Media|Alta|Crítica|
|---|---|---|---|
|☐|☑|☐|☐|

**Justificación de Urgencia:** El cambio debe realizarse en noviembre para cumplir con nuevas normativas fiscales que entran en vigor en enero 2026. La ventana de pruebas requiere implementación antes de diciembre.

### Antecedentes del Cambio

**¿Por qué se requiere?**

La actualización del sistema ERP de SAP 6.0 EHP7 a EHP8 es necesaria por las siguientes razones:

1. **Cumplimiento Normativo**: Nuevas regulaciones fiscales chilenas (DTE 2.0) requieren funcionalidades solo disponibles en EHP8
2. **Soporte del Fabricante**: SAP descontinuará soporte para EHP7 en marzo 2026
3. **Mejoras de Seguridad**: EHP8 incluye parches críticos de seguridad y correcciones de vulnerabilidades
4. **Optimización de Rendimiento**: Mejoras en procesamiento de órdenes de compra (30% más rápido según pruebas de laboratorio)
5. **Nuevas Funcionalidades**: Integración mejorada con plataforma de BI y herramientas analíticas

### Beneficios del Cambio

**Beneficios o consecuencias de no realizarlo:**

**BENEFICIOS:**

- Cumplimiento con normativas legales vigentes a partir de enero 2026
- Mantenimiento del soporte técnico del fabricante
- Mejora en tiempos de respuesta del sistema (reducción estimada del 30%)
- Mayor seguridad informática con últimos parches de seguridad
- Habilitación de nuevas capacidades de reporting y analytics

**CONSECUENCIAS DE NO REALIZAR:**

- Incumplimiento legal con posibles multas (hasta $50 millones según SII)
- Pérdida de soporte técnico oficial de SAP
- Exposición a vulnerabilidades de seguridad conocidas
- Imposibilidad de integrar nuevas herramientas de negocio
- Degradación progresiva del rendimiento del sistema

---

## 6. PLANES ASOCIADOS AL CAMBIO

### Plan de Implementación

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Detener servicios de aplicación y notificar usuarios|22:00|23/11/2025 22:15|Carlos Mendoza|+56 9 8765 4321|
|Backup completo de base de datos SAP|22:15|23/11/2025 23:00|Ricardo Silva|+56 9 7654 3210|
|Aplicar upgrade a EHP8 en servidor de aplicaciones|23:00|24/11/2025 00:30|Carlos Mendoza|+56 9 8765 4321|
|Actualizar base de datos y esquemas|00:30|24/11/2025 01:15|Ricardo Silva|+56 9 7654 3210|
|Configurar nuevos parámetros y customizing|01:15|24/11/2025 01:45|María González|+56 9 6543 2109|
|Reiniciar servicios y validar conectividad|01:45|24/11/2025 02:00|Carlos Mendoza|+56 9 8765 4321|

### Plan de Pruebas

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Verificar acceso de usuarios al sistema|02:00|24/11/2025 02:15|Andrea Rojas|+56 9 5432 1098|
|Validar transacciones críticas (FI, CO, MM)|02:15|24/11/2025 02:45|Luis Parra|+56 9 4321 0987|
|Comprobar interfaces con sistemas externos|02:45|24/11/2025 03:15|Fernando Torres|+56 9 3210 9876|
|Validar reportes fiscales y contables|03:15|24/11/2025 03:45|Patricia Morales|+56 9 2109 8765|

### Plan de Respaldo (Rollback)

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Detener servicios ERP|Según necesidad|+15 minutos|Carlos Mendoza|+56 9 8765 4321|
|Restaurar backup de base de datos|Según necesidad|+45 minutos|Ricardo Silva|+56 9 7654 3210|
|Revertir binarios a versión EHP7|Según necesidad|+30 minutos|Carlos Mendoza|+56 9 8765 4321|
|Reiniciar y validar sistema en versión anterior|Según necesidad|+20 minutos|Andrea Rojas|+56 9 5432 1098|

**Tiempo Total de Rollback Estimado:** 110 minutos (1h 50min)

---

## 7. COMUNICACIONES

### Comunicación Antes del Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Todos los usuarios SAP|16/11/2025 09:00|Notificación de ventana de mantenimiento programado|
|Portal Intranet|Toda la organización|16/11/2025 09:00|Publicación de aviso en home|
|Email Recordatorio|Gerentes de Área|22/11/2025 16:00|Recordatorio final de indisponibilidad del sistema|
|SMS|Usuarios críticos (50 personas)|23/11/2025 21:30|Aviso 30 minutos antes del inicio|

### Comunicación Durante el Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Comité de Cambios|23/11/2025 22:00|Inicio de actividades de cambio|
|WhatsApp Business|Gerentes de TI|Cada hito|Actualizaciones de progreso|
|Portal Status|Todos|Tiempo real|Dashboard con estado del cambio|

### Comunicación Después del Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Todos los usuarios SAP|24/11/2025 04:00|Sistema nuevamente disponible - Cambio exitoso|
|Email Detallado|Comité de Cambios|25/11/2025 10:00|Reporte detallado de ejecución|
|Portal Intranet|Toda la organización|24/11/2025 08:00|Confirmación de finalización|

---

## 8. APROBACIONES

|Rol|Nombre|Firma|Fecha|
|---|---|---|---|
|Solicitante|María González Rodríguez|___________________|15/11/2025|
|Jefe de Área|Roberto Sánchez|___________________|16/11/2025|
|Gerente de TI|Alejandra Vargas|___________________|17/11/2025|
|Comité de Cambios|CAB - Sesión 45/2025|___________________|18/11/2025|

**Decisión del CAB:** APROBADO con condiciones  
**Condiciones:**

- Realizar prueba completa en ambiente de QA antes del cambio
- Mantener equipo de rollback disponible durante 24 horas post-implementación
- Validación de usuarios clave antes de comunicar apertura general

---

## 9. EJECUCIÓN Y CIERRE

### Resultado de la Implementación

|Estado|Fecha/Hora Inicio|Fecha/Hora Fin|Observaciones|
|---|---|---|---|
|☑ Exitoso ☐ Fallido ☐ Parcial|23/11/2025 22:00|24/11/2025 03:45|Implementación completada según plan. Todas las pruebas exitosas. Sistema en producción desde las 04:00 hrs.|

**Desviaciones del Plan:**

- La actualización de base de datos tomó 10 minutos adicionales debido a mayor volumen de datos
- Se requirió reinicio adicional del servidor de aplicaciones por caché
- Tiempo total: 5h 45min (45 minutos más que lo estimado)

### Lecciones Aprendidas

**Aspectos Positivos:**

- Excelente coordinación entre equipos de Base de Datos y Aplicaciones
- Plan de comunicaciones efectivo, sin consultas de usuarios durante la ventana
- Backups verificados previos permitieron confianza en el proceso
- Documentación técnica actualizada facilitó la implementación

**Oportunidades de Mejora:**

- Considerar mayor tiempo para actualización de BD en futuros upgrades (volumen de datos creciente)
- Implementar script automatizado para limpieza de caché post-upgrade
- Realizar simulacro completo de rollback en ambiente de pruebas
- Mejorar monitoreo en tiempo real durante la ventana de cambio

**Recomendaciones para Próximos Cambios:**

- Agregar 1 hora adicional al tiempo estimado para upgrades de esta magnitud
- Incluir paso de limpieza de caché en procedimiento estándar
- Documentar configuración específica de parámetros de EHP8 para referencia futura

**Fecha de Cierre:** 25/11/2025  
**Cerrado por:** María González Rodríguez - Dirección de Sistemas ERP