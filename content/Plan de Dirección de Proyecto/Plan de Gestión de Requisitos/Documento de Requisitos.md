# Documento de Requisitos
## Proyecto: Transformación Digital del Instituto Técnico Profesional Crecer Más

**Versión:** 1.0 (Preliminar)  
**Fecha:** 29 de septiembre de 2025  
**Preparado por:** Ignacio Beltrán, Director de Proyectos  
**Revisado por:** Sebastián Bravo, Director de TI

---

## Control de Versiones

| Versión | Fecha | Autor | Cambios |
|---------|-------|-------|---------|
| 1.0 | 29/09/2025 | Ignacio Beltrán | Versión inicial - Requisitos de alto nivel |
| | | | |
| | | | |

---

## 1. Introducción

### 1.1 Propósito del Documento

Este documento describe los requisitos de alto nivel para el proyecto de Transformación Digital del Instituto Técnico Profesional Crecer Más. Sirve como documento base que será refinado y expandido durante la fase de planificación del proyecto.

### 1.2 Alcance

Este documento abarca los requisitos para los cuatro sistemas principales del proyecto:
- Sistema Integrado de Gestión Académica y Administrativa (SIGAA)
- Campus Virtual+
- Sistema de Alerta Temprana con Analítica Predictiva
- CRM Educativo y Plataforma de Admisión Automatizada

### 1.3 Referencias

- Caso de Negocio - Transformación Digital Crecer Más v1.0
- Acta de Constitución del Proyecto
- PMBOK 6ta Edición - Sección 5.2 Recopilar Requisitos

### 1.4 Definiciones y Acrónimos

| Término | Definición |
|---------|------------|
| SIGAA | Sistema Integrado de Gestión Académica y Administrativa |
| LMS | Learning Management System (Sistema de Gestión de Aprendizaje) |
| CRM | Customer Relationship Management |
| IA | Inteligencia Artificial |
| API | Application Programming Interface |
| UI/UX | User Interface / User Experience |
| RNF | Requisito No Funcional |
| RF | Requisito Funcional |

---

## 2. Clasificación de Requisitos

Según PMBOK 6, los requisitos se clasifican en las siguientes categorías:

### 2.1 Requisitos del Negocio
Necesidades de alto nivel de la organización que justifican el proyecto.

### 2.2 Requisitos de los Interesados
Necesidades específicas de grupos de interesados identificados.

### 2.3 Requisitos de las Soluciones
#### 2.3.1 Requisitos Funcionales
Comportamientos, acciones y procesos que el sistema debe ejecutar.

#### 2.3.2 Requisitos No Funcionales
Condiciones ambientales y cualidades (rendimiento, seguridad, usabilidad).

### 2.4 Requisitos de Transición y Preparación
Capacidades temporales necesarias para migración y puesta en marcha.

### 2.5 Requisitos del Proyecto
Condiciones que el proyecto debe cumplir durante su ejecución.

---

## 3. Requisitos del Negocio

### RN-001: Reducción de Deserción Estudiantil
**Descripción:** El proyecto debe contribuir a reducir la tasa de deserción estudiantil en un 30% en un plazo de 5 años.  
**Prioridad:** Alta  
**Criterio de Aceptación:** Sistema de alertas tempranas operativo con precisión >85% en predicción de riesgo.  
**Interesados:** Rectoría, Dirección Académica  
**Estado:** Pendiente de refinamiento

### RN-002: Crecimiento de Matrícula
**Descripción:** El proyecto debe facilitar la duplicación de la matrícula actual (2.500 a 5.000 estudiantes) en 5 años.  
**Prioridad:** Alta  
**Criterio de Aceptación:** Infraestructura tecnológica capaz de soportar 5.000+ usuarios concurrentes.  
**Interesados:** Rectoría, Dirección de Admisión  
**Estado:** Pendiente de refinamiento

### RN-003: Expansión Regional
**Descripción:** Los sistemas deben permitir operación en 3 nuevas regiones sin requerir infraestructura TI local significativa.  
**Prioridad:** Alta  
**Criterio de Aceptación:** Arquitectura cloud centralizada operativa en al menos 2 regiones piloto.  
**Interesados:** Rectoría, Dirección de TI  
**Estado:** Pendiente de refinamiento

