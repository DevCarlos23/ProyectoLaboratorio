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
 
#### **RF-UC-009–Consultar tiempo restante del laboratorio   **
 
 
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

### 3.2 Requisitos de interfaz externa

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS DE INTERFAZ EXTERNA
═══════════════════════════════════════════════════════════════════════════════

DEFINICIÓN:
Los requisitos de interfaz externa describen CÓMO el sistema interactúa con
su entorno: usuarios (UI), hardware, otros sistemas (software), y redes (comunicación).

IMPORTANCIA:
Las interfaces son puntos críticos de falla. Una interfaz mal especificada puede
hacer que todo el sistema sea inutilizable incluso si la lógica interna es perfecta.

CATEGORÍAS:
3.2.1 Interfaz de Usuario (UI)
3.2.2 Interfaz de Hardware
3.2.3 Interfaz de Software
3.2.4 Interfaz de Comunicación
-->

#### 3.2.1 Interfaz de usuario

<!-- 
OBJETIVO:
Especificar características de las interfaces gráficas o de línea de comando
que los usuarios utilizarán para interactuar con el sistema.

QUÉ INCLUIR:
- Estándares de GUI (Material Design, Bootstrap, etc.)
- Resoluciones de pantalla soportadas
- Navegadores web soportados
- Accesibilidad
- Idiomas
- Layouts generales
- Flujos de navegación principales

QUÉ NO INCLUIR AQUÍ:
Mockups detallados de cada pantalla (esos van en Apéndices o documentos de diseño).
Aquí se especifican CARACTERÍSTICAS GENERALES de la UI.
-->

**RUI-001: Estándar de interfaz web responsiva**

El sistema DEBE proporcionar una interfaz web responsiva basada en HTML5, CSS3 y JavaScript. La interfaz DEBE adaptarse automáticamente a diferentes tamaños de pantalla:
- Escritorio: Resoluciones desde 1024x768 hasta 1920x1080 píxeles
- Tablet: Resoluciones desde 768x1024 hasta 1024x1366 píxeles
- Móvil: Resoluciones desde 320x568 hasta 428x926 píxeles

La interfaz DEBE seguir principios de diseño Material Design o Bootstrap para consistencia visual. Los elementos de navegación DEBEN reorganizarse apropiadamente en dispositivos móviles (menú hamburguesa, controles táctiles más grandes, etc.).

**RUI-002: Compatibilidad de navegadores**

El sistema DEBE funcionar correctamente en los siguientes navegadores web:
- Google Chrome versión 90 o superior
- Mozilla Firefox versión 88 o superior
- Microsoft Edge versión 90 o superior
- Safari versión 14 o superior (para usuarios de macOS/iOS)

El sistema DEBE detectar navegadores no soportados y mostrar un mensaje informativo sugiriendo actualizar o cambiar de navegador.

**RUI-003: Accesibilidad (WCAG 2.1 Nivel AA)**

La interfaz de usuario DEBE cumplir con las pautas WCAG 2.1 Nivel AA para garantizar accesibilidad a usuarios con discapacidades:

- **Contraste de color**: Relación de contraste mínima de 4.5:1 para texto normal y 3:1 para texto grande
- **Navegación por teclado**: Todas las funcionalidades DEBEN ser accesibles usando solo teclado (sin mouse)
- **Etiquetas ARIA**: Elementos interactivos DEBEN tener atributos ARIA apropiados
- **Texto alternativo**: Todas las imágenes funcionales DEBEN tener texto alternativo descriptivo
- **Tamaño de fuente**: El usuario DEBE poder aumentar el tamaño de texto hasta 200% sin pérdida de funcionalidad
- **Indicadores de foco**: Elementos enfocados DEBEN tener indicador visual claro
- **Lectores de pantalla**: La interfaz DEBE ser compatible con lectores de pantalla (JAWS, NVDA, VoiceOver)

**RUI-004: Idioma de la interfaz**

El sistema DEBE proporcionar interfaz en idioma español. Todos los mensajes del sistema, etiquetas de campos, botones, mensajes de error, y ayuda contextual DEBEN estar en español.

La interfaz DEBE usar terminología clara y consistente en todo el sistema. Por ejemplo, si se usa "Usuario" en un lugar, no usar "Cliente" en otro lugar para referirse a lo mismo.

REQUISITO FUTURO: Soporte multiidioma (inglés, portugués) - Ver sección 2.6.

**RUI-005: Mensajes de error y retroalimentación**

El sistema DEBE proporcionar mensajes de error claros, específicos y accionables:
- Los mensajes DEBEN indicar QUÉ salió mal
- Los mensajes DEBEN indicar CÓMO corregir el error
- Los mensajes NO DEBEN exponer información técnica sensible (stack traces, queries SQL)
- Los mensajes de error DEBEN usar color rojo e icono de advertencia
- Los mensajes de éxito DEBEN usar color verde e icono de confirmación
- Los mensajes informativos DEBEN usar color azul e icono de información

Ejemplo de mensaje de error correcto:
✓ "El número de documento ya está registrado. Verifique que el documento sea correcto o busque el usuario existente."

Ejemplo de mensaje de error incorrecto:
✗ "Error: Duplicate entry '12345678' for key 'users.documento'"

**RUI-006: Tiempo de espera y sesión**

El sistema DEBE mostrar indicadores visuales de carga (spinners, barras de progreso) durante operaciones que tomen más de 1 segundo.

La sesión de usuario DEBE expirar después de 30 minutos de inactividad. Dos minutos antes de la expiración, el sistema DEBE mostrar un modal de advertencia con opción de "Continuar sesión" o "Cerrar sesión". Si el usuario no responde, el sistema DEBE cerrar la sesión automáticamente y redirigir a la página de login.

**RUI-007: Navegación y estructura de menú**

La interfaz DEBE tener una barra de navegación principal consistente en todas las páginas con acceso a:
- Inicio / Panel principal
- Préstamos y devoluciones
- Búsqueda de catálogo
- Gestión de usuarios
- Reportes (solo para roles autorizados)
- Configuración (solo para Administradores)
- Perfil de usuario actual
- Botón de cerrar sesión

El sistema DEBE indicar visualmente la sección activa en el menú de navegación (highlighting).

**RUI-008: Ayuda contextual**

El sistema DEBE proporcionar ayuda contextual mediante iconos de ayuda (?) junto a campos o secciones que puedan requerir aclaración. Al hacer clic/hover sobre el icono, DEBE mostrarse un tooltip con explicación breve.

Para procesos complejos (ej: primer préstamo, registro de material nuevo), el sistema PUEDE proporcionar tour guiado opcional (walkthrough) para nuevos usuarios.

**RUI-009: Atajos de teclado**

El sistema DEBE soportar atajos de teclado para operaciones frecuentes:
- F2: Nueva búsqueda rápida
- F3: Nuevo préstamo
- F4: Nueva devolución
- Ctrl+G / Cmd+G: Ir a búsqueda global
- Esc: Cancelar operación actual / cerrar modal

El sistema DEBE mostrar una ventana de ayuda con todos los atajos disponibles cuando el usuario presione F1.

<!-- 
NOTA PARA ESTUDIANTES:
Pueden incluir MOCKUPS (bocetos de pantallas) en los Apéndices (Sección 4.3)
para complementar estos requisitos de interfaz. Los mockups son muy útiles pero
NO reemplazan los requisitos escritos.

Herramientas recomendadas para mockups:
- Figma (gratis para estudiantes)
- Balsamiq
- Draw.io
- Incluso papel y lápiz (escanear y adjuntar)
-->

[Complete con requisitos adicionales de interfaz de usuario según su proyecto]

<br>

#### 3.2.2 Interfaz de hardware

<!-- 
OBJETIVO:
Especificar características del hardware con el que el sistema interactuará
directamente, incluyendo dispositivos de entrada/salida, sensores, etc.

EJEMPLOS COMUNES:
- Lectores de código de barras
- Impresoras
- Dispositivos biométricos
- Cámaras
- Sensores
- Dispositivos de almacenamiento específicos

SI NO HAY INTERFACES DE HARDWARE:
Puede indicar explícitamente: "No aplica. El sistema no requiere interfaces con
hardware especializado más allá de computadoras estándar."
-->

**RHW-001: Lector de código de barras**

El sistema DEBE integrarse con lectores de código de barras USB compatibles con estándar HID (Human Interface Device). Específicamente, el sistema DEBE soportar el lector Zebra DS2208 que será utilizado en la biblioteca.

El lector de código de barras DEBE funcionar como entrada de teclado (modo emulación de teclado). Cuando se escanea un código de barras, el sistema DEBE recibir la secuencia de caracteres seguida de un Enter automático.

El sistema DEBE aceptar códigos de barras en los siguientes formatos:
- Code 39 (para carnets de biblioteca)
- Code 128 (para identificación de materiales)
- EAN-13 / ISBN (para libros comerciales)

El sistema DEBE validar que el código escaneado tenga formato válido antes de procesarlo. Si el código no es válido, DEBE mostrar mensaje de error y permitir reintentar el escaneo.

**RHW-002: Impresora térmica de tickets**

El sistema DEBE soportar impresión de comprobantes de préstamo en impresoras térmicas de 58mm o 80mm de ancho. El sistema DEBE generar tickets en formato ESC/POS compatible con la mayoría de impresoras térmicas.

Los comprobantes DEBEN incluir:
- Logo de la biblioteca (opcional, si la impresora soporta gráficos)
- Nombre de la biblioteca
- Número de carnet del usuario
- Nombre del usuario
- Lista de materiales prestados con código y título
- Fecha de préstamo
- Fecha de devolución
- Advertencia de multas por retraso
- Código QR opcional para consulta en línea

**RHW-003: Requisitos mínimos de hardware para estaciones de trabajo**

El sistema DEBE funcionar en computadoras con las siguientes especificaciones mínimas:
- Procesador: Intel Core i3 o AMD Ryzen 3 (o equivalente, mínimo dual-core 2.0 GHz)
- Memoria RAM: 4 GB mínimo, 8 GB recomendado
- Almacenamiento: 500 MB de espacio disponible (para cache del navegador)
- Pantalla: Resolución mínima 1024x768, recomendado 1366x768 o superior
- Conectividad: Puerto USB 2.0 o superior para lector de código de barras
- Red: Tarjeta de red Ethernet o WiFi para conexión a Internet

[Complete con otros requisitos de hardware si aplica a su proyecto]

<br>

#### 3.2.3 Interfaz de software

<!-- 
OBJETIVO:
Especificar cómo el sistema interactuará con otros sistemas de software,
incluyendo sistemas operativos, bases de datos, APIs externas, servicios web, etc.

INCLUIR:
- APIs de terceros que el sistema consumirá
- Servicios web que el sistema utilizará
- Integración con sistemas corporativos existentes
- Requisitos de bases de datos
- Bibliotecas o frameworks específicos (si son restricciones)

NIVEL DE DETALLE:
Suficiente para que los desarrolladores entiendan QUÉ integraciones son necesarias,
pero sin especificar excesivamente el CÓMO (eso va en diseño técnico).
-->

**RSW-001: Integración con Sistema Municipal de Identificación (SMI)**

El sistema DEBE integrarse con la API REST del Sistema Municipal de Identificación de Ciudadanos (SMI) versión 2.1 o superior.

**Endpoint a consumir**:
- URL: `https://api.municipalidad.gob/smi/v2/ciudadano/{tipo_documento}/{numero_documento}`
- Método: GET
- Autenticación: API Key en header `X-API-Key: [token]`

**Respuesta esperada** (JSON):
```json
{
  "valido": true,
  "datos": {
    "nombres": "Juan Carlos",
    "apellidos": "Pérez González",
    "fecha_nacimiento": "1990-05-15",
    "direccion": "Calle Principal 123"
  }
}
```

**Manejo de errores**:
- Timeout: 5 segundos máximo de espera
- Si la API retorna error 404: Documento no encontrado
- Si la API retorna error 500: Error del servidor externo
- Si no hay conectividad: Permitir operación sin validación

El sistema DEBE registrar todas las consultas a la API en el log del sistema para auditoría.

**RSW-002: Servidor de correo electrónico (SMTP)**

El sistema DEBE integrarse con el servidor SMTP institucional para envío de notificaciones por correo electrónico.

**Configuración SMTP**:
- Servidor: mail.municipalidad.gob
- Puerto: 587 (STARTTLS) o 465 (SSL/TLS)
- Autenticación: Usuario y contraseña proporcionados por IT de la municipalidad
- Remitente: biblioteca@municipalidad.gob

**Tipos de correos que el sistema enviará**:
- Bienvenida a nuevos usuarios
- Notificación de vencimiento de préstamo (7 días antes, 1 día antes, día del vencimiento)
- Notificación de préstamo vencido y multa generada
- Notificación de disponibilidad de material reservado
- Bloqueo de cuenta por intentos fallidos de login (RF-002)

Los correos DEBEN incluir:
- Logo de la biblioteca en el encabezado
- Contenido en HTML con fallback a texto plano
- Link para consultar detalles en el sistema (cuando aplique)
- Instrucciones claras de qué acción debe tomar el usuario
- Pie de página con información de contacto de la biblioteca

