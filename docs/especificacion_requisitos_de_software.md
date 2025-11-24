# Especificación de Requisitos de Software (SRS)
### Proyecto: TECLAB
*Versión [1.0]*

<br>

<img height="127" alt="LogoTecLab" src="https://raw.githubusercontent.com/DevCarlos23/ProyectoLaboratorio/main/docs/LogoTecLab.JPG" />

#### Noviembre 2025

<br>

> **Nota Aclaratoria:** <br>
> Este documento fue elaborado con fines académicos como parte de una práctica formativa bajo el estándar IEEE 830-1998.
> Todos los datos, nombres de entidades, diagramas y estructuras de base de datos son simulados y no corresponden a información real.
> Este documento tiene propósitos educativos y está diseñado para enseñar la correcta especificación de requisitos de software.

<br>

> **Instrucciones para el Estudiante:** <br>
> - Elimine todos los comentarios HTML `<!-- ... -->` en la versión final
> - Reemplace todo el texto entre `[corchetes]` con información real de su proyecto
> - Utilice las tablas y formatos sugeridos como guía
> - Revise el checklist de calidad antes de entregar
> - Mantenga la numeración y estructura del estándar IEEE 830

<br>

**Control de Versiones:**

| Versión | Fecha | Autor | Descripción de Cambios |
|---------|-------|-------|------------------------|
| 1.0 | [02/11/2025] | [Equipo TECLAB] | Versión inicial del documento |
| | | | |

<br>

---

## CONTENIDO

