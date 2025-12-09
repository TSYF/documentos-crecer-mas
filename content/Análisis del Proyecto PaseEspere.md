# Análisis del Proyecto PaseEspere: Reflexión sobre Desafíos en Gestión de Proyectos IoT

**Autor:** Tomás Yáñez  
**Rol en el Proyecto:** Arquitecto de Sistemas  
**Fecha:** Noviembre 2025  
**Institución:** Gestión de Proyectos

---

## Resumen Ejecutivo

El presente ensayo analiza críticamente el proyecto PaseEspere, un sistema IoT implementado en locales de Homecenter SODIMAC para optimizar la gestión de flujo de clientes mediante tecnología de visión artificial, sensores de ocupación y dispositivos IoT. Como Arquitecto de Sistemas durante 9-10 meses del desarrollo del proyecto, enfrenté desafíos técnicos complejos (migración de hardware ESP32, rearquitectura completa de seguridad), organizacionales (gestión de prioridades dinámicas, ausencia de procesos formales) e interpersonales significativos (presiones excesivas sobre el equipo, conflictos éticos en el liderazgo).

Este análisis está estructurado siguiendo las 10 Áreas de Conocimiento del PMBOK (6ta edición), identificando las deficiencias en los procesos de gestión de proyectos y proponiendo mejoras basadas en mejores prácticas. El desafío interpersonal más crítico—exigir sacrificios irrazonables al equipo por demandas corporativas—condujo a una profunda reflexión sobre el significado del liderazgo y la importancia de alinear valores personales con la cultura organizacional.

---

## 1. Contexto del Proyecto

### 1.1 Descripción General

**PaseEspere** es un sistema IoT integral implementado en locales de Homecenter SODIMAC que optimiza el flujo de clientes en cajas de auto-atención (SCO - Self Checkout) y cajas tradicionales (POS - Point of Sale). El sistema utiliza:

**Componentes IoT:**

- **Sensores de ocupación de caja SCO:** Raspberry Pi con cámaras (PiCam) ejecutando Python con OpenCV para detectar el estado de ocupación de cada caja SCO
- **Cámaras de tracking de fila:** Sistema de visión artificial con modelos de Deep Learning para reconocer y rastrear individuos en las filas, calculando tiempos de espera estimados
- **Botoneras ESP32:** Dispositivos en cada caja POS que envían constantemente el estado de presión del botón

**Arquitectura de Comunicaciones:**

- Todas las comunicaciones se realizan por MQTTS (MQTT sobre TLS) hacia un broker interno
- **MainCPU:** NUC que actúa como broker MQTT y gestiona la lógica del sistema
- Control de dos televisores (uno por cada tipo de fila) mostrando a qué caja dirigirse o esperar

**Backend Cloud:**

- Infraestructura serverless en Google Cloud Platform (GCP)
- CI/CD con SBOM, DAST, análisis de imágenes, SAST
- Balanceo de carga con NGFW y políticas de seguridad complejas
- Versionamiento de infraestructura con Terraform
- Dashboard de analítica descriptiva con visualizaciones en serie de tiempo

**Funcionalidades:**

- Para POS: Llamado a cajas basado en estado de botoneras
- Para SCO: Dirección a cajas libres basado en sensores de ocupación
- Estimación de tiempo de espera usando análisis de velocidad de avance de fila
- Priorización manual de cajas desde el dashboard
- Desactivación manual de cajas SCO
- Persistencia y analítica de operaciones diarias

### 1.2 Objetivo del Proyecto

Mejorar la experiencia del cliente en Homecenter SODIMAC mediante:

1. Reducción de tiempos de espera percibidos
2. Optimización del flujo de clientes hacia cajas disponibles
3. Generación de datos analíticos sobre patrones de uso y eficiencia operacional
4. Soporte a la estrategia de SODIMAC de incrementar el uso de cajas SCO

### 1.3 Duración y Estado

- **Duración total del proyecto:** Aproximadamente 2 años (al momento del análisis)
- **Participación del analista:** 9-10 meses
- **Estado actual:** Fase de certificación final previo al cierre
- **Despliegue:** Funcionando completamente en 1 local, parcialmente en otro
- **Próximos pasos:** Replicación a otros locales tras certificación exitosa

### 1.4 Equipo del Proyecto

**Estructura del equipo:**

- **Mauricio Marín:** Jefe de Proyecto
- **Tomás Yáñez:** Arquitecto de Sistemas (el analista)
- **Cristobal González:** Full Stack Developer (front-heavy) y Data Scientist - responsable de los modelos ML/DL para tracking de filas y detección de ocupación de cajas SCO
- **Franz Cortez:** Full Stack Developer (back-heavy)
- **Ivan Montecino:** Jefe de Soporte Terreno y Hardware

**Cliente/Sponsor:**

- Homecenter SODIMAC, específicamente dos áreas:
    - Área de gestión de proyectos
    - Área dedicada a impulsar el uso de SCO mediante sistemas y analítica de datos

### 1.5 Responsabilidades del Arquitecto de Sistemas

Durante mi participación en el proyecto, mis responsabilidades incluyeron:

1. **Documentación de Arquitectura:**
    
    - Arquitectura completa del sistema
    - Arquitectura IoT
    - Arquitectura de redes
    - Arquitectura de sistemas de monitoreo y DevOps
    - Diagramas BPMN de procesos recurrentes
2. **Seguridad y Certificación:**
    
    - Pruebas de seguridad y hardening
    - Pentesting y reportes de vulnerabilidades
    - Certificación de seguridad de la plataforma completa
    - Refactorización de todas las comunicaciones para usar TLS con certificados autofirmados
    - Migración de dispositivos IoT a la red interna de SODIMAC
3. **Infraestructura y DevOps:**
    
    - Sistemas de monitoreo de dispositivos y aplicaciones (IoT y Cloud)
    - Pipelines de CI/CD para gestión de versiones, calidad, pruebas y despliegues
    - Migración de infraestructura Cloud de VPS a sistema serverless contenedorizado en GCP
    - Implementación de SBOM, DAST, análisis de imágenes, SAST, balanceo, NGFW con políticas complejas
4. **Hardware y Comunicaciones:**
    
    - Migración de dispositivos ESP8266 a ESP32
    - Cambio de MainCPU de Raspberry Pi 5 a NUC
5. **Gestión (temporal):**
    
    - Durante aproximadamente 2 meses, asumí el rol de líder de equipo, gestionando desarrollo y avances

---

## 2. Análisis desde las Áreas de Conocimiento del PMBOK

### 2.1 Gestión de la Integración del Proyecto

#### 2.1.1 Ausencia de Acta de Constitución

Uno de los hallazgos más significativos fue la **ausencia de un Acta de Constitución formal** (Project Charter). Según el PMBOK, el Acta de Constitución es el documento que autoriza formalmente el proyecto y proporciona al director del proyecto la autoridad para aplicar recursos organizacionales a las actividades del proyecto. La falta de este documento fundamental generó ambigüedad en:

