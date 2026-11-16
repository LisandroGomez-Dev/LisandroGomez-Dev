# Lisandro Gomez | Desarrollador Backend Java Jr.

**Java 21 · Spring Boot 3 · Spring Data JPA · PostgreSQL · Flyway · JUnit 5 · Docker**  
Analista Programador Universitario (FACENA – UNNE) · Argentina

Busco mi primera oportunidad como **Desarrollador Backend Java Jr.** para aportar código limpio, testeado y mantenible dentro de un equipo de ingeniería. Me especializo en el desarrollo de APIs REST con **Java y Spring Boot**, poniendo foco en la integridad de los datos: control de concurrencia, transacciones, manejo centralizado de errores y pruebas unitarias.

---

## 🧠 Enfoque de Ingeniería Backend

- **Arquitectura y POO:** Diseño en capas (`domain`, `application`, `infrastructure`), modelo de dominio rico con encapsulamiento estricto y DTOs inmutables con **Java Records**.
- **Patrones de Diseño:** Aplicación práctica de *State*, *Strategy*, *Factory Method* y *Repository*.
- **Persistencia e Integridad:** **Spring Data JPA / Hibernate**, migraciones versionadas con **Flyway**, restricciones relacionales en **PostgreSQL** y control de concurrencia con bloqueo optimista (`@Version`).
- **Calidad y Resiliencia:** Pruebas unitarias de servicios con **JUnit 5 y Mockito**, manejo global de excepciones (`@RestControllerAdvice` + `ProblemDetail` RFC 7807) e integración segura de webhooks idempotentes (`HMAC-SHA256`).
- **Metodología:** Experiencia trabajando en equipo bajo **Scrum** y modelado con **UML**.

---

## 🛠️ Stack Técnico

| Categoría | Tecnologías |
| :--- | :--- |
| **Lenguajes** | Java (Java 17 / Java 21), SQL |
| **Backend Java** | Spring Boot 3, Spring Web (APIs REST), Spring Data JPA, Hibernate, Jakarta Bean Validation, Spring Scheduling, Spring Boot Actuator, Maven |
| **Bases de Datos** | PostgreSQL, MySQL, SQL Server, Flyway (migraciones versionadas) |
| **Testing** | JUnit 5, Mockito |
| **Infraestructura y Herramientas** | Git, GitHub, Docker, Docker Compose, Postman, Scrum, UML |
| **Frontend Complementario** | React, TypeScript, Tailwind CSS (para construir clientes que consumen mis APIs) |

---

## 📌 Proyectos Destacados (Java + Spring Boot)

### 1. SaaS de Turnos Online y Control de Caja — API REST con Pagos
Plataforma multi-negocio para gestión de reservas con seña previa obligatoria, protección contra ausentismo y métricas financieras de caja en tiempo real.

**Stack:** `Java 21` · `Spring Boot 3.3` · `Spring Data JPA` · `Hibernate` · `PostgreSQL 16` · `Flyway` · `JUnit 5` · `Mockito` · `Docker` · `React`

- **Control de concurrencia (`@Version`):** Previene reservas duplicadas simultáneas sobre un mismo horario, retornando `HTTP 409 Conflict` con `ProblemDetail` (RFC 7807) mediante `@RestControllerAdvice`.
- **Pagos e idempotencia:** Integración con Mercado Pago Checkout Pro mediante webhook idempotente con verificación criptográfica `HMAC-SHA256` y protección contra *replay attacks* (ventana de 5 minutos), aislando llamadas HTTP externas con `TransactionTemplate` para no retener conexiones del pool HikariCP.
- **Patrones y dominio:** Máquina de estados con patrón **State** (`EstadoTurno`, 7 estados), liquidación de saldos en mostrador con **Strategy** (`Efectivo`, `Transferencia`, `Tarjeta`, `Mercado Pago`), **Factory Method** y 25 DTOs con **Java Records**.
- **Automatización y testing:** Tarea programada (`@Scheduled`) para expirar reservas impagas tras 10 minutos, cálculo de disponibilidad sin tiempos muertos y suite de tests unitarios con **JUnit 5 y Mockito**.

🔗 **Repositorio:** [LisandroGomez-Dev/Saas-Turnos](https://github.com/LisandroGomez-Dev/Saas-Turnos)

---

### 2. Motor de Gestión de Inventario con Bloqueo Optimista
API REST transaccional diseñada para prevenir la sobreventa y las condiciones de carrera (*race conditions*) sobre el stock en escenarios de alta concurrencia.

**Stack:** `Java 21` · `Spring Boot 3` · `Spring Data JPA` · `Hibernate` · `PostgreSQL` · `Flyway` · `Docker Compose` · `React`

- **Bloqueo optimista (`@Version`):** Detecta colisiones ante lecturas desactualizadas y responde `HTTP 409 Conflict`.
- **Doble barrera de integridad:** Validaciones en capa de dominio/servicio (`Bean Validation`) + restricción `CHECK (stock >= 0)` a nivel de base de datos PostgreSQL.
- **Entorno reproducible:** Esquema versionado con **Flyway** y orquestación con **Docker Compose**, acompañado de un cliente simulador en React que dispara peticiones concurrentes en tiempo real.

🔗 **Repositorio:** [LisandroGomez-Dev/motor-gestion-inventario-bloqueo-optimista](https://github.com/LisandroGomez-Dev/motor-gestion-inventario-bloqueo-optimista)

---

## 🎓 Educación

- **Analista Programador Universitario** *(Título Intermedio Finalizado — en trámite)* — FACENA, Universidad Nacional del Nordeste (UNNE) · *2023 – 2026*
- **Licenciatura en Sistemas de Información** *(En curso)* — FACENA, Universidad Nacional del Nordeste (UNNE) · *2023 – Actualidad*

---

## 📬 Contacto y Disponibilidad

- **LinkedIn:** [linkedin.com/in/lisandro-gomez-041083327](https://www.linkedin.com/in/lisandro-gomez-041083327/)
- **Email:** lisandroygomezhertler.99@gmail.com
- **Disponibilidad:** Full-time / Part-time · Remoto, híbrido o presencial (disponibilidad para relocalización)
