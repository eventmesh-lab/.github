# Plataforma Integral para Gestión de Eventos, Reservas y Servicios con Procesamiento Asíncrono

Proyecto DS 2025-02 – Facultad de Ingeniería, Escuela de Ingeniería Informática

**Periodo:** Septiembre 2025 – Enero 2026  
**Profesor:** Bismarck Ponce  
**Asignatura:** Desarrollo del Software  
**Documento Base:** Proyecto DS 2025-02.pdf  

---

## 🧭 Introducción

En la actualidad, la organización de eventos (conciertos, conferencias, talleres, festivales) requiere sistemas digitales que no solo permitan la compra de entradas, sino también la gestión integral de reservas, pagos, servicios complementarios y comunicación en tiempo real con los usuarios.

Este proyecto busca diseñar y desarrollar una **aplicación web distribuida**, con una **API REST robusta y segura**, implementada bajo los principios de **Arquitectura Hexagonal** y **Domain-Driven Design (DDD)**.  
La solución integrará **procesos asíncronos** mediante colas de mensajería, **jobs en background**, y un **API Gateway** que gestione la seguridad y autorización centralizada.

---

## 🎯 Objetivos

- Implementar un sistema modular, escalable y distribuido.  
- Integrar autenticación y autorización centralizada mediante **Keycloak**.  
- Procesar eventos y pagos de forma **asíncrona** con **RabbitMQ** y **Hangfire**.  
- Aplicar principios de **DDD** y **Arquitectura Hexagonal** en cada microservicio.  
- Proveer un entorno de despliegue **independiente por módulo** y con comunicación desacoplada.

## 🧩 Descripción General del Sistema

La plataforma permitirá a los usuarios:

- Registrarse, autenticar su identidad y reservar entradas.  
- Pagar servicios y consultar el estado de sus operaciones.  
- Recibir notificaciones en tiempo real sobre confirmaciones y recordatorios.  
- Consultar historial de reservas y facturas.  

A su vez, los organizadores y administradores podrán:

- Crear y administrar eventos, escenarios y aforos.  
- Supervisar pagos, reportes y métricas.  
- Controlar disponibilidad en tiempo real.  
- Integrar servicios complementarios (transporte, catering, merchandising).  

---

## 🧱 Arquitectura Conceptual

``` text
[ React (Frontend) ]
          ↓
[ API Gateway (YARP) ]
          ↓
 ┌─────────────────────────────────────────────┐
 | Auth | User | Event | Booking  | Payment    |
 | Notification | Report | Providers | Files   |
 └─────────────────────────────────────────────┘
          ↓
 [ RabbitMQ | Hangfire | PostgreSQL | MongoDB | Firebase ]
```

## 🧩 Estructura Organizacional (Multi-Repo)

Cada microservicio será un repositorio independiente dentro de la organización GitHub.

| Repositorio | Descripción | Estado |
|-------------|-------------|--------|
| api-gateway | Enrutador central con YARP y validación de tokens Keycloak. | 🔜 Pendiente |
| auth-service | Servicio de autenticación y autorización con Keycloak. | 🔜 Pendiente |
| user-service | Gestión de usuarios, perfiles y auditoría. | 🔜 Pendiente |
| event-service | Administración de eventos, escenarios y asientos. | 🔜 Pendiente |
| booking-service | Gestión de reservas, expiración automática y eventos de negocio. | 🔜 Pendiente |
| payment-service | Procesamiento asíncrono de pagos y facturación digital. | 🔜 Pendiente |
| notification-service | Notificaciones en tiempo real (SignalR/WebSockets). | 🔜 Pendiente |
| reporting-service | Generación de reportes, métricas y analítica. | 🔜 Pendiente |
| external-providers-service | Integración con proveedores de transporte/catering. | 🔜 Pendiente |
| frontend-app | Aplicación React para usuarios, organizadores y administradores. | 🔜 Pendiente |
| infrastructure | Configuración compartida, CI/CD y scripts de despliegue. | 🔜 Pendiente |

## 🧩 Extensiones Planificadas

- Auditoría y Logs: registro de actividad en MongoDB o ElasticSearch.
- Recomendaciones Inteligentes: sugerencias basadas en historial del usuario.
- Encuestas y Feedback: recolección de opiniones posteriores al evento.
- Marketing y Promociones: generación de descuentos y campañas.
- Streaming y Comunidad: soporte para eventos virtuales e interacción entre usuarios.

## 📋 Requerimientos Funcionales Clave

- Autenticación y Autorización – Integración con Keycloak, manejo de roles y permisos.
- Gestión de Usuarios – Registro, perfiles, historial de reservas y pagos.
- Gestión de Eventos – Creación, modificación y configuración de aforos.
- Escenarios y Asientos – Control de disponibilidad y liberación automática.
- Reservas – Procesamiento asíncrono con RabbitMQ y jobs de expiración.
- Pagos y Facturación – Conciliación y generación de comprobantes.
- Servicios Complementarios – Integración con APIs simuladas.
- Notificaciones – En tiempo real mediante SignalR/WebSockets.
- Reportes y Analítica – Métricas automáticas diarias y semanales.
- Administración y Panel de Control – Dashboard unificado con métricas clave.

## 🧪 Estado Actual del Proyecto

Fase inicial de configuración de la organización GitHub, documentación base y definición de estructura multi-repo.

## 📚 Créditos

Proyecto académico desarrollado por estudiantes de Ingeniería Informática
Facultad de Ingeniería – Universidad Católica Andrés Bello

- Gil Farías, Jesús Rodolfo
- Gonzalez Landaeta, Crismary Yetzabeh Maria

Curso: Desarrollo del Software (DS 2025-02)
Profesor: Bismarck Ponce
Fecha: Septiembre 2025 – Enero 2026

## 📜 Licencia

Este repositorio se distribuye con una licencia académica que permite su uso
con fines educativos dentro del curso "Desarrollo del Software – DS 2025-02".
El texto completo de la licencia se encuentra en el archivo `LICENSE` en la
raíz de este repositorio.

Importante: todos los repositorios de la organización **eventmesh-lab** se
rigen por la misma política de licencia académica indicada en `LICENSE`.
Esto significa que la reutilización, redistribución o explotación del código o
documentación fuera del ámbito del curso (por ejemplo, con fines comerciales
o en proyectos no relacionados con DS 2025-02) requiere autorización previa y
por escrito del equipo desarrollador.

Si necesitas autorización para un uso fuera del ámbito académico o tienes
preguntas sobre la licencia, consulta la sección "Contacto" dentro de
`LICENSE` o solicita que añadamos un `CONTACT.md` con el proceso formal de
solicitud.
