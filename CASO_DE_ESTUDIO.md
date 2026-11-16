# Caso de Estudio — Sistema de Gestión CITSA

**Cliente:** CITSA, el laboratorio de mi familia (Argentina)  
**Tipo:** Herramienta interna — Gestión de muestras, presupuestos y documentación  
**Estado:** ✅ En producción, se usa en el día a día  
**Tiempo de desarrollo:** 5 días desde cero hasta el deploy  

---

## El Contexto

CITSA es el laboratorio de mi familia. Necesitaba un sistema propio para ordenar el trabajo de todos los días: seguir las muestras, armar los presupuestos y dejar de hacer a mano la documentación repetitiva.

---

## La Solución

Una aplicación web full-stack que cubre la gestión de muestras, los presupuestos y la automatización de la documentación, y que se personaliza a las necesidades de cada empresa.

Una de las funcionalidades es un **analizador de documentos con IA**: lee el pedido de análisis o la especificación técnica de un cliente (PDF) y:
1. Identifica qué análisis se piden
2. Los matchea contra el catálogo de servicios (incluso con nombres distintos)
3. Detecta cantidades e información del cliente
4. Arma un borrador de presupuesto

El personal revisa y aprueba cada presupuesto.

---

## Funcionalidades Desarrolladas

- **Gestión de Muestras** — Seguimiento de las muestras dentro del laboratorio
- **Analizador de Documentos IA** — Claude API lee PDFs y mapea los requerimientos al catálogo de servicios
- **Gestión de Presupuestos** — Ciclo de vida completo: borrador → enviado → aprobado/rechazado, con descuentos y exportación a PDF
- **Base de Clientes** — Buscable, con historial de presupuestos
- **Catálogo de Servicios** — Análisis con precios, matrices y métodos de ensayo
- **Dashboard** — Tendencias de ingresos, tasas de conversión, KPIs mensuales
- **Autenticación por Roles** — Roles de administrador y operador, sesiones con JWT
- **Notificaciones por Email** — Alertas para nuevos presupuestos y recuperación de contraseña
- **Backups Automáticos** — Copias diarias de la base de datos

---

## Stack Tecnológico

| Capa | Tecnología |
|------|-----------|
| Frontend | React 18 + TypeScript + Vite + shadcn/ui |
| Backend | Node.js + TypeScript + Express |
| Base de datos | PostgreSQL (Drizzle ORM) |
| IA | Anthropic Claude API |
| Demo | GitHub Pages |
| Autenticación | JWT + bcrypt |

---

## Aspectos Técnicos Destacados

**Integración de IA** — El analizador de documentos usa Claude con un prompt cuidadosamente diseñado que fuerza salida en JSON estructurado, valida los IDs de servicios contra la base de datos en vivo y maneja casos borde como PDFs solo de imágenes o terminología ambigua.

**Arquitectura Monorepo** — Frontend, servidor API y paquetes compartidos (esquema de BD, validadores Zod, cliente API) organizados como workspace de pnpm para una separación limpia de responsabilidades.

**Listo para producción desde el día uno** — Logging de actividad, manejo de errores, backups automáticos y gestión de sesiones incorporados desde el inicio, no agregados después.

---

## Demo en Vivo

🔗 [Demo interactiva de CITSA](https://matugot.github.io/citsa-lab-system) — Frontend con datos de ejemplo.

---

*Desarrollado por **Mateo Gotelli** — Desarrollador Full-Stack & Automatización con IA*  
*[GitHub](https://github.com/Matugot) · [Upwork](https://www.upwork.com)*