- Los objetivos específicos y medibles del proyecto
- La autoridad y responsabilidades del equipo
- Los supuestos y restricciones iniciales
- Los criterios de éxito del proyecto

Esta deficiencia se manifestó particularmente cuando el cliente cambió sus prioridades hacia el final del proyecto, identificando el tracking de fila como "la piedra angular de la propuesta", a pesar de que inicialmente no estaba completamente definido en el alcance.

#### 2.1.2 Control de Cambios Informal

Durante el breve período como líder de equipo (~2 meses), se implementó Plane.so como herramienta de gestión de solicitudes y cambios. Sin embargo, el proyecto carecía de un **proceso formal de Control Integrado de Cambios** como lo define el PMBOK.

Según el estándar, el proceso "Realizar el Control Integrado de Cambios" debe revisar todas las solicitudes de cambio, aprobar y gestionar cambios a entregables, documentos del proyecto y al plan para la dirección del proyecto. En PaseEspere, los cambios se solicitaban y gestionaban de manera más ad-hoc, sin:

- Un Comité de Control de Cambios (CCB) formal
- Análisis de impacto sistemático en cronograma, costos y riesgos
- Documentación formal de solicitudes de cambio aprobadas/rechazadas
- Un registro de cambios estructurado

Esta informalidad en el control de cambios contribuyó a la volatilidad del alcance y a las presiones constantes sobre el equipo.

### 2.2 Gestión del Alcance del Proyecto

#### 2.2.1 Alcance Dinámico y "Scope Creep"

Al momento de incorporación al proyecto, el alcance estaba "definido a medias", particularmente en lo referente al tracking de fila. Esta situación representa un caso clásico de **scope creep** (expansión del alcance sin control adecuado). El PMBOK enfatiza que la Gestión del Alcance debe incluir procesos para garantizar que el proyecto incluya todo el trabajo requerido, y únicamente el trabajo requerido.

La evolución del tracking de fila de una funcionalidad secundaria a "la piedra angular de la propuesta" ilustra cómo la falta de una **Estructura de Desglose del Trabajo (EDT/WBS)** formal y un proceso de **Validar el Alcance** riguroso puede llevar a cambios significativos en las prioridades del proyecto sin la debida evaluación de impacto.

#### 2.2.2 Ausencia de EDT

La inexistencia de una EDT formal dificultó:

- La descomposición jerárquica del trabajo del proyecto
- La asignación clara de responsabilidades
- La estimación precisa de esfuerzos y recursos
- El seguimiento y control del progreso

#### 2.2.3 Cambios de Prioridad del Cliente

SODIMAC indicó recientemente que "hay más valor en la data de fila que en el resto del sistema", lo que demuestra una **redefinición significativa del alcance** y las prioridades. Esta situación refleja:

- Falta de claridad inicial sobre el valor esperado de cada componente
- Ausencia de un proceso de definición de alcance riguroso en la fase de iniciación
- Necesidad de reuniones frecuentes de reenfoque cuando cambian las prioridades

### 2.3 Gestión del Cronograma del Proyecto

El proyecto operaba bajo una presión temporal constante: **"Cada semana había que tener avance y pivotar agresivamente cuando cambiaban de opinión sobre ciertas cosas"**. Esta situación evidencia varios problemas en la gestión del cronograma:

#### 2.3.1 Plazos Agresivos sin Planificación Realista

La exigencia de avances semanales sin una planificación de cronograma robusta generó:

- Trabajo bajo presión constante
- Necesidad de horas extras excesivas
- Riesgo de burnout en el equipo
- Decisiones técnicas subóptimas por falta de tiempo

El caso más emblemático fue la solicitud de la gerenta comercial para entregar el tracking con un Accuracy mínimo de 0.7 "para la mañana siguiente a las 11am", lo que requirió que Cristobal trabajara toda la noche hasta la madrugada.

#### 2.3.2 Estrategia de Gestión Personal del Tiempo

Ante la volatilidad de prioridades, se desarrolló una estrategia de **reevaluación continua cada 5-15 minutos**. Esta técnica, aunque no convencional, permitió:

- Mantener claridad sobre las prioridades más actuales
- Generar trazabilidad del trabajo realizado
- Responder ágilmente a los cambios de dirección
- Defenderse de cuestionamientos sobre productividad en reuniones diarias

Esta estrategia personal de gestión representa una adaptación pragmática a un entorno de proyecto caótico, pero no sustituye una gestión formal del cronograma a nivel de proyecto.

#### 2.3.3 Ausencia de Cronograma Formal

El proyecto no contaba con:

- Un diagrama de red del cronograma
- Estimaciones de duración basadas en métodos formales
- Identificación de ruta crítica
- Reservas de contingencia para riesgos

### 2.4 Gestión de los Costos del Proyecto

Aunque no se tuvo visibilidad directa en la gestión de costos, se identificaron varias restricciones presupuestarias significativas:

#### 2.4.1 Restricciones de Hardware

"El proyecto en sí no pagaba mucho, por lo que en una ocasión estuvimos limitados en el hardware a utilizar".

Esta restricción presupuestaria impactó directamente en los desafíos técnicos, específicamente en el tracking de personas en fila. La limitación de hardware requirió:

- Frecuencia de captura de imágenes inferior a la ideal
- Refactorización de la solución original (snapshots descargadas) a streaming de imagen
- Tiempo adicional de desarrollo no planificado

#### 2.4.2 Cambios de Hardware No Presupuestados

Los cambios de hardware impuestos por SODIMAC generaron costos adicionales:

**Migración ESP8266 → ESP32:**

- Reemplazo de todas las botoneras existentes
- Costo de nuevos dispositivos
- Tiempo de migración y pruebas

**Migración Pi5 → NUC:**

- Adquisición de hardware x86 más costoso
- Motivado por requisito de cliente para instalar XDR
- Impacto en presupuesto no anticipado

#### 2.4.3 Ausencia de Gestión de Costos Formal

No existían procesos formales de:

- Estimación de costos
- Presupuestación detallada
- Control de costos
- Gestión del valor ganado

### 2.5 Gestión de la Calidad del Proyecto

#### 2.5.1 Requisitos de Accuracy en Modelos ML

La exigencia de un Accuracy mínimo de 0.7 para el modelo de tracking representa un **criterio de calidad específico** para el componente de Machine Learning. Sin embargo, este criterio:

- Fue comunicado tarde en el proyecto
- Requirió trabajo urgente de última hora
- No estaba documentado en requisitos iniciales

#### 2.5.2 Certificación de Seguridad

El proceso de certificación de seguridad con SODIMAC reveló deficiencias en la gestión de calidad:

**Problemas identificados:**