El sistema DEBE implementar cola de correos (queue) para no bloquear operaciones en caso de problemas con el servidor SMTP. Si un correo no se puede enviar, el sistema DEBE reintentar hasta 3 veces con intervalos de 5 minutos antes de marcarlo como "fallido".

**RSW-003: Base de datos PostgreSQL**

El sistema DEBE utilizar PostgreSQL versión 13 o superior como motor de base de datos.

**Requisitos de la base de datos**:
- Soporte de transacciones ACID
- Codificación UTF-8 para soporte de caracteres especiales
- Collation: es_ES.UTF-8 (o según localización)
- Timezone: Configurado según zona horaria local

El sistema DEBE crear esquema de base de datos con las siguientes características:
- Claves primarias en todas las tablas
- Claves foráneas con integridad referencial
- Índices en campos de búsqueda frecuente
- Constraints para validación de datos a nivel de BD
- Triggers para auditoría automática de cambios (opcional pero recomendado)

El sistema DEBE proporcionar scripts SQL para:
- Creación inicial del esquema
- Migración desde Excel (importación de datos legacy)
- Respaldo (backup) y restauración

**RSW-004: Servicios de respaldo (Backup)**

El sistema DEBE integrarse con el servicio de respaldo centralizado de la municipalidad mediante protocolo rsync o similar.

El sistema DEBE generar respaldos automáticos:
- **Respaldo completo**: Semanal (domingos a las 00:00)
- **Respaldo incremental**: Diario (cada día a las 00:00)
- **Respaldo de logs**: Diario (cada día a las 23:30)

Los respaldos DEBEN incluir:
- Dump completo de la base de datos
- Archivos de configuración del sistema
- Logs de auditoría
- Imágenes/documentos subidos al sistema (si los hay)

El sistema DEBE retener:
- Respaldos completos: Últimos 4 (4 semanas)
- Respaldos incrementales: Últimos 30 (30 días)
- Respaldos de logs: Últimos 90 días

El sistema DEBE notificar al administrador si un respaldo falla.

**RSW-005: Framework de desarrollo (Restricción técnica)**

[NOTA: Solo incluir esto si es una restricción REAL impuesta por el cliente o por estándares organizacionales. Normalmente, la elección de framework es decisión del equipo técnico y NO debe estar en requisitos, sino en diseño.]

Si el cliente/organización impone un framework específico, documentarlo así:

El sistema DEBE desarrollarse utilizando [Nombre del Framework] debido a estándares tecnológicos de la municipalidad. Todas las aplicaciones de la municipalidad usan este framework para facilitar mantenimiento futuro por el equipo interno de IT.

<!-- 
NOTA IMPORTANTE:
NO confunda requisitos de interfaz de software con decisiones de diseño técnico.

✓ CORRECTO (requisito):
"El sistema debe integrarse con el API de Sistema X para validar usuarios"

✗ INCORRECTO (decisión de diseño disfrazada de requisito):
"El sistema usará la biblioteca Axios para hacer llamadas HTTP"

La segunda es una decisión técnica que debe tomarse durante el diseño, no un requisito
del cliente (a menos que el cliente explícitamente lo exija por razones específicas).
-->

[Complete con otras integraciones de software relevantes para su proyecto]

<br>

#### 3.2.4 Interfaz de comunicación

<!-- 
OBJETIVO:
Especificar requisitos de comunicación en red, protocolos, seguridad de
comunicación, y requisitos de conectividad.

INCLUIR:
- Protocolos de red requeridos
- Requisitos de seguridad en comunicación
- Ancho de banda necesario
- Puertos de red
- Firewalls y configuraciones de red
- Cifrado de datos en tránsito
-->

**RCOM-001: Protocolo de comunicación web**

El sistema DEBE utilizar protocolo HTTPS (HTTP sobre TLS/SSL) para todas las comunicaciones entre navegador y servidor. El uso de HTTP sin cifrado NO DEBE ser permitido en producción.

El servidor DEBE configurarse con:
- Certificado SSL/TLS válido (no auto-firmado en producción)
- TLS versión 1.2 o superior
- Cipher suites modernos y seguros
- HTTP Strict Transport Security (HSTS) habilitado

Todas las páginas DEBEN forzar HTTPS. Si un usuario intenta acceder vía HTTP, DEBE ser redirigido automáticamente a HTTPS.

**RCOM-002: Requisitos de ancho de banda**

El sistema DEBE funcionar adecuadamente con la conexión a Internet existente de la biblioteca: 10 Mbps simétrica (download/upload).

El sistema DEBE optimizarse para uso eficiente del ancho de banda:
- Imágenes optimizadas y comprimidas
- Minificación de archivos CSS y JavaScript
- Uso de caché en navegador para recursos estáticos
- Compresión gzip/brotli para contenido textual

Con 10 Mbps, el sistema DEBE soportar al menos 15 usuarios simultáneos realizando operaciones normales sin degradación perceptible de rendimiento.

**RCOM-003: Puertos de red**

El sistema DEBE utilizar los siguientes puertos:

**Servidor Web**:
- Puerto 443 (HTTPS) - Acceso principal de usuarios
- Puerto 80 (HTTP) - Solo para redirigir a HTTPS

**Base de Datos** (acceso interno, no expuesto a Internet):
- Puerto 5432 (PostgreSQL) - Comunicación servidor web <-> BD

**SMTP** (salida):
- Puerto 587 (STARTTLS) o 465 (SSL/TLS) - Envío de correos

Todos los puertos DEBEN estar configurados en el firewall institucional. El equipo de IT de la municipalidad debe habilitar estos puertos antes del despliegue.

**RCOM-004: Seguridad en comunicación con APIs externas**

Todas las comunicaciones con APIs externas (Sistema Municipal de Identificación) DEBEN utilizar HTTPS.

Las API Keys o tokens de autenticación DEBEN:
- Almacenarse de forma segura (variables de entorno o vault, NO en código fuente)
- Transmitirse en headers HTTP, NUNCA en URL query parameters
- Tener fecha de expiración y mecanismo de renovación

El sistema DEBE implementar rate limiting para llamadas a APIs externas:
- Máximo 100 llamadas por minuto al SMI
- Implementar backoff exponencial si se reciben errores 429 (Too Many Requests)

**RCOM-005: Comunicación con impresora de red**

Si se utiliza impresora de red (no USB directa), el sistema DEBE comunicarse mediante:
- Protocolo: IPP (Internet Printing Protocol) o RAW TCP/IP
- Puerto: 631 (IPP) o 9100 (RAW)

La impresora DEBE estar en la misma red local que el servidor de aplicación para evitar problemas de latencia.

**RCOM-006: API REST del sistema (Requisito futuro)**

[En versión 1.0, el sistema NO expondrá API pública. Documentar como requisito futuro.]

En versiones futuras, el sistema PUEDE exponer una API REST pública para permitir integración con otras aplicaciones. Esta API deberá implementar:
- Autenticación mediante OAuth 2.0 o API Keys
- Versionamiento de API (v1, v2, etc.)
- Rate limiting por cliente
- Documentación OpenAPI/Swagger
- CORS configurado apropiadamente

Ver Sección 2.6 Requisitos Futuros.

[Complete con otros requisitos de comunicación específicos de su proyecto]

<br>

---

### 3.3 Requisitos no funcionales

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS NO FUNCIONALES
═══════════════════════════════════════════════════════════════════════════════

DEFINICIÓN:
Los requisitos no funcionales describen CÓMO debe comportarse el sistema, no QUÉ
debe hacer. Son atributos de calidad que el sistema debe poseer.

IMPORTANCIA CRÍTICA:
Los requisitos no funcionales son TAN IMPORTANTES como los funcionales, pero
frecuentemente se descuidan. Un sistema que hace todo lo que debe hacer (requisitos
funcionales) pero es lento, inseguro, o inestable, es un sistema FRACASADO.

CATEGORÍAS PRINCIPALES:
- Rendimiento (Performance)
- Fiabilidad (Reliability)
- Disponibilidad (Availability)
- Seguridad (Security)
- Mantenibilidad (Maintainability)
- Portabilidad (Portability)

PRINCIPIO FUNDAMENTAL:
Los requisitos no funcionales DEBEN ser CUANTIFICABLES y MEDIBLES.

✗ INCORRECTO: "El sistema será rápido"
✓ CORRECTO: "El sistema responderá a consultas en máximo 3 segundos en el 95% de los casos"

✗ INCORRECTO: "El sistema será seguro"
✓ CORRECTO: "El sistema cifrará todas las contraseñas usando bcrypt con factor de trabajo mínimo de 12"
-->

#### 3.3.1 Rendimiento

<!-- 
OBJETIVO:
Especificar requisitos de velocidad, tiempo de respuesta, throughput, capacidad,
y eficiencia de uso de recursos.

MÉTRICAS COMUNES:
- Tiempo de respuesta (response time)
- Throughput (transacciones por segundo)
- Utilización de recursos (CPU, memoria, disco, red)
- Capacidad (número de usuarios concurrentes, tamaño de base de datos)
-->

**RNFR-001: Tiempo de respuesta de interfaz web**

El sistema DEBE proporcionar tiempos de respuesta que garanticen una experiencia de usuario fluida:

- **Operaciones simples** (login, logout, navegación entre páginas): Máximo 1 segundo
- **Búsquedas en catálogo** (por título, autor, ISBN): Máximo 2 segundos
- **Operaciones de préstamo/devolución**: Máximo 3 segundos
- **Generación de reportes simples**: Máximo 5 segundos
- **Generación de reportes complejos**: Máximo 30 segundos
- **Importación masiva de datos**: Se permite mayor tiempo con indicador de progreso

Estos tiempos DEBEN cumplirse en el 95% de las operaciones (percentil 95) bajo condiciones normales de operación.

**Condiciones normales**: Hasta 15 usuarios concurrentes, base de datos con hasta 100,000 registros, servidor con carga CPU menor al 80%.

**RNFR-002: Capacidad de usuarios concurrentes**

El sistema DEBE soportar al menos 15 usuarios concurrentes simultáneos realizando operaciones sin degradación significativa de rendimiento (degradación <10% en tiempo de respuesta).

El sistema DEBE soportar hasta 50 usuarios concurrentes en momentos pico con degradación aceptable (<30% aumento en tiempo de respuesta).

**RNFR-003: Capacidad de almacenamiento de datos**

El sistema DEBE ser capaz de gestionar eficientemente:
- Hasta 100,000 registros de usuarios
- Hasta 50,000 materiales bibliográficos
- Hasta 500,000 registros de transacciones (préstamos/devoluciones) históricas
- Hasta 1,000,000 registros de auditoría

El rendimiento de búsquedas y operaciones NO DEBE degradarse significativamente cuando se alcancen estos volúmenes.

**RNFR-004: Utilización de recursos del servidor**

En condiciones normales de operación (15 usuarios concurrentes), el sistema NO DEBE exceder:
- 70% de uso de CPU
- 4 GB de uso de RAM
- 100 GB de almacenamiento en disco (incluyendo base de datos y logs)

El sistema DEBE liberar recursos apropiadamente (no memory leaks ni conexiones de BD sin cerrar).

**RNFR-005: Tamaño de página web**

Las páginas web del sistema (HTML + CSS + JS + imágenes) NO DEBEN exceder 2 MB de tamaño total por página para garantizar carga rápida incluso con conexiones lentas.

Recursos estáticos (CSS, JS, imágenes reutilizables) DEBEN configurarse con caché HTTP para evitar descargas repetidas.

**RNFR-006: Optimización de consultas a base de datos**

Las consultas SQL más frecuentes (búsqueda de usuarios, búsqueda de materiales, registro de préstamos) DEBEN completarse en menos de 100 milisegundos.

La base de datos DEBE tener índices apropiados en campos de búsqueda frecuente:
- Número de carnet de usuario
- ISBN o código de material
- Apellidos de usuario
- Título de material

<br>

#### 3.3.2 Fiabilidad

<!-- 
OBJETIVO:
Especificar requisitos sobre la capacidad del sistema de funcionar correctamente
bajo condiciones establecidas por un período de tiempo determinado.

MÉTRICAS COMUNES:
- MTBF (Mean Time Between Failures)
- MTTR (Mean Time To Repair)
- Tasa de errores aceptable
- Manejo de errores
- Recuperación ante fallos
-->

**RNFF-001: Tasa de fallos aceptable**

El sistema DEBE tener una tasa de fallos no superior a 1 fallo crítico por mes en promedio durante operación normal.

**Definición de fallo crítico**: Error que impide completamente el uso de una funcionalidad esencial (login, préstamos, devoluciones, búsqueda).

Errores menores (errores de validación, problemas de UI menores, features no esenciales) NO se consideran fallos críticos para este requisito.

**RNFF-002: Manejo robusto de errores**

El sistema DEBE manejar errores de forma elegante sin exponer al usuario a excepciones técnicas o pantallas en blanco:

