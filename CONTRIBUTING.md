# Guía de contribución

¡Gracias por tu interés en mejorar **QA Shift-Left Methodology**! Este documento explica cómo proponer cambios de manera que se mantengan la coherencia y calidad del framework.

---

## 🎯 Principios

1. **Coherencia normativa** — toda contribución debe alinearse a los estándares **vigentes** del framework. Si una norma está retirada (ej. IEEE 829/830), no la cites.
2. **Operativo antes que teórico** — preferimos plantillas que se puedan usar tal cual antes que párrafos descriptivos.
3. **Evidencia sobre opinión** — si proponés una métrica, técnica o herramienta, citá la fuente (ISO, OWASP, NIST, ISTQB Body of Knowledge, paper, benchmark).
4. **Idioma** — contenido principal en **español**; términos técnicos en inglés cuando sea estándar (ej. *test plan*, *flaky test*, *grounding*).

---

## 🛠️ Cómo contribuir

### 1. Reportar un issue

Antes de abrir un issue, buscá si ya existe uno. Para abrir uno nuevo:
- **Bug en plantilla / HTML**: usá el template `bug_report.md`.
- **Sugerencia de contenido**: usá `feature_request.md`.
- **Actualización normativa**: usá `normative_update.md`.

### 2. Pull request

```bash
# Fork del repo, después:
git checkout -b feat/mi-mejora
# editás
git commit -m "feat(05_Guias): añade sección de chaos engineering"
git push origin feat/mi-mejora
# abrís PR contra main
```

### 3. Convenciones de commit

Usamos **Conventional Commits**:
- `feat:` nueva sección, plantilla o guía
- `fix:` corrección de error o link roto
- `docs:` mejoras en README / CONTRIBUTING
- `chore:` housekeeping (CI, dependencias)
- `refactor:` reestructura sin cambio de contenido
- `style:` cambios visuales (CSS, color, layout)

Ámbito recomendado entre paréntesis (`feat(03_Planes):`, `fix(README):`).

---

## 📐 Estándares de contenido

### Estructura mínima de una guía nueva (HTML)

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Título — QA Shift-Left Methodology</title>
</head>
<body>
  <header>
    <h1>Título de la guía</h1>
    <p><strong>QA Shift-Left Methodology · by E-Gregorio</strong>
       — Plantilla alineada a ISTQB v4 (Foundation 2023) e ISO/IEC/IEEE 29119</p>
  </header>
  <!-- contenido -->
</body>
</html>
```

### Paleta del framework

| Rol | Hex | Notas |
|---|---|---|
| Primary | `#2563EB` | Azul principal |
| Primary dark | `#1D4ED8` | Hover / énfasis |
| Primary darker | `#1E40AF` | Gradientes / fondos oscuros |
| Light bg | `#DBEAFE` | Fondos suaves |
| Accent (gold) | `#F59E0B` | Highlights, CTAs |
| Success | `#10B981` |  |
| Warning | `#F97316` |  |
| Danger | `#EF4444` |  |
| Slate-900 (dark) | `#0F172A` | Modo oscuro / fondo dark |

### Estándares aceptados (referencia rápida)

| ✅ Citar | ❌ No citar |
|---|---|
| ISO/IEC/IEEE 29119 (todas las partes) | IEEE 829 (retirado) |
| ISO/IEC/IEEE 29148:2018 | IEEE 830 (reemplazado) |
| ISTQB Foundation v4 (2023) | ISTQB v3 |
| ISO/IEC 27001:**2022** | ISO 27001:**2013** |
| ISO/IEC 25010:**2023** | ISO 25010:2011 |
| WCAG **2.2** | WCAG 2.0 / 2.1 |
| OWASP Top 10 **2021** | versiones anteriores |
| OWASP LLM Top 10 (2025) | drafts pre-2025 |
| NIST AI RMF 1.0 + Generative AI Profile | — |
| ISO/IEC TR 29119-11:2020 (testing IA) | — |

---

## ✅ Checklist antes de abrir el PR

- [ ] El contenido cita normativa **vigente** (ver tabla arriba).
- [ ] La plantilla incluye encabezado consistente con la paleta del framework.
- [ ] Si añadiste una guía nueva en `05_Guias/`, también la enlazaste desde `05_Guias/index.html`.
- [ ] Si añadiste una plantilla operativa, hay un ejemplo rellenado o pseudo-completo.
- [ ] Los enlaces relativos funcionan (probaste localmente abriendo el HTML).
- [ ] Sin secretos, tokens, ni datos personales en commits.
- [ ] Si tocaste métricas o KPIs, hay justificación con fuente.

---

## 📞 Dudas

Abrí un issue con la etiqueta `question` o contactá al mantenedor:
**E-Gregorio** — [@E-Gregorio](https://github.com/E-Gregorio)

---

*QA Shift-Left Methodology — framework operativo integrado por E-Gregorio. Referencia a estándares públicos: ISTQB v4, ISO/IEC/IEEE 29119, ISO/IEC/IEEE 29148, OWASP Top 10 2021, OWASP LLM Top 10, NIST AI RMF.*
