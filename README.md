# Configuração de deploy (Vercel)

Abaixo está o trecho principal usado para deploy no Vercel. O arquivo completo está em [`vercel.json`](./vercel.json).

```json
{
  "version": 2,
  "builds": [
    {
      "src": "package.json",
      "use": "@vercel/static-build",
      "config": { "distDir": "dist" }
    }
  ],
  "routes": [
    { "src": "/api/(.*)", "dest": "/api/$1" },
    { "src": "/(.*)", "dest": "/index.html" }
  ]
}
```

> Deploy rápido: conecte o repositório no Vercel, configure:
> - Build Command: `npm run build`
> - Output Directory: `dist`
>
> Depois clique em "Deploy". super-agente-ia-web