- Errores de validación: Mostrar mensajes claros indicando qué corregir
- Errores de base de datos: Mostrar mensaje genérico y registrar error detallado en log
- Timeouts de APIs externas: Informar al usuario y ofrecer opción de reintentar
- Errores inesperados (500): Mostrar página de error amigable con opción de reportar el error

NINGÚN error DEBE exponer stack traces, queries SQL, o rutas del servidor al usuario.

**RNFF-003: Validación de datos**

El sistema DEBE validar TODOS los datos ingresados por usuarios tanto en cliente (JavaScript) como en servidor (backend) para prevenir datos corruptos o maliciosos:

- **Validación de formato**: Emails, fechas, números de documento, etc.
- **Validación de rangos**: Fechas futuras donde no aplica, números negativos donde no tiene sentido, etc.
- **Validación de integridad**: Claves foráneas válidas, relaciones consistentes
- **Sanitización**: Prevenir inyección SQL, XSS, etc.

Los datos rechazados DEBEN generar mensajes de error claros, NO simplemente fallar silenciosamente.

**RNFF-004: Integridad de transacciones**

Todas las operaciones críticas (préstamo, devolución, registro de usuario, modificación de catálogo) DEBEN ser transaccionales (ACID):

- **Atomicidad**: Si una operación falla, TODOS los cambios se revierten (rollback)
- **Consistencia**: Las reglas de negocio e integridad de BD se mantienen siempre
- **Aislamiento**: Operaciones concurrentes no interfieren entre sí
- **Durabilidad**: Operaciones completadas NO se pierden ante fallo del sistema

Ejemplo: Al registrar un préstamo, si se registra el préstamo pero falla el actualizar el estado del ejemplar, TODA la operación debe revertirse.

**RNFF-005: Recuperación ante errores de entrada**

Si un usuario ingresa datos incorrectos en un formulario largo (ej: registro de nuevo material bibliográfico con 20 campos), el sistema DEBE:
- Preservar todos los datos ya ingresados (no limpiar el formulario)
- Resaltar claramente los campos con error
- Permitir al usuario corregir solo los campos incorrectos sin reingresar todo

**RNFF-006: Logs detallados para diagnóstico**

El sistema DEBE registrar en logs:
- Todos los errores con timestamp, usuario afectado, y stack trace completo
- Advertencias (warnings) sobre situaciones anómalas
- Operaciones críticas completadas exitosamente
- Intentos de acceso no autorizado

Los logs DEBEN rotar diariamente y comprimirse después de 7 días. Los logs DEBEN retenerse por mínimo 90 días.

<br>

#### 3.3.3 Disponibilidad

<!-- 
OBJETIVO:
Especificar el porcentaje de tiempo que el sistema debe estar operativo y accesible.

MÉTRICAS COMUNES:
- Porcentaje de uptime (ej: 99.5%)
- Ventanas de mantenimiento permitidas
- Tiempo máximo de downtime
- Recuperación ante desastres
-->

**RNFD-001: Disponibilidad objetivo (Uptime)**

El sistema DEBE tener una disponibilidad mínima del 99.0% durante el horario de operación de la biblioteca (lunes a sábado, 8:00 AM a 8:00 PM).

**Cálculo**:
- Horario de operación: 12 horas/día × 6 días/semana = 72 horas/semana
- 99.0% uptime = Máximo 43 minutos de downtime no planificado por semana

Fuera del horario de operación, el sistema PUEDE estar inaccesible para mantenimiento sin afectar este SLA.

**RNFD-002: Ventanas de mantenimiento**

El sistema PUEDE tener downtime planificado para mantenimiento:
- **Mantenimiento regular**: Domingos de 00:00 a 06:00 (máximo 6 horas)
- **Actualizaciones mayores**: 2 veces por año, máximo 12 horas, con aviso de 1 semana de anticipación

El sistema DEBE mostrar página de mantenimiento informativa durante downtime planificado, indicando cuándo estará disponible nuevamente.

**RNFD-003: Monitoreo de disponibilidad**

El sistema DEBE implementar monitoreo automático de disponibilidad (health check):
- Endpoint: /health o /status
- Verificación cada 1 minuto
- Si el sistema no responde en 3 verificaciones consecutivas (3 minutos), se considera "down"

Si el sistema queda "down", DEBE enviarse notificación automática al administrador del sistema y al equipo de soporte de IT.

**RNFD-004: Recuperación ante fallo**

En caso de fallo del servidor principal, el sistema DEBE poder restablecerse en máximo 4 horas utilizando respaldos automáticos (ver RSW-004).

El proceso de recuperación DEBE estar documentado en un manual de operaciones con pasos claros para:
1. Identificar la causa del fallo
2. Decidir entre reparación vs. restauración desde backup
3. Ejecutar restauración desde último backup disponible
4. Verificar integridad de datos restaurados
5. Reiniciar servicio

[OPCIONAL: Si el presupuesto lo permite, especificar servidor de respaldo activo-pasivo para failover automático, pero esto puede estar fuera del alcance de proyectos pequeños]

**RNFD-005: Degradación controlada**

Si servicios externos (Sistema Municipal, servidor SMTP) no están disponibles, el sistema DEBE continuar operando con funcionalidad reducida en lugar de fallar completamente:

- Si SMI no está disponible: Permitir registro manual sin validación automática
- Si SMTP no está disponible: Encolar correos para envío posterior

El sistema DEBE informar al usuario cuando opera en "modo degradado" sin alarmar innecesariamente.

<br>

#### 3.3.4 Seguridad

<!-- 
OBJETIVO:
Especificar requisitos para proteger el sistema contra accesos no autorizados,
garantizar confidencialidad, integridad, y disponibilidad de la información (CIA Triad).

CATEGORÍAS:
- Autenticación
- Autorización
- Auditoría
- Confidencialidad
- Integridad de datos
- Protección contra ataques comunes
-->

**RNFS-001: Almacenamiento seguro de contraseñas**

El sistema NUNCA DEBE almacenar contraseñas en texto plano. Las contraseñas DEBEN almacenarse usando algoritmo de hashing fuerte:
- Algoritmo: bcrypt, scrypt, o Argon2
- Factor de trabajo (cost): Mínimo 12 para bcrypt
- Cada contraseña DEBE tener sal (salt) única generada aleatoriamente

El sistema NUNCA DEBE permitir recuperación de contraseñas (NO "enviar contraseña"), solo restablecimiento mediante token temporal.

**RNFS-002: Política de contraseñas**

El sistema DEBE aplicar política de contraseñas seguras:

**Para usuarios del sistema (bibliotecarios, administradores)**:
- Longitud mínima: 8 caracteres
- DEBE contener al menos: 1 mayúscula, 1 minúscula, 1 número, 1 carácter especial
- NO DEBE ser contraseña común (comparar contra lista de passwords comprometidos)
- DEBE cambiarse cada 90 días
- NO DEBE reutilizarse las últimas 5 contraseñas

**Para usuarios finales (clientes biblioteca)**: Política más relajada
- Longitud mínima: 6 caracteres
- Al menos 1 letra y 1 número

**RNFS-003: Cifrado de comunicaciones**

El sistema DEBE cifrar TODA comunicación sensible:
- HTTPS (TLS 1.2+) para todas las páginas web - Sin excepciones
- Conexiones a base de datos cifradas (si BD está en servidor separado)
- Tokens de API y credenciales transmitidas en headers cifrados, NUNCA en URL

**RNFS-004: Protección contra ataques comunes**

El sistema DEBE implementar protecciones contra vectores de ataque comunes:

**SQL Injection**:
- Usar prepared statements o ORMs
- NUNCA concatenar strings para construir queries SQL

**Cross-Site Scripting (XSS)**:
- Sanitizar TODAS las entradas de usuario antes de renderizar en HTML
- Usar Content Security Policy (CSP) headers

**Cross-Site Request Forgery (CSRF)**:
- Implementar tokens CSRF en todos los formularios
- Validar tokens en el servidor

**Clickjacking**:
- Usar X-Frame-Options: DENY o SAMEORIGIN header

**Brute Force**:
- Implementar bloqueo de cuenta después de intentos fallidos (ver RF-002)
- Implementar CAPTCHA después de 3 intentos fallidos (opcional)

**RNFS-005: Autorización y control de acceso**

El sistema DEBE verificar permisos en CADA operación, no solo en la UI:
- Verificación en backend, no confiar en controles de UI
- Principio de menor privilegio: usuarios solo acceden a lo estrictamente necesario
- Denegación por defecto: lo que no está explícitamente permitido, está prohibido

El sistema DEBE prevenir escalamiento de privilegios: un usuario con rol Bibliotecario NO DEBE poder ejecutar operaciones de Administrador aunque intente manipular requests HTTP.

**RNFS-006: Auditoría de seguridad**

El sistema DEBE registrar eventos de seguridad:
- Todos los logins exitosos y fallidos
- Cambios de contraseña
- Cambios de permisos de usuario
- Accesos a datos sensibles (historial de préstamos de usuarios)
- Intentos de acceso no autorizado
- Modificaciones a configuración del sistema

Los registros de auditoría DEBEN incluir: timestamp, usuario, dirección IP, acción, recurso afectado, resultado (éxito/fallo).

Los logs de auditoría DEBEN ser inmutables (append-only) y almacenarse de forma segura.

**RNFS-007: Gestión de sesiones**

Las sesiones de usuario DEBEN ser seguras:
- IDs de sesión generados criptográficamente aleatorios (mínimo 128 bits)
- Sesiones almacenadas en servidor, NO en cookies del cliente (excepto session ID)
- Timeout de inactividad: 30 minutos
- Sesión invalidada completamente al hacer logout
- Protección contra session fixation: regenerar session ID después de login exitoso

**RNFS-008: Protección de datos personales (GDPR/LOPD)**

El sistema DEBE cumplir con regulaciones de protección de datos:
- Almacenar solo datos personales estrictamente necesarios
- Permitir a usuarios solicitar eliminación de sus datos (derecho al olvido)
- Permitir a usuarios exportar sus datos (portabilidad de datos)
- Obtener consentimiento explícito para procesamiento de datos (al registrarse)
- Notificar a usuarios sobre brechas de seguridad que afecten sus datos

Los datos sensibles (historial de préstamos, datos personales) NO DEBEN ser accesibles por personal no autorizado.

**RNFS-009: Respaldos seguros**

Los respaldos de la base de datos DEBEN estar cifrados. Las claves de cifrado NO DEBEN almacenarse en el mismo servidor que los respaldos.

<br>

#### 3.3.5 Mantenibilidad

<!-- 
OBJETIVO:
Especificar qué tan fácil debe ser mantener, modificar, y extender el sistema.

ASPECTOS:
- Documentación del código
- Estructura modular
- Facilidad de diagnóstico de problemas
- Facilidad de actualización
-->

**RNFM-001: Documentación del código**

El código fuente DEBE estar documentado de forma que futuros desarrolladores puedan entenderlo y modificarlo:

- Funciones y métodos complejos DEBEN tener comentarios explicando QUÉ hacen y POR QUÉ (no solo CÓMO)
- Clases y módulos DEBEN tener docstrings/javadocs describiendo su propósito
- README principal DEBE explicar cómo instalar, configurar, y ejecutar el proyecto
- README DEBE incluir instrucciones para ambiente de desarrollo local

**RNFM-002: Código limpio y estándares**

