<div align="left">
  <img src="../02-assets/logo.png" alt="QA Shift-Left Methodology" width="220"/><br/>
  <sub><b>QA Shift-Left Methodology · by E-Gregorio</b> — Plantilla alineada a ISTQB v4 (Foundation 2023) e ISO/IEC/IEEE 29119</sub>
</div>


# Estrategia de Pruebas (Organizacional)

**Propósito**  
Establecer un marco común de prueba para todos los proyectos de EpiData,  
alineado a ISTQB v4 e ISO/IEC/IEEE 29119, que defina principios, niveles de prueba,  
criterios de automatización y métricas de calidad.

## Alcance
Aplica a todos los productos y servicios desarrollados, en todas las fases del ciclo de vida de software.

## Enfoques y niveles de prueba
- **Estática**: revisiones de requisitos, análisis de código, checklists.  
- **Dinámica**: unidad, integración, sistema, aceptación (UAT).  
- **No funcionales**: performance/stress, seguridad, usabilidad, accesibilidad.

## Priorización basada en riesgo (Risk-Based Testing – RBT)
- Uso de escalas **Probabilidad (P)** y **Impacto (I)** de 1–5.  
- Cálculo del nivel de riesgo **R = P × I**.  
- Cobertura priorizada según nivel: Crítico → Alto → Medio → Bajo.

## Estrategia de automatización
- Criterios ROI: repetitividad, criticidad, estabilidad de requisitos.  
- Pirámide de automatización: Unit > API > UI.  
- Integración en pipelines CI/CD.

## Ambientes y datos de prueba
- Paridad de ambientes (DEV/QA/PROD).  
- Health-checks automáticos.  
- Seeds y anonimización de datos sensibles.  
- Procedimientos de refresh.

## Métricas / KPI
- Pass Rate (por ciclo y por requisito).  
- Ejecución vs Plan (burn-down de casos).  
- Cobertura de requisitos y de riesgo.  
- Defectos abiertos/cerrados, densidad de defectos, DRE.  
- MTTR (Mean Time To Repair).  
- % de automatización por capa.  
- Resultados de pruebas no funcionales (NFR).

## Criterios de entrada, salida y suspensión
- **Entrada**: Definition of Ready para pruebas; ambientes y datos estables.  
- **Salida**: 0 defectos bloqueantes/altos, coberturas ≥ 90%, NFR cumplidos.  
- **Suspensión / Reanudación**:  
  - Suspender si defectos críticos bloquean ≥1 flujo principal, o si pruebas de stress >25 % de error.  
  - Reanudar cuando los bloqueos se resuelvan y se valide el entorno.

## Roles y responsabilidades
- **QA Lead**: definición de estrategia, coordinación global.  
- **QA Funcional / Automatización / Performance**: diseño, ejecución y reporte de pruebas.  
- **Product Owner / Business Analyst**: definición de requisitos y criterios de aceptación.  
- **Desarrollo / Arquitectura**: soporte técnico y correcciones.  
- **Project Manager / Scrum Master**: planificación y seguimiento.

## Herramientas y repositorios
- Gestión de casos de prueba y defectos: Jira + Zephyr/Xray.  
- Automatización: Playwright / PyTest.  
- Performance: JMeter / K6.  
- Observabilidad: Grafana / OpenShift logs.  