- SODIMAC no comunicó claramente los requisitos de seguridad
- Los controles solicitados estaban basados en proyectos Windows internos de SODIMAC, no todos aplicables al proyecto
- Proceso de preguntas y respuestas lento
- Necesidad de rellenar documentos con "lo más cercano a respuestas válidas" y corregir después

Esta situación evidencia **falta de un proceso de Planificar la Gestión de la Calidad** efectivo que hubiera:

- Definido estándares de calidad relevantes desde el inicio
- Establecido métricas de calidad claras y alcanzables
- Creado un plan de aseguramiento de la calidad
- Definido procesos de control de calidad

#### 2.5.3 Testing y Validación

Se realizaron pruebas exhaustivas en varios aspectos:

- Pentesting de seguridad
- Pruebas de infraestructura cloud
- Validación de dispositivos IoT
- Sin embargo, la naturaleza ad-hoc de estas pruebas (motivadas por requisitos de certificación emergentes) indica ausencia de un plan de gestión de calidad estructurado

### 2.6 Gestión de los Recursos del Proyecto

#### 2.6.1 Escasez de Recursos Humanos

En PaseEspere, existía una clara **escasez de recursos**:

"Solo Cristobal tenía la experticie y el tiempo asignado a este trabajo, el resto del equipo debía estar en otros proyectos frecuentemente".

Esta situación creó:

- Sobrecarga en miembros específicos del equipo
- Dependencia crítica en el conocimiento de individuos (riesgo de persona clave)
- Necesidad de multitarea entre proyectos
- Limitaciones en la capacidad de respuesta ante emergencias

#### 2.6.2 Gestión de Recursos Físicos

Los recursos físicos presentaron múltiples desafíos:

**Cambio de Hardware IoT:**

- ESP8266 original incompatible con la red de SODIMAC
- Necesidad de migrar a ESP32
- Aprendizaje de nueva tecnología mediante consulta con expertos internos y LLMs

**Upgrade de MainCPU:**

- Cambio de Raspberry Pi 5 a NUC
- Motivado por requisito del cliente de instalar XDR (solo disponible para x86)
- Impacto en costos y cronograma no anticipado

#### 2.6.3 Desarrollo del Equipo

Como líder temporal del equipo, enfrenté el desafío de **presiones excesivas** que impactaban negativamente el bienestar del equipo. El caso más crítico fue exigir a Cristobal trabajar toda la noche mientras su hijo le pedía tiempo juntos.

Este evento condujo a la decisión de solicitar regresar al rol de Arquitecto, renunciando al puesto de liderazgo. La reflexión resultante: **"Nada más difícil que pedirle a un hombre hacerle daño a su familia por el bien de una empresa que no lo valora"**.

### 2.7 Gestión de las Comunicaciones del Proyecto

#### 2.7.1 Canales de Comunicación con el Cliente

La comunicación con SODIMAC se gestionaba principalmente a través de:

- Correo electrónico
- Reuniones periódicas

Sin embargo, surgieron **problemas significativos de comunicación**, especialmente en las certificaciones de seguridad. La información llegaba de manera fragmentada ("por gotero"), lo que generaba:

- Retrabajos constantes
- Decisiones técnicas basadas en información incompleta
- Atrasos no planificados
- Frustración en el equipo

#### 2.7.2 Comunicación Interna del Equipo

Aunque no se describe explícitamente un plan de gestión de comunicaciones, las reuniones daily (diarias) servían como mecanismo de coordinación, aunque también se convirtieron en instancias donde se "cuestionaba la utilidad" de los miembros del equipo, lo que generó la necesidad de mantener trazabilidad detallada del trabajo.

#### 2.7.3 Ausencia de Plan de Comunicaciones

No existía un plan formal de gestión de comunicaciones que definiera:

- Requisitos de información de los interesados
- Frecuencia y formato de comunicaciones
- Responsables de comunicar información
- Métodos de distribución
- Escalación de problemas

### 2.8 Gestión de los Riesgos del Proyecto

#### 2.8.1 Ausencia de Gestión Formal de Riesgos

El proyecto **no contaba con un registro de riesgos formal** ni con procesos estructurados de identificación, análisis y respuesta a riesgos.

#### 2.8.2 Riesgos Materializados

Varios riesgos se materializaron sin haber sido identificados o mitigados:

**Incompatibilidad de Hardware con Red del Cliente:**

- **Riesgo:** ESP8266 no compatible con red SODIMAC (24Mbps mínimo)
- **Impacto:** Reemplazo completo de hardware, atrasos, costos adicionales
- **Nota:** "SODIMAC probablemente sabía, pero a nosotros nos tomó por sorpresa"

**Requisitos de Seguridad No Comunicados:**

- **Riesgo:** Requisitos de encriptación en tránsito y certificación XDR
- **Impacto:** Rearquitectura completa de seguridad, cambio de MainCPU
- **Nota:** Información entregada "por gotero" en lugar de al inicio

**Dependencia de Persona Clave:**

- **Riesgo:** Solo Cristobal tenía la experticia y tiempo para ciertos trabajos críticos
- **Impacto:** Cuello de botella, presiones excesivas, riesgo de burnout

**Cambios de Prioridad del Cliente:**

- **Riesgo:** Redefinición de alcance y prioridades durante ejecución
- **Impacto:** Retrabajos, presiones de cronograma, frustración

#### 2.8.3 Estrategias de Respuesta Reactivas

En ausencia de gestión proactiva de riesgos, las respuestas fueron reactivas:

- Trabajo urgente de última hora
- Horas extras excesivas
- Soluciones técnicas subóptimas por presión de tiempo
- Alta rotación en roles de liderazgo (el analista dejó el rol voluntariamente)

### 2.9 Gestión de las Adquisiciones del Proyecto

Aunque no se tuvo visibilidad directa en las adquisiciones formales, se identificaron varios aspectos relevantes:

#### 2.9.1 Hardware IoT

Las adquisiciones de hardware enfrentaron desafíos:

- Selección inicial incorrecta (ESP8266) por falta de especificaciones completas del cliente
- Necesidad de adquisiciones adicionales (ESP32, NUC)
- Falta de análisis make-or-buy formal

#### 2.9.2 Servicios Cloud

Migración de infraestructura:

- De VPS a GCP serverless
- Implementación de servicios de seguridad (NGFW, balanceo, etc.)
- Sin evidencia de proceso formal de adquisiciones

### 2.10 Gestión de los Interesados del Proyecto

#### 2.10.1 Identificación de Interesados

**Interesados principales identificados:**

- Homecenter SODIMAC (Área de proyectos y área de SCO)
- Gerenta comercial (stakeholder de alto poder)
- Equipo interno de desarrollo
- Usuarios finales (clientes de SODIMAC, cajeros)

#### 2.10.2 Conflictos de Interés

Se identificaron conflictos significativos:

**Entre jefaturas internas:**

- Necesidad de "estar preparado para pelear con otras jefaturas"
- Cuestionamientos sobre productividad en reuniones diarias
- Esto motivó la estrategia de documentación cada 5-15 minutos

**Con el cliente:**

- Expectativas no alineadas con capacidad del equipo
- Cambios de prioridades sin proceso formal
- Comunicación ineficiente de requisitos

#### 2.10.3 Gestión de Expectativas

La falta de un **plan de involucramiento de interesados** resultó en:

- Expectativas no gestionadas
- Conflictos evitables
- Presiones excesivas sobre el equipo
- Desmotivación y desgaste

---

## 3. Desafíos Principales y Estrategias de Solución

### 3.1 Desafíos Técnicos

#### 3.1.1 Migración de ESP8266 a ESP32

**Contexto del desafío:** Las botoneras originales del proyecto utilizaban microcontroladores ESP8266. SODIMAC requiere que todos los dispositivos IoT operen en su red interna, la cual tiene requisitos mínimos de:

- Ancho de banda base de 24Mbps
- Encriptación en tránsito
- Protocolos de comunicación seguros

Los ESP8266 no cumplían con estos requisitos, específicamente con el ancho de banda necesario.

**Estrategias implementadas:**

1. **Aprendizaje Acelerado:**
    
    - Consulta con expertos en electrónica dentro de la empresa
    - Utilización de Large Language Models (LLMs) para documentación y casos de uso
    - Revisión de documentación oficial de Espressif (fabricante)
2. **Prototipado y Validación:**
    
    - Desarrollo de prototipos con ESP32
    - Pruebas de conectividad en ambiente de SODIMAC
    - Validación de compatibilidad con MQTTS
3. **Migración Gradual:**
    
    - Reemplazo progresivo de dispositivos
    - Mantenimiento de compatibilidad durante transición

**Resultado:** Migración exitosa a ESP32, con dispositivos operando en la red de SODIMAC cumpliendo todos los requisitos de conectividad y seguridad.

#### 3.1.2 Rearquitectura Completa de Seguridad

**Contexto del desafío:** El proceso de certificación de seguridad de SODIMAC requirió:

- Encriptación en tránsito para todas las comunicaciones IoT
- Refactorización de protocolos de comunicación
- Implementación de TLS con certificados autofirmados
- Cambio de MainCPU para soportar XDR (Extended Detection and Response)
- Migración completa de infraestructura Cloud

**Componentes de la rearquitectura:**

1. **Comunicaciones IoT:**
    
    - Implementación de MQTTS (MQTT sobre TLS)
    - Generación y gestión de certificados autofirmados
    - Configuración de broker MQTT con autenticación y autorización
2. **Infraestructura Cloud:**
    
    - Migración de VPS a arquitectura serverless en GCP
    - Implementación de contenedores
    - CI/CD con múltiples capas de seguridad:
        - SBOM (Software Bill of Materials)
        - DAST (Dynamic Application Security Testing)
        - SAST (Static Application Security Testing)
        - Análisis de imágenes de contenedores
    - Balanceo de carga con Google Cloud Armor
    - NGFW (Next-Generation Firewall) con políticas complejas
    - Políticas de seguridad inteligentes
3. **Hardware:**
    
    - Cambio de Raspberry Pi 5 a NUC (arquitectura x86)
    - Motivado por requisito de XDR compatible solo con x86
    - Reconfiguración completa del MainCPU
4. **Infraestructura como Código:**
    
    - Versionamiento con Terraform
    - Reproducibilidad de ambientes
    - Control de cambios en infraestructura

**Estrategias implementadas:**

1. **Pentesting Interno:**
    
    - Realización de pruebas de penetración
    - Identificación de vulnerabilidades
    - Remediación de hallazgos
    - Documentación de procesos de hardening
2. **Consulta de Mejores Prácticas:**
    
    - Referencia a OWASP Top 10
    - Implementación de Content Security Policy
    - Configuración de headers de seguridad (X-Frame-Options, Permissions Policy)
    - Consulta de documentación de Google Cloud Security
3. **Testing Exhaustivo:**
    
    - Validación de todas las capas de seguridad
    - Pruebas de conectividad end-to-end
    - Verificación de cifrado en todos los canales

**Resultado:** Sistema completamente refactorizado cumpliendo con todos los requisitos de seguridad de SODIMAC, aunque el proceso consumió tiempo significativo y requirió esfuerzo considerable del Arquitecto de Sistemas (único miembro del equipo con la experticia necesaria).

#### 3.1.3 Optimización de Tracking de Fila con Hardware Limitado

**Contexto del desafío:** El tracking de personas en fila requería una frecuencia de captura de imágenes mayor de la que se podía lograr con el hardware disponible y las restricciones de red. La solución original descargaba snapshots individuales, lo que no proporcionaba la frecuencia necesaria.

**Estrategias implementadas:**

1. **Refactorización de Arquitectura de Captura:**
    
    - Cambio de snapshots descargadas a streaming de imagen continuo
    - Procesamiento local en la Raspberry Pi asociada a la cámara
    - Envío de resultados procesados en lugar de imágenes raw
2. **Optimización de Modelos ML:**
    
    - Ajuste de modelos de Deep Learning para operar con menor frecuencia de frames
    - Implementación de técnicas de interpolación y tracking predictivo
    - Trabajo extensivo de Cristobal para alcanzar Accuracy > 0.7

**Resultado:** Sistema de tracking operacional dentro de las restricciones de hardware, aunque requirió trabajo urgente de última hora para cumplir con el deadline impuesto.

### 3.2 Desafíos Organizacionales

#### 3.2.1 Gestión de Prioridades Dinámicas

**Contexto del desafío:** "Cada semana había que tener avance y pivotar agresivamente cuando cambiaban de opinión sobre ciertas cosas".

El proyecto operaba en un entorno de prioridades altamente volátiles, sin procesos formales de control de cambios. Adicionalmente, como Arquitecto de Sistemas, debía balancear trabajo en PaseEspere con otros proyectos de la organización.

**Estrategias implementadas:**

1. **Técnica de Reevaluación Continua:**
    - Anotación en libreta cada 5-15 minutos del estado actual del trabajo
    - Reevaluación constante de prioridades
    - Generación de trazabilidad del trabajo realizado
    - Preparación para "pelear" en reuniones diarias

**Beneficios de esta técnica:**

- Mantenimiento de claridad sobre prioridades más actuales
- Agilidad para responder a cambios de dirección
- Defensa contra cuestionamientos de productividad con evidencia concreta
- Streamlining de procesos y features

2. **Implementación de Plane.so:**
    
    - Durante el período como líder de equipo, implementación de Plane.so para gestión de tareas
    - Seguimiento de solicitudes de cambios
    - Visibilidad de work in progress
    - Aunque no era un proceso formal de control de cambios, proporcionaba estructura básica
