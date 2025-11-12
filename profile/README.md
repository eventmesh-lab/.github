# EventMesh - Plataforma de Gestión de Eventos

> **Proyecto DS 2025-02** | Facultad de Ingeniería, UCAB  
> Desarrollo del Software | Prof. Bismarck Ponce | Sep 2025 - Ene 2026

[![Documentación](https://img.shields.io/badge/docs-disponible-blue)](https://eventmesh-lab.github.io/org-docs/)
[![Estado](https://img.shields.io/badge/estado-en%20desarrollo-yellow)]()

---

## 🎯 Sobre el Proyecto

Plataforma web distribuida para gestión integral de eventos (conciertos, conferencias, talleres) con procesamiento asíncrono, permitiendo reservas, pagos, servicios complementarios y notificaciones en tiempo real.

**Tecnologías Clave:** Arquitectura Hexagonal, DDD, .NET Core, React, RabbitMQ, Hangfire, Keycloak, PostgreSQL

---

## 🏗️ Arquitectura

```
┌─────────────────┐
│  React Frontend │
└────────┬────────┘
         ↓
┌─────────────────┐
│  API Gateway    │ ← YARP + Keycloak
└────────┬────────┘
         ↓
┌──────────────────────────────────────────┐
│  Auth  │  User  │  Event  │  Booking     │
│  Payment  │  Notification  │  Reporting  │
└────────┬─────────────────────────────────┘
         ↓
┌──────────────────────────────────────────┐
│ RabbitMQ │ Hangfire │ PostgreSQL │ Mongo │
└──────────────────────────────────────────┘
```

---

## 📦 Repositorios (Multi-Repo)

| Servicio | Descripción | Estado |
|----------|-------------|--------|
| [frontend-app](https://github.com/eventmesh-lab/eventmesh-frontend) | Aplicación React (usuarios/admin) | ✅ Activo |
| [api-gateway](https://github.com/eventmesh-lab/svc_yarp_api-gateway) | Enrutamiento central (YARP) |  🟡 En proceso|
| auth-service | Autenticación con Keycloak | 🔜 Próximo |
| [event-service](https://github.com/eventmesh-lab/events-service) | Gestión de eventos y asientos |   🟡 En proceso|
| booking-service | Reservas y expiración automática | 🔜 Próximo |
| payment-service | Pagos asíncronos y facturación | 🔜 Próximo |
| notification-service | Notificaciones real-time (SignalR) | 🔜 Próximo |
| reporting-service | Analítica y métricas | 🔜 Próximo |
| user-service | Perfiles y auditoría | 🔜 Próximo |
| external-providers-service | Integración servicios externos | 🔜 Próximo |

---

## ✨ Funcionalidades Principales

**Para Usuarios:**
- 🎟️ Reserva de entradas con gestión de disponibilidad en tiempo real
- 💳 Procesamiento de pagos y descarga de facturas
- 🔔 Notificaciones instantáneas de confirmación y recordatorios
- 📊 Historial completo de reservas y transacciones

**Para Organizadores:**
- 📅 Creación y administración de eventos
- 🏟️ Control de escenarios, aforos y asientos
- 📈 Reportes automáticos y métricas de rendimiento
- 🔗 Integración con servicios complementarios (catering, transporte)

---

## 🚀 Extensiones Futuras

- 🔍 Recomendaciones inteligentes basadas en historial
- 📝 Sistema de encuestas y feedback post-evento
- 🎯 Motor de promociones y marketing
- 🎥 Soporte para eventos virtuales y streaming
- 📊 Auditoría avanzada con ElasticSearch

---

## 📚 Documentación

La documentación técnica completa se encuentra en el repositorio [`org-docs`](https://github.com/eventmesh-lab/org-docs):

- **Arquitectura:** Decisiones técnicas y patrones de diseño
- **API Reference:** Especificación de endpoints por servicio
- **Guías de Desarrollo:** Setup, convenciones y workflows
- **Diagramas:** C4 Model, casos de uso y flujos de datos

---

## 👥 Equipo

**Desarrolladores:**  
Gil Farías, Jesús Rodolfo | Gonzalez Landaeta, Crismary Yetzabeh Maria

**Institución:** Universidad Católica Andrés Bello - Escuela de Ingeniería Informática

---

## 📄 Licencia

Proyecto académico bajo licencia educativa (DS 2025-02).  
Ver [`LICENSE`](https://github.com/eventmesh-lab/.github/blob/main/LICENSE) para detalles sobre uso y restricciones.

---

**Estado actual:** Configuración inicial de infraestructura y documentación base.
