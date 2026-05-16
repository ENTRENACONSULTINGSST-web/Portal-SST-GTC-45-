# Portal SST – GTC 45 🇨🇴

Dashboard para inspecciones de Seguridad y Salud en el Trabajo (SST) según la metodología **GTC 45** de Colombia, con análisis automático de fotografías mediante **Claude AI** de Anthropic.

## ✨ Funcionalidades

- 📸 **Análisis de imágenes con IA**: Sube una foto de la inspección y Claude identifica automáticamente el factor de riesgo, probabilidad, consecuencia, intervención y acción correctiva según GTC 45.
- 📊 **Dashboard** con estadísticas y gráficas de hallazgos.
- 📋 **Gestión de hallazgos**: Crear, editar, eliminar con formulario completo GTC 45.
- 📥 **Exportar a Excel** todos los hallazgos.
- 💾 **Almacenamiento local** en el navegador (sin servidor).
- 📱 **Diseño responsive** para móvil y escritorio.

---

## 🚀 Publicar en GitHub Pages (5 minutos)

### Paso 1 — Crear repositorio

1. Ve a [github.com/new](https://github.com/new)
2. Nombre del repositorio: `portal-sst` (o el que prefieras)
3. Visibilidad: **Public**
4. Clic en **Create repository**

### Paso 2 — Subir el archivo

**Opción A – Desde la web (más fácil):**
1. En tu repositorio, clic en **"uploading an existing file"**
2. Arrastra el archivo `index.html`
3. Clic en **Commit changes**

**Opción B – Con Git:**
```bash
git init
git add index.html
git commit -m "Portal SST GTC45"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/portal-sst.git
git push -u origin main
```

### Paso 3 — Activar GitHub Pages

1. En tu repositorio: **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / **(root)**
4. Clic en **Save**
5. Espera ~2 minutos y tu app estará en:
   `https://TU_USUARIO.github.io/portal-sst/`

---

## 🔑 Configurar la API Key de Claude

1. Obtén tu clave en [console.anthropic.com](https://console.anthropic.com) → API Keys → **Create Key**
2. Abre la app en el navegador
3. Ve a **Configuración** en el menú lateral
4. Pega tu clave `sk-ant-…` y guarda

> **Seguridad:** La clave se guarda solo en tu navegador (localStorage). Nunca sale de tu dispositivo ni se envía a ningún servidor propio.

---

## 📋 Cómo usar el análisis con IA

1. Clic en **+ Nuevo Hallazgo**
2. Sube una foto (JPG/PNG, máx. 5 MB)
3. Clic en **"Analizar con Claude AI (GTC 45)"**
4. La IA completa automáticamente (campos resaltados en verde):
   - Factor de Riesgo
   - Detalle / Subtipo
   - Descripción del hallazgo
   - Nivel de Probabilidad
   - Nivel de Consecuencia
   - Medida de Intervención
   - Acción Correctiva
5. Revisa, ajusta si es necesario y guarda

---

## 🏗️ Estructura técnica

```
index.html          ← Aplicación completa (un solo archivo)
README.md           ← Esta guía
```

**Stack:** React 18 (CDN) + Recharts + SheetJS · Sin servidor · Sin build step

---

## ⚖️ Niveles de Riesgo GTC 45

| Nivel | Puntaje | Significado |
|-------|---------|-------------|
| R-I   | ≥ 600   | Alto – Acción inmediata |
| R-II  | 150–599 | Medio – Corrección urgente |
| R-III | 40–149  | Bajo – Mantener controles |
| R-IV  | < 40    | Mínimo – Revisar periódicamente |

Puntaje = Probabilidad × Consecuencia (según tablas GTC 45)