3. **Reuniones de Reenfoque:**
    
    - Convocatoria de reuniones cuando SODIMAC cambiaba prioridades
    - Realineación del equipo hacia lo más importante
    - Clarificación de expectativas

**Limitaciones:** Esta estrategia personal, aunque efectiva a nivel individual, no sustituía la necesidad de procesos formales de gestión del proyecto. Representaba más una adaptación al caos que una solución estructural.

#### 3.2.2 Comunicación Deficiente con el Cliente

**Contexto del desafío:** Los problemas más críticos de comunicación se presentaron en el proceso de certificación de seguridad:

- **Información fragmentada:** Requisitos entregados "por gotero"
- **Controles no aplicables:** Documentos basados en proyectos Windows internos de SODIMAC
- **Respuestas lentas:** SODIMAC demoraba en responder consultas
- **Presión de cronograma:** El proyecto debía avanzar rápidamente

**Estrategias implementadas:**

1. **Approach Pragmático:**
    
    - Completar documentos de certificación con "lo más cercano a respuestas válidas"
    - Enviar para revisión
    - Iterar basándose en correcciones de SODIMAC
2. **Preguntas Estratégicas:**
    
    - Identificar controles que claramente no aplican al proyecto
    - Priorizar preguntas sobre controles críticos
    - Documentar supuestos cuando no hay respuesta
3. **Paralelización de Trabajo:**
    
    - No esperar respuestas completas para avanzar
    - Trabajar en elementos de certeza mientras se esperan aclaraciones
    - Preparar múltiples escenarios posibles

**Resultado:** Aunque la estrategia permitió avanzar, generó:

- Retrabajos cuando los supuestos eran incorrectos
- Frustración en el equipo
- Atrasos no planificados
- Incremento en el esfuerzo total del proyecto

**Reflexión:** Esta situación evidencia la importancia crítica de un proceso formal de **Gestión de las Comunicaciones** y de la **Gestión de los Interesados**. Un plan de comunicaciones bien diseñado habría establecido:

- Canales formales de comunicación
- Tiempos de respuesta esperados
- Procesos de escalación
- Formato y contenido de comunicaciones

#### 3.2.3 Información Tardía sobre Requisitos de Hardware

**Contexto del desafío:** "SODIMAC probablemente sabía, pero a nosotros nos tomó por sorpresa y nos atrasó y aumentó costos. Deberían habernos dicho antes que requerían hardware específico".

Los requisitos de:

- Ancho de banda mínimo de 24Mbps
- Compatibilidad con red interna
- Requisitos de XDR para x86

No fueron comunicados al inicio del proyecto, resultando en selección incorrecta de hardware inicial.

**Estrategias implementadas:**

1. **Respuesta Reactiva:**
    
    - Identificación rápida de alternativas (ESP32, NUC)
    - Priorización de migración de hardware
    - Absorción del impacto en cronograma y costos
2. **Documentación de Lecciones:**
    
    - Registro de problemas causados por información tardía
    - Identificación de necesidad de validación temprana de requisitos de infraestructura del cliente

**Resultado:** El proyecto pudo adaptarse, pero a un costo significativo en tiempo, esfuerzo y presupuesto que pudo haberse evitado con mejor gestión de requisitos y comunicación al inicio.

### 3.3 Desafíos Interpersonales y Éticos

#### 3.3.1 El Dilema Ético: Presiones Excesivas sobre el Equipo

**Contexto del desafío:** Este fue, según la reflexión personal, "el desafío interpersonal más difícil". Como líder temporal del equipo, enfrenté la situación de transmitir presiones corporativas excesivas al equipo.

**El caso crítico:** La gerenta comercial solicitó entregar el modelo de tracking con un Accuracy mínimo de 0.7 "para la mañana siguiente a las 11am". Esto requirió que Cristobal trabajara toda la noche hasta la madrugada, mientras su micrófono capturaba a su hijo pidiéndole tiempo juntos.

**Conflicto de valores:**

- **Presión corporativa:** Cumplir con el deadline del cliente
- **Responsabilidad hacia el equipo:** Proteger el bienestar de los miembros
- **Realidad familiar:** Impacto en la vida personal de Cristobal
- **Valoración empresarial:** La empresa no valoraba adecuadamente el sacrificio del equipo

**Reflexión personal:** "Nada más difícil que pedirle a un hombre hacerle daño a su familia por el bien de una empresa que no lo valora".

#### 3.3.2 Estrategias Implementadas (o No Implementadas)

**Lo que se hizo:**

1. **Cumplimiento de la exigencia:** Se transmitió la presión al equipo
2. **Participación en el esfuerzo:** Se trabajó junto al equipo durante el período crítico
3. **Reconocimiento del problema:** Se identificó la situación como inaceptable

**Lo que no se hizo (pero debió hacerse):**

1. **Pushback hacia arriba:** No se desafió la viabilidad del deadline con la gerencia
2. **Negociación de alternativas:** No se exploraron soluciones intermedias
3. **Protección del equipo:** No se establecieron límites razonables

**Consecuencias:**

- Cristobal cumplió el objetivo técnico (Accuracy > 0.7)
- Impacto negativo en su bienestar y vida familiar
- Reflexión crítica sobre el rol del liderazgo
- Decisión de solicitar regresar al rol de Arquitecto

#### 3.3.3 Lecciones sobre Liderazgo

**Aprendizajes clave:**

1. **El liderazgo tiene significados diferentes:** "En cada empresa y equipo la jefatura significa algo distinto. En el caso de esta empresa, el mayor desafío era luchar por un trato y compensación justos para mi equipo".
    
2. **Límites personales en el liderazgo:** "Aprendí que quizás no quiero ser jefe en cualquier empresa, porque hay cosas que no estoy dispuesto a hacer".
    
3. **Alineación de valores:** El liderazgo efectivo requiere alineación entre valores personales y cultura organizacional. Cuando esta alineación no existe, el conflicto es inevitable.
    
4. **Responsabilidad hacia el equipo:** Un líder tiene la responsabilidad de proteger a su equipo de exigencias irrazonables, incluso si esto implica conflicto con niveles superiores.
    
5. **Sostenibilidad:** Las prácticas de "trabajo heroico" constante no son sostenibles y eventualmente dañan tanto al equipo como a los resultados del proyecto.
    

#### 3.3.4 Contexto Cultural Organizacional

La situación descrita no era un evento aislado sino reflejo de una **cultura organizacional** que:

- Normaliza horas extras excesivas
- Prioriza entregas de corto plazo sobre sostenibilidad
- No valora adecuadamente el sacrificio del equipo
- Genera conflictos entre jefaturas
- Cuestiona la productividad en lugar de apoyar

Esta cultura, común en algunas organizaciones tecnológicas, es contraria a las mejores prácticas de gestión de proyectos y recursos humanos, y genera:

- Alta rotación de personal
- Burnout
- Baja calidad por apresuramiento
- Desmotivación
- Pérdida de talento

---

## 4. Análisis de Causa Raíz de los Desafíos

### 4.1 Deficiencias en la Iniciación del Proyecto

La ausencia de un Acta de Constitución y de una definición clara inicial del alcance crearon una **base inestable** para todo el proyecto. Sin un documento fundacional que estableciera:

- Objetivos medibles
- Autoridad y responsabilidades
- Supuestos y restricciones
- Criterios de éxito

El proyecto quedó vulnerable a cambios constantes y falta de alineación entre stakeholders.

### 4.2 Ausencia de Procesos de Gestión Formal

La falta de procesos formales en múltiples áreas (cambios, riesgos, comunicaciones) generó un **entorno reactivo** donde el equipo constantemente respondía a crisis en lugar de prevenir problemas.

**Procesos faltantes críticos:**

- Gestión de cambios integrada
- Identificación y gestión de riesgos
- Plan de gestión de comunicaciones
- Planificación del cronograma
- Gestión de la calidad
- Gestión de interesados

### 4.3 Desconexión entre Áreas Organizacionales

Los conflictos entre jefaturas y la falta de comunicación clara entre SODIMAC y el equipo de desarrollo evidencian **problemas de gobernanza** y gestión de interesados a nivel organizacional.

### 4.4 Restricciones de Recursos

El proyecto operaba con recursos humanos y financieros limitados, lo que amplificaba el impacto de cualquier cambio o problema imprevisto.

**Manifestaciones:**

- Un solo miembro del equipo con tiempo completo (Cristobal)
- Resto del equipo compartido con otros proyectos
- Limitaciones presupuestarias en hardware
- Único especialista en seguridad (el Arquitecto)

### 4.5 Cultura Organizacional

La normalización de exigencias irrazonables (entregas de última hora, horas extras excesivas) refleja una **cultura organizacional problemática** que prioriza resultados de corto plazo sobre la sostenibilidad y el bienestar del equipo.

Esta cultura genera:

- Decisiones subóptimas por presión de tiempo
- Desgaste del equipo
- Rotación de personal
- Conflictos éticos para líderes
- Calidad comprometida

### 4.6 Comunicación Deficiente con el Cliente

SODIMAC no proporcionó información completa y oportuna sobre:

- Requisitos de infraestructura
- Estándares de seguridad
- Prioridades del proyecto

Esta falta de comunicación efectiva generó:

- Selección incorrecta de hardware inicial
- Retrabajos constantes
- Atrasos no planificados
- Incremento en costos

### 4.7 Alcance Mal Definido

La definición "a medias" del alcance inicial, particularmente del tracking de fila, permitió que esta funcionalidad evolucionara de componente secundario a "piedra angular" sin proceso formal de evaluación de impacto.

---

## 5. Propuestas de Mejora

Basándose en el análisis de los desafíos y en las mejores prácticas del PMBOK, se proponen las siguientes mejoras para proyectos similares:

### 5.1 En la Iniciación del Proyecto

**5.1.1 Desarrollo de Acta de Constitución:**

- Documentar formalmente objetivos, alcance, stakeholders, y criterios de éxito
- Obtener firmas de aprobación de sponsors y stakeholders clave
- Establecer claramente la autoridad del director/jefe de proyecto
- Definir supuestos y restricciones explícitamente
- Identificar riesgos de alto nivel

**5.1.2 Identificación Temprana de Requisitos Técnicos:**

- Realizar análisis exhaustivo de infraestructura del cliente antes de seleccionar hardware
- Validar requisitos de red, seguridad, y compatibilidad en fase de diseño
- Incluir margen para requisitos no documentados inicialmente
- Solicitar documentación completa de estándares y políticas del cliente

**5.1.3 Identificación Completa de Interesados:**

- Mapear todos los interesados del proyecto
- Analizar su poder, interés, e influencia
- Desarrollar estrategias de involucramiento específicas
- Identificar expectativas y preocupaciones de cada grupo

### 5.2 En la Planificación

**5.2.1 Desarrollo de EDT Completa:**

- Descomponer el trabajo en paquetes gestionables
- Asignar responsabilidades claras para cada paquete de trabajo
- Facilitar estimaciones realistas de esfuerzo y duración
- Establecer base para seguimiento y control

**5.2.2 Cronograma Realista:**

- Estimar duraciones basándose en datos históricos y capacidad real del equipo
- Incluir buffers para riesgos e incertidumbres
- Identificar dependencias entre tareas
- Establecer hitos significativos
- Comunicar el cronograma a todos los stakeholders

**5.2.3 Plan de Gestión de Riesgos:**

- Identificar riesgos técnicos, organizacionales, e interpersonales
- Analizar probabilidad e impacto de cada riesgo
- Desarrollar estrategias de respuesta (evitar, transferir, mitigar, aceptar)
- Establecer disparadores y propietarios de riesgos
- Mantener registro de riesgos actualizado

**Riesgos que debieron identificarse en PaseEspere:**

- Incompatibilidad de hardware con infraestructura del cliente (Alta probabilidad, Alto impacto)
- Requisitos de seguridad no comunicados (Media probabilidad, Alto impacto)
- Dependencia crítica en persona clave (Alta probabilidad, Alto impacto)
- Cambios de alcance por cliente (Alta probabilidad, Medio-Alto impacto)

**5.2.4 Plan de Gestión de Comunicaciones:**

- Definir requisitos de información de cada stakeholder
- Establecer canales, frecuencia y formato de comunicaciones
- Definir tiempos de respuesta esperados
- Establecer procesos de escalación
- Asignar responsables de comunicación

**5.2.5 Plan de Gestión de la Calidad:**

- Definir estándares de calidad aplicables
- Establecer métricas de calidad específicas y medibles
- Planificar actividades de aseguramiento de calidad
- Definir procesos de control de calidad
- Establecer criterios de aceptación para cada entregable

**5.2.6 Presupuesto Detallado:**

- Estimar costos de recursos humanos
- Incluir costos de hardware, software, e infraestructura
- Establecer reserva de contingencia
- Definir procesos de control de costos
- Establecer autoridad para aprobación de gastos

### 5.3 En la Ejecución

**5.3.1 Liderazgo Ético y Sostenible:**

- Establecer límites razonables de horas de trabajo
- Proteger al equipo de exigencias irrazonables
- Practicar pushback constructivo hacia arriba cuando sea necesario
- Priorizar el bienestar del equipo junto con los resultados del proyecto
- Reconocer que el "trabajo heroico" no es sostenible

**5.3.2 Desarrollo del Equipo:**