### RN-004: Eficiencia Operativa
**Descripción:** El proyecto debe reducir los costos operativos administrativos en al menos $40.000.000 CLP anuales.  
**Prioridad:** Media  
**Criterio de Aceptación:** Métricas documentadas de reducción de tiempos en procesos administrativos.  
**Interesados:** Dirección Administrativa, Dirección de Finanzas  
**Estado:** Pendiente de refinamiento

### RN-005: Modalidad Híbrida Competitiva
**Descripción:** Posicionar al instituto como líder en educación técnica con modalidad híbrida de calidad.  
**Prioridad:** Alta  
**Criterio de Aceptación:** Campus Virtual+ operativo con satisfacción de usuarios >80%.  
**Interesados:** Dirección Académica, Dirección de Comunicaciones  
**Estado:** Pendiente de refinamiento

---

## 4. Requisitos de los Interesados

### 4.1 Estudiantes

#### RE-EST-001: Acceso a Información Académica
**Descripción:** Los estudiantes deben poder consultar sus notas, asistencia y avance curricular en tiempo real.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-EST-002: Experiencia Digital Moderna
**Descripción:** La interfaz debe ser intuitiva, responsive y accesible desde dispositivos móviles.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-EST-003: Plataforma de Aprendizaje Virtual
**Descripción:** Los estudiantes deben acceder a contenidos, participar en foros y entregar tareas online.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

### 4.2 Docentes

#### RE-DOC-001: Gestión de Notas y Asistencia
**Descripción:** Los docentes deben poder registrar notas y asistencia de forma rápida y eficiente.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-DOC-002: Alertas de Estudiantes en Riesgo
**Descripción:** Los docentes deben recibir alertas automáticas sobre estudiantes con riesgo de deserción.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-DOC-003: Herramientas Pedagógicas Digitales
**Descripción:** Los docentes requieren herramientas para crear y gestionar contenido educativo digital.  
**Prioridad:** Media  
**Estado:** Pendiente de refinamiento

### 4.3 Coordinadores de Carrera

#### RE-COORD-001: Dashboards de Seguimiento
**Descripción:** Los coordinadores necesitan visualización en tiempo real del desempeño de sus cohortes.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-COORD-002: Reportes Académicos Automatizados
**Descripción:** Generación automática de reportes de rendimiento, deserción y avance curricular.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

### 4.4 Personal Administrativo

#### RE-ADM-001: Digitalización de Matrícula
**Descripción:** El proceso de matrícula debe ser completamente digital y automatizado.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-ADM-002: Certificados Digitales
**Descripción:** Generación y emisión automática de certificados y documentos oficiales.  
**Prioridad:** Media  
**Estado:** Pendiente de refinamiento

### 4.5 Dirección Académica

#### RE-DIRAC-001: Analítica Institucional
**Descripción:** Acceso a métricas institucionales y KPIs académicos en tiempo real.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-DIRAC-002: Intervención Proactiva
**Descripción:** Capacidad de identificar y actuar sobre problemas académicos antes de que escalen.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

### 4.6 Equipo de Admisión

#### RE-ADMI-001: Gestión de Leads
**Descripción:** El CRM debe permitir seguimiento completo del funnel de admisión.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

#### RE-ADMI-002: Automatización de Comunicaciones
**Descripción:** Envío automático de correos, WhatsApp y notificaciones según etapa del postulante.  
**Prioridad:** Media  
**Estado:** Pendiente de refinamiento

---

## 5. Requisitos Funcionales por Sistema

### 5.1 Sistema Integrado de Gestión Académica y Administrativa (SIGAA)

#### RF-SIGAA-001: Gestión de Matrícula
**Descripción:** El sistema debe permitir el registro, modificación y consulta de matrículas estudiantiles.  
**Prioridad:** Alta  
**Módulo:** Gestión Académica  
**Estado:** Pendiente de refinamiento  
**Notas:** Incluir campos personalizados por carrera

#### RF-SIGAA-002: Registro de Notas
**Descripción:** El sistema debe permitir el ingreso, cálculo automático y consulta de calificaciones.  
**Prioridad:** Alta  
**Módulo:** Gestión Académica  
**Estado:** Pendiente de refinamiento  
**Notas:** Validar escalas de calificación por carrera

