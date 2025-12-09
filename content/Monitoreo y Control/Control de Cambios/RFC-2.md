# Formulario de Requerimiento de Cambio (RFC)

**RFC N°:** 002-2025  
**Estado:** APROBADO - EN EJECUCIÓN  
**Tipo de Cambio:** Urgente

---

## 1. INFORMACIÓN DEL SOLICITANTE

|Campo|Valor|
|---|---|
|Nombre|Jorge Hernández López|
|Área/Entidad|Infraestructura de Redes|
|Teléfono|+56 2 2987 6543|

|Campo|Valor|
|---|---|
|Asignado a|Daniela Pérez|
|Cargo|Ingeniero de Redes Senior|
|Correo electrónico|daniela.perez@empresa.cl|

---

## 2. INFORMACIÓN DE MONITOREO

|Detalle de Suspensión de Monitoreo|Fecha y Hora de Inicio|Fecha y Hora de Término|¿Se debe suspender monitoreo?|
|---|---|---|---|
|Switch Core Principal: SW-CORE-DC1<br>VLANs: 10, 20, 30, 40, 50, 100, 200<br>IPs: 10.10.1.1, 10.10.1.2 (HSRP)|02:00:00|06:00:00|☑ SI ☐ NO|

---

## 3. INFORMACIÓN DE RESPALDO

|Fecha y Hora de Inicio|Fecha y Hora de Término|¿Se debe suspender el respaldo?|
|---|---|---|
|01:00:00|07:00:00|☑ SI ☐ NO|

---

## 4. INFORMACIÓN DE CMDB

|Detalle de Modificación CMDB|Acción|
|---|---|
|Eliminar: Cisco Catalyst 6509-E (Serial: FXS1234ABCD)<br>Crear: Cisco Nexus 9500 (Serial: FDO2567WXYZ)<br>Modificar: Configuraciones de routing, VLANs, ACLs|☑ MODIFICA ☑ ELIMINA ☑ CREA|

---

## 5. INFORMACIÓN GENERAL DEL CAMBIO

### Datos Básicos

|Cliente|Código del Cambio|Fecha de Requerimiento|Elementos de Configuración Afectados (CI)|
|---|---|---|---|
|Toda la Organización|CHG-2025-002|10/11/2025|SW-CORE-DC1, FW-PERIMETRAL-01, RTR-WAN-01, SW-DIST-01 a SW-DIST-08|

### Programación

|Fecha Ejecución de Actividades|Hora Ejecución|Tiempo Estimado (horas)|¿Genera Indisponibilidad?|
|---|---|---|---|
|20/11/2025|02:00|4 horas (incluye Rollback)|☑ SI ☐ NO|

### Líneas de Servicio y Productos Afectados

|Línea de Servicio (señale con X)|Producto Afectado|
|---|---|
|☑ Centro de Datos|Toda la infraestructura de red del DC principal|
|☑ Redes / Telecomunicaciones|Conectividad LAN, WAN, Internet, VPN|
|☑ CCC / Mesa De Ayuda|Sistema de ticketing, telefonía IP|
|☑ Soporte Aplicaciones|Todas las aplicaciones corporativas|
|☑ Soporte Infraestructura|Servidores, almacenamiento, virtualización|
|Otro||

### Urgencia del Cambio

|Baja|Media|Alta|Crítica|
|---|---|---|---|
|☐|☐|☑|☐|

**Justificación de Urgencia:** El switch core actual presenta fallas intermitentes en módulo de supervisión identificadas en los últimos 7 días. Riesgo alto de falla completa que afectaría a toda la organización (2.500 usuarios). Equipo de reemplazo ya disponible en sitio.

### Antecedentes del Cambio

**¿Por qué se requiere?**

El switch core Cisco Catalyst 6509-E instalado en 2012 presenta los siguientes problemas críticos:

1. **Fallas Intermitentes**: Reinicios espontáneos del módulo de supervisión detectados en últimas 2 semanas (eventos: 12/11, 14/11, 17/11)
2. **Fin de Vida del Equipo**: EOL (End of Life) declarado por Cisco en 2020, sin soporte de software desde 2022
3. **Capacidad Insuficiente**: Actual throughput de 720 Gbps vs. requerimiento de 1.2 Tbps para nuevos servicios cloud
4. **Seguridad**: No soporta últimas funcionalidades de segmentación de red (TrustSec, MACsec)
5. **Consumo Energético**: Consume 4.8 KW vs. 2.1 KW del equipo nuevo (ahorro anual: $2.800.000)

**Análisis de Riesgo:**

- Probabilidad de falla completa en próximos 30 días: 70% (según RCA de eventos recientes)
- Impacto de falla sin planificación: Indisponibilidad total de 8-12 horas en horario laboral
- Impacto financiero de falla no planificada: $180.000.000 (pérdidas operacionales)

### Beneficios del Cambio

**Beneficios o consecuencias de no realizarlo:**

**BENEFICIOS:**

- Eliminación de riesgo de falla catastrófica del switch core
- Incremento de capacidad de 720 Gbps a 3.2 Tbps (340% más capacidad)
- Reducción de latencia en 40% (de 1.2ms a 0.7ms promedio)
- Soporte para tecnologías modernas: SDN, automation, telemetry
- Reducción de consumo energético en 56% (ahorro anual estimado: $2.800.000)
- Soporte técnico del fabricante por 5 años
- Mejora en seguridad: soporte para MACsec, TrustSec, y micro-segmentación

**CONSECUENCIAS DE NO REALIZAR:**

- Riesgo inminente (70%) de falla total sin planificación en horario laboral
- Indisponibilidad de 8-12 horas afectando a 2.500 usuarios
- Pérdidas operacionales estimadas: $180 millones (ventas, producción, servicios)
- Imposibilidad de implementar nuevos proyectos de transformación digital
- Costos crecientes de mantenimiento de equipo legacy
- Exposición a vulnerabilidades sin parches disponibles

---

## 6. PLANES ASOCIADOS AL CAMBIO

### Plan de Implementación

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Verificar backup de configuraciones actuales|01:30|20/11/2025 01:45|Jorge Hernández|+56 9 7890 1234|
|Activar anuncio de mantenimiento en todos canales|01:45|20/11/2025 02:00|Andrea Castro|+56 9 6789 0123|
|Desconectar enlaces WAN y migrar tráfico a ruta secundaria|02:00|20/11/2025 02:20|Daniela Pérez|+56 9 5678 9012|
|Apagar switch core actual y desconectar cableado|02:20|20/11/2025 02:40|Tomás Fuentes|+56 9 4567 8901|
|Instalar físicamente nuevo Nexus 9500|02:40|20/11/2025 03:10|Tomás Fuentes|+56 9 4567 8901|
|Conectar fibras y cables de cobre según diagrama|03:10|20/11/2025 03:40|Miguel Rojas|+56 9 3456 7890|
|Cargar configuración base y verificar sintaxis|03:40|20/11/2025 04:00|Daniela Pérez|+56 9 5678 9012|
|Activar interfaces y validar VLANs|04:00|20/11/2025 04:20|Jorge Hernández|+56 9 7890 1234|
|Configurar routing protocols (OSPF, BGP, HSRP)|04:20|20/11/2025 04:50|Daniela Pérez|+56 9 5678 9012|
|Migrar tráfico WAN a nuevo equipo|04:50|20/11/2025 05:10|Jorge Hernández|+56 9 7890 1234|
|Ajustar QoS y políticas de seguridad|05:10|20/11/2025 05:30|Carolina Silva|+56 9 2345 6789|

