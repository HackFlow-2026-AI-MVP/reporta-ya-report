# Parte 2 — Web, despliegue, UX y demo

## 6. Frontend web

React, Vite, TypeScript, Tailwind, React Router y Axios. Diseño mobile-first para Chrome, con cuatro rutas: `/`, `/evidence`, `/timeline`, `/summary`. Configurar `VITE_API_URL=https://<api-railway>/api` en Vercel.

## 7. Backend

Node.js + Express, `mysql2`, dotenv, CORS y Helmet. Variables: `DATABASE_URL` (o credenciales MySQL equivalentes), `FRONTEND_URL`, `PORT`, `NODE_ENV`. `.env` queda fuera de Git. La versión MVP no cuenta con autenticación: no almacenar información real de víctimas.

## 8. Despliegue Railway

Crear servicio API y MySQL. Ejecutar `sql/schema.sql`, configurar las credenciales con referencias internas de Railway, `FRONTEND_URL` con el dominio Vercel y `NODE_ENV=production`. Validar endpoint de salud y catálogo antes de conectar el frontend. Confirmar límites/costos del plan usado.

## 9. Despliegue Vercel

Importar el repo frontend, raíz `frontend`, build `npm run build`, output `dist`. Definir `VITE_API_URL` HTTPS para producción/preview. Agregar dominio Vercel en `FRONTEND_URL` de Railway y verificar recarga directa de rutas.

## 10. UX/UI

- Paleta: tinta `#102A43`, teal `#0F766E`, fondo `#F5F7FA`; ámbar y rojo comunican prioridad.
- Tipografía: Manrope para títulos, DM Sans para interfaz, fallback de sistema.
- Pantallas: bienvenida y crear caso; formulario de evidencia; timeline con prioridades; resumen con compartir simulado.
- Flujo: crear caso → registrar evidencia → revisar cronología → generar resumen → compartir mediante Web Share o copia local.

## 11. Cronograma del equipo

| Fase (min) | Integrante A | Integrante B | Integrante C |
|---|---|---|---|
| 0–30 | Componentes/rutas frontend | MySQL, esquema y catálogo | problema, pitch y ambiente deploy |
| 30–60 | Formularios y consumo API | Casos/evidencias y validación | Integración inicial y guion demo |
| 60–90 | Timeline/resumen | API completa y healthcheck | Deploy Railway/Vercel |
| 90–120 | Responsive y errores | CORS, DB remota | Recorrido punta a punta |
| 120–150 | Congelar UI | Congelar API | Ensayo pitch/demo y contingencias |
| 150–180 | Correcciones bloqueantes | Health final | Presentación y checklist |

## 12. Pitch de 4 minutos

| Tiempo | Mensaje | Visual |
|---|---|---|
| 0:00–0:45 | Información de amenazas queda dispersa; reconstruir hechos es difícil. | Problema, sin detalles gráficos. |
| 0:45–1:15 | Reporta Ya! permite documentar hechos y ordenarlos. | Nombre y promesa. |
| 1:15–2:30 | Registrar evidencia, fecha, contexto y prioridad; ver timeline/resumen. | Demo web con datos ficticios. |
| 2:30–3:15 | Impacto: más claridad para explicar lo ocurrido. | Resumen y flujo de compartir simulado. |
| 3:15–4:00 | Stack simple; MVP y límites de seguridad honestos. | React, Express, MySQL; siguiente paso: autenticación. |

## 13. Demo de 60 segundos

0–10 s crear caso; 10–30 s ingresar evidencia ficticia; 30–45 s mostrar cronología ordenada; 45–58 s abrir resumen y señalar número/conteo; 58–60 s aclarar que compartir es simulado y el producto no sustituye a autoridades.

## 14. Preguntas del jurado

- **¿Es una denuncia oficial?** No; organiza hechos para que la persona decida qué hacer.
- **¿Garantiza validez probatoria?** No afirma autenticidad ni cadena de custodia.
- **¿Cómo protege datos?** La demo usa datos inventados; el MVP necesita autenticación y autorización antes de uso real.
- **¿Por qué no IA?** Priorizamos un flujo determinista, rápido y verificable.
- **¿Cómo validarán impacto?** Piloto futuro mediría tiempo para reconstruir hechos y claridad percibida, con protocolo ético.

## 15. Plan B

- Railway falla: reiniciar servicio y revisar health/logs sin exponer secretos; si no vuelve, mostrar capturas etiquetadas como respaldo.
- Vercel falla: presentar ejecución local si está preparada; no afirmar deploy disponible.
- Sin internet: grabación/capturas con datos ficticios.
- Backend falla: explicar el fallo y narrar el flujo sobre el respaldo, sin inventar resultados.

## 16. Checklist

- [ ] Cuatro pantallas web funcionan en Chrome móvil/escritorio.
- [ ] MySQL, API y frontend conectan con variables de entorno.
- [ ] HTTPS, CORS de Vercel y rutas de recarga confirmados.
- [ ] `.env` ignorado, secretos fuera de commits.
- [ ] Demo solo con datos ficticios; no presentar como listo para evidencia real.
- [ ] Pitch 4 min y demo 60 s ensayados; plan B accesible.

## Integración de esta parte

Commit propuesto, con autor **CODERT0PH**: `docs: add report part 2 web deployment and demo`. Rama `feature/report-parte-2` → PR a `develop`.
