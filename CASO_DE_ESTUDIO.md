# Caso de Estudio — Sistema de Gestión CITSA

**Cliente:** CITSA (Centro de Investigaciones Toxicológicas), Argentina  
**Tipo:** Herramienta interna — Gestión de presupuestos y flujos de trabajo  
**Estado:** ✅ En producción, en uso activo  
**Tiempo de desarrollo:** 5 días desde cero hasta el deploy  

---

## El Problema

CITSA es un centro de investigaciones toxicológicas que brinda servicios de análisis de laboratorio a municipios, organismos del Estado, universidades y empresas privadas de todo el país.

Su proceso de presupuestación era completamente manual:
- El personal revisaba documentos técnicos y licitaciones a mano
- Buscaban manualmente cada análisis requerido en un catálogo de más de 300 servicios
- Armaban las cotizaciones en planillas de Excel, línea por línea
- El proceso completo llevaba **entre 1 y 2 horas por presupuesto**

Con un alto volumen de solicitudes entrantes, esto consumía una parte significativa del tiempo productivo del equipo cada semana.

---

## La Solución

Una aplicación web full-stack que automatiza todo el proceso — desde la recepción del documento hasta la cotización final.

La funcionalidad central: un **analizador de documentos con IA** que lee cualquier PDF (licitación, pliego técnico, normativa) y automáticamente:
1. Identifica qué análisis toxicológicos se requieren
2. Los matchea contra el catálogo de servicios (incluso con nombres distintos)
3. Detecta cantidades e información del cliente
4. Genera un borrador de presupuesto completo en segundos

El personal solo revisa y aprueba — sin búsqueda manual.

---

## Funcionalidades Desarrolladas

- **Analizador de Documentos IA** — Claude API lee PDFs y mapea los requerimientos al catálogo de servicios
- **Gestión de Presupuestos** — Ciclo de vida completo: borrador → enviado → aprobado/rechazado, con descuentos y exportación a PDF
- **Base de Clientes** — 390+ clientes importados, buscables, con historial completo de presupuestos
- **Catálogo de Servicios** — 300+ análisis toxicológicos con precios, matrices y métodos de ensayo
- **Dashboard Predictivo** — Tendencias de ingresos, tasas de conversión, KPIs mensuales
- **Autenticación por Roles** — Roles de administrador y operador, sesiones con JWT
- **Notificaciones por Email** — Alertas automáticas para nuevos presupuestos y recuperación de contraseña
- **Backups Automáticos** — Snapshots diarios de la base de datos enviados por email

---

## Resultados

| Métrica | Antes | Después |
|---------|-------|---------|
| Tiempo por presupuesto | ~2 horas | < 5 minutos |
| Errores manuales | Frecuentes | Casi nulos |
| Personas usando el sistema | 0 | 10 |
| Tiempo de desarrollo y deploy | — | 5 días |

---

## Stack Tecnológico

| Capa | Tecnología |
|------|-----------|
| Frontend | React 18 + TypeScript + Vite + shadcn/ui |
| Backend | Node.js + TypeScript + Express |
| Base de datos | PostgreSQL (Drizzle ORM) |
| IA | Anthropic Claude API |
| Deploy | Replit |
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
