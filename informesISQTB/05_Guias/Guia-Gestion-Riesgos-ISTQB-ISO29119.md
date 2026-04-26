<div align="left">
  <img src="../02-assets/logo.png" alt="QA Shift-Left Methodology" width="220"/><br/>
  <sub><b>QA Shift-Left Methodology · by E-Gregorio</b> — Plantilla alineada a ISTQB v4 (Foundation 2023) e ISO/IEC/IEEE 29119</sub>
</div>

# Gestión de Riesgos en QA (ISTQB/ISO 29119) — Guía práctica

> Documento listo para pegar en Confluence/Docs. Incluye **anclas de puntuación**, **matriz P×I**, **ejemplos**, y **plantillas**.

---

## 1) Concepto y objetivo

* **Riesgo**: evento/amenaza con **Probabilidad (P)** y **Impacto (I)**.
* **Nivel de riesgo** = función de P e I. Usaremos **R = P × I** (escala 1–5).
* **Pruebas basadas en el riesgo (RBT)**: priorizar **qué** probar y **con qué profundidad** para **reducir el riesgo residual**.

---

## 2) Escalas de anclaje (para puntuar iguales en todo el equipo)

> Usa estas **anclas** como “reglas del juego”. Adáptalas a tu negocio si es necesario.

### 2.1 Impacto (I)

|  I | Ancla (elige lo que aplique)                                                                     |
| -: | ------------------------------------------------------------------------------------------------ |
|  1 | Impacto menor; flujo de bajo uso; sin efecto en dinero/imagen.                                   |
|  2 | Molestia para usuarios internos; **workaround** simple; sin ingresos afectados.                  |
|  3 | Afecta módulo importante; pérdida de tiempo del usuario; pequeño costo reputacional.             |
|  4 | Afecta **proceso crítico** (p. ej., pagos); posible pérdida económica o incumplimiento menor.    |
|  5 | **Daño severo**: caída de ventas, **PII** expuesta, multas/regulación, fuerte daño reputacional. |

### 2.2 Probabilidad (P)

|  P | Ancla (elige lo que aplique)                                                                                                |
| -: | --------------------------------------------------------------------------------------------------------------------------- |
|  1 | Área estable, **sin cambios** recientes; **alta cobertura**; pocos defectos históricos.                                     |
|  2 | Cambios menores o dependencia simple; historial de baja falla.                                                              |
|  3 | Cambios moderados; **múltiples dependencias**; cobertura media (50–70%).                                                    |
|  4 | Cambios grandes; **código nuevo/modificado**; cobertura baja; historial de fallas.                                          |
|  5 | **Alta incertidumbre**: integración nueva/externa, arquitectura compleja, **ambiente inestable**, datos críticos difíciles. |

> **Indicadores útiles para P**: churn de código, nº de integraciones, cobertura de pruebas, defectos previos, experiencia del equipo, salud de ambientes/datos.

---

## 3) Matriz de riesgo y acciones

### 3.1 Clasificación por R = P × I

| Rango | Nivel       | Qué significa                            | Decisión típica                                                                                      |
| :---: | ----------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------- |
|  ≥ 20 | **Crítico** | Riesgo inaceptable sin tratamiento       | **Primero**; mayor profundidad; incluir no funcionales (perf/seguridad); **gate** de salida estricto |
| 12–19 | **Alto**    | Requiere atención prioritaria            | Técnicas adicionales y cobertura sólida; monitoreo cercano                                           |
|  6–11 | **Medio**   | Puede gestionarse con controles estándar | Cobertura adecuada + exploratoria dirigida                                                           |
|  1–5  | **Bajo**    | Riesgo menor                             | **Smoke/regresión** ligera; monitoreo pasivo                                                         |

> **Prioridad de prueba** se ordena por **R** (si empatan: Regulatorio > Dinero > Cliente clave > Plazo).

### 3.2 Tabla “acción por nivel” (resumen operativo)

| Nivel   | Técnicas/recomendaciones                                                                                                       | Criterios de salida                                 |
| ------- | ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------- |
| Crítico | Más técnicas (límite/partición, combinatoria, transiciones), **perf/seguridad**, resiliencia, revisiones estáticas adicionales | Umbrales estrictos (p. ej., P95 ≤ 3s; 0 Bloq/Altos) |
| Alto    | Pruebas negativas/extremos, integración end-to-end, **datos reales anonimizados**, health checks                               | Cobertura alta de requisitos/riesgos                |
| Medio   | Regresión núcleo, exploratoria por **charters**, accesibilidad/usabilidad si aplica                                            | Cobertura adecuada; defectos críticos = 0           |
| Bajo    | Smoke y básicos; automatización solo si ROI                                                                                    | Sin bloqueantes                                     |

---

## 4) Ejemplos prácticos

