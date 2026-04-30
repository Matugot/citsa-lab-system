# 🧪 CITSA — Sistema de Gestión de Presupuestos con IA

**Demo interactiva** del sistema de gestión desarrollado para CITSA (Centro de Investigaciones Toxicológicas).

🔗 **[Ver demo en vivo](https://matugot.github.io/citsa-lab-system)**

---

## ¿Qué hace este sistema?

CITSA gestionaba sus presupuestos manualmente — revisando licitaciones a mano y armando cotizaciones en planillas. Este sistema automatiza todo el proceso:

- **Analizador de documentos IA**: subís un PDF de licitación y Claude AI identifica automáticamente qué análisis toxicológicos se requieren, los matchea contra el catálogo y genera el presupuesto
- **Gestión de presupuestos**: CRUD completo con estados, descuentos, exportación PDF
- **Catálogo de servicios**: 300+ analitos con precios y métodos de ensayo
- **Dashboard con analytics**: métricas de revenue, conversión, actividad reciente

**Resultado**: reducción del tiempo de cotización de ~2 horas a menos de 5 minutos.

---

## Stack

- **Frontend**: React 18 + TypeScript + Vite + shadcn/ui + Tailwind
- **Backend**: Node.js + TypeScript + Express + Drizzle ORM + PostgreSQL  
- **IA**: Anthropic Claude API (análisis de documentos PDF)
- **Infra**: Railway (backend + DB) + Vercel (frontend)

---

## Esta demo

La demo es una versión estática del frontend con datos de ejemplo. Muestra la interfaz real del sistema incluyendo el flujo del analizador de documentos IA.

Para ver el sistema completo (con backend real y base de datos), contactame.

---

**Mateo Gotelli** — AI Automation & Full-Stack Developer  
[Upwork](https://www.upwork.com) · [GitHub](https://github.com/Matugot)