#### RF-SIGAA-003: Control de Asistencia
**Descripción:** El sistema debe registrar y reportar asistencia de estudiantes por asignatura.  
**Prioridad:** Alta  
**Módulo:** Gestión Académica  
**Estado:** Pendiente de refinamiento

#### RF-SIGAA-004: Portal Estudiante
**Descripción:** Portal web para que estudiantes consulten su información académica y administrativa.  
**Prioridad:** Alta  
**Módulo:** Portal  
**Estado:** Pendiente de refinamiento

#### RF-SIGAA-005: Portal Docente
**Descripción:** Portal web para gestión de cursos, notas, asistencia y materiales por parte de docentes.  
**Prioridad:** Alta  
**Módulo:** Portal  
**Estado:** Pendiente de refinamiento

#### RF-SIGAA-006: Gestión Financiera
**Descripción:** Control de pagos, aranceles, becas y estados financieros de estudiantes.  
**Prioridad:** Media  
**Módulo:** Administración Financiera  
**Estado:** Pendiente de refinamiento

#### RF-SIGAA-007: Certificados Digitales
**Descripción:** Generación automática de certificados de alumno regular, notas, título, etc.  
**Prioridad:** Media  
**Módulo:** Certificación  
**Estado:** Pendiente de refinamiento

#### RF-SIGAA-008: Seguimiento por Carrera
**Descripción:** Módulo de seguimiento del avance curricular de estudiantes por malla.  
**Prioridad:** Alta  
**Módulo:** Seguimiento Académico  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS FUNCIONALES SIGAA DURANTE PLANIFICACIÓN]_

### 5.2 Campus Virtual+

#### RF-CV-001: Gestión de Cursos
**Descripción:** Creación, configuración y administración de cursos virtuales.  
**Prioridad:** Alta  
**Módulo:** LMS  
**Estado:** Pendiente de refinamiento

#### RF-CV-002: Contenido Multimedia
**Descripción:** Soporte para subir y reproducir videos, documentos, presentaciones y otros recursos.  
**Prioridad:** Alta  
**Módulo:** LMS  
**Estado:** Pendiente de refinamiento

#### RF-CV-003: Foros de Discusión
**Descripción:** Herramienta de foros para interacción asíncrona entre estudiantes y docentes.  
**Prioridad:** Media  
**Módulo:** Colaboración  
**Estado:** Pendiente de refinamiento

#### RF-CV-004: Sistema de Tareas
**Descripción:** Creación, entrega y calificación de tareas y trabajos online.  
**Prioridad:** Alta  
**Módulo:** Evaluación  
**Estado:** Pendiente de refinamiento

#### RF-CV-005: Videoconferencias
**Descripción:** Integración de herramienta de videoconferencias para clases sincrónicas.  
**Prioridad:** Alta  
**Módulo:** Comunicación Sincrónica  
**Estado:** Pendiente de refinamiento

#### RF-CV-006: Feedback y Calificaciones
**Descripción:** Sistema de retroalimentación y calificación de actividades del LMS.  
**Prioridad:** Alta  
**Módulo:** Evaluación  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS FUNCIONALES CAMPUS VIRTUAL+ DURANTE PLANIFICACIÓN]_

### 5.3 Sistema de Alerta Temprana con Analítica Predictiva

#### RF-SAT-001: Recolección de Datos
**Descripción:** Integración automática con SIGAA y Moodle para obtener datos de desempeño estudiantil.  
**Prioridad:** Alta  
**Módulo:** Integración  
**Estado:** Pendiente de refinamiento

#### RF-SAT-002: Motor Predictivo
**Descripción:** Algoritmo de IA que predice riesgo de deserción con precisión >85%.  
**Prioridad:** Alta  
**Módulo:** Machine Learning  
**Estado:** Pendiente de refinamiento

#### RF-SAT-003: Dashboard de Seguimiento
**Descripción:** Panel de visualización de estudiantes en riesgo para tutores y coordinadores.  
**Prioridad:** Alta  
**Módulo:** Visualización  
**Estado:** Pendiente de refinamiento

#### RF-SAT-004: Sistema de Alertas
**Descripción:** Generación y envío automático de alertas por correo según nivel de riesgo detectado.  
**Prioridad:** Alta  
**Módulo:** Notificaciones  
**Estado:** Pendiente de refinamiento

