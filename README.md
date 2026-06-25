# Monitor de Base de Soya · Chicago vs Bolivia

Dashboard interactivo de precios históricos mensuales de soya — CBOT Chicago, exportación FOB boliviana y precio local Santa Cruz de la Sierra — con base, correlación y editor de datos integrado.

**Ver en vivo →** `https://[tu-usuario].github.io/soybean-basis`

---

## Qué muestra

| Sección | Contenido |
|---|---|
| 01 Historial de precios | Serie mensual 2000–2026 en $/TM y ¢/bu |
| 02 La base | Bolivia − Chicago: prima o descuento histórico |
| 03 Correlación | Tabla de Pearson (niveles y cambios MaM) + correlación móvil 12 meses |
| 04 Comovimiento | Diagramas de dispersión Chicago vs exportación y local |
| 05 Lectura | Seis conclusiones analíticas clave |
| 06 Editor de datos | Agregar, editar, exportar e importar datos sin tocar el código |

## Unidades

El selector arriba a la derecha cambia todos los gráficos simultáneamente entre:
- **$/TM** — US dólares por tonelada métrica
- **¢/bu** — US centavos por bushel (conversión: 1 TM = 36.744 bu)

## Fuentes

| Serie | Fuente |
|---|---|
| Chicago (CBOT) | CAO SIPREM — 07.2 Precios Internacionales / CBOT vía INE |
| Bolivia exportación FOB | CAO SIPREM — 07.3 Precios de Exportación (habas de soya) |
| Bolivia local (Santa Cruz) | CAO SIPREM — 07 Precios Agroindustriales (grano de soya en planta) |

Cobertura: **2000–2026** · Último dato: **Mayo 2026**

## Cómo actualizar los datos

### Opción A — Editor integrado (sin tocar código)
1. Abrir el dashboard en el navegador
2. Ir a la sección **Editor de datos**
3. Clic en **＋ Agregar mes** → ingresar año, mes y los tres precios en $/TM
4. Clic en **↓ Exportar JSON** para guardar el archivo actualizado
5. Subir el nuevo `index.html` al repositorio (ver abajo)

### Opción B — Editar directamente el JSON en el archivo
Los datos están embebidos en `index.html` como `const SEED = {...}`.
Buscar el año/mes correspondiente y editar los campos `chicago_tm`, `export_tm`, `local_tm`.
Los valores `_bu` se recalculan automáticamente en el navegador.

### Cómo subir la actualización a GitHub
1. Ir a [github.com](https://github.com) → tu repositorio `soybean-basis`
2. Clic en `index.html` → ícono del lápiz (editar) → pegar el contenido nuevo → **Commit changes**
3. El sitio se actualiza en ~1 minuto

## Estructura del repositorio

```
soybean-basis/
├── index.html      ← dashboard completo (HTML + CSS + JS + datos embebidos)
└── README.md       ← este archivo
```

## Tecnologías

- **Chart.js 4.4.1** — gráficos (CDN, sin instalación)
- **Google Fonts** — Playfair Display + Inter (CDN)
- Sin framework, sin build step, sin dependencias npm

---

*Elaborado para AMG – Aviation Marketing Group · Santa Cruz de la Sierra, Bolivia*  
*Datos: CAO – Cámara Agropecuaria del Oriente (SIPREM)*
