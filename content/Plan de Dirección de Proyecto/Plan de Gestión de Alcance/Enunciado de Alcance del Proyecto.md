# Enunciado del Alcance del Proyecto

## Sistema de Monitoreo de Desempeño Estudiantil

**Proyecto:** Sistema de Monitoreo de Desempeño Estudiantil  
**Fecha:** 26 de agosto de 2025  
**Versión:** 1.0  
**Gerente de Proyecto:** Ignacio Beltrán, Director de Proyectos  
**Patrocinador:** Patricio Núñez, Director Académico

---

## 1. Descripción del Alcance del Proyecto

El proyecto consiste en el diseño, desarrollo e implementación de un sistema integral de monitoreo de desempeño estudiantil para el Instituto Técnico Profesional Crecer Más. Este sistema centralizará la información académica proveniente de SIGAA y Moodle, proporcionando herramientas de visualización, análisis predictivo y alertas automatizadas para mejorar el seguimiento del progreso estudiantil y reducir los índices de deserción.

El sistema funcionará sobre la infraestructura tecnológica actual (servidor físico, base de datos MySQL) e implementará tecnologías de inteligencia artificial para el análisis predictivo del riesgo de deserción estudiantil.

## 2. Descripción del Alcance del Producto

### 2.1 Características Principales del Producto

- **Integración bidireccional** con sistemas académicos existentes (SIGAA y Moodle)
- **Motor de inteligencia artificial** con precisión superior al 85% para predicción de deserción
- **Interfaz web responsiva** compatible con dispositivos móviles y de escritorio
- **Sistema de notificaciones automatizadas** vía correo electrónico
- **Dashboard ejecutivo** con métricas y KPIs institucionales
- **Seguridad de datos** conforme a normativas de protección de datos personales
- **Escalabilidad** para soportar el crecimiento institucional proyectado

### 2.2 Funcionalidades del Sistema

- Visualización de calificaciones por estudiante, curso y cohorte
- Seguimiento de asistencia y participación en tiempo real
- Generación de alertas tempranas por bajo rendimiento o riesgo de deserción
- Reportes ejecutivos para coordinadores de carrera y directivos
- Análisis de tendencias y patrones académicos
- Gestión de usuarios y perfiles de acceso diferenciados

## 3. Entregables del Proyecto

### 3.1 Entregables de Planificación

- Plan de Gestión del Proyecto
- Análisis de requisitos técnicos y funcionales
- Arquitectura del sistema y diseño técnico
- Plan de integración con sistemas existentes
- Plan de capacitación y gestión del cambio

### 3.2 Entregables de Desarrollo

- **Tablero de Visualización de Datos**
    
    - Dashboard principal con métricas estudiantiles
    - Vistas por estudiante individual
    - Vistas por cohorte y programa académico
    - Reportes exportables en formatos PDF y Excel
- **Sistema de Alertas y Notificaciones**
    
    - Motor de reglas de negocio para alertas
    - Templates de correos electrónicos personalizables
    - Sistema de notificaciones web en tiempo real
    - Panel de gestión de alertas para coordinadores
- **Motor de Inteligencia Artificial**
    
    - Algoritmos de machine learning para predicción de deserción
    - Modelo entrenado con datos históricos institucionales
    - API de servicios de predicción
    - Dashboard de monitoreo del rendimiento del modelo
- **Integración de Sistemas**
    
    - APIs de conexión con SIGAA
    - APIs de conexión con Moodle
    - Servicios de sincronización de datos
    - Middleware de transformación de datos

### 3.3 Entregables de Implementación

- Sistema instalado y configurado en producción
- Base de datos migrada y validada
- Pruebas de integración completadas
- Documentación técnica y de usuario
- Capacitación completada para usuarios finales

### 3.4 Entregables de Cierre

- Manual de operación del sistema
- Plan de mantenimiento y soporte
- Informe final del proyecto
- Lecciones aprendidas documentadas
- Transferencia de conocimiento completada

## 4. Criterios de Aceptación

### 4.1 Criterios Técnicos

- El sistema debe integrar exitosamente con SIGAA y Moodle sin afectar el rendimiento de estos sistemas
- El motor de IA debe alcanzar una precisión mínima del 85% en la predicción de riesgo de deserción
- Los tiempos de respuesta del sistema no deben exceder los 3 segundos para consultas estándar
- El sistema debe soportar acceso concurrente de hasta 200 usuarios simultáneos
- Disponibilidad del sistema mínima del 99.5% durante horario laboral

### 4.2 Criterios Funcionales

- Todas las funcionalidades especificadas en los requisitos deben operar correctamente
- Los reportes deben generarse en tiempo real basados en datos actualizados
- Las alertas deben enviarse dentro de los 15 minutos posteriores a la detección del evento
- La interfaz debe ser intuitiva y no requerir más de 2 horas de capacitación por usuario

