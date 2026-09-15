# Visión y Alcance del Sistema

## 1. Introducción

El presente documento define la visión y el alcance del sistema **SIGTAM-EPS**, una plataforma integral orientada a la gestión de la atención médica, los turnos de pacientes y la dispensación de medicamentos en una Entidad Promotora de Salud (EPS). El propósito de este documento es servir como marco de referencia común para el equipo de desarrollo, los interesados del negocio y los responsables de la validación, de modo que exista una comprensión unificada sobre qué hará el sistema, para quién lo hará y bajo qué condiciones operará.

## 2. Visión del Sistema

### 2.1 Declaración de visión

**SIGTAM-EPS** será una plataforma integrada que centralice y automatice la gestión de la atención médica, la administración de turnos presenciales y virtuales, y la dispensación de medicamentos tanto en farmacia como a domicilio para una EPS. El sistema proporcionará trazabilidad completa del proceso asistencial, optimizará los tiempos de espera mediante algoritmos de priorización clínica y notificaciones en tiempo real, y garantizará la entrega oportuna de medicamentos mediante la gestión inteligente de inventarios y rutas logísticas optimizadas.

### 2.2 Objetivo general

Desarrollar una plataforma de software que integre los procesos de atención, turnos y medicamentos de una EPS, mejorando la experiencia del paciente, la eficiencia operativa del personal de salud y la calidad del servicio, con soporte en mecanismos de notificación, trazabilidad, auditoría y optimización.

### 2.3 Objetivos específicos

1. Integrar en un único sistema los módulos de atención médica, gestión de turnos y gestión de medicamentos.
2. Automatizar la asignación, priorización y seguimiento de turnos presenciales y virtuales en tiempo real.
3. Digitalizar el registro de consultas, diagnósticos y fórmulas médicas electrónicas, vinculándolas automáticamente con el módulo de farmacia.
4. Optimizar la gestión de inventarios farmacéuticos mediante alertas de stock mínimo y vencimiento.
5. Coordinar la entrega de medicamentos en farmacia y a domicilio mediante rutas optimizadas y re-optimización dinámica.
6. Garantizar la trazabilidad y auditoría de todo el proceso asistencial y farmacéutico, cumpliendo con normativas legales aplicables.
7. Proporcionar información estadística en tiempo real para la toma de decisiones operativas y estratégicas.

### 2.4 Beneficios esperados

| Beneficio | Descripción | Actor |
|---|---|---|
| Reducción de tiempos de espera | Priorización clínica y turnos virtuales | Pacientes |
| Eliminación de filas físicas | Check-in por QR y turnos remotos | Pacientes |
| Continuidad del tratamiento | Notificaciones y entrega a domicilio | Pacientes crónicos |
| Eficiencia operativa | Automatización de turnos y farmacia | Personal de salud |
| Control de inventario | Alertas de stock y vencimiento | Auxiliares de farmacia |
| Reducción de costos logísticos | Rutas optimizadas y agrupación de pedidos | Coordinación logística |
| Cumplimiento normativo | Trazabilidad y auditoría exportable | Auditores de salud |
| Toma de decisiones | Panel de métricas en tiempo real | Coordinadores de EPS |

## 3. Alcance del Sistema

### 3.1 Alcance funcional

El sistema SIGTAM-EPS comprenderá los siguientes módulos funcionales:

#### 3.1.1 Módulo de gestión de usuarios y seguridad
- Registro e inicio de sesión de pacientes mediante documento de identidad y contraseña.
- Gestión de perfiles y roles con control de acceso basado en permisos para pacientes, médicos, auxiliares de farmacia y administradores.
- Encriptación de credenciales y validación de formato de cédula.

#### 3.1.2 Módulo de turnos y filas
- Solicitud de turno virtual remoto con selección de especialidad, tiempo estimado de espera y generación de código QR.
- Visualización del estado de la fila en tiempo real y alertas visuales.
- Check-in presencial por escaneo de código QR.
- Asignación y llamada de turnos por parte del médico, con visualización en pantallas de sala de espera.
- Reasignación dinámica de turnos por prioridad médica.
- Cancelación o aplazamiento de turnos con reajuste automático de la lista de espera.
- Registro de disponibilidad de consultorios y profesionales, con bloqueo automático por ausencias.

#### 3.1.3 Módulo de atención médica
- Registro de evolución y fórmula médica electrónica, con guardado atómico vinculado al paciente.
- Historial de turnos y recetas pasadas, con exportación digital.
- Calificación del servicio de atención por parte del paciente.

#### 3.1.4 Módulo de farmacia y medicamentos
- Notificación de disponibilidad de medicamentos al paciente.
- Turno integrado de farmacia generado automáticamente al cierre de la consulta.
- Solicitud de entrega de medicamentos a domicilio para pacientes con movilidad reducida o tratamiento crónico.
- Gestión de inventario farmacéutico con operaciones atómicas y alertas de stock mínimo.
- Alertas de caducidad de medicamentos con filtros por lote.
- Confirmación de entrega en ventanilla mediante firma digital o escaneo de cédula.

#### 3.1.5 Módulo de logística y rutas
- Cálculo de ruta óptima.
- Generación de rutas dinámicas para entregas grupales.
- Re-optimización de ruta ante nuevos pedidos, evaluando costo adicional e insertando en la ruta más conveniente.