#### RF-SAT-005: Registro de Intervenciones
**Descripción:** Registro y seguimiento de acciones tomadas para apoyar a estudiantes en riesgo.  
**Prioridad:** Media  
**Módulo:** Gestión de Casos  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS FUNCIONALES SISTEMA ALERTA TEMPRANA DURANTE PLANIFICACIÓN]_

### 5.4 CRM Educativo y Plataforma de Admisión Automatizada

#### RF-CRM-001: Gestión de Leads
**Descripción:** Registro y seguimiento de postulantes desde primer contacto hasta matrícula.  
**Prioridad:** Alta  
**Módulo:** Gestión de Leads  
**Estado:** Pendiente de refinamiento

#### RF-CRM-002: Formulario Inteligente
**Descripción:** Formulario de postulación web con validaciones y autocompletado inteligente.  
**Prioridad:** Alta  
**Módulo:** Admisión  
**Estado:** Pendiente de refinamiento

#### RF-CRM-003: Automatización de Correos
**Descripción:** Envío automático de correos según etapa del funnel de admisión.  
**Prioridad:** Media  
**Módulo:** Marketing Automation  
**Estado:** Pendiente de refinamiento

#### RF-CRM-004: Integración WhatsApp
**Descripción:** Envío de notificaciones automáticas vía WhatsApp.  
**Prioridad:** Media  
**Módulo:** Marketing Automation  
**Estado:** Pendiente de refinamiento

#### RF-CRM-005: Dashboard de Campañas
**Descripción:** Visualización de métricas de conversión y rendimiento de campañas de admisión.  
**Prioridad:** Media  
**Módulo:** Analytics  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS FUNCIONALES CRM EDUCATIVO DURANTE PLANIFICACIÓN]_

---

## 6. Requisitos No Funcionales

### 6.1 Rendimiento (Performance)

#### RNF-PERF-001: Tiempo de Respuesta
**Descripción:** Las consultas estándar del sistema deben responder en menos de 3 segundos.  
**Prioridad:** Alta  
**Métrica:** Percentil 95 de respuestas < 3 segundos  
**Estado:** Pendiente de refinamiento

#### RNF-PERF-002: Usuarios Concurrentes
**Descripción:** El sistema debe soportar al menos 500 usuarios concurrentes sin degradación.  
**Prioridad:** Alta  
**Métrica:** Load testing con 500 usuarios simultáneos  
**Estado:** Pendiente de refinamiento

#### RNF-PERF-003: Escalabilidad
**Descripción:** La arquitectura debe permitir escalamiento horizontal para soportar crecimiento futuro.  
**Prioridad:** Alta  
**Métrica:** Capacidad de añadir instancias sin cambios de código  
**Estado:** Pendiente de refinamiento

### 6.2 Seguridad

#### RNF-SEG-001: Autenticación
**Descripción:** El sistema debe implementar autenticación segura para todos los usuarios.  
**Prioridad:** Alta  
**Métrica:** Autenticación multifactor opcional disponible  
**Estado:** Pendiente de refinamiento

#### RNF-SEG-002: Control de Acceso
**Descripción:** Implementación de control de acceso basado en roles (RBAC).  
**Prioridad:** Alta  
**Métrica:** Permisos granulares por rol y módulo  
**Estado:** Pendiente de refinamiento

#### RNF-SEG-003: Protección de Datos
**Descripción:** Los datos sensibles deben estar encriptados en tránsito y en reposo.  
**Prioridad:** Alta  
**Métrica:** TLS 1.3 para tránsito, AES-256 para reposo  
**Estado:** Pendiente de refinamiento

#### RNF-SEG-004: Auditoría
**Descripción:** Todas las acciones críticas deben quedar registradas en logs de auditoría.  
**Prioridad:** Media  
**Métrica:** Log completo de accesos y modificaciones  
**Estado:** Pendiente de refinamiento

### 6.3 Disponibilidad y Confiabilidad

#### RNF-DISP-001: Uptime
**Descripción:** El sistema debe tener una disponibilidad mínima del 99.5% en horario laboral.  
**Prioridad:** Alta  
**Métrica:** Máximo 21.6 horas de downtime anual  
**Estado:** Pendiente de refinamiento