- Implementar prácticas de pair programming y knowledge sharing para reducir dependencia en individuos
- Proporcionar tiempo para capacitación y aprendizaje
- Rotar responsabilidades para desarrollar capacidades en múltiples miembros
- Celebrar logros y reconocer contribuciones

**5.3.3 Comunicación Proactiva con Cliente:**

- Reuniones regulares de estado con SODIMAC
- Comunicación temprana de problemas y riesgos
- Solicitud proactiva de información necesaria
- Documentación de todos los acuerdos y decisiones
- Escalación oportuna cuando hay falta de respuesta

### 5.4 En el Monitoreo y Control

**5.4.1 Control Integrado de Cambios:**

- Establecer Comité de Control de Cambios (CCB)
- Definir proceso formal para solicitud, evaluación, y aprobación de cambios
- Analizar impacto de cambios en alcance, cronograma, costos, y riesgos
- Documentar todas las decisiones de cambios
- Comunicar cambios aprobados a todos los stakeholders

**5.4.2 Gestión del Valor Ganado:**

- Implementar seguimiento de valor ganado (EVM)
- Monitorear variaciones de cronograma y costos
- Proyectar costos y fechas de finalización
- Tomar acciones correctivas oportunas

**5.4.3 Revisiones de Calidad:**

- Realizar auditorías de calidad periódicas
- Validar que entregables cumplen criterios de aceptación
- Implementar mejoras de proceso basadas en lecciones aprendidas

**5.4.4 Monitoreo de Riesgos:**

- Revisar registro de riesgos regularmente
- Identificar nuevos riesgos emergentes
- Evaluar efectividad de respuestas a riesgos
- Actualizar estrategias de respuesta según sea necesario

### 5.5 En el Cierre

**5.5.1 Proceso Formal de Lecciones Aprendidas:**

- Realizar sesión de retrospectiva con todo el equipo
- Documentar qué funcionó bien y qué debe mejorarse
- Identificar mejores prácticas para futuros proyectos
- Archivar documentación del proyecto
- Compartir conocimiento con la organización

**Nota:** PaseEspere aún no ha realizado proceso formal de lecciones aprendidas, lo cual es una oportunidad perdida de capturar conocimiento valioso.

**5.5.2 Validación de Alcance:**

- Verificar que todos los entregables cumplen criterios de aceptación
- Obtener aceptación formal del cliente
- Documentar cualquier trabajo pendiente o defecto conocido

**5.5.3 Transición a Operaciones:**

- Proporcionar documentación completa
- Capacitar al equipo de soporte
- Establecer acuerdos de nivel de servicio (SLA)
- Transferir conocimiento de manera estructurada

### 5.6 A Nivel Organizacional

**5.6.1 Cultura de Proyectos:**

- Promover uso de metodologías de gestión de proyectos
- Proporcionar capacitación en PMBOK o framework relevante
- Establecer PMO (Project Management Office) para estandarización
- Reconocer y recompensar buenas prácticas de gestión

**5.6.2 Cultura de Trabajo Sostenible:**

- Eliminar normalización de horas extras excesivas
- Establecer políticas de balance trabajo-vida
- Valorar y recompensar trabajo de calidad sobre "heroísmo"
- Crear ambiente psicológicamente seguro donde es aceptable decir "no"

**5.6.3 Gestión del Talento:**

- Desarrollar planes de carrera para retener talento
- Proporcionar compensación justa
- Reconocer contribuciones del equipo
- Invertir en desarrollo profesional

---

## 6. Conclusiones y Lecciones Aprendidas

### 6.1 Sobre la Gestión de Proyectos

**6.1.1 La importancia de los procesos de iniciación:** La ausencia de un Acta de Constitución y definición clara del alcance al inicio del proyecto PaseEspere generó problemas que se manifestaron durante toda la ejecución. Esta experiencia valida la sabiduría del PMBOK: invertir tiempo en la iniciación y planificación previene costosos problemas posteriores.

**6.1.2 Los procesos formales no son burocracia innecesaria:** En ausencia de procesos formales de gestión (cambios, riesgos, comunicaciones), el proyecto se volvió caótico y reactivo. Los procesos del PMBOK, lejos de ser burocracia, proporcionan estructura que permite al equipo trabajar eficientemente y anticipar problemas.

**6.1.3 La gestión de riesgos es fundamental:** Múltiples riesgos se materializaron en PaseEspere sin haber sido identificados o mitigados. Una gestión proactiva de riesgos habría permitido:

- Identificar tempranamente incompatibilidades de hardware
- Anticipar cambios de prioridades del cliente
- Preparar planes de contingencia
- Reducir impacto cuando los riesgos se materializan

**6.1.4 La comunicación efectiva es crítica:** Los problemas de comunicación con SODIMAC (información fragmentada, requisitos no comunicados, respuestas lentas) generaron retrabajos, atrasos, y frustración. Un plan de comunicaciones formal habría establecido expectativas claras y procesos de escalación.

**6.1.5 El alcance debe estar bien definido:** La evolución del tracking de fila de funcionalidad secundaria a "piedra angular" sin proceso formal de evaluación de impacto ilustra los peligros del scope creep. El alcance debe definirse claramente al inicio y los cambios deben gestionarse formalmente.

### 6.2 Sobre el Liderazgo y lo Interpersonal

**6.2.1 El liderazgo implica proteger al equipo:** Un líder efectivo debe actuar como escudo para su equipo, protegiéndolo de exigencias irrazonables. El caso de Cristobal trabajando toda la noche mientras su hijo le pedía tiempo ilustra el costo humano de fallar en esta responsabilidad.

**6.2.2 Los valores personales importan:** La experiencia en PaseEspere enseñó que el liderazgo en algunas organizaciones implica acciones que pueden no alinearse con valores personales. Es importante reconocer estos conflictos y tomar decisiones conscientes sobre qué tipo de líder se quiere ser y en qué tipo de organización.

**6.2.3 La cultura organizacional determina el éxito:** Una cultura que normaliza horas extras excesivas, no valora al equipo, y prioriza entregas de corto plazo sobre sostenibilidad es tóxica y contraproducente. Los líderes individuales pueden hacer diferencia, pero el cambio cultural requiere acción a nivel organizacional.

**6.2.4 El "trabajo heroico" no es sostenible:** Las prácticas de trabajo bajo presión constante, entregas de última hora, y sacrificios personales excesivos no son sostenibles. Eventualmente llevan a burnout, rotación de personal, y calidad comprometida. Los proyectos deben planificarse para ser completados con ritmo sostenible de trabajo.

**6.2.5 Es válido establecer límites:** La decisión de solicitar regresar al rol de Arquitecto después de la experiencia como líder no es fracaso sino reconocimiento de límites personales. No todos deben aspirar a liderazgo, y no todo liderazgo es apropiado para toda persona.

### 6.3 Sobre Aspectos Técnicos

