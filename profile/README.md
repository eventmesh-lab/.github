# Plataforma Integral para Gestión de Eventos, Reservas y Servicios con Procesamiento Asíncrono

**Proyecto DS 2025-02 – Facultad de Ingeniería, Escuela de Ingeniería Informática**

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

---

## 🧠 Actores Principales

- **Usuario Final:** realiza reservas, pagos y consulta su historial.  
- **Organizador:** crea y administra eventos, controla aforos y disponibilidad.  
- **Administrador:** supervisa la operación global del sistema.  
- **Sistema Externo de Pagos:** pasarela simulada para procesar pagos.  
- **Proveedores Externos:** transporte, catering y merchandising integrados vía RabbitMQ.

---

## ⚙️ Tecnologías y Estándares

| Capa / Componente | Tecnología | Descripción |
|--------------------|-------------|--------------|
| Backend | .NET 8, MediatR | Implementación modular orientada a dominios |
| Mensajería | RabbitMQ | Procesamiento asíncrono de eventos |
| Jobs | Hangfire | Tareas programadas y background jobs |
| Gateway | YARP | Enrutamiento y balanceo de peticiones |
| Seguridad | Keycloak | Gestión de identidad y autorización |
| Persistencia | PostgreSQL, MongoDB | Bases de datos relacional y documental |
| Frontend | React | Aplicación web dinámica |
| Notificaciones | SignalR/WebSockets | Comunicación en tiempo real |
| Almacenamiento | Firebase Storage | Archivos multimedia y comprobantes |
| Despliegue | Docker / CI-CD | Integración continua y contenedores |

---

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

``` mermaid 
[ React (Frontend) ]
          ↓
[ API Gateway (YARP) ]
          ↓
 ┌────────────────────────────────────┐
 | Auth | User | Event | Booking | Payment |
 | Notification | Report | Providers | Files |
 └────────────────────────────────────┘
          ↓
 [ RabbitMQ | Hangfire | PostgreSQL | MongoDB | Firebase ]
```