#### RNF-DISP-002: Backup
**Descripción:** Backup automático diario de todos los datos críticos con retención de 30 días.  
**Prioridad:** Alta  
**Métrica:** RPO < 24 horas, RTO < 4 horas  
**Estado:** Pendiente de refinamiento

#### RNF-DISP-003: Recuperación ante Desastres
**Descripción:** Plan de recuperación ante desastres documentado y probado semestralmente.  
**Prioridad:** Media  
**Métrica:** Simulacro de DR exitoso cada 6 meses  
**Estado:** Pendiente de refinamiento

### 6.4 Usabilidad

#### RNF-USA-001: Interfaz Intuitiva
**Descripción:** La interfaz debe ser usable sin capacitación extensiva.  
**Prioridad:** Alta  
**Métrica:** Usuario nuevo completa tarea estándar en < 5 minutos  
**Estado:** Pendiente de refinamiento

#### RNF-USA-002: Responsive Design
**Descripción:** La interfaz debe ser completamente funcional en dispositivos móviles y tablets.  
**Prioridad:** Alta  
**Métrica:** Funcionalidad completa en pantallas desde 320px  
**Estado:** Pendiente de refinamiento

#### RNF-USA-003: Accesibilidad
**Descripción:** Cumplimiento con estándares WCAG 2.1 nivel AA para accesibilidad web.  
**Prioridad:** Media  
**Métrica:** Auditoria de accesibilidad aprobada  
**Estado:** Pendiente de refinamiento

### 6.5 Compatibilidad e Integración

#### RNF-COMP-001: Navegadores Web
**Descripción:** Compatibilidad con Chrome, Firefox, Safari y Edge en versiones actuales.  
**Prioridad:** Alta  
**Métrica:** Testing en últimas 2 versiones de cada navegador  
**Estado:** Pendiente de refinamiento

#### RNF-COMP-002: Integración con Sistemas Existentes
**Descripción:** APIs RESTful documentadas para integración con sistemas actuales y futuros.  
**Prioridad:** Alta  
**Métrica:** Documentación OpenAPI 3.0 completa  
**Estado:** Pendiente de refinamiento

### 6.6 Mantenibilidad

#### RNF-MANT-001: Código Documentado
**Descripción:** Todo el código debe estar documentado según estándares de la industria.  
**Prioridad:** Media  
**Métrica:** Cobertura de documentación > 80%  
**Estado:** Pendiente de refinamiento

#### RNF-MANT-002: Arquitectura Modular
**Descripción:** Arquitectura de microservicios que permita actualizar módulos independientemente.  
**Prioridad:** Alta  
**Métrica:** Módulos desplegables sin afectar otros servicios  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS NO FUNCIONALES DURANTE PLANIFICACIÓN]_

---

## 7. Requisitos de Transición y Preparación

### RT-001: Migración de Datos
**Descripción:** Migración completa de datos desde sistemas actuales sin pérdida de información.  
**Prioridad:** Alta  
**Criterio de Aceptación:** 100% de datos críticos migrados y validados  
**Estado:** Pendiente de refinamiento

### RT-002: Plan de Capacitación
**Descripción:** Capacitación completa para todos los usuarios según su rol.  
**Prioridad:** Alta  
**Criterio de Aceptación:** 90% de usuarios capacitados antes de go-live  
**Estado:** Pendiente de refinamiento

### RT-003: Operación Paralela
**Descripción:** Período de operación paralela de sistemas antiguos y nuevos durante transición.  
**Prioridad:** Media  
**Criterio de Aceptación:** Mínimo 1 mes de operación paralela sin incidentes  
**Estado:** Pendiente de refinamiento

### RT-004: Plan de Rollback
**Descripción:** Procedimiento documentado para revertir a sistemas anteriores en caso de falla crítica.  
**Prioridad:** Alta  
**Criterio de Aceptación:** Procedimiento probado y documentado  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS DE TRANSICIÓN DURANTE PLANIFICACIÓN]_

---

## 8. Requisitos del Proyecto

### RP-001: Metodología Ágil
**Descripción:** El proyecto debe ejecutarse usando metodología ágil con sprints de 2 semanas.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