**6.3.1 La validación temprana de requisitos de infraestructura es crucial:** Los problemas con hardware incompatible (ESP8266, luego Pi5) pudieron evitarse con validación temprana de los requisitos de red y seguridad de SODIMAC. Siempre validar compatibilidad con el ambiente del cliente antes de seleccionar tecnologías.

**6.3.2 La seguridad debe integrarse desde el diseño:** La rearquitectura completa de seguridad fue costosa en tiempo y esfuerzo. Integrar seguridad desde el diseño inicial (Security by Design) es más eficiente que retrofitting posterior.

**6.3.3 Las restricciones de recursos impactan soluciones técnicas:** Las limitaciones de hardware y presupuesto requirieron soluciones creativas (streaming en lugar de snapshots). Es importante comunicar claramente el impacto de restricciones de recursos en la calidad y capacidades del sistema.

**6.3.4 La documentación técnica es inversión:** El tiempo invertido en documentar arquitecturas (sistema completo, IoT, redes, DevOps) demostró ser valioso para onboarding de nuevos miembros, comunicación con stakeholders, y toma de decisiones técnicas.

### 6.4 Lecciones Transferibles a Futuros Proyectos

**6.4.1 Para Iniciación:**

- Siempre desarrollar Acta de Constitución formal
- Validar requisitos de infraestructura del cliente tempranamente
- Identificar y analizar stakeholders comprehensivamente
- Documentar supuestos y restricciones explícitamente

**6.4.2 Para Planificación:**

- Desarrollar EDT completa para descomposición del trabajo
- Crear cronograma realista con buffers
- Implementar plan de gestión de riesgos
- Establecer plan de comunicaciones formal
- Definir estándares y métricas de calidad

**6.4.3 Para Ejecución:**

- Practicar liderazgo ético y sostenible
- Proteger al equipo de exigencias irrazonables
- Comunicar proactivamente con el cliente
- Implementar knowledge sharing para reducir dependencias

**6.4.4 Para Control:**

- Establecer proceso formal de control de cambios
- Monitorear progreso con métricas objetivas
- Revisar y actualizar riesgos regularmente
- Tomar acciones correctivas oportunamente

**6.4.5 Para Cierre:**

- Realizar sesión formal de lecciones aprendidas
- Documentar conocimiento para futuros proyectos
- Obtener aceptación formal del cliente
- Celebrar logros del equipo

### 6.5 Reflexión Final

El proyecto PaseEspere, a pesar de sus desafíos organizacionales e interpersonales, está logrando sus objetivos técnicos. El sistema está funcionando, está en fase de certificación final, y hay planes de replicación a otros locales. Técnicamente, el proyecto puede considerarse un éxito.

Sin embargo, el costo humano fue alto. La experiencia ilustra que el éxito del proyecto no debe medirse únicamente en términos de entregables técnicos, sino también en términos del impacto en las personas involucradas. Un proyecto verdaderamente exitoso es aquel que logra sus objetivos técnicos mientras mantiene el bienestar del equipo.

La ausencia de procesos formales de gestión de proyectos no impidió la entrega técnica, pero sí generó caos, estrés, conflictos, y costos ocultos significativos. La pregunta no es si el proyecto pudo completarse sin estos procesos (claramente sí), sino si pudo completarse de mejor manera con ellos (definitivamente sí).

El análisis del proyecto PaseEspere desde la perspectiva del PMBOK revela claramente que las mejores prácticas de gestión de proyectos no son teóricas o académicas, sino profundamente prácticas. Cada proceso, cada documento, cada análisis recomendado por el PMBOK responde a problemas reales que proyectos reales enfrentan. La experiencia en PaseEspere valida estos principios al demostrar, mediante su ausencia, el valor que proporcionan.

Finalmente, la experiencia más importante es personal: la comprensión de que el liderazgo no es solo sobre completar tareas, sino sobre cómo se completan y a qué costo. Es sobre valores, límites, y el tipo de líder que se elige ser. Y a veces, la decisión más valiente no es aceptar más responsabilidad, sino reconocer cuándo algo no está alineado con quién se es.

---

## Referencias

### Gestión de Proyectos

1. Project Management Institute. (2017). _Guía del PMBOK®: Guía de los Fundamentos para la Dirección de Proyectos_ (Sexta edición). Newtown Square, PA: Project Management Institute.
    
2. Kerzner, H. (2017). _Project Management: A Systems Approach to Planning, Scheduling, and Controlling_ (12th ed.). Wiley.
    
3. Schwalbe, K. (2015). _Information Technology Project Management_ (8th ed.). Cengage Learning.
    

### Seguridad en Aplicaciones Web

4. Mozilla Developer Network. (s.f.). _Content Security Policy (CSP)_. Recuperado de https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP
    
5. Mozilla Developer Network. (s.f.). _X-Frame-Options_. Recuperado de https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options
    
6. Mozilla Developer Network. (s.f.). _Permissions Policy_. Recuperado de https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Permissions_Policy
    
7. Content Security Policy. (s.f.). _CSP Reference & Examples_. Recuperado de https://content-security-policy.com/
    
8. OWASP Foundation. (s.f.). _OWASP Top 10 - 2021: Los diez riesgos más críticos en aplicaciones web_. Recuperado de https://owasp.org/Top10/es/
    

### Infraestructura Cloud y Seguridad

9. Google Cloud. (s.f.). _Google Cloud Armor: Protección contra ataques DDoS y aplicación de políticas de seguridad_. Recuperado de https://cloud.google.com/security/products/armor#documentation
    
10. Google Cloud. (s.f.). _Application Load Balancer: Balanceo de carga para aplicaciones HTTP(S)_. Recuperado de https://docs.cloud.google.com/load-balancing/docs/application-load-balancer?hl=es
    

### IoT y Hardware

11. Espressif Systems. (s.f.). _ESP-IDF Programming Guide_. Recuperado de https://docs.espressif.com/projects/esp-idf/en/stable/esp32/index.html

### Metodologías Ágiles y Gestión de Proyectos de Software

12. Schwaber, K., & Sutherland, J. (2020). _The Scrum Guide: The Definitive Guide to Scrum: The Rules of the Game_. Scrum.org.
    
13. Beck, K., et al. (2001). _Manifesto for Agile Software Development_. Agile Alliance.
    

### Arquitectura de Sistemas y DevOps

14. Bass, L., Clements, P., & Kazman, R. (2012). _Software Architecture in Practice_ (3rd ed.). Addison-Wesley Professional.
    
15. Kim, G., Humble, J., Debois, P., & Willis, J. (2016). _The DevOps Handbook: How to Create World-Class Agility, Reliability, and Security in Technology Organizations_. IT Revolution Press.
    

### Ética en Gestión de Proyectos

16. Project Management Institute. (2020). _Code of Ethics and Professional Conduct_. Newtown Square, PA: Project Management Institute.

---

**Fin del Documento**