### 4.3 Criterios de Satisfacción del Usuario

- Satisfacción de usuarios finales (coordinadores y docentes) superior al 80%
- Reducción documentada en tiempo de generación de reportes académicos
- Adopción del sistema por al menos el 90% de los coordinadores de carrera
- Feedback positivo de la dirección académica sobre la utilidad del sistema

### 4.4 Criterios de Seguridad y Cumplimiento

- Cumplimiento total con normativas de protección de datos personales
- Implementación de controles de acceso basados en roles
- Auditoría completa de seguridad sin vulnerabilidades críticas
- Backup y recuperación de datos probados exitosamente

## 5. Exclusiones del Proyecto

### 5.1 Exclusiones Técnicas

- **NO incluye** desarrollo de aplicaciones móviles nativas (iOS/Android)
- **NO incluye** integración con sistemas externos no mencionados (ej: sistemas de biblioteca, cafetería)
- **NO incluye** migración a infraestructura en la nube (el sistema operará en servidor físico actual)
- **NO incluye** desarrollo de funcionalidades de gestión financiera o facturación

### 5.2 Exclusiones Funcionales

- **NO incluye** funcionalidades de comunicación directa entre estudiantes y docentes (chat, mensajería)
- **NO incluye** gestión de horarios o calendarios académicos
- **NO incluye** sistema de evaluaciones en línea o e-learning
- **NO incluye** gestión de recursos físicos (aulas, laboratorios, equipos)

### 5.3 Exclusiones de Datos

- **NO incluye** migración de datos académicos anteriores al año 2020
- **NO incluye** integración con datos externos de redes sociales o plataformas no académicas
- **NO incluye** análisis de datos no relacionados con el desempeño académico

### 5.4 Exclusiones de Servicios

- **NO incluye** soporte técnico más allá del período de garantía de 6 meses
- **NO incluye** capacitación presencial fuera de las instalaciones del instituto
- **NO incluye** mantenimiento correctivo posterior al período de garantía

## 6. Restricciones del Proyecto

### 6.1 Restricciones Presupuestarias

- Presupuesto máximo asignado: $480.000.000 CLP
- No se pueden exceder las asignaciones por categoría sin aprobación del patrocinador

### 6.2 Restricciones Temporales

- Duración máxima del proyecto: 21 meses (agosto 2025 - mayo 2027)
- Fecha límite no negociable para go-live: abril 2027
- Hitos intermedios establecidos son de cumplimiento obligatorio

### 6.3 Restricciones Tecnológicas

- Debe ser compatible con infraestructura actual (servidor físico, MySQL)
- Desarrollo debe utilizar tecnologías open source cuando sea posible
- Debe mantener compatibilidad con versiones actuales de SIGAA y Moodle

### 6.4 Restricciones de Recursos

- Disponibilidad limitada de coordinadores de carrera para pruebas (máximo 4 horas semanales)
- Acceso a sistemas productivos solo durante ventanas de mantenimiento programadas
- Equipo de TI interno tiene disponibilidad parcial (50% de su tiempo)

### 6.5 Restricciones Regulatorias

- Cumplimiento obligatorio con Ley de Protección de Datos Personales
- Todas las comunicaciones con estudiantes deben cumplir con políticas institucionales
- Acceso a datos estudiantiles limitado a personal autorizado

## 7. Supuestos del Proyecto

### 7.1 Supuestos Técnicos

- Los sistemas SIGAA y Moodle mantendrán su estructura de datos actual durante el proyecto
- La infraestructura de red actual soportará el tráfico adicional generado por el nuevo sistema
- Las APIs necesarias para integración estarán disponibles y documentadas
- No habrá cambios mayores en las versiones de los sistemas existentes

### 7.2 Supuestos Organizacionales

- Los coordinadores de carrera estarán disponibles para validación y pruebas según cronograma
- No habrá cambios significativos en la estructura organizacional durante el proyecto
- El personal de TI actual tendrá las competencias necesarias para operar el sistema
- La dirección académica mantendrá su apoyo al proyecto durante toda su ejecución

### 7.3 Supuestos de Datos

- Los datos históricos en SIGAA y Moodle están completos y son confiables
- Los formatos de datos actuales son consistentes y estandarizados
- No habrá cambios en los criterios de evaluación académica durante el proyecto

### 7.4 Supuestos Externos

- No habrá cambios en la normativa de protección de datos que afecten el proyecto
- Los proveedores de software mantendrán el soporte para las versiones actuales
- No habrá restricciones presupuestarias adicionales por parte de la institución

---

**Aprobado por:**

- **Patricio Núñez** - Director Académico y Patrocinador del Proyecto
- **Ignacio Beltrán** - Gerente del Proyecto

**Fecha de Aprobación:** [A completar tras revisión]  
**Versión:** 1.0  
**Próxima Revisión:** [Según plan de gestión de cambios]
