# Aviation Intelligence — Daily Briefing

Dashboard diario de noticias de aviación con IA, hosteado en Vercel.

## Deploy en 5 pasos

### 1. Sube este proyecto a GitHub
```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/aviation-briefing.git
git push -u origin main
```

### 2. Importa en Vercel
- Entra a https://vercel.com/new
- Conecta tu cuenta de GitHub
- Selecciona el repositorio `aviation-briefing`
- Click en **Deploy** (sin cambiar nada)

### 3. Agrega tu API Key de Anthropic
En Vercel → tu proyecto → **Settings** → **Environment Variables**:
```
ANTHROPIC_API_KEY = sk-ant-...tu-key...
```
Luego ve a **Deployments** → click en los tres puntos del último deploy → **Redeploy**.

### 4. (Opcional) Dominio propio
En Vercel → **Settings** → **Domains** → agrega `briefing.cruzair.com`
Luego agrega el CNAME en tu DNS.

### 5. (Recomendado) Proteger con Cloudflare Access
- Entra a https://one.dash.cloudflare.com
- Access → Applications → Add an application → Self-hosted
- Domain: tu URL de Vercel o dominio propio
- Policy: permitir solo correos @cruzair.com (o los que quieras)

## Estructura
```
aviation-briefing/
├── api/
│   └── claude.js        ← proxy seguro a Anthropic (API key nunca expuesta)
├── public/
│   └── index.html       ← el dashboard
├── vercel.json          ← configuración de Vercel
└── README.md
```

## Iteraciones planificadas
- [x] v1: Base funcional con generación de briefing
- [ ] v2: Historial de briefings anteriores
- [ ] v3: Notificaciones / auto-refresh diario
- [ ] v4: Múltiples idiomas (ES/EN)