- [1 INTRODUCCIÓN](#1-introducción)
  - [1.1 Propósito](#11-propósito)
  - [1.2 Alcance](#12-alcance)
  - [1.3 Personal involucrado](#13-personal-involucrado)
  - [1.4 Definiciones, acrónimos y abreviaturas](#14-definiciones-acrónimos-y-abreviaturas)
  - [1.5 Referencias](#15-referencias)
  - [1.6 Resumen](#16-resumen)
- [2 DESCRIPCIÓN GENERAL](#2-descripción-general)
  - [2.1 Perspectiva del producto](#21-perspectiva-del-producto)
  - [2.2 Funciones del producto](#22-funciones-del-producto)
  - [2.3 Características de los usuarios](#23-características-de-los-usuarios)
  - [2.4 Restricciones](#24-restricciones)
  - [2.5 Suposiciones y dependencias](#25-suposiciones-y-dependencias)
  - [2.6 Requisitos futuros](#26-requisitos-futuros)
- [3 REQUISITOS ESPECÍFICOS](#3-requisitos-específicos)
  - [3.1 Requisitos funcionales](#31-requisitos-funcionales)
  - [3.2 Requisitos de interfaz externa](#32-requisitos-de-interfaz-externa)
    - [3.2.1 Interfaz de usuario](#321-interfaz-de-usuario)
    - [3.2.2 Interfaz de hardware](#322-interfaz-de-hardware)
    - [3.2.3 Interfaz de software](#323-interfaz-de-software)
    - [3.2.4 Interfaz de comunicación](#324-interfaz-de-comunicación)
  - [3.3 Requisitos no funcionales](#33-requisitos-no-funcionales)
    - [3.3.1 Rendimiento](#331-rendimiento)
    - [3.3.2 Fiabilidad](#332-fiabilidad)
    - [3.3.3 Disponibilidad](#333-disponibilidad)
    - [3.3.4 Seguridad](#334-seguridad)
    - [3.3.5 Mantenibilidad](#335-mantenibilidad)
    - [3.3.6 Portabilidad](#336-portabilidad)
  - [3.4 Requisitos de diseño](#34-requisitos-de-diseño)
  - [3.5 Requisitos de calidad](#35-requisitos-de-calidad)
  - [3.6 Restricciones del sistema](#36-restricciones-del-sistema)
  - [3.7 Atributos del sistema](#37-atributos-del-sistema)
- [4 APÉNDICES](#4-apéndices)
  - [4.1 Modelos de casos de uso](#41-modelos-de-casos-de-uso)
  - [4.2 Glosario](#42-glosario)
  - [4.3 Diagramas del sistema](#43-diagramas-del-sistema)
  - [4.4 Matriz de trazabilidad](#44-matriz-de-trazabilidad)
  - [4.5 Criterios de evaluación](#45-criterios-de-evaluación)

<br>

---

## 1 INTRODUCCIÓN

### 1.1 Propósito

Este documento de Especificación de Requisitos de Software (SRS), elaborado bajo la guía del estándar IEEE 830, describe los requisitos funcionales y no funcionales para el Sistema de Gestión de Laboratorios y Préstamo de Equipos "TECLAB", en su versión de Producto Mínimo Viable (MVP).

El propósito primario de este SRS es establecer un acuerdo formal y una base técnica común de entendimiento entre el cliente (la Dirección de Tecnologías de la Información - DTI de la Universidad Tecnológica de los Andes - UTA) y el equipo de desarrollo. Servirá como la única fuente de verdad para la implementación, el diseño de casos de prueba por parte del equipo de QA, y la validación final del sistema por parte del cliente.

Este documento será utilizado por el equipo de desarrollo como guía de implementación, por los analistas para la gestión de cambios en el alcance, por el equipo de QA para el diseño de pruebas de aceptación, y por los gerentes para la planificación de recursos y seguimiento del cronograma de 4.5 meses establecido para el MVP.

### 1.2 Alcance

Nombre del Sistema: Sistema de Gestión de Laboratorios y Préstamo de Equipos TECLAB (MVP v1.0)

Descripción:
TECLAB es una solución de software diseñada para digitalizar, organizar y gestionar centralizadamente los 8 laboratorios de cómputo y el servicio de préstamo de equipos tecnológicos (portátiles, tablets, cámaras) de la Universidad Tecnológica de los Andes (UTA). El sistema resolverá los problemas críticos de disponibilidad, seguridad, mantenimiento y trazabilidad que afectan actualmente a los 320 computadores de escritorio y los 125 equipos prestables.

El sistema se enfoca en tres módulos principales para el MVP: Gestión de Inventario y Mantenimiento, Sistema de Reservas (para laboratorios y equipos), y Gestión de Préstamo/Devolución. Este sistema proporcionará una plataforma confiable y eficiente, permitiendo a docentes y técnicos administrar los recursos y a los estudiantes acceder a ellos de manera justa.

Beneficios Principales:

Eliminación de la desorganización actual, estableciendo trazabilidad completa del 100% de los equipos.

Reducción del tiempo de inactividad de los equipos a través de la automatización de flujos de mantenimiento.

Incremento en la seguridad y reducción de pérdidas por medio de registros detallados de salida y entrada.

Optimización en la asignación de recursos limitados (laboratorios y equipos portátiles).

Objetivos del Sistema:

Lograr la trazabilidad del 100% de los 445 activos (320 de escritorio + 125 prestables) en el sistema en la primera semana de operación.

Implementar el sistema de reservas online para los 8 laboratorios de cómputo y todos los equipos prestables.

Establecer un flujo de mantenimiento preventivo y correctivo que reduzca el tiempo promedio de reparación en un 40%.

Proveer la infraestructura para reportes estadísticos que ayuden a la DTI en la toma de decisiones.

Asegurar la operatividad completa del MVP antes del inicio del próximo semestre académico (4.5 meses).

Límites del Sistema (Fuera de Alcance del MVP):

Integración con Sistemas Financieros: El MVP NO gestionará la contabilidad o el presupuesto de la DTI o la UTA.

Gestión de Cursos y Horarios Académicos: El sistema no sincronizará directamente las mallas curriculares de los programas. Solo gestionará la disponibilidad de los recursos físicos.

Portal de Pago de Multas: Las penalizaciones por no devolución serán registradas, pero el procesamiento de pagos o la integración con pasarelas de pago NO están incluidas en el MVP.

Seguridad Física (Hardware): El sistema NO gestionará elementos de seguridad física como cerraduras electrónicas o alarmas de movimiento.

<br>

### 1.3 Personal involucrado


| Nombre | Rol | Responsabilidades | Información de Contacto |
|--------|-----|-------------------|-------------------------|
| **Jhon Casas** | Arquitecto de Software / Líder Técnico | - Diseño de arquitectura del sistema<br>- Tomar decisiones técnicas<br>- Revisar código y estándares<br>- Supervisar integración de módulos | **Email:** jhonacasas@ucompensar.edu.com<br>**Tel:** +57 301 555 8421 |
| **Carol Gonzales** | Analista de Requisitos | - Elicitación y análisis de requisitos<br>- Documentar SRS<br>- Validación con usuarios y stakeholders<br>- Control de cambios en requisitos | **Email:** cdalugonzalez@ucompensar.edu.co<br>**Tel:** +57 300 912 4477 |
| **Daniel Avila** | Gerente/Jefe de Proyecto | - Coordinar al equipo de desarrollo<br>- Gestionar tiempos y recursos<br>- Punto principal de contacto interno<br>- Gestión de riesgos y resolución de conflictos | **Email:** dsavila@ucompensar.edu.co<br>**Tel:** +57 320 774 9832 |
| **Carlos Bonilla** | Líder de QA/Testing | - Diseñar plan y estrategia de pruebas<br>- Validación de requisitos implementados<br>- Reporte y seguimiento de defectos<br>- Garantizar calidad del producto | **Email:** cbonilla@ucompensar.edu.co<br>**Tel:** +57 313 660 5248 |


<!-- 
NOTA PARA PROYECTOS ACADÉMICOS:
En contextos académicos, pueden incluir roles como:
- Docente/Asesor del proyecto
- Estudiantes por rol (analista, desarrollador, tester)
- "Cliente simulado" o stakeholder de práctica
-->

<br>

### 1.4 Definiciones, acrónimos y abreviaturas

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Proporcionar un glosario de términos técnicos, acrónimos y abreviaturas utilizados
en el documento para garantizar comprensión común.

IMPORTANCIA:
Evita ambigüedades y malentendidos. Un mismo término puede significar cosas diferentes
en distintos contextos (ej: "usuario" puede ser usuario final o usuario del sistema).

ORGANIZACIÓN:
Liste los términos en orden alfabético para facilitar la consulta.

TIPOS DE ENTRADAS:
1. Términos del dominio del negocio
2. Términos técnicos de software
3. Acrónimos del proyecto
4. Abreviaturas utilizadas en el documento

FORMATO SUGERIDO:
-->

| Término | Definición |
|---------|------------|
| **API** | Application Programming Interface (Interfaz de Programación de Aplicaciones). Conjunto de definiciones y protocolos para integrar y comunicar aplicaciones de software. |
| **CRUD** | Create, Read, Update, Delete. Operaciones básicas de gestión de datos en una base de datos. |
| **Framework** | Estructura conceptual y tecnológica de soporte definida, normalmente con artefactos o módulos de software concretos, que puede servir de base para la organización y desarrollo de software. |
| **IEEE 830** | Estándar del Instituto de Ingenieros Eléctricos y Electrónicos para especificaciones de requisitos de software. |
| **RF** | Requisito Funcional. Especifica una función que debe realizar el sistema. |
| **RNF** | Requisito No Funcional. Especifica criterios de calidad, restricciones o atributos del sistema. |
| **SRS** | Software Requirements Specification (Especificación de Requisitos de Software). |
| **Stakeholder** | Cualquier persona, grupo u organización que puede afectar o ser afectado por el proyecto. |
| **UI** | User Interface (Interfaz de Usuario). Medio con que el usuario puede comunicarse con el sistema. |
| **UX** | User Experience (Experiencia de Usuario). Percepción y respuesta del usuario resultante del uso o anticipación del uso de un producto. |

<!-- 
INSTRUCCIONES:
1. Agregue TODOS los términos técnicos o del dominio que use en el documento
2. Agregue los acrónimos de su organización o proyecto específico
3. Defina términos ambiguos de manera precisa para su contexto
4. Si usa términos en inglés, incluya la traducción al español

EJEMPLO DE TÉRMINOS ESPECÍFICOS DE DOMINIO (Biblioteca):

| Término | Definición |
|---------|------------|
| **Ejemplar** | Copia física específica de un material bibliográfico. Un libro puede tener múltiples ejemplares. |
| **Material bibliográfico** | Cualquier recurso disponible en la biblioteca: libros, revistas, DVDs, etc. |
| **Préstamo a domicilio** | Tipo de préstamo que permite al usuario llevar material fuera de la biblioteca por un período determinado. |
| **Préstamo en sala** | Tipo de préstamo que solo permite consultar el material dentro de las instalaciones de la biblioteca. |
| **Usuario activo** | Usuario registrado que ha realizado al menos un préstamo en los últimos 12 meses. |
-->

[Complete la tabla con los términos específicos de su proyecto]

<br>

### 1.5 Referencias

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Listar todos los documentos, estándares, normas y recursos externos referenciados
en este SRS o que proporcionan contexto adicional.

IMPORTANCIA:
Permite a los lectores:
- Profundizar en temas específicos
- Validar el cumplimiento de estándares
- Acceder a documentación complementaria
- Verificar la trazabilidad con otros documentos del proyecto

TIPOS DE REFERENCIAS COMUNES:
1. Estándares y normas (IEEE, ISO, etc.)
2. Documentos del proyecto (plan de proyecto, visión, arquitectura)
3. Documentación técnica de frameworks o tecnologías
4. Bibliografía de referencia
5. Sitios web y recursos en línea

FORMATO SUGERIDO (estilo académico):
-->

**Estándares y Normas:**

1. IEEE Computer Society. (1998). *IEEE Recommended Practice for Software Requirements Specifications*. IEEE Std 830-1998. Nueva York: IEEE.

2. ISO/IEC/IEEE 29148:2018. *Systems and software engineering — Life cycle processes — Requirements engineering*. Ginebra: International Organization for Standardization.

**Documentos del Proyecto:**

3. [Nombre del Autor]. ([Año]). *Documento de Visión del Proyecto [Nombre del Proyecto]*. [Organización]. Versión [X.X].

4. [Nombre del Autor]. ([Año]). *Plan de Gestión del Proyecto [Nombre del Proyecto]*. [Organización].

**Documentación Técnica:**

5. [Framework/Tecnología]. ([Año]). *Documentación Oficial*. Recuperado de [URL]

6. [Base de Datos]. ([Año]). *Manual de Referencia*. Recuperado de [URL]

**Bibliografía de Referencia:**

7. Sommerville, I. (2016). *Ingeniería de Software* (10ª ed.). México: Pearson Educación.

8. Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del Software: Un Enfoque Práctico* (9ª ed.). México: McGraw-Hill Education.

**Recursos en Línea:**

9. Material del curso de Levantamiento de Requerimientos. (2025). [Universidad/Institución]. Disponible en [URL del aula virtual].

<!-- 
EJEMPLO COMPLETO PARA PROYECTO BIBLIOTECARIO:

**Estándares y Normas:**
1. IEEE Std 830-1998. Software Requirements Specifications.
2. ISO 2709:2008. Information and documentation — Format for information exchange.

**Documentos del Proyecto:**
3. Rodríguez, M. (2024). Documento de Visión - Sistema BiblioTech. Biblioteca Municipal Central.
4. González, A. (2024). Estudio de Factibilidad - Automatización de Procesos Bibliotecarios.

**Documentación Técnica:**
5. Django Framework Documentation. (2024). Disponible en: https://docs.djangoproject.com/
6. PostgreSQL 15 Documentation. (2024). Disponible en: https://www.postgresql.org/docs/15/

**Bibliografía:**
7. Lippincott, S. (2015). Library Automation in Transitional Societies: Lessons from Eastern Europe. Oxford: Chandos Publishing.
-->

[Complete esta sección con las referencias relevantes para su proyecto]

<br>

### 1.6 Resumen

Este documento de Especificación de Requisitos de Software está organizado en cuatro secciones principales que siguen el estándar IEEE 830-1998.

La Sección 2, Descripción General, presenta una visión global del sistema TECLAB sin entrar en detalles de implementación. Incluye la perspectiva del producto dentro del contexto organizacional de la UTA, un resumen de las funciones principales (Gestión de Inventario, Reservas y Préstamos), las características de los diferentes tipos de usuarios (Docentes, Técnicos, Estudiantes), y las restricciones generales bajo las cuales debe operar. También documenta las suposiciones y dependencias clave para el éxito del MVP.

La Sección 3, Requisitos Específicos, constituye el núcleo técnico del documento. Esta sección detalla exhaustivamente todos los requisitos funcionales (lo que el sistema debe hacer, como 'UC-01 solicitar préstamo de equipo') y los requisitos no funcionales (cómo debe comportarse el sistema, incluyendo rendimiento, seguridad y disponibilidad). Incluye especificaciones detalladas de las interfaces del sistema (usuario, hardware, software y comunicación), criterios de rendimiento, y otros atributos de calidad que el sistema debe cumplir.

La Sección 4, Apéndices, contiene información complementaria que respalda las secciones anteriores, incluyendo el Glosario de términos específicos (como "Activo Prestables" o "Faltas por No Show") y matrices de trazabilidad. En el contexto de este proyecto, incluirá los modelos de Casos de Uso (UML) y diagramas del sistema, así como referencias a artefactos clave como el prototipo de alta fidelidad.

<br>

---

## 2 DESCRIPCIÓN GENERAL

### 2.1 Perspectiva del Producto

#### Propósito

Esta sección proporciona un contexto y visión general del sistema de préstamo de equipos de laboratorio, sin entrar en detalles técnicos específicos. El objetivo es que los lectores comprendan el panorama general antes de revisar los requisitos detallados en la Sección 3.

#### Visión General del Sistema

El producto a desarrollar es un sistema de gestión de préstamos de equipos, orientado a controlar la disponibilidad, reserva y entrega de instrumentos del laboratorio. El sistema permitirá al personal autorizado (administradores, técnicos y docentes) registrar préstamos, devoluciones y programar mantenimientos preventivos, asegurando un uso eficiente y organizado de los recursos del laboratorio.
El sistema se integrará con los módulos existentes de autenticación de usuarios y base de datos del laboratorio, y proporcionará interfaces para:
- Usuarios internos: Registrar préstamos, devoluciones y consultas sobre disponibilidad de equipos.
- Base de datos: Almacenar y recuperar información histórica sobre préstamos, devoluciones y estado de los equipos.
- Módulo de reportes: Generar reportes de uso de equipos, frecuencia de préstamos y mantenimiento en formatos PDF o Excel.

#### Relaciones con Otros Sistemas

- Módulo de autenticación: Validación de usuarios autorizados para realizar préstamos y devoluciones.
- Base de datos del laboratorio: Almacenamiento y recuperación de registros históricos de préstamos y mantenimiento.
- Sistemas externos (futuros): Posible integración con sistemas de notificaciones (correo electrónico o SMS) para avisar sobre devoluciones pendientes o mantenimiento de equipos.

#### Restricciones y Consideraciones

Solo el personal autorizado puede registrar préstamos o devoluciones; los estudiantes o usuarios finales no tendrán acceso administrativo.
Se debe garantizar la seguridad y consistencia de la información sobre préstamos y disponibilidad de equipos.
El sistema será implementado como aplicación web, compatible con navegadores modernos y dispositivos de escritorio.
 
### 2.1.2 Perspectiva del Producto

#### Contexto del Sistema

El sistema de Préstamo de Equipos de Laboratorio es un producto completamente nuevo que reemplazará parcialmente los registros manuales actuales de préstamos y devoluciones de equipos. Actualmente, el control se realiza mediante hojas de cálculo Excel y registros físicos, lo que dificulta el seguimiento del estado de los equipos y el historial de préstamos.
El sistema funcionará como una aplicación web independiente, pero interactuará con ciertos sistemas externos para mejorar la funcionalidad y seguridad:
- Módulo de autenticación institucional: Para validar credenciales de los usuarios internos (docentes, técnicos y administradores).
- Servidor de correo electrónico institucional: Para notificaciones automáticas de devoluciones y reservas de equipos.
- Servidor de respaldo centralizado del laboratorio: Para garantizar la integridad y disponibilidad de la información.
El sistema digitalizará completamente los procesos de préstamo, devolución y consulta de equipos, manteniendo la lógica de negocio actual pero eliminando el manejo de papel y hojas de cálculo.

#### Relación con Sistemas Existentes

Actualmente, los procesos que serán reemplazados incluyen:
- Hojas de cálculo Excel para registro de préstamos y devoluciones.
- Registro físico de equipos prestados y devueltos.
- Control manual del estado de los equipos y su mantenimiento.
El nuevo sistema permitirá automatizar estos procesos, centralizando la información y facilitando el acceso a reportes estadísticos de uso de los equipos.
#### Interfaces del Sistema (Visión General)
El sistema interactuará con:
1. Usuarios del Sistema:
- Docentes, técnicos y administradores, a través de una interfaz web para registrar préstamos, devoluciones y generar reportes.
2. Sistemas Externos:
- Módulo de autenticación institucional (para validación de usuarios).
- Servidor SMTP para envío de correos de notificación.
- Servidor de respaldo institucional para almacenamiento seguro.
3. Hardware:
- Computadoras de escritorio o portátiles del personal autorizado.
- Servidor de base de datos para almacenamiento centralizado.
- Impresoras opcionales para comprobantes de préstamo.
 
          ┌──────────────────┐
          │     Usuarios     │────┐
          │ Docentes/Técnicos│    │
          └──────────────────┘    ▼
                            ┌──────────────────────────────┐
                            │Sistema de Préstamo de Equipos│
                            └──────────────────────────────┘
                             │             │               │
                             ▼             ▼               ▼
                    ┌─────────────┐ ┌─────────────┐ ┌──────────────┐
                    │ Base de     │ │ Servidor de │ │ Servidor de  │
                    │ Datos       │ │ Correo      │ │ Autenticación│
                    └─────────────┘ └─────────────┘ └──────────────┘

<br>

### 2.2 Funciones del producto

El sistema TECLAB tendrá como propósito principal optimizar la administración, control y seguimiento de los laboratorios institucionales y del préstamo de equipos tecnológicos.
Permitirá automatizar los procesos de registro, préstamo, reserva, mantenimiento y control de inventario, garantizando transparencia, trazabilidad y eficiencia en la gestión de los recursos.

A continuación, se describen las funciones principales del sistema, organizadas por módulos funcionales:
- Módulo de Gestión de Usuarios

Registro de nuevos usuarios (estudiantes, docentes, técnicos y administradores) mediante formularios validados.

Actualización y mantenimiento de la información personal y académica.

Asignación automática de roles y permisos según el tipo de usuario (por ejemplo: “Administrador”, “Encargado de laboratorio”, “Estudiante”).

Control de estados de usuarios (activo, suspendido, sancionado o egresado).

Recuperación de contraseñas y autenticación mediante credenciales únicas.

Registro de actividad del usuario dentro del sistema para fines de auditoría.

- Módulo de Gestión de Laboratorios

Registro y actualización de información detallada de cada laboratorio (nombre, ubicación, capacidad, tipo, equipamiento disponible y horario de funcionamiento).

Control de disponibilidad de los laboratorios en tiempo real.

Asignación de responsables por laboratorio, con permisos específicos de administración.

Gestión de mantenimiento programado o correctivo del laboratorio.

Visualización de horarios y reservas mediante calendario interactivo.

Control de accesos al laboratorio, permitiendo saber qué usuarios lo han utilizado y cuándo.
- Módulo de Gestión de Equipos y Recursos

Registro completo de equipos tecnológicos (computadores, herramientas, periféricos, instrumentos, etc.).

Identificación mediante códigos o etiquetas QR para agilizar su localización.

Asociación de cada equipo con su laboratorio correspondiente.

Actualización automática del estado del equipo (disponible, en préstamo, en mantenimiento o dado de baja).

Registro del historial de cada equipo (fecha de ingreso, reparaciones, préstamos realizados, daños reportados).

Control de inventario general con búsqueda avanzada por filtros (tipo de equipo, marca, número de serie, estado, laboratorio, etc.).

Alerta automática de equipos con mantenimiento pendiente o próximos a vencimiento de garantía.
- Módulo de Préstamo y Devolución

Solicitud de préstamo de equipos o recursos por parte de los usuarios autorizados.

Validación automática de disponibilidad y verificación de requisitos del usuario (por ejemplo, sin sanciones activas).

Registro detallado del préstamo (equipo, fecha de entrega, fecha prevista de devolución, responsable y observaciones).

Generación automática de comprobantes o recibos digitales.

Control de devoluciones con validación de estado del equipo.

Registro de retrasos, daños o pérdidas con posibilidad de generar sanciones.

Historial completo de préstamos realizados por usuario y por equipo.
- Módulo de Reservas

Solicitud anticipada de reserva de equipos o laboratorios.

Aprobación, modificación o cancelación de reservas por parte del encargado.

Control de tiempos de reserva y liberación automática de recursos no utilizados.

Integración con el calendario institucional para evitar conflictos de horarios.

Envío de notificaciones automáticas al usuario cuando su reserva es aprobada, rechazada o modificada.
- Módulo de Mantenimiento y Soporte Técnico

Registro de incidentes o fallas reportadas por los usuarios.

Asignación de tareas de mantenimiento preventivo o correctivo.

Seguimiento del estado de reparación de equipos.

Historial de mantenimientos realizados a cada equipo o laboratorio.

Generación de reportes de equipos más problemáticos o con fallas recurrentes.
- Módulo de Notificaciones y Comunicaciones

Envío automático de correos o alertas del sistema para recordar fechas de devolución o vencimiento de préstamos.

Notificaciones sobre disponibilidad de equipos o aprobación de reservas.

Alertas al administrador sobre retrasos, daños o incidencias en equipos.

Comunicados generales a los usuarios sobre mantenimiento, cambios de horario o novedades institucionales.

Integración con panel de notificaciones dentro del sistema web.
- Módulo de Reportes y Estadísticas

Generación de reportes personalizados sobre uso de laboratorios, cantidad de préstamos y reservas realizadas.

Estadísticas de equipos más utilizados, usuarios más activos y laboratorios con mayor demanda.

Reportes de equipos en mantenimiento o dados de baja.

Análisis de disponibilidad de recursos por fechas o periodos académicos.

Exportación de reportes en formatos PDF y Excel.
- Módulo de Administración del Sistema

Creación y gestión de cuentas de administradores, técnicos y encargados de laboratorio.

Configuración de parámetros generales del sistema (horarios de préstamo, duración máxima, sanciones por retraso, entre otros).

Gestión de copias de seguridad y restauración de la base de datos.

Control de accesos y auditoría de todas las operaciones realizadas.

Gestión de roles, permisos y niveles de acceso a la información.

Mantenimiento general del sistema (actualización de módulos, configuración de interfaz y soporte técnico).

#### Resumen General del Funcionamiento

El sistema TECLAB operará de forma integrada, conectando todos los módulos anteriores para garantizar una gestión centralizada de los recursos de laboratorio.
El flujo principal permitirá que un usuario autenticado realice reservas o préstamos de equipos, los encargados gestionen la disponibilidad y mantenimiento, y los administradores supervisen toda la actividad mediante reportes y auditorías.

<br>

### 2.3 Características de los usuarios

| Caracteristicas        | Estudiante                                                                                                                                                                                                                      | Docente                                                                                                                                                                                         | Monitor Laboratorio                                                                                                                                                                                    | Encargado Préstamos                                                                                                                                                             | Tecnico de Soporte                                                                                                                                                          | Coordinadora de Laboratorios                                                                                                        | Director TI                                                                                                                                                                 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Descripción            | Estudiante que gestiona constantemente solicitudes de equipos y asistencia a laboratorios                                                                                                                                       | Docente que gestiona la solicitud de reserva de laboratorio, solicita software especifico                                                                                                       | Personal especial encargado de manejar los laboratorios tanto en disponibilidad como estado actual                                                                                                     | Personal encargado de entregar y recibir los quipos de prestamo revisar su condicion y reportar algun error                                                                     | Especialista en gesttion mantenimiento y reparacion de equipos de computo encargado de mantener equipos                                                                     | Maneja los horarios de los laboratorios aprueba las reservas de los docentes así como el manejo de esa información                  | Director encargado de consultar reportes y sacar estadisticas para mejorar inversion                                                                                        |
| Responsabilidades      | Consulta disponibilidad de labs y equipos,Reserva puesto en laboratorio,Solicita préstamo de equipo (portátil/tablet/cámara), Reporta daños o problemas técnicos, Consulta historial de préstamos, Visualiza sanciones o multas | Reserva laboratorio completo para clase, Solicita instalación de software específico, Reporta problemas técnicos, Consulta estadísticas de uso de sus estudiantes                               | Abre y cierra laboratorio en su turno, Registrar ingreso de estudiantes, Reportar inasistencias, Reportar daños o mal funcinamiento, Monitorear el uso adecuado, apoyar en problemas tecnicos basicos. | Entrega y recibe equipos prestables, verifica estado fisico del equipo, registra prestamos y devoluciones, calcular multas por retraso o daños, bloquea usuarios con sanciones. | Recibe tickets de soporte, diagnostica y repara equipos dañados, actualiza estado de equipos en mantenimiento, instala y actualiza software, gestiona licencias de software | Asigna monitores a labs y turnos, aprueba reservas de docentes, gestiona horarios de disponibilidad de labs, genera reportes de uso | Consulta dashboards estrategicos, toma decisiones de inversion, presenta informes a rectoria, gestiona presupuesto de mantenimiento                                         |
| Nivel Tecnico          | Bajo                                                                                                                                                                                                                            | Medio                                                                                                                                                                                           | Medio                                                                                                                                                                                                  | Medio                                                                                                                                                                           | Alto                                                                                                                                                                        | Alto                                                                                                                                | Alto                                                                                                                                                                        |
| Experiencia de Dominio | Novato                                                                                                                                                                                                                          | Intermedio                                                                                                                                                                                      | Experto                                                                                                                                                                                                | Experto                                                                                                                                                                         | Experto                                                                                                                                                                     | Experto                                                                                                                             | Intermedio                                                                                                                                                                  |
| Frecuencia de Uso      | Diario                                                                                                                                                                                                                          | Diario                                                                                                                                                                                          | Diario                                                                                                                                                                                                 | Diario                                                                                                                                                                          | Semanal                                                                                                                                                                     | Diario                                                                                                                              | Ocasional                                                                                                                                                                   |
| Funciones Principales  | *Consultar laboratorios disponibles *Reservar puesto en el laboratorio *Solicitar prestamo de equipo *Revisar multas o sanciones                                                                                                | *Reserva Laboratorio para clases completas *Solicitar instalación o reparación de equipos o software *Reportar incidencias en los equipos *Revisar estadisticas de los estudiantes que reservan | *Registra el ingreso de los estudiantes *Reporta inasistencias *Brinda soporte en problemas técnicos básicos                                                                                           | *Encargado de recibir y entregar los equipos de prestamos *Revisar el estado de los equipos y notificarlos *Registrar los prestamos *Calcular multas                            | *Recibe tickets de soporte *Reporta, documenta y repara los equipos dañados *Gestiona las licencias de los equipos                                                          | *Asigna monitores a los laboratorios *Gestiona horarios de disponibilidad *Crea reportes de uso                                     | *Consulta dashboards *Revisa los reportes para mejorar la infraestructura e invertir capital *Presenta un informe general a rectoría *Gestiona presupuesto de mantenimiento |
| Necesidades Especiales | No aplica                                                                                                                                                                                                                       | No aplcia                                                                                                                                                                                       |                                                                                                                                                                                                        | No aplica                                                                                                                                                                       | No aplica                                                                                                                                                                   | No aplica                                                                                                                           | Acceso rapido a los reportes                                                                                                                                                |



<br>

### 2.4 Restricciones

2.4.1 Restricciones Regulatorias y Legales

- El sistema debe cumplir con la Ley 1581 de 2012 sobre Protección de Datos Personales.
- Cumplimiento de la Ley 1712 de 2014 de Transparencia y Acceso a la Información Pública:
- Los datos agregados sobre uso e inversión deben ser públicos.
- Los datos personales de usuarios no deben divulgarse.
- Cumplimiento del Decreto 1510 de 2013 sobre control de bienes del Estado:
- Debe existir trazabilidad completa de ubicación y responsable de cada activo tecnológico.
- Los registros de auditoría deben conservarse por al menos 2 años.
- El sistema no debe permitir instalación de software no licenciado y debe emitir alertas sobre licencias próximas a vencer.
- Debe generar reportes de cumplimiento para Microsoft, Adobe y Autodesk durante auditorías.

2.4.2 Restricciones Tecnológicas

- El sistema debe operar en servidores locales (on-premise); el uso de infraestructura en la nube no está permitido.
- Especificaciones del servidor:
- Linux Ubuntu Server 22.04 LTS
- 8 GB de RAM
- 500 GB de almacenamiento
- Red institucional:
- LAN con switches Cisco
- WiFi institucional (eduroam con autenticación RADIUS)
- Integración obligatoria:
- Sistema de autenticación Active Directory (LDAP)
- Exportación e importación de datos en CSV o Excel
- Compatibilidad de clientes:
- Navegadores: Chrome 100+, Firefox 90+, Edge 100+
- Tablets Android 10 (usadas por monitores)

#### Restricciones adicionales:

Algunos laboratorios (como Electrónica) operan en red aislada; el sistema debe funcionar sin conexión y sincronizar datos posteriormente.

2.4.3 Restricciones de Implementación

- El sistema debe desarrollarse con tecnologías open source (sin licencias propietarias).
- Plazo máximo: 4.5 meses (MVP operativo en enero de 2026).
- Presupuesto total: $85,000,000 COP (~$21,000 USD).
- Distribución presupuestaria:

- Desarrollo del sistema: $52,000,000
- Hardware adicional: $18,000,000
- Etiquetado de equipos: $5,000,000
- Capacitación y puesta en marcha: $10,000,000
- Base de datos: PostgreSQL versión 13 o superior.
- Disponibilidad mínima: 99% durante horario de laboratorios (7:00 AM – 9:00 PM, lunes a sábado).
- El sistema debe ser 100% web, sin requerir instalación local.
- Lenguajes de desarrollo recomendados: Java o Python (compatibilidad institucional).

2.4.4 Restricciones de Interfaz e Integración

- Integración obligatoria con Active Directory (LDAP institucional).
- Exportación de reportes en formato CSV o Excel para la Contraloría.
- Compatibilidad con lectores de código de barras y QR (Zebra DS2208 o equivalente).
- Uso exclusivo del servidor SMTP institucional (mail.uta.edu.co) para notificaciones automáticas.
- Interfaz web responsive y optimizada para dispositivos móviles.
- El sistema debe contar con una API interna para registrar software, versiones y equipos asociados.

2.4.5 Restricciones Operacionales

- Capacidad mínima: Soportar 1,000 usuarios concurrentes en picos de demanda.
- Migración inicial:
- 450 equipos (320 desktops, 85 portátiles, 40 tablets, cámaras y accesorios).
- Etiquetado físico de equipos (QR/códigos de barras) antes del 31 de diciembre de 2025.
- Migración de datos:
- No puede causar interrupción del servicio por más de 4 horas.
- Capacitación máxima:
- Monitores: 3 horas
- Encargada de préstamos: 6 horas
- Técnicos: 4 horas
- Estudiantes: autoguiada mediante videos y tutoriales
- Auditoría: El sistema debe mantener bitácoras de actividad accesibles solo a personal autorizado.

2.4.6 Restricciones Éticas y de Acceso

- Privacidad: No se permite monitorear pantallas ni registrar actividades personales.
- Equidad: El sistema de reservas debe garantizar igualdad de acceso a todos los estudiantes.
- Transparencia: Cualquier algoritmo de priorización o penalización debe ser explicable y auditable.
- No discriminación:
- Las sanciones deben ser proporcionales y graduales.
- No se deben aplicar bloqueos permanentes automáticos.

2.4.7 Restricciones Presupuestarias y de Recursos

- Presupuesto máximo: $85,000,000 COP (no ampliable).
- Equipo de trabajo limitado a:
- 2 desarrolladores
- 1 analista
- 1 tester

### Hardware adicional permitido:

- 10 lectores de código de barras
- 8 tablets para monitore
- 1 impresora de etiquetas

No se permite contratación externa adicional ni adquisición de software propietario con costos recurrentes.

<br>

### 2.5 Suposiciones y dependencias

- Conectividad: Se asume que el laboratorio contara con conexión a internet   
- Mantenimiento: Se asume que el administrador del laboratorio proporcionara un soporte técnico continuo  
- Personal: Se asume que el personal deberá contar con el conocimiento mínimo/básico de informática y el manejo de dispositivos de escaneo 
- Tecnología: Se entiende que el hardware como computadores, impresoras y escáneres sean compatibles con los requisitos técnicos como el navegador web, puertos etc.
                                    
### 2.5.1 Dependencias 
- Proveedor de Hosting: El sistema depende de la infraestructura del servidor, actualizaciones o problemas con el equipo 
- Estudiante: El sistema depende del acceso de la base de datos o API para ver el estado del estudiante (activo/inactivo)
- Escaner: El sistema depende de los dispositivos de códigos de barras para la entrega y compra de los equipos 

<br>

### 2.6 Requisitos futuros

Los siguientes requisitos han sido identificados como deseables o críticos para la evolución del Sistema TECLAB, pero han sido excluidos del alcance del Producto Mínimo Viable (MVP v1.0) por limitaciones de tiempo y presupuesto (4.5 meses). Estos servirán como hoja de ruta para las Versiones 2.0 y posteriores.

Versión 2.0 (Post-MVP):

Integración con Sistemas de Pago para Multas: Implementar la integración con pasarelas de pago (online/TPV) para que los estudiantes puedan pagar multas generadas por retrasos o pérdidas de equipos directamente a través del portal.

Sistema de Notificaciones Avanzadas: Migrar de simples notificaciones por correo a notificaciones push para reservas y alertas de devoluciones a través de una aplicación móvil o integración con el portal del estudiante de la UTA.

Módulo de Trazabilidad GPS: Incluir un módulo para registrar la ubicación GPS (a través de check-in manual o tecnología IoT futura) de los equipos de alto valor (ej. portátiles, cámaras) al momento del préstamo/devolución para mayor seguridad.

Generación de Reportes Predictivos: Desarrollar informes avanzados que utilicen datos históricos para predecir la demanda de laboratorios o equipos en diferentes épocas del semestre, ayudando a la DTI a planificar adquisiciones.

Reconocimiento Facial/Biométrico para Acceso a Laboratorios: Integrar el sistema con tecnología biométrica para automatizar el registro de entrada y salida a los laboratorios de cómputo, mejorando el control de acceso.

Consideración Arquitectónica:

Aunque estas funcionalidades no se implementarán en la versión 1.0, la arquitectura del sistema se diseñará de manera modular para permitir su incorporación futura sin requerir rediseños mayores, especialmente en lo referente a la Gestión de Faltas y Sanciones para la futura integración con pagos.

[Complete esta subsección con los requisitos futuros identificados para su proyecto]

<br>

---

## 3 REQUISITOS ESPECÍFICOS

### 3.1 Requisitos funcionales

**PLANTILLA DE REQUISITO FUNCIONAL:**

| **ID** | RF-XXX |
|--------|--------|
| **Nombre** | [Nombre corto descriptivo del requisito] |
| **Descripción** | [Descripción detallada y precisa de la funcionalidad. Use lenguaje claro, sin ambigüedades. Especifique inputs, procesamiento, y outputs esperados.] |
| **Prioridad** | Esencial / Deseable / Opcional |
| **Estabilidad** | Alta / Media / Baja |
| **Fuente** | [Stakeholder que solicitó este requisito] |
| **Criterios de Aceptación** | 1. [Criterio medible 1]<br>2. [Criterio medible 2]<br>3. [Criterio medible 3] |
| **Dependencias** | [RF-XXX, RF-YYY] o "Ninguna" |
| **Comentarios** | [Cualquier información adicional relevante] |

#### **RF-UC-01 – Visualizar estadisticas del laboratorio**

| ID | RF-UC- 01|
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre | Visualizar estadisticas del laboratorio|
| Descripción| Proceso mediante el cual el docente accede y obtiene un resumen analítico de los datos registrados en el laboratorio como (tasa de asistencia, tiempo de uso), permitiendo la interpretación y evaluación de la información obtenida, así como la identificación de patrones, tendencias o resultados relevantes que faciliten la toma de decisiones y el seguimiento de los experimentos realizados.|
| Prioridad| Deseable|
| Estabilidad| Media |
| Fuente| Docente responsable del laboratorio|
| Criterios de  aceptación | 1.El sistema debe permitir  al usuario poder seleccionar un rango de fechas. 2.Los datos deben ser concisos y precisos ,coincidiendo con la información previamente registrada en la base de datos del laboratorio  3.El acceso de la funcionalidad debe estar únicamente a usuarios autorizados  por ejemplo (docentes o administrativos)   |
| Dependencias| Modulo de generación de reportes de uso de laboratorio (uc-16 )|
| Comentarios| Se recomienda incluir gráficos estadísticos (barras o pastel)para una visualización mas clara  de los datos|
<br>

#### **RF-UC-02 – Registrar solicitud de préstamo de equipo**

| **Campo** | **Descripción** |
|------------|-----------------|
| **ID** | RF-UC-02 |
| **Nombre** | Registrar solicitud de préstamo de equipo |
| **Descripción** | Permite al usuario (estudiante o docente) realizar la solicitud de préstamo de un equipo disponible (portátil, tablet, cámara, kit, etc.) a través del sistema, especificando fechas, tipo de equipo y motivo de uso. El sistema valida la disponibilidad y el estado del usuario antes de aceptar la solicitud. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Encargada de préstamos |
| **Criterios de aceptación** | 1. El sistema debe permitir al usuario seleccionar tipo de equipo, rango de fechas y motivo del préstamo.<br>2. El sistema debe validar que el usuario no tenga sanciones activas ni otro préstamo vigente.<br>3. Debe confirmar la disponibilidad del equipo.<br>4. Debe generarse un comprobante digital con código único de solicitud. |
| **Dependencias** | Módulo de gestión de inventario (RF-UC-10) y autenticación de usuarios. |
| **Comentarios** | Se recomienda incluir una vista de calendario para seleccionar fechas disponibles y evitar traslapes de reservas. |

---

#### **RF-UC-03 – Registrar entrega de equipo prestado**

| **Campo** | **Descripción** |
|------------|-----------------|
| **ID** | RF-UC-03 |
| **Nombre** | Registrar entrega de equipo prestado |
| **Descripción** | Proceso mediante el cual el encargado de préstamos registra la entrega física del equipo al usuario, verificando identidad mediante carnet o QR y completando un checklist digital del estado del equipo antes de la entrega. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Encargada de préstamos |
| **Criterios de aceptación** | 1. El sistema debe permitir escanear el código del equipo y del carnet del usuario.<br>2. Debe mostrar el checklist de revisión del estado físico.<br>3. No debe permitirse finalizar la entrega sin completar el checklist.<br>4. Debe actualizar automáticamente el estado del equipo a “Prestado”. |
| **Dependencias** | RF-UC-02 (solicitud de préstamo) y RF-UC-10 (inventario). |
| **Comentarios** | Se recomienda incluir captura fotográfica del equipo antes de la entrega como evidencia. |

---

#### **RF-UC-04 – Registrar devolución de equipo prestado**

| **Campo** | **Descripción** |
|------------|-----------------|
| **ID** | RF-UC-04 |
| **Nombre** | Registrar devolución de equipo prestado |
| **Descripción** | Permite al encargado registrar la devolución del equipo, verificando su estado físico y funcional, actualizando el inventario y calculando automáticamente multas por retraso o daños. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Encargada de préstamos / Técnico de soporte |
| **Criterios de aceptación** | 1. El sistema debe escanear el código del equipo y asociarlo al préstamo activo.<br>2. Debe permitir registrar observaciones o daños detectados.<br>3. Debe calcular automáticamente la multa por retraso.<br>4. El estado del equipo debe actualizarse a “Disponible” o “En mantenimiento”. |
| **Dependencias** | RF-UC-03 (entrega de equipo) y módulo de mantenimiento. |
| **Comentarios** | Se recomienda generar comprobante digital de devolución y enviar correo con el resumen del préstamo. |

---

#### **RF-UC-05 – Enviar alertas de vencimiento y sanciones**

| **Campo** | **Descripción** |
|------------|-----------------|
| **ID** | RF-UC-05 |
| **Nombre** | Enviar alertas de vencimiento y sanciones |
| **Descripción** | Funcionalidad mediante la cual el sistema notifica automáticamente a los usuarios cuando un préstamo está próximo a vencer o cuando se genera una multa o sanción por retraso. |
| **Prioridad** | Media |
| **Estabilidad** | Alta |
| **Fuente** | Dirección de TI / Encargada de préstamos |
| **Criterios de aceptación** | 1. El sistema debe enviar alertas automáticas 24h antes del vencimiento y cada día de retraso.<br>2. Debe notificar por correo institucional y mensaje interno.<br>3. Las multas generadas deben registrarse automáticamente.<br>4. Solo usuarios y administradores autorizados podrán ver las sanciones. |
| **Dependencias** | RF-UC-02 al RF-UC-04 (flujo de préstamo completo) y módulo de notificaciones. |
| **Comentarios** | Se sugiere incluir recordatorio visual en el panel del usuario al iniciar sesión. |

---

####  RF-LAB-001 – Registro y Control de Préstamo de Laboratorios
 
| **Campo** | **Detalle** |
|------------|-------------|
| **ID** | RF-LAB-001 |
| **Nombre** | Registro y Control de Préstamos de Laboratorio |
| **Descripción** | El sistema deberá permitir que los usuarios (docentes o estudiantes) soliciten el préstamo de laboratorios indicando fecha, hora, duración y propósito del uso. El sistema verificará la disponibilidad y registrará la reserva si no existen conflictos. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento funcional derivado de la gestión de espacios académicos en BiblioSys |
| **Criterios de aceptación** | - El sistema valida que no haya reservas duplicadas.<br>- El usuario recibe confirmación automática del préstamo.<br>- Se genera un código de reserva único. |
| **Dependencias** | Módulo de autenticación de usuarios, módulo de calendario de disponibilidad. |
| **Comentarios** | Este requerimiento extiende la funcionalidad del préstamo de recursos hacia los laboratorios físicos. |

####  RF-LAB-002 –  Validación de Disponibilidad y Capacidad del Laboratorio

| **Campo** | **Detalle** |
|------------|-------------|
| **ID** | RF-LAB-002 |
| **Nombre** | Validación de Disponibilidad y Capacidad del Laboratorio |
| **Descripción** | El sistema deberá mostrar en tiempo real la disponibilidad y capacidad de cada laboratorio, evitando sobreasignaciones y asegurando el cumplimiento de límites de aforo establecidos. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Solicitud del área de infraestructura académica |
| **Criterios de aceptación** | - El sistema bloquea reservas en horarios ocupados.<br>- Muestra mensaje de error si el aforo es superado.<br>- Permite filtrar por tipo de laboratorio o capacidad. |
| **Dependencias** | RF-LAB-001 (registro de préstamos), base de datos de laboratorios y aforos. |
| **Comentarios** | Permite mantener la integridad de la información de reservas y la seguridad de los usuarios. |

#### RF-LAB-003 – Control de Acceso y Registro de Uso del Laboratorio

| **Campo** | **Detalle** |
|------------|-------------|
| **ID** | RF-LAB-003 |
| **Nombre** | Control de Acceso y Registro de Uso del Laboratorio |
| **Descripción** | El sistema deberá registrar el ingreso y salida de los usuarios que utilicen laboratorios, mediante lectura de carnet institucional o código QR, para garantizar control de asistencia y trazabilidad de uso. |
| **Prioridad** | Media |
| **Estabilidad** | Alta |
| **Fuente** | Política de control institucional de recursos físicos |
| **Criterios de aceptación** | - Solo usuarios con reservas activas pueden ingresar.<br>- Se genera registro de ingreso y salida en el sistema.<br>- El historial queda disponible para reportes administrativos. |
| **Dependencias** | RF-LAB-001 (registro de préstamos), módulo de autenticación. |
| **Comentarios** | Mejora la trazabilidad y seguridad dentro de las instalaciones académicas. |

####  RF-LAB-004 –  Generación de Reportes de Uso de Laboratorios

| **Campo** | **Detalle** |
|------------|-------------|
| **ID** | RF-LAB-004 |
| **Nombre** | Generación de Reportes de Uso de Laboratorios |
| **Descripción** | El sistema deberá generar reportes automáticos y personalizados sobre el uso de laboratorios, indicando número de reservas, usuarios frecuentes, horarios de mayor demanda y uso por facultad. |
| **Prioridad** | Media |
| **Estabilidad** | Media |
| **Fuente** | Dirección Académica y Administrador del Sistema |
| **Criterios de aceptación** | - Reportes exportables en PDF y Excel.<br>- Filtros por fecha, tipo de laboratorio y usuario.<br>- Visualización gráfica en dashboard administrativo. |
| **Dependencias** | RF-LAB-001, RF-LAB-003 (datos históricos de uso). |
| **Comentarios** | Permite análisis estadístico para la toma de decisiones y planificación de recursos. |

#### **RF-UC-006 – Visualizar materiales del laboratorio         **
 
 
| **ID**                | RF-006 |
|-----------------------|--------|
| **Nombre**            | Visualizar materiales del laboratorio |
| **Descripción**       | El sistema debe permitir que los usuarios visualicen una lista clara y organizada de los materiales disponibles, incluyendo herramientas, componentes y recursos básicos. La información debe estar actualizada y visible. |
| **Prioridad**         | Media |
| **Estabilidad**       | Media |
| **Fuente**            | Consultar material y recursos del laboratorio |
| **Criterios de Aceptación** | 1. [Se muestra un listado organizado de materiales]<br>2. [La información está actualizada]<br>3. [Acceso permitido sin permisos especiales] |
| **Dependencias**      | Inventario básico del laboratorio |
| **Comentarios**       | Disponible para cualquier usuario registrado. |
 
#### **RF-UC-007 – Generar reporte general del laboratorio        **
 
| **ID**                | RF-007 |
|-----------------------|--------|
| **Nombre**            | Generar reporte general del laboratorio |
| **Descripción**       | El sistema debe permitir generar un informe completo con fallas reportadas, equipos utilizados, materiales solicitados y estadísticas generales. El reporte debe generarse sin errores y permitir su visualización|
| **Prioridad**         | Alta |
| **Estabilidad**       | Alta |
| **Fuente**            | Consultar reporte general del laboratorio |
| **Criterios de Aceptación** | 1. El reporte se genera sin errores.<br>2. Incluye todos los datos relevantes.<br>3. Se puede descargar en PDF. |
| **Dependencias**      | Datos históricos, inventario, reportes |
| **Comentarios**       | Usado par informar tanto a los usuarios como a los administradores |
|
 
#### **RF-UC-008 –  Actualizar datos del laboratorio  **
 
| **ID**                | RF-008 |
|-----------------------|--------|
| **Nombre**            | Actualizar datos del laboratorio |
| **Descripción**       | El sistema debe permitir al personal autorizado actualizar información importante del laboratorio, como horarios, disponibilidad y estado general. Los cambios deben reflejarse de inmediato y registrados. |
| **Prioridad**         | Alta |
| **Estabilidad**       | Media |
| **Fuente**            |Modificar datos del laboratorio |
| **Criterios de Aceptación** | 1. Los cambios se guardan correctamente.<br>2. La información se actualiza en tiempo real.<br>3. Solo usuarios con permisos pueden modificar datos. |
| **Dependencias**      | Módulo de autenticación y permisos |
| **Comentarios**       | Se vera la información a solo personas autorizadas |
 
#### **RF-UC-009 –Consultar tiempo restante del laboratorio **
 
| **ID**                | RF-009 |
|-----------------------|--------|
| **Nombre**            | Consultar tiempo restante del laboratorio |
| **Descripción**       | El sistema debe permitir que el usuario consulte de manera clara cuánto tiempo le queda disponible en su sesión actual dentro del laboratorio. El sistema mostrará el tiempo restante en minutos u horas, actualizándose automáticamente para que el usuario pueda organizar su trabajo antes de que finalice su turno. |
| **Prioridad**         | Alta |
| **Estabilidad**       | Alta |
| **Fuente**            | Consultar tiempo restante del laboratorio |
| **Criterios de Aceptación** | 1. El usuario puede ver el tiempo restante en pantalla.<br>2. El tiempo debe actualizarse en tiempo real.<br>3. El sistema debe mostrar una alerta cuando falten pocos minutos. |
| **Dependencias**      | Módulo de control de acceso y tiempo de uso |
| **Comentarios**       | Útil para informar al usuario del tiempo que tiene |

#### **RF-AUT-02  –Validación y autenticación segura de usuarios**
| *ID*                      | RF-AUT-02                                                                                                                                                                                                                                                                    |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *Nombre*                  | Validación y autenticación segura de usuarios                                                                                                                                                                                                                                 |
| *Descripción*             | El sistema debe encargarse de verificar que el usuario realmente es quien dice ser. Para esto, valida credenciales en la base de datos, revisa el estado de la cuenta (si está activa, suspendida o bloqueada) y genera una sesión segura para evitar accesos no autorizados. |
| *Prioridad*               | Esencial                                                                                                                                                                                                                                                                      |
| *Estabilidad*             | Alta                                                                                                                                                                                                                                                                          |
| *Fuente*                  | Área de Seguridad / TI                                                                                                                                                                                                                                                        |
| *Criterios de Aceptación* | 1. El sistema debe validar la contraseña usando métodos seguros (hash).<br>2. No debe permitir acceso si la cuenta está suspendida o bloqueada.<br>3. Debe crear una sesión segura después de autenticar correctamente al usuario.                                            |
| *Dependencias*            | Ninguna                                                                                                                                                                                                                                                                       |
| *Comentarios*             | Este requisito es la base para todo lo demás en el sistema; sin autenticación segura, nada más podría funcionar bien.                                                                           
#### **RF-AUT-01  –Inicio de sesión de usuarios**
| *ID*                      | RF-AUT-01                                                                                                                                                                                                                                                                                                              |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *Nombre*                  | Inicio de sesión de usuarios                                                                                                                                                                                                                                                                                            |
| *Descripción*             | El sistema debe permitir que cualquier usuario registrado pueda iniciar sesión ingresando su correo institucional y su contraseña. El sistema valida que los datos sean correctos, revisa que la cuenta esté activa y, si todo está bien, permite el acceso al sistema mostrando su panel correspondiente según su rol. |
| *Prioridad*               | Esencial                                                                                                                                                                                                                                                                                                                |
| *Estabilidad*             | Alta                                                                                                                                                                                                                                                                                                                    |
| *Fuente*                  | Área de TI / Usuarios finales                                                                                                                                                                                                                                                                                           |
| *Criterios de Aceptación* | 1. El usuario puede escribir su correo y contraseña sin restricciones.<br>2. El sistema debe validar que la cuenta exista y esté activa.<br>3. Si los datos son correctos, el usuario debe entrar directamente al sistema; si no, se muestra un mensaje claro y respetuoso indicando el error.                          |
| *Dependencias*            | RF-AUT-002                                                                                                                                                                                                                                                                                                              |
| *Comentarios*             | Después de varios intentos fallidos, el sistema puede aplicar bloqueo temporal para mayor seguridad.                                                                                                                                                                                                                    |                                                                              |

## 4 APÉNDICES

### 4.1 Modelos de casos de uso

**Lista de Casos de Uso del Sistema:**

- **CU-001**: Solicitar Préstamo de equipo
- **CU-002**: Realizar Devolución de Material
- **CU-003**: Registrar Nuevo Usuario
- **CU-004**: Renovar Prestamo
- **CU-005**: Proceso Pago de Multa
- **CU-006**: Reservar espacio de laboratorio
- **CU-007**: Configurar parametros de sistema

<br>

# **CU-01: Solicitar Préstamo de Equipo**
 
| **Campo** | **Descripción** |
| ---------- | --------------- |
| **ID** | CU-01 |
| **Nombre** | Solicitar Préstamo de Equipo |
| **Actores** | Usuario del laboratorio (actor primario), Sistema de Gestión del Laboratorio (actor secundario) |
| **Descripción** | Este caso de uso permite al usuario solicitar el préstamo de un equipo del laboratorio. El sistema verifica la disponibilidad del equipo y notifica al usuario si la reserva ha sido exitosa o si el equipo no está disponible. |
| **Precondiciones** | 1. El usuario ha iniciado sesión en el sistema.<br>2. El usuario está registrado y autorizado para realizar préstamos.<br>3. El sistema tiene inventario de equipos actualizado. |
| **Postcondiciones** | 1. Si el préstamo fue exitoso, el equipo queda reservado para el usuario.<br>2. Si el equipo no está disponible, el sistema notifica al usuario y no se realiza la reserva. |
| **Flujo Principal** | 1. El usuario accede al módulo “Préstamo de Equipos”.<br>2. El usuario selecciona el equipo que desea solicitar.<br>3. El sistema **verifica la disponibilidad del equipo** (<<include>> CU-01.1).<br>4. Si el equipo está disponible:<br> 4.1. El sistema registra la solicitud y marca el equipo como reservado.<br> 4.2. El sistema **notifica al usuario que la reserva fue exitosa** (<<extend>>).<br> 4.3. Fin del caso de uso.<br>5. Si el equipo **no está disponible**, el sistema **notifica al usuario la no disponibilidad del equipo** (<<extend>>).<br>6. Fin del caso de uso. |
| **Flujos Alternativos** | **5a. Equipo no disponible:**<br> 5a1. El sistema muestra mensaje “El equipo solicitado no se encuentra disponible en este momento”.<br> 5a2. El sistema puede sugerir equipos similares o permitir que el usuario programe una reserva futura.<br> 5a3. Fin del flujo alternativo. |
| **Flujos de Excepción** | **3a. Error en la verificación de disponibilidad:**<br> 3a1. Si ocurre un fallo en la comunicación con la base de datos o el sistema de inventario, se muestra el mensaje “Error al verificar la disponibilidad, intente más tarde”.<br> 3a2. Se registra el error en el log del sistema.<br> 3a3. El flujo termina sin crear la solicitud de préstamo. |
| **Requisitos Relacionados** | RF-001 (Gestión de préstamos)<br>RF-002 (Verificación de disponibilidad de equipo)<br>RF-003 (Notificación al usuario)<br>RNF-001 (Disponibilidad del sistema 99%)<br>RNF-002 (Tiempo máximo de respuesta 2 segundos) |
 
---
 
## **Subcaso de Uso Incluido**
 
| **Campo** | **Descripción** |
| ---------- | --------------- |
| **ID** | CU-01.1 |
| **Nombre** | Verificar Disponibilidad en el Sistema |
| **Tipo** | Subcaso de uso (<<include>>) |
| **Usado por** | CU-01: Solicitar Préstamo de Equipo |
| **Descripción** | Este subcaso valida si el equipo solicitado está disponible en el inventario del laboratorio antes de procesar el préstamo. |
| **Entradas** | Identificador del equipo solicitado. |
| **Salidas** | Estado de disponibilidad (Disponible / No disponible). |
| **Flujo Principal** | 1. El sistema recibe el ID del equipo solicitado.<br>2. Consulta el inventario del laboratorio.<br>3. Si el equipo está marcado como “Disponible”: devuelve estado = Disponible.<br>4. Si el equipo está marcado como “Prestado” o “En mantenimiento”: devuelve estado = No disponible.<br>5. Fin del subcaso. |
| **Excepciones** | **2a. Error de conexión al inventario:** El sistema notifica error de consulta y no permite continuar el préstamo. |

---
 
## **Subcasos Extendidos**

### **CU-01.A: Notificar al Usuario Reserva Exitosa**
 
| **Campo** | **Descripción** |
| ---------- | --------------- |
| **Tipo** | Subcaso de uso (<<extend>>) |
| **Descripción** | Envía un mensaje o alerta al usuario indicando que el préstamo del equipo fue procesado correctamente. |
| **Entradas** | ID del préstamo, datos del usuario. |
| **Salidas** | Confirmación visual o por correo electrónico. |
| **Flujo Principal** | 1. El sistema genera mensaje “Reserva exitosa”.<br>2. Muestra detalles del equipo, fecha y hora de retiro.<br>3. Fin del subcaso. |

---

### **CU-01.B: Notificar al Usuario No Disponibilidad del Equipo**

| **Campo** | **Descripción** |
| ---------- | --------------- |
| **Tipo** | Subcaso de uso (<<extend>>) |
| **Descripción** | Informa al usuario que el equipo no puede ser reservado por no estar disponible. |
| **Entradas** | ID del equipo, estado de disponibilidad. |
| **Salidas** | Mensaje de no disponibilidad en pantalla o correo electrónico. |
| **Flujo Principal** | 1. El sistema muestra mensaje “El equipo solicitado no está disponible actualmente”.<br>2. Ofrece opción para seleccionar otro equipo o programar reserva futura.<br>3. Fin del subcaso. |

### **Caso de Uso: CU-002 – Realizar Devolución de Material**
 
| **Campo** | **Descripción** |
|------------|----------------|
| **Nombre** | Realizar devolución de material |
| **Actores** | Usuario del laboratorio (actor primario), Administrador del sistema (actor secundario) |
| **Descripción** | Este caso de uso permite al administrador registrar la devolución de un artículo por parte del usuario. El sistema actualiza el estado del préstamo y genera las multas correspondientes si aplica. |
| **Precondiciones** | 1. El material ha sido entregado al administrador.<br>2. El administrador ha iniciado sesión en el sistema.<br>3. Existe un registro de préstamo activo para el material. |
| **Postcondiciones** | 1. El registro de préstamo se marca como “Cerrado” o “Devuelto”.<br>2. Se genera un registro de multa por retraso si aplica. |
| **Flujo Principal** | 1. El administrador ingresa el código del material o del préstamo.<br>2. El sistema recupera la información del préstamo activo.<br>3. El administrador confirma la devolución del material.<br>4. El sistema calcula si hubo retraso y genera multa en caso necesario.<br>5. El sistema actualiza el estado del préstamo a “Devuelto”.<br>6. Fin del caso de uso. |
| **Flujos Alternos** | **FA 2.1:** Material devuelto con retraso (se genera multa).<br>En el paso 4 del flujo principal, el sistema calcula la multa basada en el tiempo excedido y registra el valor correspondiente. |
| **Flujos de Excepción** | **FE 2.1:** Material devuelto dañado.<br>En el paso 3 del flujo principal, el administrador marca el material como “dañado”. El sistema registra el daño y genera una notificación al usuario. |
| **Requisitos Relacionados** | **RF 2.1:** El sistema debe poder identificar el préstamo activo a partir del código del material.<br>**RF 2.2:** El sistema debe recalcular las multas por retraso de acuerdo con las políticas vigentes. |
 
## **CU-003: Registrar Nuevo Usuario**
 
| **Campo** | **Descripción** |
|------------|----------------|
| **ID** | CU-003 |
| **Nombre** | Registrar Nuevo Usuario |
| **Actores** | Administrador del sistema (actor primario) |
| **Descripción** | Este caso de uso permite al administrador registrar un nuevo usuario en el sistema. El sistema valida los datos ingresados, genera las credenciales y almacena la información en la base de datos. |
| **Precondiciones** | 1. El administrador ha iniciado sesión en el sistema.<br>2. El sistema está disponible y conectado a la base de datos. |
| **Postcondiciones** | 1. El usuario queda registrado en el sistema.<br>2. El sistema genera credenciales de acceso para el nuevo usuario. |
| **Flujo Principal** | 1. El administrador accede al módulo “Gestión de Usuarios”.<br>2. El administrador selecciona la opción “Registrar nuevo usuario”.<br>3. El sistema muestra el formulario de registro.<br>4. El administrador ingresa los datos del usuario (nombre, correo, rol, etc.).<br>5. El sistema valida la información ingresada.<br>6. El sistema guarda los datos y genera las credenciales del usuario.<br>7. El sistema notifica al administrador que el registro fue exitoso.<br>8. Fin del caso de uso. |
| **Flujos Alternos** | **FA 5.1:** Datos incompletos.<br>En el paso 5, si faltan campos obligatorios, el sistema muestra un mensaje de error solicitando completar la información. |
| **Flujos de Excepción** | **FE 6.1:** Error al guardar en la base de datos.<br>En el paso 6, si ocurre un fallo en la conexión o escritura de datos, el sistema muestra el mensaje “No fue posible registrar al usuario. Intente nuevamente”. |
| **Requisitos Relacionados** | **RF 003.1:** El sistema debe validar que no existan usuarios con el mismo correo electrónico.<br>**RF 003.2:** El sistema debe asignar un rol predeterminado al usuario según el tipo de cuenta. |
 
## **CU-006: Renovar Préstamo**
 
| **Campo** | **Descripción** |
|------------|----------------|
| **ID** | CU-006 |
| **Nombre** | Renovar Préstamo |
| **Actores** | Usuario del laboratorio (actor primario), Administrador del sistema (actor secundario) |
| **Descripción** | Este caso de uso permite al usuario solicitar la renovación de un préstamo activo. El sistema verifica la disponibilidad del material y, si es posible, extiende la fecha de devolución. |
| **Precondiciones** | 1. El usuario ha iniciado sesión en el sistema.<br>2. Existe un préstamo activo registrado en el sistema.<br>3. El material solicitado no está reservado por otro usuario. |
| **Postcondiciones** | 1. La fecha de devolución del préstamo se actualiza.<br>2. El sistema registra la renovación en el historial de préstamos. |
| **Flujo Principal** | 1. El usuario accede al módulo “Mis Préstamos”.<br>2. El usuario selecciona el préstamo que desea renovar.<br>3. El sistema verifica que el material esté disponible para renovación.<br>4. El sistema actualiza la fecha de devolución del préstamo.<br>5. El sistema notifica al usuario que la renovación fue exitosa.<br>6. Fin del caso de uso. |
| **Flujos Alternos** | **FA 3.1:** Material reservado por otro usuario.<br>En el paso 3, si el material tiene una reserva activa, el sistema notifica al usuario que no es posible renovar el préstamo. |
| **Flujos de Excepción** | **FE 4.1:** Error en la actualización del registro.<br>En el paso 4, si el sistema no puede guardar la nueva fecha, muestra el mensaje “No fue posible renovar el préstamo. Intente nuevamente.” |
| **Requisitos Relacionados** | **RF 006.1:** El sistema debe validar la disponibilidad del material antes de la renovación.<br>**RF 006.2:** El sistema debe registrar la fecha de renovación en el historial del préstamo. |

## **CU-007: Procesar Pago de Multa**
 
| **Campo** | **Descripción** |
|------------|----------------|
| **ID** | CU-007 |
| **Nombre** | Procesar Pago de Multa |
| **Actores** | Usuario del laboratorio (actor primario), Administrador del sistema (actor secundario) |
| **Descripción** | Este caso de uso permite al usuario pagar una multa generada por la devolución tardía o el daño de un material. El sistema registra el pago y actualiza el estado de la multa. |
| **Precondiciones** | 1. El usuario ha iniciado sesión en el sistema.<br>2. Existe una multa activa asociada al usuario.<br>3. El sistema de pagos está disponible. |
| **Postcondiciones** | 1. La multa se marca como pagada.<br>2. El sistema registra el pago en el historial de transacciones. |
| **Flujo Principal** | 1. El usuario accede al módulo “Mis Multas”.<br>2. El usuario selecciona la multa pendiente de pago.<br>3. El sistema muestra el detalle de la multa y el monto a pagar.<br>4. El usuario selecciona el método de pago (efectivo, tarjeta, etc.).<br>5. El sistema procesa el pago.<br>6. El sistema actualiza el estado de la multa a “Pagada”.<br>7. El sistema genera un comprobante y lo muestra al usuario.<br>8. Fin del caso de uso. |
| **Flujos Alternos** | **FA 5.1:** Pago cancelado por el usuario.<br>En el paso 5, si el usuario cancela la operación, el sistema retorna al listado de multas sin registrar cambios. |
| **Flujos de Excepción** | **FE 5.2:** Error en la transacción.<br>En el paso 5, si ocurre un fallo con el proveedor de pagos, el sistema muestra el mensaje “Error en el procesamiento del pago. Intente nuevamente.” |
| **Requisitos Relacionados** | **RF 007.1:** El sistema debe registrar todos los pagos realizados por los usuarios.<br>**RF 007.2:** El sistema debe generar un comprobante de pago para cada transacción exitosa. |

| Campo | Descripción |
| :--- | :--- |
| **ID** | CU-019 |
| **Nombre** | **Reservar Espacio de Laboratorio** |
| **Actores** | Usuario del Laboratorio |
| **Descripción** | Permite al Usuario seleccionar una fecha, hora y un espacio o equipo fijo dentro del laboratorio para asegurar su uso en un periodo determinado. |
|---|---|
| **Precondiciones** | 1. Usuario ha iniciado sesión.<br>2. Espacio/recurso disponible.<br>3. El Usuario debe contar con identificación, carnet institucional y registro previo en el sistema. |
|---|---|
| **Postcondiciones** | 1. Se registra la reserva en el sistema, vinculada al Usuario y al espacio.<br>2. El espacio de laboratorio queda marcado como "Reservado" en el calendario de recursos. |
|---|---|
| **Flujo Principal (Pasos)** | 1. Usuario selecciona "Reservar Laboratorio/Espacio".<br>2. Sistema muestra disponibilidad .<br>3. Usuario selecciona fecha, horas y espacio.<br>4. Sistema verifica disponibilidad y límites.<br>5. Usuario confirma.<br>6. Sistema registra la reserva.<br>7. Sistema envía confirmación al Usuario. |
|---|---|
| **Flujos Alternos** | **FA 19.1:** Modificación de Reserva (cambio de hora). |
| **Flujos de Excepción** | **FE 19.1:** Límite de Reserva Excedido. |
|---|---|
| **Requisitos Relacionados** | **RF 19.1:** El sistema debe mostrar la disponibilidad de los espacios de laboratorio en tiempo real.<br>**RF 19.2:** El sistema debe permitir definir diferentes tipos de espacios con reglas de reserva específicas.<br>**RNF 19.1:** La interfaz de reserva debe proveer una vista calendario clara para facilitar la selección de horarios. |

 | Campo | Descripción |
| :--- | :--- |
| **ID** | CU-009 |
| **Nombre** | **Configurar Parámetros del Sistema** |
| **Actores** | Administrador del Sistema |
| **Descripción** | Permite al Administrador definir y ajustar los parámetros generales del sistema, incluyendo horarios de funcionamiento, políticas de préstamo y requisitos de los usuarios para el uso de equipos. |
|---|---|
| **Precondiciones** | 1. El Administrador ha iniciado sesión en el sistema.<br>2. El Administrador cuenta con permisos de configuración.<br>3. El sistema está en funcionamiento y con acceso a la base de datos de parámetros. |
|---|---|
| **Postcondiciones** | 1. Los parámetros quedan registrados y activos en el sistema.<br>2. Los cambios afectan inmediatamente las reglas de préstamo y disponibilidad de equipos. |
|---|---|
| **Flujo Principal** | 1. El Administrador accede al módulo “Parámetros del Sistema”.<br>2. El sistema muestra los parámetros configurables actuales.<br>3. El Administrador selecciona el parámetro a modificar o agregar.<br>4. El Administrador ingresa los nuevos valores (ej. horario de funcionamiento, política de préstamo, requisitos del usuario).<br>5. El sistema valida los valores ingresados.<br>6. El Administrador confirma la configuración.<br>7. El sistema guarda los cambios y actualiza las reglas de préstamo. |
|---|---|
| **Flujos Alternativos** | **FA 9.1: Modificación Rechazada**<br>1. El Administrador ingresa valores fuera de rango permitido.<br>2. El sistema muestra un mensaje de error indicando el parámetro inválido.<br>3. El Administrador corrige los valores y repite el proceso. |
| **Flujos de Excepción** | **FE 9.1: Error de Conexión**<br>1. El sistema no puede acceder a la base de datos de parámetros.<br>2. Se muestra mensaje “Error al guardar configuración, intente más tarde”.<br>3. Se registra el error en el log del sistema. |
|---|---|
| **Parámetros del Sistema** | - Horario de funcionamiento: Días y horas en que se pueden solicitar y devolver equipos.<br>- Política de préstamo: Tiempo máximo de uso de los equipos (ejemplo: por horas o por días).<br>- Requisitos del usuario: Identificación válida, carnet institucional y registro previo en el sistema. |
| **Requisitos Relacionados** | RF-009.1 (Gestión de parámetros configurables)<br>RF-009.2 (Validación de valores de configuración)<br>RNF-009.1 (Disponibilidad inmediata de cambios)<br>RNF-009.2 (Interfaz clara para administración) |

| Campo | Descripción |
| :--- | :--- |
| **ID** | CU-012 |
| **Nombre** | **Login (Iniciar Sesión)** |
| **Actores** | Usuario del Laboratorio, Administrador del Sistema |
| **Descripción** | Permite a cualquier usuario registrado acceder al sistema mediante la verificación de sus credenciales (nombre de usuario/email y contraseña). |
| **Precondiciones** | 1. El usuario tiene una cuenta activa en el sistema.<br>2. El sistema está operativo y con conexión a la base de datos de usuarios. |
| **Postcondiciones** | 1. El usuario es redirigido a la pantalla principal correspondiente a su rol (ej. 'Dashboard del Usuario' o 'Panel de Administración').<br>2. Se establece una sesión de usuario activa en el sistema. |
| **Flujo Principal** | 1. El Usuario accede a la página de inicio del sistema.<br>2. El Sistema muestra el formulario de inicio de sesión.<br>3. El Usuario ingresa su nombre de usuario/email y contraseña.<br>4. El Usuario presiona el botón "Iniciar Sesión".<br>5. El Sistema verifica las credenciales (Ver CU-014: Autenticar).<br>6. Si es exitoso, el Sistema crea la sesión y redirige al Dashboard. |
| **Flujos Alternativos** | **FA 12.1: Recuperación de Contraseña**<br>1. El Usuario selecciona la opción "¿Olvidó su contraseña?".<br>2. El Sistema solicita el email del Usuario y envía un enlace o código de recuperación.<br>3. El Usuario sigue el proceso externo para restablecer su contraseña. |
| **Flujos de Excepción** | **FE 12.1: Credenciales Inválidas**<br>1. En el paso 5 del Flujo Principal, el Sistema detecta que el usuario o la contraseña son incorrectos.<br>2. El Sistema muestra el mensaje "Usuario o contraseña inválida, por favor, intente de nuevo".<br>3. El flujo termina. |
| **Requisitos Relacionados** | RF-012.1: Validación de credenciales<br>RF-012.2: Soporte para recuperación de contraseña<br>RNF-012.1: Tiempo de respuesta: 1 segundo |

| Campo | Descripción |
| :--- | :--- |
| **ID** | CU-014 |
| **Nombre** | **Autenticar Credenciales** |
| **Actores** | Sistema de Gestión del Laboratorio (Actor Primario/Backend) |
| **Descripción** | Caso de uso interno que verifica la identidad de un usuario al comparar de forma segura el nombre de usuario y la contraseña proporcionada con los registros cifrados en la base de datos, determinando si el acceso debe ser concedido o denegado. |
| **Precondiciones** | 1. Se ha proporcionado un Nombre de Usuario/Email y una Contraseña cifrada para verificación.<br>2. La base de datos de usuarios es accesible. |
| **Postcondiciones** | 1. Se devuelve un resultado binario (Verdadero/Falso) sobre la validez de las credenciales. |
| **Flujo Principal** | 1. El caso de uso solicitante (ej. CU-012) llama a CU-014 con las credenciales.<br>2. El Sistema consulta la base de datos de usuarios para el Nombre de Usuario/Email.<br>3. El Sistema compara la contraseña proporcionada con la contraseña almacenada (cifrada).<br>4. El Sistema verifica el estado de la cuenta (activa/inactiva, bloqueada/desbloqueada).<br>5. **Si (Coincidencia y Activa):** El Sistema devuelve **VERDADERO** al caso de uso solicitante.<br>6. **Si (No Coincidencia o Inactiva):** El Sistema devuelve **FALSO** al caso de uso solicitante. |
| **Flujos Alternativos** | **FA 14.1: Cuenta Bloqueada**<br>1. En el paso 4, el Sistema detecta que la cuenta está bloqueada por múltiples intentos fallidos.<br>2. El Sistema devuelve **FALSO** y registra el intento fallido con la razón "Cuenta Bloqueada". |
| **Flujos de Excepción** | **FE 14.1: Error de Acceso a BD**<br>1. El Sistema no puede establecer conexión con la base de datos de usuarios.<br>2. El Sistema registra el error en el log y devuelve un código de error al solicitante. |
| **Requisitos Relacionados** | RF-014.1: Capacidad de consulta segura en BD<br>RNF-014.1: Seguridad: uso de cifrado avanzado para la protección de credenciales<br>RNF-014.2: Disponibilidad: 99.9% |

| Campo | Descripción |
| :--- | :--- |
| **ID** | CU-019 |
| **Nombre** | **Reservar Espacio de Laboratorio** |
| **Actores** | Usuario del Laboratorio |
| **Descripción** | Permite al Usuario seleccionar una fecha, hora y un espacio o equipo fijo dentro del laboratorio para asegurar su uso en un periodo determinado. |
|---|---|
| **Precondiciones** | 1. Usuario ha iniciado sesión.<br>2. Espacio/recurso disponible.<br>3. El Usuario debe contar con identificación, carnet institucional y registro previo en el sistema. |
|---|---|
| **Postcondiciones** | 1. Se registra la reserva en el sistema, vinculada al Usuario y al espacio.<br>2. El espacio de laboratorio queda marcado como "Reservado" en el calendario de recursos. |
|---|---|
| **Flujo Principal (Pasos)** | 1. Usuario selecciona "Reservar Laboratorio/Espacio".<br>2. Sistema muestra disponibilidad .<br>3. Usuario selecciona fecha, horas y espacio.<br>4. Sistema verifica disponibilidad y límites.<br>5. Usuario confirma.<br>6. Sistema registra la reserva.<br>7. Sistema envía confirmación al Usuario. |
|---|---|
| **Flujos Alternos** | **FA 19.1:** Modificación de Reserva (cambio de hora). |
| **Flujos de Excepción** | **FE 19.1:** Límite de Reserva Excedido. |
|---|---|
| **Requisitos Relacionados** | **RF 19.1:** El sistema debe mostrar la disponibilidad de los espacios de laboratorio en tiempo real.<br>**RF 19.2:** El sistema debe permitir definir diferentes tipos de espacios con reglas de reserva específicas.<br>**RNF 19.1:** La interfaz de reserva debe proveer una vista calendario clara para facilitar la selección de horarios. |

**Diagrama de Casos de Uso:**

Diagrama de caso de uso para la solicitud y prestamo de equipo.

![](https://img.plantuml.biz/plantuml/svg/XLJ1JXin4Br7oZzCmm4QDMc1jX888fAGRL4He2QHUeY4Xjr9PF3QY-sbq8eFwg6dVW8_rh6TaAK4LNjPZsVUctdpTW-iG-FANDPhhpAQ2aLmVFJfywXtF1x0sc0xsKeEbrSnkhMvyp7PhjVibL056ioXmFGAPpHqTvB0KEfGpIHLCqfBALg2d_KQG8_JPqQNAkjhgSsICLngav695ujOrnZzlHgwhzVgjNL8jFc11ZB1dAbu-AF0wQBbTEj2EwTzNmOXfqkkGya3O4YgrpYBCs6U5SgTqCg3Ek5uXaE1CsuR8IFeezNMluojteMXbY8LhinyvCmy_681S-qFW-jI53esjh-_3ztKQKFMlzThw0_GA6s9HkW6e8NnCdKeh2DcEpD2fQ906OiUbOJ68cCrgMt0MlB1FrvWhrZ4zQtFEwzWRupxhNURhoC7FAwcqMo6YsPpecoSahKjU0HFDb6CGu4jTjz_jmbhlTxX8EdzIxbG2uvKAakHSM3Zz4AA6R88Gjldr3Tan5IaF9-mXLRYGaYH8MOJHGf8WetZpvdFZqxwBt8ERXsfB99sfIEZq8cRLQHAkq3gpG7ppO3oarQRy8kMJoS_7tmRdP-SikP9ijD__r_GYM8HoTmWqArmsc8Lv_JB4kT-QOcl9DcjMh61KXqq27wAGuoXrUg45QmisDiJNlYCEfsgyBZG8EoktUxCfOJTQiKBY1Ha3O253w8a-tQfxqhikKoxbVBd2Jp_quIdzFwZzWkOol9IW_TYzl3REf7goBSENLlc8kTrNvSK4c1QgbZ8dGlsRU4DGSfHG0eczngs9KrTR6Guwew6aVf4E-JFd43dWYiaWgGx1a3UGrv8kiHeY4lYatu3TnY8bGOifBSmxprR_3wiy2N0uiy4IzRs50SCnZ_Slm00)

**Diagrama Caso de Uso 2**

<img height="127" alt="LogoTecLab" src="https://raw.githubusercontent.com/DevCarlos23/ProyectoLaboratorio/main/docs/Multimedia.jfif" />

**Diagrama Caso de Uso 3**

<img height="127" alt="LogoTecLab" src="https://raw.githubusercontent.com/DevCarlos23/ProyectoLaboratorio/main/docs/autenticacion 3.png" />

*Plantilla elaborada con propósitos académicos*  
*Basada en IEEE Std 830-1998*  
*Versión  1.0 - Octubre 2025*