### RP-002: Control de Calidad
**Descripción:** Cobertura mínima de 80% en pruebas automatizadas para código crítico.  
**Prioridad:** Alta  
**Estado:** Pendiente de refinamiento

### RP-003: Documentación Técnica
**Descripción:** Documentación técnica completa entregada al finalizar cada fase.  
**Prioridad:** Media  
**Estado:** Pendiente de refinamiento

### RP-004: Reuniones de Seguimiento
**Descripción:** Reuniones semanales de seguimiento con stakeholders clave.  
**Prioridad:** Media  
**Estado:** Pendiente de refinamiento

_[ESPACIO PARA AGREGAR MÁS REQUISITOS DEL PROYECTO DURANTE PLANIFICACIÓN]_

---

## 9. Priorización de Requisitos

### 9.1 Método de Priorización

Se utilizará el método MoSCoW para priorizar requisitos:

- **Must Have (Debe Tener):** Requisitos críticos sin los cuales el sistema no funciona
- **Should Have (Debería Tener):** Requisitos importantes pero no críticos
- **Could Have (Podría Tener):** Requisitos deseables pero no esenciales
- **Won't Have (No Tendrá):** Requisitos fuera del alcance actual

### 9.2 Matriz de Priorización (Preliminar)

| Categoría | Must Have | Should Have | Could Have |
|-----------|-----------|-------------|------------|
| **Requisitos de Negocio** | RN-001, RN-002, RN-003, RN-005 | RN-004 | - |
| **Requisitos Funcionales** | Por definir en planificación | Por definir en planificación | Por definir en planificación |
| **Requisitos No Funcionales** | RNF-PERF-001/002/003, RNF-SEG-001/002/003, RNF-DISP-001, RNF-USA-001/002, RNF-COMP-001/002 | RNF-SEG-004, RNF-DISP-002/003, RNF-USA-003 | - |

_[ESTA MATRIZ SERÁ EXPANDIDA Y REFINADA DURANTE LA FASE DE PLANIFICACIÓN]_

---

## 10. Criterios de Aceptación General

Todos los requisitos deben cumplir con los siguientes criterios antes de ser considerados completos:

### 10.1 Características de Requisitos Válidos

- **Inequívocos:** Claramente definidos sin ambigüedades
- **Medibles:** Con criterios de aceptación cuantificables
- **Trazables:** Vinculados a objetivos de negocio y casos de prueba
- **Completos:** Con toda la información necesaria para implementación
- **Coherentes:** Sin contradicciones con otros requisitos
- **Aceptables:** Aprobados por stakeholders clave

### 10.2 Estado de Requisitos

Cada requisito puede estar en uno de los siguientes estados:

- **Propuesto:** Identificado pero no validado
- **Aprobado:** Validado y aprobado por stakeholders
- **En Desarrollo:** Siendo implementado
- **En Pruebas:** Bajo verificación de QA
- **Completado:** Implementado y verificado
- **Rechazado:** No será implementado
- **Diferido:** Pospuesto para versión futura

---

## 11. Dependencias y Restricciones

### 11.1 Dependencias Técnicas

- Infraestructura cloud disponible y contratada
- Acceso a sistemas actuales (SIGAA y Moodle) para integración
- Herramientas de desarrollo y testing licenciadas
- Disponibilidad de datos históricos para entrenamiento de modelos de IA

### 11.2 Restricciones del Proyecto

- Presupuesto fijo de $400.000.000 CLP
- Duración máxima de 18 meses
- Debe mantener sistemas actuales operativos durante implementación
- Cumplimiento con normativas de protección de datos personales chilenas

### 11.3 Supuestos

- Disponibilidad de stakeholders para validación de requisitos
- Personal técnico calificado disponible para desarrollo
- Estudiantes y docentes disponibles para pruebas piloto
- Infraestructura de red institucional soporta nuevos sistemas

---

## 12. Gestión de Cambios a Requisitos

### 12.1 Proceso de Cambio

Todo cambio a requisitos aprobados debe:

1. Ser solicitado formalmente mediante formato de solicitud de cambio
2. Incluir justificación de negocio y análisis de impacto
3. Ser evaluado por el Comité de Control de Cambios
4. Ser aprobado antes de su implementación
5. Ser reflejado en nueva versión de este documento

