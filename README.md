# DREAMERS-VC — Portal de Inversores

Portal privado de seguimiento de inversiones para **Dreamers Startup Ventures**.

🌐 **Live:** [joseantonioborge.github.io/DREAMERS-VC](https://joseantonioborge.github.io/DREAMERS-VC)

---

## Arquitectura

```
DREAMERS-VC (este repo — GitHub Pages)
└── index.html          ← Portal completo (SPA, ~500KB)

angelclub-api (repo separado — Vercel Serverless)
├── api/
│   ├── auth.js         ← POST login
│   ├── startups.js     ← GET/PUT/POST startups
│   ├── ratings.js      ← valoraciones inversores
│   ├── access_logs.js  ← registro de accesos
│   └── health.js       ← diagnóstico DB
├── lib/
│   ├── mongo.js        ← conexión MongoDB Atlas
│   └── auth.js         ← validación API keys
└── scripts/seed.js     ← poblar DB inicial
```

---

## Portfolio actual

| Startup | Sector | Capital Inv. | Equity | Estado |
|---|---|---|---|---|
| Oncoheroes Biosciences | Biotech | $385,000 | 1.87% | Activa |
| Astrocyte Pharma | Pharma | $350,000 | 1.74% | Activa |
| Elicio Therapeutics | Therapeutics | $546,146 | 0.30% | Nasdaq (ELTX) |

**Total invertido:** $1,281,146

---

## Stack técnico

| Capa | Tecnología |
|---|---|
| Frontend | HTML/CSS/JS vanilla (SPA) |
| Hosting | GitHub Pages |
| Backend | Vercel Serverless Functions (Node.js) |
| Base de datos | MongoDB Atlas (cluster Dreamers) |
| Datos live | TradingView Widget + Yahoo Finance API |

---

## Despliegue

### Portal (este repo)
```bash
# Editar index.html y hacer commit/push a main
# GitHub Pages despliega automáticamente
git add index.html
git commit -m "feat: descripción del cambio"
git push origin main
```

### API (repo angelclub-api)
```bash
# Variables de entorno en Vercel:
# MONGODB_URI     — MongoDB Atlas connection string
# API_KEY_ADMIN   — clave admin (openssl rand -hex 32)
# API_KEY_INVESTOR — clave inversores
```

---

## Versiones

| Versión | Descripción |
|---|---|
| v3.29 | Capital Elicio actualizado a $546,146 · desglose tickets · Nº acciones |
| v3.27 | Backup anterior |
| v3.19 | Primera versión estable con API |

---

## Estructura de carpetas locales

```
Desktop/DREAMERS-VC/
├── portal/             ← clon de este repo (GitHub Pages)
│   └── index.html
├── api/                ← clon de angelclub-api (Vercel)
│   ├── api/
│   ├── lib/
│   └── scripts/
└── backup/             ← snapshots históricos del portal
    ├── index_v3.19.html
    └── index_v3.27.html
```