### Plan de Pruebas

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Verificar conectividad a Internet desde 5 puntos|05:30|20/11/2025 05:40|Andrea Castro|+56 9 6789 0123|
|Validar conectividad WAN a sucursales (10 sitios)|05:40|20/11/2025 05:50|Miguel Rojas|+56 9 3456 7890|
|Probar VPN de acceso remoto (5 usuarios piloto)|05:50|20/11/2025 06:00|Carolina Silva|+56 9 2345 6789|
|Validar acceso a aplicaciones críticas (ERP, CRM, Email)|06:00|20/11/2025 06:15|Roberto Díaz|+56 9 1234 5678|
|Verificar telefonía IP (llamadas internas y externas)|06:15|20/11/2025 06:25|Andrea Castro|+56 9 6789 0123|
|Monitorear métricas de performance durante 30 min|06:25|20/11/2025 06:55|Jorge Hernández|+56 9 7890 1234|

### Plan de Respaldo (Rollback)

|Tarea|Hora|Fecha/Hora Finalización|Responsable|Celular|
|---|---|---|---|---|
|Declarar necesidad de rollback|Según necesidad|+5 minutos|Jorge Hernández|+56 9 7890 1234|
|Apagar Nexus 9500 y desconectar cableado|Según necesidad|+20 minutos|Tomás Fuentes|+56 9 4567 8901|
|Reinstalar Catalyst 6509-E|Según necesidad|+30 minutos|Tomás Fuentes|+56 9 4567 8901|
|Reconectar cableado según topología original|Según necesidad|+20 minutos|Miguel Rojas|+56 9 3456 7890|
|Encender equipo y validar configuración|Según necesidad|+15 minutos|Daniela Pérez|+56 9 5678 9012|
|Restaurar rutas WAN y validar servicios|Según necesidad|+20 minutos|Jorge Hernández|+56 9 7890 1234|

**Tiempo Total de Rollback Estimado:** 110 minutos (1h 50min)

---

## 7. COMUNICACIONES

### Comunicación Antes del Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Toda la organización|11/11/2025 10:00|Anuncio inicial de mantenimiento programado crítico|
|Portal Intranet|Todos|11/11/2025 10:00|Banner permanente con cuenta regresiva|
|Teams|Gerentes y Jefes de Área|18/11/2025 15:00|Reunión informativa sobre alcance del cambio|
|Email Recordatorio|Toda la organización|19/11/2025 16:00|Recordatorio 10 horas antes|
|SMS Masivo|Personal crítico (200 personas)|20/11/2025 01:30|Alerta 30 minutos antes|
|Pop-up en sistemas|Usuarios activos|20/11/2025 01:45|Aviso final de 15 minutos|

### Comunicación Durante el Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Teams - War Room|Equipo técnico (15 personas)|Continuo|Canal dedicado para coordinación|
|WhatsApp - Gerencia|Gerentes TI y Operaciones|Cada 30 min|Actualizaciones de progreso|
|Email|Comité de Crisis|Cada hito|Estado de avance del cambio|
|Portal Status Page|Toda la organización|Tiempo real|Dashboard con estado y tiempo estimado|

### Comunicación Después del Cambio

|Medio|Destinatario|Fecha/Hora|Mensaje|
|---|---|---|---|
|Email|Toda la organización|20/11/2025 07:00|Confirmación de finalización exitosa|
|SMS|Personal crítico|20/11/2025 07:00|Sistema disponible - cambio completado|
|Portal Intranet|Todos|20/11/2025 07:30|Reporte de éxito con métricas|
|Video mensaje|Toda la organización|20/11/2025 10:00|CIO agradece colaboración y confirma mejoras|
|Email Técnico|Comité de Cambios|21/11/2025 14:00|Informe detallado post-implementación|

---

## 8. APROBACIONES