### 12.2 Análisis de Impacto

Cada cambio de requisito debe evaluar impacto en:

- Alcance del proyecto
- Cronograma
- Presupuesto
- Calidad
- Riesgos
- Otros requisitos relacionados

---

## 13. Trazabilidad de Requisitos

### 13.1 Vinculación con Objetivos

Este documento será complementado con la **Matriz de Trazabilidad de Requisitos** que vinculará:

- Requisitos → Objetivos de Negocio
- Requisitos → Entregables del Proyecto
- Requisitos → Casos de Prueba
- Requisitos → Paquetes de Trabajo (EDT/WBS)

### 13.2 Métricas de Trazabilidad

Durante la planificación se establecerán métricas para:

- Porcentaje de requisitos trazados a objetivos
- Porcentaje de requisitos con casos de prueba
- Porcentaje de requisitos implementados vs planificados

---

## 14. Próximos Pasos

### 14.1 Actividades de Refinamiento

Durante la fase de planificación se realizarán las siguientes actividades para completar este documento:

1. **Talleres de Requisitos por Sistema:** Sesiones de 4 horas con stakeholders de cada sistema para detallar requisitos funcionales.

2. **Entrevistas con Usuarios Finales:** Entrevistas individuales con estudiantes, docentes, coordinadores y administrativos para capturar necesidades específicas.

3. **Análisis de Procesos Actuales:** Mapeo detallado de procesos AS-IS para identificar requisitos de mejora.

4. **Prototipado de Interfaces:** Creación de mockups para validar requisitos de usabilidad con usuarios.

5. **Definición de Criterios de Aceptación:** Establecimiento de criterios medibles y verificables para cada requisito.

6. **Análisis de Viabilidad Técnica:** Validación técnica de requisitos con el equipo de desarrollo.

7. **Priorización Final:** Sesión de priorización con Comité Directivo del Proyecto.

### 14.2 Cronograma de Refinamiento

| Actividad | Semanas | Responsable |
|-----------|---------|-------------|
| Talleres de Requisitos | 2-4 | Product Owner |
| Entrevistas de Usuario | 3-5 | UX Researcher |
| Análisis de Procesos | 2-3 | Business Analyst |
| Prototipado | 4-6 | UX Designer |
| Criterios de Aceptación | 5-7 | Product Owner + QA Lead |
| Análisis Técnico | 6-8 | Arquitecto de Software |
| Priorización Final | 8 | Director de Proyectos |

### 14.3 Entregables Esperados

Al finalizar el refinamiento de requisitos, se completarán:

- Especificaciones funcionales detalladas por sistema (80-120 requisitos adicionales estimados)
- Criterios de aceptación específicos para cada requisito
- Prototipos de interfaz validados con usuarios
- Matriz de Trazabilidad de Requisitos completa
- Casos de uso detallados para funcionalidades críticas
- Documento de Arquitectura Técnica alineado con requisitos
- Plan de Pruebas basado en requisitos

---

## 15. Aprobaciones

Este documento requiere aprobación de los siguientes stakeholders antes de pasar a la fase de diseño:

| Rol | Nombre | Firma | Fecha | Estado |
|-----|--------|-------|-------|--------|
| **Patrocinador Ejecutivo** | María Inés Zamora (Rectora) | _____________ | ___/___/2025 | Pendiente |
| **Patrocinador SIGAA** | Patricio Núñez (Dir. Académico) | _____________ | ___/___/2025 | Pendiente |
| **Patrocinador Campus Virtual** | Patricio Núñez (Dir. Académico) | _____________ | ___/___/2025 | Pendiente |
| **Patrocinador Sistema Alerta** | Carolina Rivas (Dir. Vinculación) | _____________ | ___/___/2025 | Pendiente |
| **Patrocinador CRM** | Paula Araya (Jefa Admisión) | _____________ | ___/___/2025 | Pendiente |
| **Director de TI** | Sebastián Bravo | _____________ | ___/___/2025 | Pendiente |
| **Director de Proyectos** | Ignacio Beltrán | _____________ | ___/___/2025 | Pendiente |

---

## 16. Historial de Cambios Significativos

Esta sección documentará cambios mayores realizados después de la versión inicial:

| Versión | Fecha | Cambios | Impacto | Aprobado por |
|---------|-------|---------|---------|--------------|
| 1.0 | 29/09/2025 | Versión inicial con requisitos de alto nivel | N/A | Pendiente |
| | | | | |
| | | | | |

---

## Anexos

### Anexo A: Plantilla de Requisito Detallado

_Esta plantilla se utilizará durante el refinamiento para documentar requisitos con mayor detalle:_

```
ID: [Sistema]-[Tipo]-[Número]
Título: [Nombre descriptivo corto]
Descripción: [Descripción detallada de qué se requiere]
Categoría: [Funcional / No Funcional / Negocio / Transición / Proyecto]
Sistema: [SIGAA / Campus Virtual+ / Sistema Alerta / CRM]
Módulo: [Nombre del módulo específico]
Prioridad: [Must Have / Should Have / Could Have / Won't Have]
Origen: [Stakeholder o fuente que solicitó el requisito]
Justificación: [Por qué es necesario este requisito]
Criterios de Aceptación:
  1. [Criterio medible y verificable]
  2. [Criterio medible y verificable]
  3. [...]
Dependencias: [Lista de requisitos relacionados o prerrequisitos]
Supuestos: [Supuestos asociados al requisito]
Restricciones: [Limitaciones o restricciones]
Impacto si no se implementa: [Consecuencias de no incluir este requisito]
Estimación de esfuerzo: [Story Points / Horas / Días estimados]
Riesgos: [Riesgos identificados relacionados con este requisito]
Notas adicionales: [Cualquier información relevante adicional]
Casos de prueba asociados: [IDs de casos de prueba cuando estén disponibles]
Estado: [Propuesto / Aprobado / En Desarrollo / En Pruebas / Completado]
Versión: [Número de versión del requisito]
Fecha última modificación: [Fecha]
Modificado por: [Nombre]
```

### Anexo B: Glosario de Términos

| Término | Definición |
|---------|------------|
| Matrícula | Proceso de inscripción formal de un estudiante en una carrera y período académico específico |
| Deserción | Abandono definitivo de los estudios por parte de un estudiante |
| Cohorte | Grupo de estudiantes que ingresan juntos en un mismo período académico |
| Malla Curricular | Estructura ordenada de asignaturas que componen un programa de estudios |
| Lead | Persona que ha mostrado interés en estudiar en la institución pero aún no se matricula |
| Funnel de Admisión | Proceso secuencial desde primer contacto hasta matrícula efectiva |
| Dashboard | Panel de visualización de métricas e indicadores clave |
| LMS | Sistema de gestión de aprendizaje (Learning Management System) |
| Sprint | Ciclo de desarrollo ágil de duración fija (2 semanas en este proyecto) |
| Stakeholder | Persona u organización con interés en el proyecto |

_[ESTE GLOSARIO SERÁ EXPANDIDO DURANTE LA FASE DE PLANIFICACIÓN]_

### Anexo C: Referencias a Documentos Relacionados

- **Caso de Negocio:** Transformación Digital Crecer Más v1.0
- **Matriz de Trazabilidad de Requisitos:** [Será creada en siguiente fase]
- **Plan de Gestión del Alcance:** [Referencia al documento cuando esté disponible]
- **EDT/WBS:** EDT.pdf
- **Diccionario EDT:** [Referencia al documento cuando esté disponible]

---

**Documento preparado por:** Ignacio Beltrán - Director de Proyectos  
**Revisado por:** Sebastián Bravo - Director de TI  
**Versión:** 1.0 (Preliminar - Requisitos de Alto Nivel)  
**Fecha de emisión:** 29 de septiembre de 2025  
**Próxima revisión programada:** Durante Fase de Planificación (Semana 2-8 del proyecto)

---

## Notas Finales

Este es un **documento vivo** que evolucionará durante todo el proyecto. Se espera que:

- Se agreguen entre 80-120 requisitos funcionales adicionales durante el refinamiento
- Se detallen los criterios de aceptación con métricas específicas
- Se establezcan las relaciones de trazabilidad completas
- Se validen todos los requisitos con stakeholders mediante talleres y entrevistas
- Se actualice el estado de cada requisito conforme avanza el proyecto

**El equipo de proyecto debe consultar siempre la última versión aprobada de este documento.**