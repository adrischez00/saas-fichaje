# SaaS de Fichajes para PYMEs

Plataforma de fichajes en producción, con varios clientes de pago activos.  
Pensada para PYMEs que necesitan cumplir con la obligación legal de registro horario sin recurrir a hojas de cálculo ni a software heredado.

> El código de este proyecto se mantiene **privado por motivos de seguridad y de negocio** (producto en explotación comercial). Este repositorio contiene la documentación, decisiones técnicas y capturas reales del producto.

**Más información:** [Portfolio – Proyecto Fichajes](https://portfolio-adrisanchez.vercel.app/proyecto/fichajes)  
**Contacto comercial / demo:** adri.ia.dev@gmail.com

---

## El problema

Toda empresa en España está obligada por ley a registrar la jornada de sus empleados. La mayoría de PYMEs lo resuelve con Excel, papel o sistemas heredados que no preparan los datos para una inspección y obligan a recomponer informes a mano cuando llega una auditoría de la Inspección de Trabajo.

## La solución

Un SaaS web orientado a quitar fricción a empresa y empleado:

- El trabajador ficha desde móvil u ordenador, sin instalar nada.
- El responsable gestiona horarios, ausencias y usuarios desde un panel limpio.
- La empresa tiene en un clic los informes en el formato que pide la Inspección de Trabajo.

## Funcionalidades principales

- Fichaje web responsive (móvil y escritorio)
- Panel de administración con gestión de usuarios, turnos y ausencias
- Exportaciones legales en CSV, PDF y XLSX listas para inspección
- Multi-empresa: una sola plataforma gestiona varias organizaciones
- Roles diferenciados (empleado, responsable, administrador)
- Trazabilidad completa de cambios para auditoría

## Capturas

<p align="center">
  <img src="docs/captura-1.png" width="700" alt="Vista de fichaje"/>
</p>

<p align="center">
  <img src="docs/captura-2.png" width="700" alt="Panel de administración"/>
</p>

## Stack

| Capa | Tecnología |
|---|---|
| Frontend | Next.js · TypeScript · Tailwind · shadcn/ui |
| Backend | FastAPI (Python) |
| Base de datos | PostgreSQL en Neon · Prisma |
| Infraestructura | Vercel · Cloud Run · Docker |
| Autenticación | JWT con roles |

## Decisiones técnicas

**FastAPI en lugar de Node.** Tipado estricto con Pydantic y mejor rendimiento procesando exportaciones pesadas (PDF y XLSX con miles de registros mensuales por cliente).

**Neon como base de datos.** Branching de base de datos para crear entornos de staging por cliente sin coste extra ni replicación manual.

**shadcn/ui en vez de librería cerrada.** Control total del código de cada componente, sin atarme a versiones de terceros y con tema consistente en todo el panel.

**Exportaciones legales como ciudadano de primera.** Es la funcionalidad que más decide la venta: una PYME no contrata un fichaje por el fichaje, lo contrata por estar tranquila ante una inspección.

**Multi-tenant desde el principio.** Aislamiento por empresa a nivel de modelo y de permisos, no añadido a posteriori. Permite escalar el SaaS sin reescribir la base de datos.

## Estado actual

- En producción
- Varios clientes de pago activos
- Mantenimiento y desarrollo de nuevas funcionalidades en curso

## ¿Quieres una demo o información?

¿Eres una PYME y quieres simplificar el registro horario, o un reclutador interesado en mi perfil?

📧 **adri.ia.dev@gmail.com**  
🌐 [portfolio-adrisanchez.vercel.app](https://portfolio-adrisanchez.vercel.app)  
💼 [LinkedIn](https://www.linkedin.com/in/adrian-sanchez-guerrero)