| ID   | Riesgo (tipo)                                          |  P  |  I  |  R  | Nivel   | Qué hago                                                                            |
| ---- | ------------------------------------------------------ | :-: | :-: | :-: | ------- | ----------------------------------------------------------------------------------- |
| RSK1 | **Checkout** supera **P95=3s** en hora pico (Producto) |  4  |  5  |  20 | Crítico | Pruebas de **rendimiento** tempranas, escenarios pico, profiling; **gate** P95 ≤ 3s |
| RSK2 | Validación de **pagos** falla (Producto)               |  3  |  5  |  15 | Alto    | Casuística negativa/extremos, integración PSP, monitoreo                            |
| RSK3 | **STG inestable** (Proyecto)                           |  4  |  4  |  16 | Alto    | Health checks diarios, “stop the line”, owner de ambiente                           |
| RSK4 | Nueva **UI catálogo** (cambios medianos)               |  3  |  3  |  9  | Medio   | Exploratoria por charters, regresión núcleo, accesibilidad                          |
| RSK5 | Reportes analíticos de **bajo uso**                    |  2  |  2  |  4  | Bajo    | Smoke de endpoints, validaciones básicas de datos                                   |
| RSK6 | **OAuth** con proveedor externo nuevo                  |  5  |  4  |  20 | Crítico | Flujos OAuth completos, resiliencia a timeouts, pruebas de seguridad                |

---

## 5) Registro de riesgos (plantilla mínima)

> Usa esta tabla en tu doc/Sheets; enlázala con el **RTM** y el **Plan**.

| Campo                        | Ejemplo / Guía                        |
| ---------------------------- | ------------------------------------- |
| **Riesgo\_ID**               | RSK-001                               |
| **Tipo** (Producto/Proyecto) | Producto                              |
| **Descripción**              | P95 > 3s en checkout                  |
| **P (1–5)**                  | 4                                     |
| **I (1–5)**                  | 5                                     |
| **R = P×I**                  | 20                                    |
| **Nivel**                    | Crítico                               |
| **Estrategia**               | Mitigar (o Evitar/Transferir/Aceptar) |
| **Owner**                    | QA Perf                               |
| **Estado**                   | Abierto / En curso / Cerrado          |
| **TC\_asociados**            | TS-12/TC-301, TC-304                  |
| **Notas / Contingencia**     | Gate P95 ≤ 3s; rollback si > 3s       |

**Estrategias**

* *Evitar*: cambiar alcance/diseño para que el riesgo no exista.
* *Mitigar*: bajar P o I (hardening, pruebas, feature flags, *canary*).
* *Transferir*: proveedor/seguro.
* *Aceptar*: documentar y **vigilar**; plan de contingencia.

---

## 6) Cómo se integra en tu flujo QA

1. **Identificar** riesgos (brainstorm, entrevistas, causa–efecto).
2. **Evaluar** con las **anclas** y calcular **R = P×I**.
3. **Priorizar** por R y decidir **técnicas** y **profundidad** de prueba.
4. **Vincular** riesgo→requisito→test en el **RTM**.
5. **Ejecutar y monitorear** (KPIs, defectos, resultados); actualizar **riesgo residual**.
6. **Reportar** en **Informe de Avance** y de **Cierre** (incluye residual y decisión de salida).

---

## 7) Mini-leyenda para pegar en tus documentos

> **Impacto (I)**: 1 menor · 2 molestia interna · 3 módulo importante · 4 proceso crítico/\$\$ · 5 ventas/PII/regulación.
> **Probabilidad (P)**: 1 estable/alta cobertura · 2 cambios menores · 3 moderado/dep · 4 cambios grandes/cob baja · 5 integración nueva/ambiente inestable.
> **Buckets**: `R≥20` Crítico · `12–19` Alto · `6–11` Medio · `≤5` Bajo.
> **Desempate**: Regulatorio > Dinero > Cliente clave > Plazo.

---

## 8) Checklist rápido (por sprint)

* [ ] Top 5 riesgos **identificados y puntuados** (P/I/R).
* [ ] **Plan** indica cómo el riesgo afecta **minuciosidad/alcance**.
* [ ] **RTM** enlaza RSK→US/REQ→TS/TC.
* [ ] **Ejecución** prioriza Crítico/Alto **primero**.
* [ ] **KPIs** revisados (Pass Rate, Cobertura de riesgo/req, Defectos, MTTR, DRE, NFR).
* [ ] **Riesgo residual** comunicado en Cierre y **aceptado** (o no) por PO/PM.

---

### Snippet para tu hoja de cálculo (opcional)

* **Nivel** (según R):

  ```
  =SI(R>=20,"Crítico",SI(R>=12,"Alto",SI(R>=6,"Medio","Bajo")))
  ```
* **R**:

  ```
  =P*I
  ```

---