#### 3.1.6 Módulo de analítica y auditoría
- Panel de control de tiempos de espera con gráficos estadísticos en tiempo real y segmentación por especialidad o sede.
- Reporte de trazabilidad y auditoría de medicamentos exportable, con filtros por fecha y documento.

### 3.2 Alcance técnico

| Aspecto | Definición |
|---|---|
| Arquitectura | Sistema basado en módulos integrados, con comunicación en tiempo real y servicios de notificación |
| Modelado de rutas | Representación del entorno geográfico y aplicación de optimización |
| Persistencia | Base de datos relacional con operaciones atómicas para inventario, recetas y turnos |
| Seguridad | Autenticación con documento y contraseña encriptada; control de acceso basado en roles |
| Notificaciones | Alertas push y SMS para disponibilidad de medicamentos y proximidad de turno |
| Interfaz | Aplicación web responsive; interfaz clínica para médicos; panel administrativo. |

### 3.3 Actores del sistema

| Actor | Rol principal |
|---|---|
| Paciente | Solicita turnos, consulta estado de fila, recibe notificaciones, solicita domicilios, califica el servicio. |
| Médico | Llama turnos, registra evolución y fórmula médica electrónica. |
| Auxiliar de farmacia | Gestiona inventario, confirma entregas, actualiza stock. |
| Administrador de farmacia | Recibe alertas de caducidad, supervisa inventario. |
| Coordinador de la EPS | Visualiza métricas de tiempos de espera, supervisa operación. |
| Coordinador de logística | Genera rutas dinámicas, agrupa pedidos, optimiza despachos. |
| Domiciliario | Ejecuta rutas, recibe re-optimizaciones ante nuevos pedidos. |
| Personal administrativo | Reasigna turnos por prioridad médica. |
| Auditor de salud | Genera reportes de trazabilidad y auditoría. |
| Administrador del sistema | Gestiona perfiles, roles y permisos. |

### 3.4 Fuera del alcance

Quedan explícitamente fuera del alcance del proyecto:

1. **Gestión de historias clínicas completas** más allá del registro de evolución y fórmula médica asociada al turno.
2. **Facturación y procesos contables** de la EPS.
3. **Integración con sistemas externos** de aseguradoras, entidades regulatorias o plataformas de pago, salvo que se definan en una fase posterior.
4. **Telemedicina** (videoconsultas), aunque el sistema gestiona turnos virtuales.
5. **Gestión de recursos humanos** de la EPS (nómina, contratación).
6. **Mantenimiento y logística de vehículos** propios de la EPS.
7. **Aplicaciones nativas** para sistemas operativos específicos, si se opta por una solución web responsive.
8. **Módulo de urgencias hospitalarias** más allá de la priorización por triage en turnos programados.

## 4. Requisitos

### 4.1 Requisitos funcionales

Los requisitos funcionales se derivan directamente de las 23 historias de usuario, agrupadas en los seis módulos descritos en la sección 3.1. Cada historia de usuario constituye una unidad funcional verificable con criterios de aceptación definidos.

### 4.2 Requisitos no funcionales

| Categoría | Requisito |
|---|---|
| Rendimiento | Actualización de estado de fila en tiempo real con latencia inferior a 2 segundos. |
| Disponibilidad | Disponibilidad mínima del 99% en horario de atención. |
| Seguridad | Encriptación de contraseñas, validación de identidad y control de acceso por roles. |
| Escalabilidad | Soporte para múltiples sedes y especialidades sin degradación del servicio. |
| Usabilidad | Interfaz intuitiva para pacientes de todas las edades y condiciones. |
| Trazabilidad | Registro completo de acciones para auditoría normativa. |
| Compatibilidad | Funcionamiento en navegadores modernos y dispositivos móviles. |
| Mantenibilidad | Arquitectura modular que facilite la evolución independiente de cada módulo. |

## 5. Restricciones y Supuestos

### 5.1 Restricciones

1. El sistema debe cumplir con la normativa legal vigente en materia de salud, protección de datos personales y auditoría farmacéutica.
2. La validación de geolocalización requiere que el paciente otorgue permisos de ubicación en su dispositivo.
3. La re-optimización de rutas está sujeta a restricciones de capacidad del vehículo y ventanas de tiempo.
4. El cálculo de rutas óptimas depende de la disponibilidad de datos geográficos actualizados.
5. La integración con pasarelas de pago o sistemas externos no está contemplada en esta fase.

### 5.2 Supuestos

1. La EPS cuenta con la infraestructura tecnológica mínima para desplegar el sistema.
2. Los pacientes tienen acceso a dispositivos móviles o computadores con conexión a internet.
3. El personal de salud recibirá capacitación para el uso del sistema.
4. Los datos de inventario y disponibilidad de medicamentos serán mantenidos actualizados por el personal de farmacia.
5. Las sedes de la EPS cuentan con conectividad estable para el funcionamiento en tiempo real.

## 6. Criterios de Éxito

El éxito del sistema SIGTAM-EPS se medirá con base en los siguientes indicadores:

1. Reducción del tiempo promedio de espera en sala en al menos un 30%.
2. Disminución de filas físicas y aglomeraciones en sedes.
3. Incremento en la adherencia a tratamientos mediante notificaciones y entrega a domicilio.
4. Reducción de pérdidas de medicamentos por vencimiento.
5. Optimización de costos logísticos mediante rutas eficientes.
6. Cumplimiento del 100% de los requisitos de trazabilidad y auditoría.
7. Satisfacción del paciente medida a través del módulo de calificación.