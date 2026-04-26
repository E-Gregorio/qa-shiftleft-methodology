<div align="center">

# QA Shift-Left Methodology

**Framework operativo integrado para QA Shift-Left.** Unifica la aplicación práctica de ISTQB v4, ISO/IEC/IEEE 29119, ISO/IEC/IEEE 29148, OWASP y NIST AI RMF en una estrategia ejecutable: testing manual, automation, E2E, performance, seguridad y testing de IA/LLM.

17 documentos ejecutables · Guías estratégicas · Framework VCR propio (Valor + Costo + Riesgo) · Modelo de madurez

[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](LICENSE)
[![ISTQB](https://img.shields.io/badge/ISTQB-v4%20Foundation%202023-2563EB)](#-marco-normativo-actualizado)
[![ISO/IEC/IEEE 29119](https://img.shields.io/badge/ISO%2FIEC%2FIEEE-29119-1D4ED8)](#-marco-normativo-actualizado)
[![ISO/IEC/IEEE 29148](https://img.shields.io/badge/ISO%2FIEC%2FIEEE-29148%3A2018-1D4ED8)](#-marco-normativo-actualizado)
[![OWASP LLM Top 10](https://img.shields.io/badge/OWASP-LLM%20Top%2010-EF4444)](#-testing-de-ia--llm)
[![NIST AI RMF](https://img.shields.io/badge/NIST-AI%20RMF%201.0-10B981)](#-testing-de-ia--llm)

</div>

---

## Sobre este framework

Este es un **framework operativo integrado** mantenido por [E-Gregorio](https://github.com/E-Gregorio).

> ⚠️ **Aclaración de autoría:** este repositorio **no reclama autoría de Shift-Left Testing, ISTQB, ISO/IEC/IEEE 29119, ISO/IEC/IEEE 29148, OWASP ni NIST AI RMF**. Esas metodologías y estándares son **públicos** y pertenecen a sus respectivos organismos (ISTQB, ISO, IEEE, OWASP Foundation, NIST).

### ¿Qué aporta este repositorio?

El rol del autor es el de **integrador estratégico**. Lo que sí es de autoría propia:

1. **La integración operativa** de metodologías y estándares que ya existen pero que normalmente se aplican por separado.
2. **La unificación de 17 documentos ejecutables** (plantillas, guías, informes, modelo de madurez) que permiten a un equipo aplicarlos de forma cohesionada.
3. **El framework VCR** (Valor + Costo + Riesgo) — metodología propia para priorización objetiva de automatización.
4. **La estrategia de implementación end-to-end** que articula testing manual, automation, E2E, performance, seguridad y testing de IA/LLM bajo una sola visión operativa.

### ¿Por qué existe?

Para darle a equipos QA un marco ejecutable y completo que normalmente tendrían que construir desde cero combinando documentación dispersa de múltiples fuentes (sitios oficiales de ISTQB, ISO, OWASP, NIST, papers, blogs).

### Características del framework

- **No se queda en lo teórico**: cada concepto viene con plantilla, ejemplo y criterio de aceptación.
- **Referencia a normativa vigente** (no a estándares retirados como IEEE 829/830).
- **Cubre el QA moderno completo**: manual, automation E2E, API, performance, seguridad, accesibilidad y **testing de IA/LLM**.
- **Accionable desde el día 1**: las plantillas se copian, se pegan en Confluence/Jira/Notion y funcionan.

> 🎯 **Propósito:** que un equipo QA pueda madurar de **nivel reactivo** a **nivel preventivo y predictivo** usando un único marco coherente, sin tener que reconstruir la integración entre estándares.

---

## 🚀 Inicio rápido

### Punto de entrada principal
Abrí el archivo principal del framework:
```
informesFormatoHtml/setup_QA_ShiftleftTesting.html
```

### Portal de guías estratégicas
```
informesFormatoHtml/05_Guias/index.html
```

### Sitio publicado
Una vez hecho el primer push a `main`, GitHub Actions despliega automáticamente todo el contenido en GitHub Pages:
```
https://e-gregorio.github.io/qa-shiftleft-methodology/
```

---

## 📁 Estructura del proyecto

```
qa-shiftleft-methodology/
├── informesFormatoHtml/                # 🎯 FRAMEWORK PRINCIPAL (HTML)
│   ├── setup_QA_ShiftleftTesting.html  # Presentación principal
│   ├── 03_Planes/                      # Plantillas de planificación
│   ├── 04_Informes/                    # Informes y métricas
│   └── 05_Guias/                       # Guías estratégicas
│       ├── guia-estimacion-vcr.html
│       ├── guia-estrategia-pruebas.html
│       ├── guia-gestion-riesgos.html
│       ├── guia-testing-ia-llm.html        ⭐ NUEVO
│       ├── guia-testing-performance.html   ⭐ NUEVO
│       ├── guia-devsecops-security.html    ⭐ NUEVO
│       └── marco-normativo-estandares.html
├── informesISQTB/                      # Fuentes en Markdown
├── Command_Center_Shift-Left-Testing/  # Plataforma de comando QA
├── .github/workflows/pages.yml         # Auto-deploy a GitHub Pages
├── LICENSE                             # CC BY-NC-ND 4.0
└── README.md
```

---

## 🧭 Cobertura del framework

### Disciplinas de testing soportadas

| Disciplina | Cobertura | Guía |
|---|---|---|
| **Testing manual exploratorio** | Charters, session-based testing, heurísticas | `guia-estrategia-pruebas.html` |
| **Test design (ISTQB)** | Black-box, white-box, experience-based | `guia-estrategia-pruebas.html` |
| **Automation E2E** | Estrategia, anti-patterns, Page Object Model | `guia-estrategia-pruebas.html` |
| **API / Contract testing** | REST, GraphQL, Pact, schema validation | `guia-estrategia-pruebas.html` |
| **Performance / Load** | k6, Lighthouse, perfiles de carga, ISO 25010 | `guia-testing-performance.html` |
| **Seguridad / DevSecOps** | SAST, DAST, SCA, OWASP ASVS, Top 10 2021 | `guia-devsecops-security.html` |
| **Accesibilidad** | WCAG 2.2, axe-core, Lighthouse a11y | `guia-estrategia-pruebas.html` |
| **🤖 Testing de IA / LLM** | OWASP LLM Top 10, ISO/IEC TR 29119-11, NIST AI RMF, MLPerf, evals | `guia-testing-ia-llm.html` |
| **Risk-based testing** | Probabilidad × Impacto, ISTQB risk approach | `guia-gestion-riesgos.html` |
| **Estimación VCR** | Valor + Costo + Riesgo → decisión de automatización | `guia-estimacion-vcr.html` |

---

## 📐 Marco normativo (actualizado)

Este framework se mantiene alineado a **estándares vigentes**, no retirados. Si encontrás material en internet citando IEEE 829/830, ya no aplican.

| Estándar | Estado | Uso en el framework |
|---|---|---|
| **ISTQB Foundation Level v4 (2023)** | ✅ Vigente | Cuerpo metodológico base |
| **ISO/IEC/IEEE 29119-1:2022** | ✅ Vigente | Conceptos y vocabulario |
| **ISO/IEC/IEEE 29119-2:2013** | ✅ Vigente | Procesos de testing |
| **ISO/IEC/IEEE 29119-3:2021** | ✅ Vigente | **Test Documentation (sucesor de IEEE 829)** |
| **ISO/IEC/IEEE 29119-4:2021** | ✅ Vigente | Técnicas de prueba |
| **ISO/IEC/IEEE 29119-11:2020** | ✅ Vigente | **Testing de sistemas basados en IA** |
| **ISO/IEC/IEEE 29148:2018** | ✅ Vigente | **Requirements Engineering (sucesor de IEEE 830)** |
| **ISO/IEC 25010:2023** | ✅ Vigente | Modelo de calidad de producto |
| **ISO/IEC 25059:2023** | ✅ Vigente | Modelo de calidad para sistemas IA |
| **ISO/IEC 27001:2022** | ✅ Vigente | Seguridad de la información |
| **ISO 9001:2015** | ✅ Vigente | Gestión de calidad |
| **WCAG 2.2** (W3C, oct 2023) | ✅ Vigente | Accesibilidad |
| **OWASP Top 10 (2021)** | ✅ Vigente | Vulnerabilidades web |
| **OWASP ASVS 4.0.3** | ✅ Vigente | Verificación de seguridad |
| **OWASP LLM Top 10 (2025)** | ✅ Vigente | Riesgos de aplicaciones LLM |
| **NIST AI RMF 1.0** | ✅ Vigente | Gestión de riesgos de IA |
| **MLPerf Inference / Training** | ✅ Vigente | Benchmarking de modelos |
| ~~IEEE 829-2008~~ | ❌ Retirado (2009) | Reemplazado por ISO 29119-3 |
| ~~IEEE 830-1998~~ | ❌ Reemplazado | Reemplazado por ISO 29148 |
| ~~ISO 27001:2013~~ | ❌ Reemplazado | Reemplazado por 27001:2022 |
| ~~WCAG 2.1~~ | ⚠️ Vigente pero superado | Reemplazado por WCAG 2.2 |

---

## 📊 Metodología VCR (Valor-Costo-Riesgo)

Mecanismo de **priorización objetiva** para decidir qué automatizar:

```
VCR = Valor + Costo + Riesgo
```

| Componente | Escala | Significado |
|---|---|---|
| **Valor (V)** | 1–3 | Beneficio de negocio |
| **Costo (C)** | 1–3 | Esfuerzo de prueba manual recurrente |
| **Riesgo (R)** | 1–9 | Probabilidad × Impacto (ISO 31000) |

**Regla de decisión:** Si `VCR ≥ 9` → **Automatizar** · Si `VCR < 9` → **Manual / exploratoria**

Detalle completo en [`05_Guias/guia-estimacion-vcr.html`](informesFormatoHtml/05_Guias/guia-estimacion-vcr.html).

---

## 🤖 Testing de IA / LLM

Sección que **diferencia** este framework. Cubre lo que la mayoría de documentación no toca:

- **Evals** (evaluaciones de modelo): exact match, semantic similarity, LLM-as-a-judge, rubric-based.
- **OWASP LLM Top 10 (2025)**: prompt injection, insecure output handling, training-data poisoning, model DoS, supply-chain, sensitive info disclosure, insecure plugin design, excessive agency, overreliance, model theft.
- **Performance de LLMs**: latencia (TTFT, TPOT), throughput (tokens/s), tail-latency p95/p99, cost-per-call, context-window stress.
- **Calidad de respuesta**: groundedness (RAG), hallucination rate, refusal rate, toxicity (Perspective API), bias (BBQ benchmark).
- **Robustez**: adversarial prompts, jailbreak resistance, multi-turn coherence.
- **Regression testing en producción**: golden datasets, canary evals, shadow mode, A/B con métricas estadísticamente significativas.
- **Estándares aplicables**: ISO/IEC TR 29119-11:2020, ISO/IEC 25059:2023, NIST AI RMF 1.0, EU AI Act (referencia).
- **Benchmarking**: MLPerf, HELM, MMLU, HumanEval, ARC.

Detalle en [`05_Guias/guia-testing-ia-llm.html`](informesFormatoHtml/05_Guias/guia-testing-ia-llm.html).

---

## 🛠️ Stack tecnológico recomendado

| Capa | Herramientas |
|---|---|
| **E2E / UI** | Playwright (TS), Cypress, WebdriverIO |
| **API / Contract** | Postman/Newman, REST Assured, Pact |
| **Performance** | k6, JMeter, Lighthouse CI, Gatling |
| **Seguridad** | OWASP ZAP (DAST), Semgrep / SonarQube (SAST), Trivy / Snyk (SCA), Gitleaks (secrets) |
| **Accesibilidad** | axe-core, Pa11y, Lighthouse a11y |
| **Testing IA/LLM** | promptfoo, Ragas, DeepEval, OpenAI evals, Helicone |
| **Observabilidad QA** | Allure, ReportPortal, Grafana + Prometheus |
| **CI/CD** | GitHub Actions, GitLab CI, Azure DevOps |
| **TDM** | Faker, Snowfakery, anonimización con Presidio |

---

## 📈 Métricas y KPIs

### Cobertura
- **Code coverage:** ≥ 80% (unit), ≥ 60% (integration)
- **Functional coverage:** ≥ 95% en flujos críticos
- **Requirements traceability:** 100%

### Calidad
- **Defect density:** ≤ 3 defectos / 100 SP
- **Defect leakage** (escapes a producción): ≤ 5%
- **MTTR de defectos críticos:** < 24h

### Eficiencia
- **Automation rate:** ≥ 70% de regresión automatizada
- **Tiempo de ejecución regresión completa:** < 30 min
- **First Time Right** (PRs sin rework por QA): ≥ 85%

### LLM/IA (cuando aplica)
- **Groundedness (RAG):** ≥ 0.85
- **Hallucination rate:** ≤ 5%
- **p95 TTFT:** < 1.5s
- **Eval pass rate (golden set):** ≥ 95%

---

## 🎯 Modelo de madurez

| Nivel | Características | Foco |
|---|---|---|
| **L1 — Reactivo** | Testing al final, manual, sin métricas | Empezar con plantillas operativas |
| **L2 — Gestionado** | Plan de prueba formal, gestión de defectos | Adoptar VCR + risk-based |
| **L3 — Preventivo** | Shift-left activo, automation regression | Integrar CI/CD + métricas |
| **L4 — Predictivo** | Performance + security + a11y en pipeline | Adoptar DevSecOps + observabilidad |
| **L5 — Optimizado** | Testing IA/LLM, evals continuos, evidencia para auditoría | Diferenciador real |

---

## 📋 Plantillas disponibles

### Planificación (`03_Planes/`)
- **Master Test Plan** (ISO/IEC/IEEE 29119-3 §5)
- **Test Plan por sprint**
- **User Stories ISTQB-compatible**

### Informes y seguimiento (`04_Informes/`)
- Calendario de pruebas (Test Schedule)
- Informe de avance / Test Progress Report
- Informe de cierre (Test Completion Report)
- Reporte de defectos (individual + consolidado)
- Métricas de calidad (dashboard)
- Checklist de revisión (peer review)

### Guías estratégicas (`05_Guias/`)
- Guía de estimación VCR
- Guía de estrategia de pruebas
- Guía de gestión de riesgos
- 🆕 Guía de testing de IA / LLM
- 🆕 Guía de performance testing modernizado
- 🆕 Guía de DevSecOps y testing de seguridad
- Marco normativo y estándares

---

## 🤝 Contribuciones

Este es un proyecto **abierto** —si tu equipo lo usa o querés sugerir mejoras, sos más que bienvenido. Ver [CONTRIBUTING.md](CONTRIBUTING.md).

## 📞 Contacto

**E-Gregorio** · Autor del framework operativo integrado · QA Lead / Test Architect
- GitHub: [@E-Gregorio](https://github.com/E-Gregorio)
- Repo: [qa-shiftleft-methodology](https://github.com/E-Gregorio/qa-shiftleft-methodology)

## 📝 Licencia

Esta metodología se distribuye bajo **[Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)](LICENSE)**.

| ✅ Podés | ❌ No podés |
|---|---|
| Compartir el contenido | Modificarlo y republicarlo como tuyo |
| Citarlo en presentaciones / formaciones | Usarlo con fines comerciales |
| Usarlo internamente en tu equipo | Distribuir versiones derivadas |
| Linkear desde tu blog / LinkedIn | Eliminar la atribución al autor de la integración |

Para uso comercial o adaptaciones, abrí un issue en el repo o contactame por GitHub.

---

<div align="center">

**Si este framework te ayudó, dejá una ⭐ — es la forma de decir gracias en GitHub.**

</div>
