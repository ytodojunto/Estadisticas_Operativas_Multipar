# Estadísticas MULTIPAR — sitio interactivo (2025-2026)

Este es un sitio estático (HTML + JS, sin backend) con las estadísticas de despachos de MULTIPAR: despachos, CF, maniobras, francos cubiertos, reciprocidad con empresas colegas, por práctico/agencia/canal, con selector de año (2025 completo, 2026 hasta agosto) y filtro por mes.

## Cómo publicarlo en GitHub Pages (sin escribir código)

1. Entrá a github.com, iniciá sesión (o creá una cuenta gratuita) y hacé clic en **New repository**. Ponele un nombre, por ejemplo `multipar-estadisticas`, y creálo (puede ser público o privado — si es privado, GitHub Pages solo funciona en planes pagos; si lo compartís con los socios colegas conviene público, o "unlisted" agregándolos como colaboradores).
2. Dentro del repo recién creado, hacé clic en **Add file → Upload files**.
3. Arrastrá los 4 archivos de esta carpeta: `index.html`, `data.json`, `data_2026.json` y este `README.md`. Hacé clic en **Commit changes**.
4. Andá a **Settings → Pages** (menú de la izquierda).
5. En "Build and deployment", elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guardá.
6. Esperá un minuto y GitHub te va a mostrar la URL pública, algo como `https://<tu-usuario>.github.io/multipar-estadisticas/`. Esa es la que le pasás a los socios colegas.

## Acceso con usuario y contraseña

El sitio pide usuario y contraseña antes de mostrar el contenido (usuario `Multipar`, la contraseña que definiste). **Importante:** esto NO es una seguridad real — es un sitio estático público en GitHub Pages, así que cualquiera que sepa programar puede ver el código fuente (Ctrl+U en el navegador) y encontrar la forma de entrar sin la clave. Sirve para que un visitante casual o un buscador no vea los datos por accidente, pero no para proteger información realmente sensible.

Si en algún momento necesitás protección de verdad (que solo entren las personas que vos autorizás, sin poder saltearla), las opciones son:
- Repo **privado** + GitHub Pages con "Enforce access control" (requiere plan GitHub Pro/Team, y que cada socio colega tenga su propia cuenta de GitHub agregada como colaborador).
- Otro hosting con autenticación real, como Netlify o Cloudflare Pages con protección por contraseña a nivel de servidor.

Para uso interno entre socios de confianza, con el link sin publicitar y el login que ya tiene, alcanza.

## Actualizar mes a mes / agregar un año nuevo

Cuando tengas un mes nuevo cargado (por ejemplo septiembre 2026), avisame y te regenero el `data_2026.json` — solo hay que subir ese archivo de nuevo al repo (Upload files, reemplaza el que ya existe) y el sitio se actualiza solo, no hay que tocar `index.html`.

El sitio tiene un selector de año arriba a la izquierda (chips "2025" / "2026", ambos activos). Cuando arranque 2027, avisame y agrego el chip nuevo.

## Qué muestra

- Evolución mensual de despachos y facturación (CF).
- Ranking de prácticos (despachos, CF total, CF promedio, maniobras, francos cubiertos, cuántas veces cubrieron a una empresa colega).
- Despachos y CF por agencia propia, y por canal de navegación.
- Reciprocidad con empresas colegas: a quién le cubrimos despachos y quién nos cubrió a nosotros.
- Una sección de "cosas para confirmar" con las inconsistencias de datos detectadas en las planillas (ver detalle abajo).

## Metodología

El color de fondo de las celdas en las planillas mensuales originales se usó para reconstruir los eventos:
violeta = maniobra (crédito al práctico 2 del par), azul = demora, amarillo = cubierto en franco,
verde = cedido a colega, oro = cubrimos a colega, rojo = cancelado.

Ver `claude/metodologia_estadisticas_despachos.md` y `claude/empresas_colegas_y_agencias.md` en el Proyecto de Claude para el detalle completo.
