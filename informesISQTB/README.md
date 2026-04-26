<div align="left">
  <img src="02-assets/logo.png" alt="QA Shift-Left Methodology" width="240"/>
  <br/>
  <sub><b>QA Shift-Left Methodology · by E-Gregorio</b> — Centro de Control QA (ISTQB v4 / ISO/IEC/IEEE 29119 / ISO/IEC/IEEE 29148)</sub>
</div>


# Centro de Control de QA

Repositorio operativo para estandarizar la planificación, ejecución, trazabilidad y reportes de QA:
planes maestros y por sprint, informes, guías de estimación y métricas, con integración a base de datos
para Epics → User Stories → Test Suites → Test Cases → Defects.

**Normas de referencia**
- ISTQB Foundation Level v4.0 — Cap. 5 (Planificación, Control, Reporte)
- ISO/IEC/IEEE 29119-2 (Test Process) y 29119-3 (Test Documentation)
- ISO/IEC/IEEE 29119 / 29148 — Test Documentation y Requisitos de Software

---

## Estructura

```

informesISQTB/
├─ assets/
│  └─ logo.png
├─ 01\_Estrategia\_de\_Pruebas.md
├─ 1. Calendario de Pruebas – Test Schedule.md
├─ 2. Métricas de Prueba.md
├─ Guía de Estimación VCR y Story Points para Historias de Usuario.MD
├─ Informe de Avance de Prueba.md
├─ Informe de Prueba\_IEEE 29119-3.md
├─ informe de defecto.md
├─ plantillaMasterTestPlan.md
├─ plantillaTestPlan.md
├─ plantilaUS\_ISQTB.html
├─ ISO 29119) — Guía práctica.md
└─ 01-Control/
├─ QA_Gobierno_ISTQB.xlsx
└─ README.md

```

- Los documentos `.md` están listos para VS Code / GitHub / Confluence.
- La plantilla de **Historia de Usuario** es HTML (edición y copia directa a Google Docs).

---

## Documentos clave y uso

| Documento | Cuándo usar | Contenido mínimo normativo |
|---|---|---|
| `01_Estrategia_de_Pruebas.md` | Inicio del proyecto (marco organizacional) | Tipos y niveles de prueba; RBT (P×I); automatización; ambientes/datos; KPIs; **Criterios de Entrada/Salida y Suspensión/Reanudación** |
| `plantillaMasterTestPlan.md` | Inicio de programa/release | Alcance, estrategia, roles/recursos, calendario global, riesgos, **Entrada/Salida** y **Suspensión/Reanudación**, métricas, trazabilidad |
| `plantillaTestPlan.md` | Cada sprint/iteración | Alcance por sprint, calendario por tester, datos/ambientes, riesgos, **Entrada/Salida** y **Suspensión/Reanudación**, métricas de seguimiento |
| `plantilaUS_ISQTB.html` | Refinamiento y Planning Poker | Descripción Como/Quiero/Para; reglas; criterios; dependencias; **Estimación** (SP, V, C, P, I, R=P×I, VCR) con política VCR≥9 |
| `1. Calendario de Pruebas – Test Schedule.md` | Planificación y seguimiento | Fases por tester y global; hitos; dependencias; replan si desviación ≥10% |
| `2. Métricas de Prueba.md` | Seguimiento y reporte | Avance (plan vs ejecución), calidad (defectos, severidad, DRE, MTTR), proceso, NFR; umbrales recomendados |
| `Informe de Avance de Prueba.md` | Diario/semanal | Estado vs plan, desviaciones, bloqueos, riesgos nuevos, plan próximo período |
| `Informe de Prueba_IEEE 29119-3.md` | Cierre de ciclo | Resumen ejecutivo, cobertura, métricas finales, defectos y riesgo residual, lecciones aprendidas |
| `informe de defecto.md` | Al detectar un bug | Pasos, esperado/real, severidad/prioridad, evidencia, trazabilidad US/TC/Build, workaround, estado |

---

## Base de datos y trazabilidad

Estructura lógica para trazabilidad total:

```

epics → user\_stories → test\_suites → test\_cases → defects

````

- **user_stories** almacena: estado, prioridad, criterios, reglas, dependencias y **estimación** (SP, V, C, P, I, R=P×I, VCR).
- **Política VCR**: si **VCR ≥ 9** → deuda técnica (automatizar y entra en regresión). Si menor, pruebas manuales.
- **test_suites / test_cases** dan granularidad de ejecución; **defects** se enlazan a TC/US con severidad y estado.
- El archivo `01-Control/QA_Gobierno_ISTQB.xlsx` centraliza dashboard, RTM y KPIs (si lo usas como fuente de tablero).

---

## Flujo de trabajo

1) **Inicio**
- Ajustar `01_Estrategia_de_Pruebas.md`.
- Completar `plantillaMasterTestPlan.md` (alcance, riesgos y criterios).

2) **Sprint**
- Refinar historias con `plantilaUS_ISQTB.html`.
- En Planning Poker, estimar **SP, V, C, P, I** → calcular **R=P×I** y **VCR**.
- Completar `plantillaTestPlan.md` (alcance, calendario por tester, criterios).
- Actualizar Supabase con Epics/US/TS/TC/Defects.

3) **Ejecución y seguimiento**
- Ejecutar casos; registrar evidencias y defectos.
- Actualizar métricas y emitir `Informe de Avance de Prueba.md`.
- Aplicar criterios de suspensión si corresponde (ej.: stress con error-rate >25%).

4) **Cierre**
- Emitir `Informe de Prueba_IEEE 29119-3.md` con métricas finales y riesgo residual.
- Actualizar decisiones de automatización y regresión según **VCR**.

---

## Logo en documentos

- En **este README** y en cualquier `.md` dentro de `informesISQTB/`:

```html
<div align="left">
  <img src="assets/logo.png" alt="QA Shift-Left Methodology" width="240"/>
</div>
````

* En documentos ubicados dentro de una **subcarpeta** (p. ej. `01-Control/README.md`), usa:

```html
<div align="left">
  <img src="../assets/logo.png" alt="QA Shift-Left Methodology" width="240"/>
</div>
```

---

## Convenciones

* IDs: `EP-###`, `US_##`, `TS_###`, `TC-####`, `BUG-####`, `RSK-###`.
* Evidencias por caso: `evidencias/TC-0153/` (capturas, videos, logs).
* Adjuntos por defecto: `defectos/BUG-0421/`.
* Mensajes de commit con ID: `TC-0153 evidencia + RTM link`.

---

## Comandos útiles (PowerShell)

```powershell
cd "C:\Users\Epidater\Desktop\ControlQA"
tree /f
```

```powershell
cd "C:\Users\Epidater\Desktop\ControlQA"
tree /f > estructura-proyecto.txt