El código DEBE seguir estándares de codificación reconocidos:
- Nombres de variables, funciones, y clases descriptivos (no abreviaciones crípticas)
- Funciones pequeñas con responsabilidad única (idealmente <50 líneas)
- DRY (Don't Repeat Yourself): evitar código duplicado
- Seguir guías de estilo del lenguaje (PEP8 para Python, PSR para PHP, etc.)

El proyecto DEBE incluir linter configurado para verificar cumplimiento de estándares.

**RNFM-003: Modularidad**

El sistema DEBE estructurarse en módulos independientes con responsabilidades claras:
- Separación entre lógica de negocio, acceso a datos, y presentación (MVC o similar)
- Bajo acoplamiento entre módulos
- Alta cohesión dentro de módulos

Modificaciones en un módulo NO DEBEN requerir cambios en múltiples otros módulos (excepto casos justificados).

**RNFM-004: Facilidad de configuración**

Parámetros configurables del sistema (URLs de APIs, credenciales de BD, timeouts, límites, etc.) NO DEBEN estar hardcodeados en el código fuente.

La configuración DEBE externalizarse en:
- Archivo de configuración (config.ini, .env, etc.)
- Variables de entorno
- Base de datos de configuración (para parámetros modificables desde UI de administración)

Cambios de configuración NO DEBEN requerir recompilación o modificación de código.

**RNFM-005: Logs para diagnóstico**

El sistema DEBE generar logs suficientemente detallados para diagnosticar problemas:
- Niveles de log apropiados: DEBUG, INFO, WARNING, ERROR, CRITICAL
- En producción: nivel INFO o WARNING como mínimo
- En desarrollo: nivel DEBUG disponible
- Logs DEBEN incluir contexto: usuario, operación intentada, datos relevantes (sin exponer información sensible)

**RNFM-006: Manejo de dependencias**

El proyecto DEBE documentar claramente todas las dependencias externas:
- Archivo requirements.txt (Python), package.json (Node.js), composer.json (PHP), etc.
- Versiones específicas o rangos de versiones compatibles
- Instrucciones para instalar dependencias

Actualizaciones de dependencias DEBEN probarse en ambiente de staging antes de producción.

<br>

#### 3.3.6 Portabilidad

<!-- 
OBJETIVO:
Especificar qué tan fácil es transferir el sistema a diferentes entornos o plataformas.

ASPECTOS:
- Independencia de plataforma
- Facilidad de migración
- Compatibilidad
-->

**RNFP-001: Independencia de sistema operativo del servidor**

El sistema DEBE poder ejecutarse en servidores Linux (Ubuntu 20.04+, Debian 10+, CentOS 8+) sin modificaciones.

El sistema PUEDE ser compatible con otros sistemas operativos (Windows Server, macOS) pero esto NO es un requisito esencial.

**RNFP-002: Compatibilidad de base de datos**

Aunque el sistema usará PostgreSQL en producción (ver restricción RSW-003), el código DEBE estructurarse de forma que migrar a otro RDBMS (MySQL, MariaDB) requiera cambios mínimos.

Esto se logra usando:
- ORM (Object-Relational Mapping) que abstrae el motor de BD
- Evitar queries SQL específicas de PostgreSQL (a menos que sean críticas para rendimiento)

**RNFP-003: Contenedorización (Deseable)**

[Este es un requisito DESEABLE, no esencial para v1.0]

El sistema DEBERÍA poder empaquetarse en contenedores Docker para facilitar despliegue en diferentes entornos:
- Dockerfile para construir imagen del sistema
- docker-compose.yml para orquestar contenedores (app, BD, nginx)

Esto facilitaría:
- Despliegue consistente en desarrollo, staging, y producción
- Migración futura a servicios cloud (AWS, Azure, GCP)
- Escalabilidad horizontal (múltiples instancias)

**RNFP-004: Independencia de ruta de instalación**

El sistema NO DEBE asumir rutas fijas del sistema de archivos hardcodeadas. Las rutas DEBEN ser configurables o relativas a la ubicación de instalación.

Esto permite instalar el sistema en diferentes directorios según las políticas de cada organización.

**RNFP-005: Exportación de datos**

El sistema DEBE permitir exportar datos en formatos estándar para facilitar migración futura:
- Exportación de catálogo de materiales: CSV, JSON, MARCXML
- Exportación de usuarios: CSV, JSON
- Exportación de transacciones: CSV, JSON

Esto garantiza que los datos NO quedan "atrapados" en el sistema.

---

### 3.4 Requisitos de diseño

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS DE DISEÑO
═══════════════════════════════════════════════════════════════════════════════

OBJETIVO:
Especificar restricciones o decisiones de diseño que deben seguirse por razones
específicas (regulatorias, estándares organizacionales, compatibilidad, etc.).

NOTA IMPORTANTE:
Esta sección es OPCIONAL y debe usarse con cuidado. En general, se debe dar
libertad al equipo de diseño para tomar decisiones técnicas. Solo incluir aquí
decisiones de diseño que son IMPUESTAS por requisitos externos no negociables.

DIFERENCIA CLAVE:
- Restricción legítima: "El sistema debe seguir el manual de identidad visual de la municipalidad"
- Micro-gestión técnica: "El sistema debe usar patrón MVC con controladores en carpeta /app/controllers"

La segunda es una decisión técnica que debe quedar en manos del equipo de desarrollo,
a menos que haya una razón de negocio FUERTE para especificarla.
-->

**RD-001: Estándares de interfaz de usuario**

El diseño de la interfaz de usuario DEBE seguir el Manual de Identidad Visual de la Municipalidad disponible en [URL o referencia]:

- Paleta de colores: Usar colores oficiales de la municipalidad
  - Primario: #004B87 (azul institucional)
  - Secundario: #FFB81C (amarillo institucional)
  - Textos: #333333
  - Fondos: #FFFFFF, #F5F5F5

- Tipografía: Usar fuentes oficiales
  - Encabezados: Montserrat Bold
  - Cuerpo de texto: Open Sans Regular

- Logo: Incluir logo oficial de la municipalidad en header de todas las páginas

**RD-002: Formato de reportes**

Los reportes generados por el sistema DEBEN seguir el formato estándar de documentos de la biblioteca:
- Header con logo y nombre de la biblioteca
- Pie de página con dirección, teléfono, y sitio web
- Formato PDF con metadatos adecuados (título, autor, fecha de creación)

**RD-003: Nomenclatura de identificadores**

El sistema DEBE seguir las siguientes convenciones de nomenclatura establecidas por la biblioteca:

- **Carnets de usuarios**: Formato "BMUN-XXXXXX" donde XXXXXX es número consecutivo
- **Código de materiales**: 
  - Libros: ISBN-13 cuando disponible
  - Otros materiales: "MAT-XXXXXX" número consecutivo
- **Números de préstamo**: Formato "PREST-AAAA-XXXXXX" donde AAAA es año y XXXXXX consecutivo del año

[Si NO hay restricciones específicas de diseño impuestas externamente, puede indicarlo explícitamente]

**Nota**: Además de los requisitos anteriores, las decisiones de arquitectura y diseño técnico del sistema (patrones de diseño, estructura de base de datos, organización de código, etc.) quedan a criterio del equipo de desarrollo, siempre que cumplan con todos los requisitos funcionales y no funcionales especificados en este documento.

<br>

---

### 3.5 Requisitos de calidad

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS DE CALIDAD
═══════════════════════════════════════════════════════════════════════════════

OBJETIVO:
Especificar estándares de calidad que el sistema y el proceso de desarrollo deben cumplir.

NOTA: Algunos de estos requisitos pueden solaparse con requisitos no funcionales.
La diferencia es que aquí especificamos procesos y prácticas de calidad, mientras
que en RNF especificamos atributos del sistema final.
-->

**RC-001: Cobertura de pruebas**

El sistema DEBE tener pruebas automatizadas con cobertura mínima de:
- **Pruebas unitarias**: 70% de cobertura del código
- **Pruebas de integración**: Todas las integraciones críticas (SMI, SMTP, BD)
- **Pruebas de interfaz (E2E)**: Flujos de usuario principales (login, préstamo, devolución, búsqueda)

Las pruebas DEBEN ejecutarse automáticamente antes de cada despliegue. Un despliegue NO DEBE realizarse si las pruebas fallan.

**RC-002: Revisión de código**

Todo código antes de fusionarse a la rama principal (main/master) DEBE pasar por:
- Revisión por al menos un desarrollador adicional (peer review)
- Aprobación explícita del revisor
- Pasar todas las pruebas automatizadas
- Cumplir con los estándares de código (verificado por linter)

**RC-003: Control de versiones**

El proyecto DEBE usar sistema de control de versiones (Git) con las siguientes prácticas:
- Commits frecuentes con mensajes descriptivos
- Rama main/master siempre en estado desplegable (no romper main)
- Feature branches para desarrollo de nuevas funcionalidades
- Tags para versiones de producción (v1.0, v1.1, etc.)

**RC-004: Ambiente de staging**

El sistema DEBE probarse en ambiente de staging (idéntico a producción) antes de cada despliegue a producción. Los despliegues a producción SOLO se realizan si las pruebas en staging son exitosas.

**RC-005: Plan de pruebas**

El equipo DEBE crear un Plan de Pruebas documentado que especifique:
- Casos de prueba para cada requisito funcional
- Estrategia de pruebas (unitarias, integración, sistema, aceptación)
- Criterios de aceptación
- Responsables de ejecutar pruebas

<br>

---

### 3.6 Restricciones del sistema

<!-- 
Esta sección puede usarse para enumerar restricciones adicionales no cubiertas
en secciones previas, o puede referenciarse a la Sección 2.4 si todas las
restricciones ya fueron documentadas allí.
-->

Ver Sección 2.4 para restricciones completas del sistema. Las restricciones principales son:

- Restricciones tecnológicas: Servidores Linux existentes, PostgreSQL como BD
- Restricciones de integración: API del Sistema Municipal de Identificación v2.1
- Restricciones presupuestarias: Máximo $25,000 USD
- Restricciones de tiempo: Implementación en 6 meses
- Restricciones de personal: Equipo de 4 personas
- Restricciones regulatorias: Cumplimiento de Ley de Protección de Datos Personales

[O puede expandir con restricciones adicionales no mencionadas en 2.4]

<br>

---

### 3.7 Atributos del sistema

<!-- 
Esta sección puede usarse para especificar atributos adicionales del sistema
no cubiertos en otras secciones, o puede omitirse si todo ya está documentado.

Ejemplos de atributos adicionales:
- Estándares de documentación
- Procesos de entrega
- Capacitación requerida
- Garantías y soporte post-implementación
-->

**A-001: Documentación de usuario**

El sistema DEBE incluir:
- **Manual de Usuario Final** (para clientes de biblioteca que usen catálogo en línea): Mínimo 10 páginas, con capturas de pantalla
- **Manual de Usuario del Sistema** (para bibliotecarios): Mínimo 30 páginas, con procedimientos paso a paso para todas las operaciones
- **Manual de Administrador**: Mínimo 20 páginas, incluyendo configuración, respaldos, solución de problemas
- **Ayuda en línea**: Documentación contextual accesible desde la interfaz del sistema

Toda la documentación DEBE estar en español y en formato PDF.

**A-002: Capacitación del personal**

El proveedor del sistema DEBE proporcionar capacitación al personal de la biblioteca:
- **Capacitación para bibliotecarios**: 2 sesiones de 4 horas (total 8 horas)
  - Sesión 1: Operaciones diarias (préstamos, devoluciones, búsqueda)
  - Sesión 2: Gestión de usuarios, reportes básicos
  
- **Capacitación para administradores**: 2 sesiones de 4 horas (total 8 horas)
  - Sesión 1: Configuración del sistema, gestión de catálogo
  - Sesión 2: Respaldos, solución de problemas, reportes avanzados

La capacitación DEBE incluir material impreso y ejercicios prácticos. DEBE realizarse en las instalaciones de la biblioteca.

**A-003: Período de garantía**

El sistema DEBE incluir garantía de 12 meses desde la fecha de aceptación en producción, que incluye:
- Corrección de errores (bugs) sin costo adicional
- Soporte técnico vía email con tiempo de respuesta máximo de 48 horas laborales
- Actualizaciones de seguridad sin costo

Después del período de garantía, se establecerá contrato de mantenimiento separado (fuera del alcance de este SRS).

**A-004: Migración de datos**

El proveedor DEBE realizar la migración de datos desde el sistema actual (Excel) al nuevo sistema, incluyendo:
- Importación de catálogo de materiales (~25,000 registros)
- Importación de usuarios (~15,000 registros)
- Validación de integridad de datos migrados
- Generación de reporte de migración con estadísticas y problemas encontrados

La migración DEBE realizarse en coordinación con el personal de la biblioteca para resolver inconsistencias en datos legacy.

**A-005: Criterios de aceptación del sistema**

El sistema se considerará aceptado cuando:
1. Todos los requisitos funcionales esenciales estén implementados y probados
2. Todos los requisitos no funcionales esenciales se cumplan
3. La migración de datos se haya completado exitosamente
4. La capacitación del personal se haya completado
5. El sistema haya operado en producción por 2 semanas sin errores críticos
6. El cliente firme documento de aceptación formal

<br>

---

## 4 APÉNDICES

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 4: APÉNDICES
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO:
Los apéndices contienen información complementaria que respalda y aclara las
secciones anteriores, pero que por su extensión o naturaleza se documenta mejor
por separado.

CONTENIDO TÍPICO:
- Modelos de casos de uso
- Diagramas del sistema
- Prototipos de interfaces
- Esquemas de base de datos
- Matrices de trazabilidad
- Glosario extendido
- Análisis de requisitos
- Criterios de evaluación

NOTA IMPORTANTE:
Los apéndices NO son opcionales si contienen información crítica para entender
los requisitos. Son parte integral del SRS.
-->

### 4.1 Modelos de casos de uso

<!-- 
Los casos de uso describen interacciones completas entre actores y el sistema
para lograr un objetivo específico. Complementan los requisitos funcionales
proporcionando contexto y flujos de trabajo.
-->

**Lista de Casos de Uso del Sistema:**

- **CU-01**: Solicitar Préstamo de equipo
- **CU-002**: Realizar Devolución de Material
- **CU-003**: Registrar Nuevo Usuario
- **CU-004**: Buscar Material en Catálogo
- **CU-005**: Crear Reserva de Material
- **CU-006**: Renovar Préstamo
- **CU-007**: Procesar Pago de Multa
- **CU-008**: Generar Reporte de Materiales Más Prestados
- **CU-009**: Configurar Parámetros del Sistema
- **CU-010**: Realizar Respaldo de Datos
- ... [continuar según necesidad]

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

<!-- 
Opción 2: Plantilla para Subcasos Simples

Para subcasos simples pero que aún merecen documentación separada:

| **Campo**           | **Descripción**                                                  |
| ------------------- | ---------------------------------------------------------------- |
| **ID**              | CU-XXX.Y                                                         |
| **Nombre**          | [Nombre del Subcaso]                                             |
| **Usado por**       | CU-AAA, CU-BBB                                                   |
| **Propósito**       | [Breve descripción: qué hace y por qué existe el subcaso]        |
| **Entradas**        | [Datos o parámetros que recibe del caso de uso padre]            |
| **Salidas**         | [Datos o resultados que retorna al caso de uso padre]            |
| **Flujo Principal** | 1. [Paso 1]<br>2. [Paso 2]<br>3. [Paso 3]                        |
| **Excepciones**     | [Descripción de las excepciones o errores manejados, si los hay] |


Opción 3: **Documentación Inline (No es Subcaso Separado)**

Cuando NO merece subcaso separado, documentar directamente en el flujo principal:

CU-001: Realizar Préstamo

Flujo Principal
1. El bibliotecario selecciona "Nuevo Préstamo"
2. El sistema solicita identificación del usuario
3. El bibliotecario ingresa carnet
4. **El sistema valida estado del usuario:**
   4.1. Verifica que usuario existe en BD
   4.2. Verifica que usuario.estado = "activo"
   4.3. Verifica que multas vencidas = 0
   4.4. Si alguna validación falla → Excepción 4a
5. El sistema muestra información del usuario
-->


<!--
## ERRORES COMUNES

### **Error 1: Documentar todo como subcaso**

**Incorrecto:**

CU-001: Login
  └─ CU-001.1: Mostrar Formulario de Login  ← NO merece subcaso
  └─ CU-001.2: Validar Formato de Email     ← Trivial
  └─ CU-001.3: Verificar Credenciales       ← SÍ es subcaso
  └─ CU-001.4: Crear Sesión                 ← Trivial
  └─ CU-001.5: Redirigir a Dashboard        ← Trivial


**Correcto:**

CU-001: Login
  Pasos inline: 1-10
  Paso 4: [Subcaso incluido: CU-VAL-001 Verificar Credenciales]
  Otros pasos: documentados inline


### **Error 2: Confundir subcaso con función técnica**

**Incorrecto subcaso:**

CU-LOG-001: Escribir en Log
  Propósito: Guardar mensaje en archivo de log

  Flujo:
  1. Abrir archivo log en modo append
  2. Escribir timestamp + nivel + mensaje
  3. Cerrar archivo


**Problema:** Esto es una **función técnica**, no un subcaso de uso. No tiene lógica de negocio, no le importa al usuario final.

**Correcto:** Documentar como función en documentación técnica, no como caso de uso.


### **Error 3: Subcasos demasiado granulares**

**Incorrecto:**

CU-001: Realizar Préstamo
  └─ CU-001.1: Validar Usuario
       └─ CU-001.1.1: Verificar Usuario Existe
       └─ CU-001.1.2: Verificar Usuario Activo
       └─ CU-001.1.3: Verificar Sin Multas


**Problema:** Demasiada granularidad. Los sub-subcasos rara vez son necesarios.

**Correcto:**

CU-001: Realizar Préstamo
  └─ CU-001.1: Validar Usuario
       Pasos dentro del subcaso:
       1. Verificar usuario existe
       2. Verificar usuario activo
       3. Verificar sin multas vencidas



### **Error 4: Mezclar subcasos con flujos alternativos**

**Incorrecto:**

CU-001: Login
  └─ CU-001.1: Login con Google      ← NO es subcaso, es alternativa
  └─ CU-001.2: Login con Facebook    ← NO es subcaso, es alternativa
  └─ CU-001.3: Login tradicional     ← NO es subcaso, es alternativa


**Problema:** Estos son **flujos alternativos** del mismo caso de uso, no subcasos.

**Correcto:**

CU-001: Login

Flujo Principal:
1. Usuario selecciona método de autenticación

Flujo Alternativo 1a: Login con Google
  1a1. Sistema redirige a OAuth de Google
  1a2. ...

Flujo Alternativo 1b: Login con Facebook
  1b1. Sistema redirige a OAuth de Facebook
  1b2. ...

-->


**Diagrama de Casos de Uso:**

Diagrama de caso de uso para la solicitud y prestamo de equipo.

![](https://img.plantuml.biz/plantuml/svg/XLJ1JXin4Br7oZzCmm4QDMc1jX888fAGRL4He2QHUeY4Xjr9PF3QY-sbq8eFwg6dVW8_rh6TaAK4LNjPZsVUctdpTW-iG-FANDPhhpAQ2aLmVFJfywXtF1x0sc0xsKeEbrSnkhMvyp7PhjVibL056ioXmFGAPpHqTvB0KEfGpIHLCqfBALg2d_KQG8_JPqQNAkjhgSsICLngav695ujOrnZzlHgwhzVgjNL8jFc11ZB1dAbu-AF0wQBbTEj2EwTzNmOXfqkkGya3O4YgrpYBCs6U5SgTqCg3Ek5uXaE1CsuR8IFeezNMluojteMXbY8LhinyvCmy_681S-qFW-jI53esjh-_3ztKQKFMlzThw0_GA6s9HkW6e8NnCdKeh2DcEpD2fQ906OiUbOJ68cCrgMt0MlB1FrvWhrZ4zQtFEwzWRupxhNURhoC7FAwcqMo6YsPpecoSahKjU0HFDb6CGu4jTjz_jmbhlTxX8EdzIxbG2uvKAakHSM3Zz4AA6R88Gjldr3Tan5IaF9-mXLRYGaYH8MOJHGf8WetZpvdFZqxwBt8ERXsfB99sfIEZq8cRLQHAkq3gpG7ppO3oarQRy8kMJoS_7tmRdP-SikP9ijD__r_GYM8HoTmWqArmsc8Lv_JB4kT-QOcl9DcjMh61KXqq27wAGuoXrUg45QmisDiJNlYCEfsgyBZG8EoktUxCfOJTQiKBY1Ha3O253w8a-tQfxqhikKoxbVBd2Jp_quIdzFwZzWkOol9IW_TYzl3REf7goBSENLlc8kTrNvSK4c1QgbZ8dGlsRU4DGSfHG0eczngs9KrTR6Guwew6aVf4E-JFd43dWYiaWgGx1a3UGrv8kiHeY4lYatu3TnY8bGOifBSmxprR_3wiy2N0uiy4IzRs50SCnZ_Slm00)

### 4.2 Glosario

<!--
Glosario extendido complementando la Sección 1.4.
Incluye términos adicionales que surgieron durante la especificación detallada.
-->

[Si ya documentó un glosario completo en 1.4, puede referenciarlo:]

Ver Sección 1.4 para el glosario completo de términos, acrónimos y abreviaturas utilizados en este documento.

[O expandir con términos adicionales específicos del dominio:]

**Términos Adicionales del Dominio Bibliotecario:**

| Término | Definición |
|---------|------------|
| **Catálogo bibliográfico** | Registro organizado de todos los materiales disponibles en la biblioteca, con información descriptiva de cada uno. |
| **Clasificación Dewey** | Sistema Dewey de clasificación decimal utilizado para organizar libros por temas. Rango de 000 a 999. |
| **ISBN** | International Standard Book Number. Código único de 13 dígitos que identifica libros comerciales. |
| **MARC** | MAchine-Readable Cataloging. Formato estándar para representar y comunicar información bibliográfica en forma legible por computadora. |
| **Morosidad** | Estado de un usuario que no ha devuelto materiales en la fecha establecida. |
| **Obra** | Contenido intelectual (ej: "Don Quijote de la Mancha"). Una obra puede tener múltiples ediciones y ejemplares. |
| **Política de préstamo** | Reglas que definen cuántos materiales puede prestar cada tipo de usuario, por cuántos días, y si puede renovar. |
<br>

### 4.3 Diagramas del sistema

<!--
Incluya diagramas que ayuden a visualizar la arquitectura, estructura de datos,
flujos de información, etc.

TIPOS DE DIAGRAMAS ÚTILES:
- Diagrama de contexto (relación del sistema con su entorno)
- Diagrama de arquitectura de alto nivel
- Diagrama de componentes
- Diagrama de despliegue
- Modelo entidad-relación de la base de datos
- Diagramas de flujo de procesos críticos
- Wireframes/mockups de interfaces principales
-->

**4.3.1 Diagrama de Contexto del Sistema**

[Incluya diagrama mostrando el sistema y sus interacciones con actores externos y sistemas externos]

[![](https://img.plantuml.biz/plantuml/svg/VLRBRkCs5DthAswpwKm0mzEi2cCQZ2ofYG2_8Cf1fx4NZCGuH2JI9Qcaaw8VCyjPp6e-mJ_MIxqiMtQz2KBUnpdd7bxxapPKcIBF8972iB-D73pmXunBmv8dvwUKFNB180gys9tTJ098Cggru-XdBhPKqHmKImmLcup1FmxWPqoJvusIXKWzcKdryQFcsh2SNb_3X6-Up3WhsEb0cXYfch0RnPWu7OSWcHAoYVpCiao-Lg5IfKoLOJ3ECAyy_Hs94Vx6u9ShvzykTAgKVArXLqa-LSyjm7tU1vjdk46IFgSRpAMGCiof58C1a8eaZ4ljOgkTypFyPZ_WUl4y2WZSBgVkR4xWNVZsLy6PIkdxAi8fcSF5KXTKSJdqCiwmyagCcqdG2w0QYkeUMgcQn7qSNfUX3zsJVeARvbmWP4LJgLQYHbzcKdlLoMXfa934mTG5BvZ5aJkfeU_7Vt5vsLVXyd8btZN7ADaDquRlVWZeGgRloywrKQ1ZcLvt0i4VSH2LCleCcpzH8CMM8KlrlW-fwJmj14_ubcOhWI325ENbZpoXYSLY4Kx36aFEeUEmWrfClN2K2yWqNgo49vLY4e8C8nHMuOciAvZjsHAj42iHCOruKecL48sY6N_3OLJ3G-SMXqLQ7VoGBEOaZCExhWIXU3mdmOIL8_TsFrA-aIN_CHgVQgJz9tjG57noTVNXruf_LaMVmH_cMyMqL7GbujqtbVFQcBmvFurvudwUBsEeSCzduUocXjaOUd3_n5CSoZgLhs9mQ5xdqCf7eQLRyKtZs8vkx1oSSXZ7rKjrdLhaeykAlrFBS7JPqjnJYuA9wo6dW8nWIPPk5Cw7tYJ49n8SSrHsMGskMvkFxFxGHMOe9DJilcRIZYTYec0l5BPgzmrNSovnJhSqORXdDHgGQgV97sJiqTPh6enW9XjNIy4qO117mwCtfCehgqDESJgSPaoVvZ0EnvDm7WUUPL8pE1f0dqV4DkKkEG1TldGfQ8CFZnPA9anR-x_8hAXGzkWSTXl10Nmcm72MRoNAOH-pcp5bq81VG1nmFqtEzQVX3FT8vFhpg5czvRexFPn7lYcGLNrcAGc6_oksbSgmBaTLF-O-dQg-rQXA0aoXwUux9YPMaudSQBiOQP5ojDpk-nbpDTjtkfo5NhXezs_RhsM0Js44TxXFKWgyt7GfJLSYuGN-fS8slR-DumKPufTI3EuYN5VlfqQyby2dHcgGA6lfc6wDCo23w2wqsjeLUHuWliaH1E85oHxD3Q7Pr64y8UlwyVPGbOFfE0BBoF_Np0_mcA1c_lmSg7eRs3dLayI969dlljPpkbVwYqY6XDokszNHWqOCDONkkE4ah8CLNk5fzasVRBMshKCUwgrzloHZk0tzTP_5VWzRcN8gB8_giFgYkm-8DyJcQmS_dvX8yOVVVm00)](https://editor.plantuml.com/uml/VLRBRkCs5DthAswpwKm0mzEi2cCQZ2ofYG2_8Cf1fx4NZCGuH2JI9Qcaaw8VCyjPp6e-mJ_MIxqiMtQz2KBUnpdd7bxxapPKcIBF8972iB-D73pmXunBmv8dvwUKFNB180gys9tTJ098Cggru-XdBhPKqHmKImmLcup1FmxWPqoJvusIXKWzcKdryQFcsh2SNb_3X6-Up3WhsEb0cXYfch0RnPWu7OSWcHAoYVpCiao-Lg5IfKoLOJ3ECAyy_Hs94Vx6u9ShvzykTAgKVArXLqa-LSyjm7tU1vjdk46IFgSRpAMGCiof58C1a8eaZ4ljOgkTypFyPZ_WUl4y2WZSBgVkR4xWNVZsLy6PIkdxAi8fcSF5KXTKSJdqCiwmyagCcqdG2w0QYkeUMgcQn7qSNfUX3zsJVeARvbmWP4LJgLQYHbzcKdlLoMXfa934mTG5BvZ5aJkfeU_7Vt5vsLVXyd8btZN7ADaDquRlVWZeGgRloywrKQ1ZcLvt0i4VSH2LCleCcpzH8CMM8KlrlW-fwJmj14_ubcOhWI325ENbZpoXYSLY4Kx36aFEeUEmWrfClN2K2yWqNgo49vLY4e8C8nHMuOciAvZjsHAj42iHCOruKecL48sY6N_3OLJ3G-SMXqLQ7VoGBEOaZCExhWIXU3mdmOIL8_TsFrA-aIN_CHgVQgJz9tjG57noTVNXruf_LaMVmH_cMyMqL7GbujqtbVFQcBmvFurvudwUBsEeSCzduUocXjaOUd3_n5CSoZgLhs9mQ5xdqCf7eQLRyKtZs8vkx1oSSXZ7rKjrdLhaeykAlrFBS7JPqjnJYuA9wo6dW8nWIPPk5Cw7tYJ49n8SSrHsMGskMvkFxFxGHMOe9DJilcRIZYTYec0l5BPgzmrNSovnJhSqORXdDHgGQgV97sJiqTPh6enW9XjNIy4qO117mwCtfCehgqDESJgSPaoVvZ0EnvDm7WUUPL8pE1f0dqV4DkKkEG1TldGfQ8CFZnPA9anR-x_8hAXGzkWSTXl10Nmcm72MRoNAOH-pcp5bq81VG1nmFqtEzQVX3FT8vFhpg5czvRexFPn7lYcGLNrcAGc6_oksbSgmBaTLF-O-dQg-rQXA0aoXwUux9YPMaudSQBiOQP5ojDpk-nbpDTjtkfo5NhXezs_RhsM0Js44TxXFKWgyt7GfJLSYuGN-fS8slR-DumKPufTI3EuYN5VlfqQyby2dHcgGA6lfc6wDCo23w2wqsjeLUHuWliaH1E85oHxD3Q7Pr64y8UlwyVPGbOFfE0BBoF_Np0_mcA1c_lmSg7eRs3dLayI969dlljPpkbVwYqY6XDokszNHWqOCDONkkE4ah8CLNk5fzasVRBMshKCUwgrzloHZk0tzTP_5VWzRcN8gB8_giFgYkm-8DyJcQmS_dvX8yOVVVm00)

**4.3.2 Diagrama de Arquitectura de Alto Nivel**

[Incluya diagrama mostrando capas principales: Presentación, Lógica de Negocio, Acceso a Datos, Integraciones]
[![](https://img.plantuml.biz/plantuml/svg/XLVDSjis4BxpARQ-r7RYPZAPNZoTJ6LQSTMnVYegwNJg7Y0Iek6000k0IfnEhts0vWbop26dt7hLc_H9kWl-YtBZWqVS_G0illsm2tnl7JEko2GmytiX78zTOTXPp79cWwyIlX6AGpYVBkQpyMm51lrCfP87WNqjLCuCoo3MMQuLLmx-203_BbZyEZMwK4cefJRVVPSRRj7DOg7Ly-TmBT9RTo4BVXYjUAeHMGEl3EVgC39XJjiQzmkNKhyv31JAyTJqrby8zVems1ccx9ORosGR0xilmTeat7WWN4WSwQqlj7AHUCVXwTFWpoup621RCyiF4mC_ttBc7fWNvt72IGwNWc7e6OE4mwYJ8_yjdOQPs789Pn09wpZYBiHQ2htYyUsDEjuVyGn2IYqyWeYRhK16x4aGvBWYIpaSXQF522x7i5YE8yptA9piti-EO932SZ-_Jf1Nis7lu6U-lb5BRb47LcpPRu1BlE7h4ZLQJ03dMs4uBmeAvCJxMIwyt_zJsd4mn3NeJJCKuFGKDwAGbtJtYPsVdbRcC_XXDRt-zZ64KVJiCVp8jYoAZSXTux_GsbbCPVvaoZ18mIHSSYjIrI12b2rpI1O_X_3Mw8m_XXV2y8r--xW20OoJ5CqHsp1JHijLueEb10rekzwzlvg4_kTiV3KF9tFYhXLqHTjqzpaffCPytAXHuP1N4IEpky_gHjrZOjB2Y8Gb9Kk5knsEkkBM4Tv_lBG5HgUjnnVLnnV6XCpjFY2hsW-AKQVqCHoqCBkFM28oRU7-HbtohPO5QO2Ngv4il7Su4jM02cCbpbGVGzYqa0u1zx1WQRM5p9k6q9bsOkEPQjPNP3gqTgwDu_NQvST3OciO9hLL6cPh8Ia5t7OrzugHqISAOiCJhcBKLJLpAIdbZ9Pqq5WSSwlXU7an2ayQG2S7O56Ej95MibB_Nd0D62vGnL9OtM3392vQ4Vo_uXk5uJYQ0_uUhUOH2Q-kZvNiY1Khd4Pvx8c6AEeBfuUjJr27qAmn7S2tecdmUqBfmVUKWjllgQKVYjT66qP7AZtSg4Ze9nQD1il8z9081WoG61RC6KfMC_DzLmsZDTMN9jDOU2yRtoJB9S-eO4AuVDdQfqpnEmQ-nU2uVlvVMWRpvHIETKuU9ay6IMyQoj45_KSLNLAEaN9jNMfuzDCrLjdjqsUFJevet-i4atz8BD5u-Mg2zIcYZybiDRvQjiM-touhzOHIu7wmvomcDwhkDTD2OG_9cVGisqp49Qe_99gk5ZTgd35HurpU0zQzg2uSE65ILgOr1bxajl8_bBszXIbt8JRW63Mw-sIfklREiSy2BGPEP5mNhit1aZSd3-k2pdOVSBHk_I_mE59CcEvC9neofWecsm8WJ8pz5jQ6izVS03OOZ44DyXXBNIHmLD5eOVoMODeUrMmF2BvH6EuaeLwngRj5JNg7n0HhHqdtHE76NL4ggQ5z3_eGtsRRKqshbjLoD8jUZPVHw7hiQqp_jbH5VwtJLAYKMiRUGPIbfuJrEv9M6u6ThrlUOs-hnCJYszt7gbt5jvLowfBS3Dbs30_9fHi4QMMKIwGKK-fqGZ7w9VA-PfOynPGOhngTSyFs3c-bgHWJP324TopnK6uCbRCMjlle3EcHd0Ob8JBIhHuev6jSKLQB04tAovZWU2CBBrwBQv4U-4c0zoKuEtlkMncSGwHnFvXxnE0zQRLe_4s5gmrDuwyDRPskBKqnhWrLpMtzLNiD_EgrgLcg_l45J-S8rq4r8phDfeclSROH3tt_Ex29e-yghnJrhjijrZGCF9r5IcfQJydKdhKDkAPk6DB0qrbau6id3BgJUFyw2Vh3kzR-nYjZRt_ry7O7bSKtqzeGjCchSuag9EL5J-ZY7tGAVWLmEUaK2zMJrNKKzAjyEMrTY11dxBsAdqJH3q7WizFCKIkcVrhgUInqYXCILnrx-2RHRzGtpMb1yz3NaFY0lwNk0K27aWeHbDNiC29kgnyMn26qvUzBM6pvvzXtpEv3nh5U-IBAttfau0jdWspEsRclgBkF1BMbPll83XiLqbyjWw1RRG-XUzNu8BWJn9V1NTPxw43obAgdB_61lxij9xDmig2UDLh-z7Ao6eShlDvCmddagxe7HPpUwUM5dgloQLmMVMpbB66-vE8bWIigrhsN0Up-mSxCFFIIvxuKusi07s1A9FYAZCl6Yy4VCsF4ci6_V_qDU7cxqoVL_3YrBR2L26p4ipcHhsCEehawnlLBmKSXrCP3wzXV4UIkZVVq55iGNbr45I3QSOriJOcGEgvwalMl2vgm6hGYHZj35gRWwt8R3hF81WF65kTYlKMeBUK5lOU0Uo-zNn9FYjTiLjtCplm3gx3TqTMpZQxeXHCKvBfyLFXDufDzkxTFlEdIcnqqdkjRZedeDr8upeGJARLV9BIIQydubDtJLZGHVETpAEXonIGStnMsl5TXpcc_MO_Aam3dBnKM1D_Z_oAJ_m40)](https://editor.plantuml.com/uml/XLVDSjis4BxpARQ-r7RYPZAPNZoTJ6LQSTMnVYegwNJg7Y0Iek6000k0IfnEhts0vWbop26dt7hLc_H9kWl-YtBZWqVS_G0illsm2tnl7JEko2GmytiX78zTOTXPp79cWwyIlX6AGpYVBkQpyMm51lrCfP87WNqjLCuCoo3MMQuLLmx-203_BbZyEZMwK4cefJRVVPSRRj7DOg7Ly-TmBT9RTo4BVXYjUAeHMGEl3EVgC39XJjiQzmkNKhyv31JAyTJqrby8zVems1ccx9ORosGR0xilmTeat7WWN4WSwQqlj7AHUCVXwTFWpoup621RCyiF4mC_ttBc7fWNvt72IGwNWc7e6OE4mwYJ8_yjdOQPs789Pn09wpZYBiHQ2htYyUsDEjuVyGn2IYqyWeYRhK16x4aGvBWYIpaSXQF522x7i5YE8yptA9piti-EO932SZ-_Jf1Nis7lu6U-lb5BRb47LcpPRu1BlE7h4ZLQJ03dMs4uBmeAvCJxMIwyt_zJsd4mn3NeJJCKuFGKDwAGbtJtYPsVdbRcC_XXDRt-zZ64KVJiCVp8jYoAZSXTux_GsbbCPVvaoZ18mIHSSYjIrI12b2rpI1O_X_3Mw8m_XXV2y8r--xW20OoJ5CqHsp1JHijLueEb10rekzwzlvg4_kTiV3KF9tFYhXLqHTjqzpaffCPytAXHuP1N4IEpky_gHjrZOjB2Y8Gb9Kk5knsEkkBM4Tv_lBG5HgUjnnVLnnV6XCpjFY2hsW-AKQVqCHoqCBkFM28oRU7-HbtohPO5QO2Ngv4il7Su4jM02cCbpbGVGzYqa0u1zx1WQRM5p9k6q9bsOkEPQjPNP3gqTgwDu_NQvST3OciO9hLL6cPh8Ia5t7OrzugHqISAOiCJhcBKLJLpAIdbZ9Pqq5WSSwlXU7an2ayQG2S7O56Ej95MibB_Nd0D62vGnL9OtM3392vQ4Vo_uXk5uJYQ0_uUhUOH2Q-kZvNiY1Khd4Pvx8c6AEeBfuUjJr27qAmn7S2tecdmUqBfmVUKWjllgQKVYjT66qP7AZtSg4Ze9nQD1il8z9081WoG61RC6KfMC_DzLmsZDTMN9jDOU2yRtoJB9S-eO4AuVDdQfqpnEmQ-nU2uVlvVMWRpvHIETKuU9ay6IMyQoj45_KSLNLAEaN9jNMfuzDCrLjdjqsUFJevet-i4atz8BD5u-Mg2zIcYZybiDRvQjiM-touhzOHIu7wmvomcDwhkDTD2OG_9cVGisqp49Qe_99gk5ZTgd35HurpU0zQzg2uSE65ILgOr1bxajl8_bBszXIbt8JRW63Mw-sIfklREiSy2BGPEP5mNhit1aZSd3-k2pdOVSBHk_I_mE59CcEvC9neofWecsm8WJ8pz5jQ6izVS03OOZ44DyXXBNIHmLD5eOVoMODeUrMmF2BvH6EuaeLwngRj5JNg7n0HhHqdtHE76NL4ggQ5z3_eGtsRRKqshbjLoD8jUZPVHw7hiQqp_jbH5VwtJLAYKMiRUGPIbfuJrEv9M6u6ThrlUOs-hnCJYszt7gbt5jvLowfBS3Dbs30_9fHi4QMMKIwGKK-fqGZ7w9VA-PfOynPGOhngTSyFs3c-bgHWJP324TopnK6uCbRCMjlle3EcHd0Ob8JBIhHuev6jSKLQB04tAovZWU2CBBrwBQv4U-4c0zoKuEtlkMncSGwHnFvXxnE0zQRLe_4s5gmrDuwyDRPskBKqnhWrLpMtzLNiD_EgrgLcg_l45J-S8rq4r8phDfeclSROH3tt_Ex29e-yghnJrhjijrZGCF9r5IcfQJydKdhKDkAPk6DB0qrbau6id3BgJUFyw2Vh3kzR-nYjZRt_ry7O7bSKtqzeGjCchSuag9EL5J-ZY7tGAVWLmEUaK2zMJrNKKzAjyEMrTY11dxBsAdqJH3q7WizFCKIkcVrhgUInqYXCILnrx-2RHRzGtpMb1yz3NaFY0lwNk0K27aWeHbDNiC29kgnyMn26qvUzBM6pvvzXtpEv3nh5U-IBAttfau0jdWspEsRclgBkF1BMbPll83XiLqbyjWw1RRG-XUzNu8BWJn9V1NTPxw43obAgdB_61lxij9xDmig2UDLh-z7Ao6eShlDvCmddagxe7HPpUwUM5dgloQLmMVMpbB66-vE8bWIigrhsN0Up-mSxCFFIIvxuKusi07s1A9FYAZCl6Yy4VCsF4ci6_V_qDU7cxqoVL_3YrBR2L26p4ipcHhsCEehawnlLBmKSXrCP3wzXV4UIkZVVq55iGNbr45I3QSOriJOcGEgvwalMl2vgm6hGYHZj35gRWwt8R3hF81WF65kTYlKMeBUK5lOU0Uo-zNn9FYjTiLjtCplm3gx3TqTMpZQxeXHCKvBfyLFXDufDzkxTFlEdIcnqqdkjRZedeDr8upeGJARLV9BIIQydubDtJLZGHVETpAEXonIGStnMsl5TXpcc_MO_Aam3dBnKM1D_Z_oAJ_m40)

**4.3.3 Diagrama de Componentes del Sistema**

**[Incluya diagrama mostrando los principales componentes/módulos del sistema y sus interacciones]

**Módulo de prestamos**

[![](https://img.plantuml.biz/plantuml/svg/ZLMxRjim5Dtr5RUURC11ban5KIIMtGQ5dRgnaux1DNNZig18bQGC64K_fcE6JDcwwiTAwcN9bjfuiKoUS-xHVVdIMDGsZGKm5ITAahHapZPy8xYonBu5RxXa8eq8teKNv-75GrZ1tWU1vLOGJ3bkDSO83XGUHE0C5jbBb0hbBvOwUtAXOcM285JI8fUa7oOgbH7g_H2JP0o3gqHmXendBn8ckOMrip0OmSy0tASM7oQQSZ6lf9KGf1sx_86Hqks80tUvIZINMrZSXt0W-Oi5IlgEeEb7wZGDNA_NIqXG8oIr0EoTu4w9b74Ntmn6FNPMf7USaG-NFt7LOQJ0m1ptXO5vzh9rR-sHahRAaTx23WMFi8Ws1fRz5ipbqJrgsWeq7bkxEt5Ja5qM3dRkgwD-FpL_KEF1lrMa83KfQgx6477ZC7p3SpM8qPBcACOWikUOsuxCCFJEVMGyk0aFXzxF1rTZxFTIek4nXtb2LGlV9eQssHy9YN8Mh4lZgGMfB7zqDws4DEjpKmBAulRvcCbTzemWM-X_LwBgYrjANFO6_ijmgtHNNtnQNa4DsFkJAyR8A70vGglQaKxVignHTwIxulBLST8AVnobgdXtc4LvIwyE51yOe-1NOpDCDyDeuoWJDBxUCFKChx5KncurhRxCSqKH8oFPdDLnxNxSbg-rXoQsILLbFnEhnNgPLpX6Bi0V5vFPNV74CPZIcdozWriIdTleT2NCXT-Hw8NZxCcgg4X1EVDEgobLqpg6-Sxa8lcEAgvr7xjp_9hy4g3BwUhJwPoXfau5w7LoD0fBqeORIowJicoMaddwmktMTaasgR1vwFP-wXKuwjgcGdkZ7Paly7aVpedEPuPflg7SxdGIbk2MkmfxX6aR-8zWLwxBZYqRadoV5elATUxvUhxodRYw_lprOJxxEBkP3aV19Sd8_Ql_1G00)](https://editor.plantuml.com/uml/ZLMxRjim5Dtr5RUURC11ban5KIIMtGQ5dRgnaux1DNNZig18bQGC64K_fcE6JDcwwiTAwcN9bjfuiKoUS-xHVVdIMDGsZGKm5ITAahHapZPy8xYonBu5RxXa8eq8teKNv-75GrZ1tWU1vLOGJ3bkDSO83XGUHE0C5jbBb0hbBvOwUtAXOcM285JI8fUa7oOgbH7g_H2JP0o3gqHmXendBn8ckOMrip0OmSy0tASM7oQQSZ6lf9KGf1sx_86Hqks80tUvIZINMrZSXt0W-Oi5IlgEeEb7wZGDNA_NIqXG8oIr0EoTu4w9b74Ntmn6FNPMf7USaG-NFt7LOQJ0m1ptXO5vzh9rR-sHahRAaTx23WMFi8Ws1fRz5ipbqJrgsWeq7bkxEt5Ja5qM3dRkgwD-FpL_KEF1lrMa83KfQgx6477ZC7p3SpM8qPBcACOWikUOsuxCCFJEVMGyk0aFXzxF1rTZxFTIek4nXtb2LGlV9eQssHy9YN8Mh4lZgGMfB7zqDws4DEjpKmBAulRvcCbTzemWM-X_LwBgYrjANFO6_ijmgtHNNtnQNa4DsFkJAyR8A70vGglQaKxVignHTwIxulBLST8AVnobgdXtc4LvIwyE51yOe-1NOpDCDyDeuoWJDBxUCFKChx5KncurhRxCSqKH8oFPdDLnxNxSbg-rXoQsILLbFnEhnNgPLpX6Bi0V5vFPNV74CPZIcdozWriIdTleT2NCXT-Hw8NZxCcgg4X1EVDEgobLqpg6-Sxa8lcEAgvr7xjp_9hy4g3BwUhJwPoXfau5w7LoD0fBqeORIowJicoMaddwmktMTaasgR1vwFP-wXKuwjgcGdkZ7Paly7aVpedEPuPflg7SxdGIbk2MkmfxX6aR-8zWLwxBZYqRadoV5elATUxvUhxodRYw_lprOJxxEBkP3aV19Sd8_Ql_1G00)

**4.3.4 Modelo Entidad-Relación de la Base de Datos**

[Incluya diagrama ER mostrando entidades principales y sus relaciones]

Ejemplo de entidades principales:
- Usuario (id, carnet, nombres, apellidos, email, tipo_usuario, fecha_registro, estado)
- Material (id, isbn, titulo, autor, editorial, año, categoria, ubicacion)
- Ejemplar (id, material_id, codigo_barras, estado, fecha_adquisicion)
- Prestamo (id, usuario_id, ejemplar_id, fecha_prestamo, fecha_devolucion_esperada, fecha_devolucion_real, estado)
- Multa (id, prestamo_id, monto, fecha_generacion, fecha_pago, estado)
- Reserva (id, usuario_id, material_id, fecha_reserva, estado)

[![](https://img.plantuml.biz/plantuml/svg/jLbDRzl86RxhLmoCNTWMRCDEugOGDa5eYKgOIAIMaepTee0m8iVA92I76PBEUZUzzjP3sr-mnnvoAFQsL_sJ_fA-yyKlKNRQRGF446VUuRmVp_l95rcEULx44OfPI29sIlZfcguZod8IlEtr3j6G9JTqKt0SqEql2Ge98bbE8vRrilSqIJ77CGeYd6Nefnw2VrSuUB_Xh4Z28OiOHnEwUPj_JwA8VLJxZ8U4gxsh28ZbgiKv-wWMHvY_lueAqljJhvVJF29eAbb3TfBJ48UdFeaqCwTeJhESn1XTIPuNmFCVawCHnHjW2mlU0vBc1OwEXIYskt16rcY0blEbvJlUwigvcZZUmXvQw2Y8A4boaWa98unA9U3Z7gpJ_0uTzFkx1_lz0uGpL6G5vfHf7VHHlq_3bLxizz40EUx2Vcdxw9jlPc-UFvTKfwUQEC0y8JaGNLl-y9Nb7pqwFmR2fUjykxGrSH_bD6Mha0L53FmmeBRTvVJeS6YFbXFhyEHmPisjcUSlxCDZVI81KjuyS-yD2OlN73HGaLsSdvkNuHHiI4EsP_i6L8zN2HWcflgkaRMmzMv8EGa2of862-NXd4JaXYNieicXt3LxZphs-WXiJwCMHtjKPqna56U1tXOUACwUBvOZnm83mOFZZk6NCpbi2iR91f36MsAfFV93IeLxi6GL4wb1Yfjqu34uhDqyN3ZNukRvSZwptP4pykJDUbtT71THZhDLIf9G0nDUQG-TgJK1AKyUAIgspWY_bPTBYeNztQB170u4_EcFM6j_uKn1Nciw4-xLuH9pPxwmf-0FAU4PIt24FXG4u8qHYL2clAtB8_IvfZje-awlMEdD1xsZ00aJ79EQbI-xZ9n23Fe8mMNr5cTlws2vl3Isv2ogcN_gkC2qRuqy7zHVkJI80y-MbCYjkzDlS8ylm-a-dBIWGG4Eu6BPwWQNTneDZkon1RX6vv9o7J4m7xnJA2N73VlNKH9miWiGGQ2s0OeqPe2bW6HiXuQcEmH6p2UW-YREfk0LlcDDQX0oInexCSu9fm2y1chCwWDmeTcw7cCkddP6Wxo8wbm-hfcno1bVfPmc0Krnr1Mk90d9LXa98Cb9c3UWMKKr4NLAQOnH9ywLBspgszS0C16uHzSZ-3iKVxo5RunCGWhtKDn6ZU9X-q-sIWj8KO6nczQ9ETiAjfVw80qfYt77HW1yRiHzgv1y97UTmRQawM8f95d0QMfGPE9GiTOihcve1Z_tk8S4_cf34i9hkXevyvddWcEAoEnwgzgp5YV6S6QLCWxd0QSywZQ5WZ5DDc2uClAO6Dq4gFtQdiucbWyL0KifuF5c-ramBWk38YdXMG-2ven6C7b7uZJ2l8bWixeFmVS3VRnRDR2GRjXgZJd7sVt1KHS29LzDjEp4dORQPxvmTPcXR7VbspFBjuQEvuejszUvwyfwRRKo9Wu_5CBY2WzbCaoX483Wtzhz_-KrnVxKgrdBB6bh0KSWVjogtSpg0zRgBl76BQezfc-JjJ9ZMNJiEzPn92ItB2gQ8U4-z9J2rwDXHynKIgzHT-UHwleLoQ220AUi6t-72D9ErF6oVNbmP5ylRLMqNTlkK67Fe5278IgAfehFEj0Re6e8Oz3Lf6Weyxz68A3Dzg-j6W3rYiOVi27kRC9FB_vFqFV54SMKkegV1yqYIrTRbSskjt36pb35YQ47qT3MGMDekKDxeWF8TpD7r5lQLhfdO3czgV9OL_rHLTYxQ0eOk1RHZ3KFTmQHLZa2jLBTDFBP52AY0czL8MBf0QFiYHnxdFr1ewWgGh9Y5E_RKBNEA-pB8iBQ_jKhGt3CT0ks4rYDbLMgRQlqNXlFh9UMl6lekIFF5R_hTapnfj4UnIHdaDFridgTFRQDBoyi_xKjwnyGnfsFRLzuT9L5xec7NnmDzTqTn5y03GDfaUng2AalQw0q4Dp0Ittdj_bo0m-bFcKKd0e3oV2eyxOp4HB0WaIpx6ri5qWLKguc7aJs2YiuAzgpWR9kYacIuNUaA_obdCaXIxWRARJJ9hUqQ_TUZ06VZWBPs9e8CKmrBFed2CXPJfCwhsKDMVP4ujgwqPiD4U4Swdj3qs7rYVToPIr7piA3bgHcziQwjZike4Pl6ZnYcmSRMcYLP8H8ErGZlPtSjgOrjKfv5-KFUWC6UsY5Dyi-l7Saa-DrXCt1hdP1fYZbZVlU7s9X3fo8vCDKt_nw3gvKxIK59DZ6Ubyqaz1XG7HgTP7o58JvA6hvgm_9HVYYFU-P2S-dJwUdx2TKI_07EOLuTz2cg5BTWQX489Vla9Z8k-SDhUHr8AhRDP3rohvF4zPgR_KgfDgBWntA6bEah0v21kyitz4X8365hAGiToJbfqeA5VQ1eZMXwNYZjYz6HodV_aCk7n_yH-TC_RJz9TbxikJC77kG409FG3ACH73VHwmyioul68eWBcRHYDsO-HIWIbHZBoVM7E84SksN7a1fqE_3nYaQgh7izjU41WofDm7AHVyVRt_EmUfYgaeahItdEvhq3j9BH3TOzEzCRY_g0qY0CU4nJK045cq_vwQvBDKyqBwW9fG3f6OtbsNhIR8JT769mkrdd6dIQePfo1ytoSyRv6RAQOWVDOYVbhGWc8hLrQGIPLJF9j5pzDMZSqarLNDFE8LKhOOkv8n2J0NI0iI27n4o4GF2QYWyXxJDOc1qlrtsjne1Ze8Y4hyoiW5Zg5XMr_rTSofJ5n7CkQOOOQHRYov38o6zl1-fyXzqi9STINzdijqpfDeOUQLLAWEykUOcnlBTZHAyufNdMqVDgGaicxx8hEiuSLOHb1szl7vEuNguEsF0lqO6-jUV_wP1pikokDjCvltIJ6ewC3V6gMuQeBGW4jQ23PufHp7ZX06245yYNcYJtYfVQKmP1i00z7HPoXAwZWW29qyPnr7bURhzW_Vz01A9aeETQ3aKJYML650C8Es40f9eZT_X4_7cW781622HiYohyOvcFXSlGl7srmXm8rAFaPraKc1RFZA8D2D80DyMz1rewW0TNLHp8gbO8BsidGMHRWYNO_szMZRCz_iBP-RDqVTewa6TLsfQTm43zDNvsUKvn18k3IdaqyQjwGU47x8iPsetPMBqeZxdHQZX3BAFWChi5aU5q9PuRVKjJCKpfIljKG78hUD1MSZDLMWmdBgUrgPEiXpfp5_QF-jqn2hej9MqPZdufj2Ipe-IfV5a-TeJ0KCtsEh-YpDaU3MfjJGoS5Q12sWVdHacdbNImFhZC-6oqXzl2K0PrTHsOZwB8Eb-Chn3FLHUTbS9L7N9GFha3CtXHScjZ9eoVm17LMQwhFXM1SEJtxz5udkhC2-4ME5-lplJlWpFWoeUL0quq3oLD0dR9JFjkEBxgDJA1p0MhdkTl9L1vCwEQvQ8o4OyIC1A_KDVA6EdACQKxlk26QXqMJqZeYFG0tANaua8PAf25dGHlYLencaCCcEvCwxlZ1dV_fmGjMF6Kx1xZSLNOvrw8QX4M9Ml1gYkvqCBxFm1uidsxwx1v8A5WDW8_alYJ9nyF7RHqOBmGCGEk0vCweg_qR6Eci9Vn0SvaWHYCWnEbcGK0fVEbOA0ar1y5H04mjTaeMiusVu543K4x_1ji130gnuufP329PJy6JggyWyxhfFSQ4K02HTV1_K7rtUC9faYr20wKn-MJyhdzWTXIMpCVYQ-dSYLCdyqHinoosJeizRyiBbvNqeyLT52voQvK2-YzVh9JfTfb0WW4n_jeDEeLFVA7huPx4cQpv-rXfVt7YbBYNkFgV4Aa9pNLvKFJvmtDZhy-iNNXy9Lb8_qUY_WRn57_mO0)](https://editor.plantuml.com/uml/jLbDRzl86RxhLmoCNTWMRCDEugOGDa5eYKgOIAIMaepTee0m8iVA92I76PBEUZUzzjP3sr-mnnvoAFQsL_sJ_fA-yyKlKNRQRGF446VUuRmVp_l95rcEULx44OfPI29sIlZfcguZod8IlEtr3j6G9JTqKt0SqEql2Ge98bbE8vRrilSqIJ77CGeYd6Nefnw2VrSuUB_Xh4Z28OiOHnEwUPj_JwA8VLJxZ8U4gxsh28ZbgiKv-wWMHvY_lueAqljJhvVJF29eAbb3TfBJ48UdFeaqCwTeJhESn1XTIPuNmFCVawCHnHjW2mlU0vBc1OwEXIYskt16rcY0blEbvJlUwigvcZZUmXvQw2Y8A4boaWa98unA9U3Z7gpJ_0uTzFkx1_lz0uGpL6G5vfHf7VHHlq_3bLxizz40EUx2Vcdxw9jlPc-UFvTKfwUQEC0y8JaGNLl-y9Nb7pqwFmR2fUjykxGrSH_bD6Mha0L53FmmeBRTvVJeS6YFbXFhyEHmPisjcUSlxCDZVI81KjuyS-yD2OlN73HGaLsSdvkNuHHiI4EsP_i6L8zN2HWcflgkaRMmzMv8EGa2of862-NXd4JaXYNieicXt3LxZphs-WXiJwCMHtjKPqna56U1tXOUACwUBvOZnm83mOFZZk6NCpbi2iR91f36MsAfFV93IeLxi6GL4wb1Yfjqu34uhDqyN3ZNukRvSZwptP4pykJDUbtT71THZhDLIf9G0nDUQG-TgJK1AKyUAIgspWY_bPTBYeNztQB170u4_EcFM6j_uKn1Nciw4-xLuH9pPxwmf-0FAU4PIt24FXG4u8qHYL2clAtB8_IvfZje-awlMEdD1xsZ00aJ79EQbI-xZ9n23Fe8mMNr5cTlws2vl3Isv2ogcN_gkC2qRuqy7zHVkJI80y-MbCYjkzDlS8ylm-a-dBIWGG4Eu6BPwWQNTneDZkon1RX6vv9o7J4m7xnJA2N73VlNKH9miWiGGQ2s0OeqPe2bW6HiXuQcEmH6p2UW-YREfk0LlcDDQX0oInexCSu9fm2y1chCwWDmeTcw7cCkddP6Wxo8wbm-hfcno1bVfPmc0Krnr1Mk90d9LXa98Cb9c3UWMKKr4NLAQOnH9ywLBspgszS0C16uHzSZ-3iKVxo5RunCGWhtKDn6ZU9X-q-sIWj8KO6nczQ9ETiAjfVw80qfYt77HW1yRiHzgv1y97UTmRQawM8f95d0QMfGPE9GiTOihcve1Z_tk8S4_cf34i9hkXevyvddWcEAoEnwgzgp5YV6S6QLCWxd0QSywZQ5WZ5DDc2uClAO6Dq4gFtQdiucbWyL0KifuF5c-ramBWk38YdXMG-2ven6C7b7uZJ2l8bWixeFmVS3VRnRDR2GRjXgZJd7sVt1KHS29LzDjEp4dORQPxvmTPcXR7VbspFBjuQEvuejszUvwyfwRRKo9Wu_5CBY2WzbCaoX483Wtzhz_-KrnVxKgrdBB6bh0KSWVjogtSpg0zRgBl76BQezfc-JjJ9ZMNJiEzPn92ItB2gQ8U4-z9J2rwDXHynKIgzHT-UHwleLoQ220AUi6t-72D9ErF6oVNbmP5ylRLMqNTlkK67Fe5278IgAfehFEj0Re6e8Oz3Lf6Weyxz68A3Dzg-j6W3rYiOVi27kRC9FB_vFqFV54SMKkegV1yqYIrTRbSskjt36pb35YQ47qT3MGMDekKDxeWF8TpD7r5lQLhfdO3czgV9OL_rHLTYxQ0eOk1RHZ3KFTmQHLZa2jLBTDFBP52AY0czL8MBf0QFiYHnxdFr1ewWgGh9Y5E_RKBNEA-pB8iBQ_jKhGt3CT0ks4rYDbLMgRQlqNXlFh9UMl6lekIFF5R_hTapnfj4UnIHdaDFridgTFRQDBoyi_xKjwnyGnfsFRLzuT9L5xec7NnmDzTqTn5y03GDfaUng2AalQw0q4Dp0Ittdj_bo0m-bFcKKd0e3oV2eyxOp4HB0WaIpx6ri5qWLKguc7aJs2YiuAzgpWR9kYacIuNUaA_obdCaXIxWRARJJ9hUqQ_TUZ06VZWBPs9e8CKmrBFed2CXPJfCwhsKDMVP4ujgwqPiD4U4Swdj3qs7rYVToPIr7piA3bgHcziQwjZike4Pl6ZnYcmSRMcYLP8H8ErGZlPtSjgOrjKfv5-KFUWC6UsY5Dyi-l7Saa-DrXCt1hdP1fYZbZVlU7s9X3fo8vCDKt_nw3gvKxIK59DZ6Ubyqaz1XG7HgTP7o58JvA6hvgm_9HVYYFU-P2S-dJwUdx2TKI_07EOLuTz2cg5BTWQX489Vla9Z8k-SDhUHr8AhRDP3rohvF4zPgR_KgfDgBWntA6bEah0v21kyitz4X8365hAGiToJbfqeA5VQ1eZMXwNYZjYz6HodV_aCk7n_yH-TC_RJz9TbxikJC77kG409FG3ACH73VHwmyioul68eWBcRHYDsO-HIWIbHZBoVM7E84SksN7a1fqE_3nYaQgh7izjU41WofDm7AHVyVRt_EmUfYgaeahItdEvhq3j9BH3TOzEzCRY_g0qY0CU4nJK045cq_vwQvBDKyqBwW9fG3f6OtbsNhIR8JT769mkrdd6dIQePfo1ytoSyRv6RAQOWVDOYVbhGWc8hLrQGIPLJF9j5pzDMZSqarLNDFE8LKhOOkv8n2J0NI0iI27n4o4GF2QYWyXxJDOc1qlrtsjne1Ze8Y4hyoiW5Zg5XMr_rTSofJ5n7CkQOOOQHRYov38o6zl1-fyXzqi9STINzdijqpfDeOUQLLAWEykUOcnlBTZHAyufNdMqVDgGaicxx8hEiuSLOHb1szl7vEuNguEsF0lqO6-jUV_wP1pikokDjCvltIJ6ewC3V6gMuQeBGW4jQ23PufHp7ZX06245yYNcYJtYfVQKmP1i00z7HPoXAwZWW29qyPnr7bURhzW_Vz01A9aeETQ3aKJYML650C8Es40f9eZT_X4_7cW781622HiYohyOvcFXSlGl7srmXm8rAFaPraKc1RFZA8D2D80DyMz1rewW0TNLHp8gbO8BsidGMHRWYNO_szMZRCz_iBP-RDqVTewa6TLsfQTm43zDNvsUKvn18k3IdaqyQjwGU47x8iPsetPMBqeZxdHQZX3BAFWChi5aU5q9PuRVKjJCKpfIljKG78hUD1MSZDLMWmdBgUrgPEiXpfp5_QF-jqn2hej9MqPZdufj2Ipe-IfV5a-TeJ0KCtsEh-YpDaU3MfjJGoS5Q12sWVdHacdbNImFhZC-6oqXzl2K0PrTHsOZwB8Eb-Chn3FLHUTbS9L7N9GFha3CtXHScjZ9eoVm17LMQwhFXM1SEJtxz5udkhC2-4ME5-lplJlWpFWoeUL0quq3oLD0dR9JFjkEBxgDJA1p0MhdkTl9L1vCwEQvQ8o4OyIC1A_KDVA6EdACQKxlk26QXqMJqZeYFG0tANaua8PAf25dGHlYLencaCCcEvCwxlZ1dV_fmGjMF6Kx1xZSLNOvrw8QX4M9Ml1gYkvqCBxFm1uidsxwx1v8A5WDW8_alYJ9nyF7RHqOBmGCGEk0vCweg_qR6Eci9Vn0SvaWHYCWnEbcGK0fVEbOA0ar1y5H04mjTaeMiusVu543K4x_1ji130gnuufP329PJy6JggyWyxhfFSQ4K02HTV1_K7rtUC9faYr20wKn-MJyhdzWTXIMpCVYQ-dSYLCdyqHinoosJeizRyiBbvNqeyLT52voQvK2-YzVh9JfTfb0WW4n_jeDEeLFVA7huPx4cQpv-rXfVt7YbBYNkFgV4Aa9pNLvKFJvmtDZhy-iNNXy9Lb8_qUY_WRn57_mO0)

**4.3.5 Mockups de Interfaces Principales**

[Incluya bocetos o mockups de las pantallas principales:]
- Pantalla de login
- Panel principal / Dashboard
- Pantalla de préstamos
- Pantalla de búsqueda de catálogo
- Pantalla de registro de usuario

[Puede usar herramientas como Figma, Balsamiq, o incluso dibujos escaneados]

<br>

### 4.4 Matriz de trazabilidad

<!--
La matriz de trazabilidad vincula requisitos con otros artefactos del proyecto
para asegurar que todos los requisitos están cubiertos en diseño, implementación,
y pruebas.

TIPOS DE TRAZABILIDAD:
- Requisitos <-> Casos de Uso
- Requisitos <-> Casos de Prueba
- Requisitos <-> Módulos de Código
- Requisitos <-> Fuente (stakeholder que lo solicitó)
-->

**4.4.1 Matriz Requisitos - Casos de Uso**

| Requisito | Caso de Uso Relacionado | Prioridad |
|-----------|-------------------------|-----------|
| RF-001 | CU-000 (Login) | Esencial |
| RF-010 | CU-003 (Registrar Usuario) | Esencial |
| RF-030 | CU-001 (Realizar Préstamo) | Esencial |
| RF-031 | CU-001 (Realizar Préstamo) | Esencial |
| RF-040 | CU-002 (Realizar Devolución) | Esencial |
| ... | ... | ... |

**4.4.2 Matriz Requisitos - Casos de Prueba**

| Requisito | Casos de Prueba | Estado Prueba |
|-----------|-----------------|---------------|
| RF-001 | TC-001, TC-002, TC-003 | Pendiente |
| RF-002 | TC-004, TC-005 | Pendiente |
| RF-010 | TC-010, TC-011, TC-012, TC-013 | Pendiente |
| ... | ... | ... |

[Esta matriz se completará durante la fase de pruebas]

<br>


*Plantilla elaborada con propósitos académicos*  
*Basada en IEEE Std 830-1998*  
*Versión  1.0 - Octubre 2025*