|Rol|Nombre|Firma|Fecha|
|---|---|---|---|
|Solicitante|Jorge Hernández López|___________________|10/11/2025|
|Jefe de Área|Sandra Ramírez|___________________|11/11/2025|
|Gerente de TI|Fernando Castillo|___________________|12/11/2025|
|Gerente de Operaciones|Patricia Wong|___________________|12/11/2025|
|CIO|Rodrigo Valenzuela|___________________|13/11/2025|
|Comité de Cambios|CAB Emergencia 44/2025|___________________|13/11/2025|

**Decisión del CAB:** APROBADO - Urgente  
**Condiciones:**

- Mantener equipo técnico completo durante 48 horas post-cambio
- Rollback automático si falla más del 10% de las pruebas
- Proveedor Cisco debe estar on-site durante la implementación
- Configurar monitoreo intensivo por 1 semana

---

## 9. EJECUCIÓN Y CIERRE

### Resultado de la Implementación

|Estado|Fecha/Hora Inicio|Fecha/Hora Fin|Observaciones|
|---|---|---|---|
|☑ Exitoso ☐ Fallido ☐ Parcial|20/11/2025 02:00|20/11/2025 06:55|Cambio ejecutado exitosamente. Todas las pruebas pasaron. Sistema estable. Performance superior a la esperada.|

**Desviaciones del Plan:**

- Instalación física tomó 10 minutos menos de lo estimado (rack pre-configurado)
- Activación de HSRP requirió ajuste de timers (+5 minutos)
- Pruebas finales extendidas 30 minutos para validación exhaustiva
- Tiempo total: 4h 55min (55 minutos más de lo estimado por pruebas extendidas)

**Métricas Observadas:**

- Latencia promedio: 0.65ms (objetivo: <0.7ms) ✓
- Throughput pico durante pruebas: 850 Gbps (capacidad: 3.2 Tbps) ✓
- CPU utilization: 8% (excelente)
- Pérdida de paquetes: 0% ✓
- Tiempo de convergencia OSPF: 4.2 segundos ✓

### Lecciones Aprendidas

**Aspectos Positivos:**

- Pre-staging del equipo y pre-configuración del rack ahorraron 30 minutos
- Excelente coordinación entre equipos de networking, datacenter y operaciones
- Plan de comunicación muy efectivo: cero consultas durante ventana de cambio
- Documentación técnica detallada facilitó ejecución sin contratiempos
- Presencia de ingeniero Cisco on-site generó confianza y soporte inmediato
- Equipo de rollback completo en sitio (nunca se necesitó pero generó tranquilidad)

**Oportunidades de Mejora:**

- Revisar configuración default de HSRP timers para futuros despliegues de Nexus
- Crear playbook automatizado con Ansible para configuración base de switches core
- Implementar checklist digital para validaciones (actualmente en papel)
- Mejorar sistema de etiquetado de cables para acelerar reconexión física

**Aspectos Técnicos Destacables:**

- Nueva plataforma demostró rendimiento 40% superior a especificaciones
- Funcionalidades de telemetry streaming permitieron visibilidad en tiempo real
- Capacidad de troubleshooting mejorada significativamente vs. plataforma anterior
- Integración con herramientas de automation (Ansible, Python) es excelente

**Recomendaciones para Próximos Cambios:**

- Este tipo de cambio crítico requiere al menos 3 semanas de planificación
- Mantener siempre equipo de rollback completo en sitio para cambios de infraestructura core
- Extender ventana de pruebas en 1 hora para validación exhaustiva de servicios
- Documentar configuraciones "as-built" inmediatamente post-implementación
- Realizar capacitación del equipo en nuevas funcionalidades de la plataforma

**Incidentes Post-Implementación:**

- Ninguno en primeras 72 horas
- Monitoreo intensivo confirma estabilidad total del sistema
- Usuarios reportan mejora perceptible en velocidad de red

**Fecha de Cierre:** 23/11/2025  
**Cerrado por:** Jorge Hernández López - Infraestructura de Redes  
**Aprobación de Cierre:** Fernando Castillo - Gerente de TI