# Apuntes sobre Vitest

## ⚡Testing con Vitest #1 — ¿Qué es Vitest y por qué está sustituyendo a Jest?

Hoy arrancamos la serie de Testing con Vitest + TypeScript.
Empezamos entendiendo por qué Vitest se ha convertido en el estándar moderno para testear aplicaciones frontend.

🔍 ¿En qué consiste?

Vitest es un test runner moderno, creado por el equipo de Vite, que busca reemplazar a Jest ofreciendo un entorno más rápido, más ligero y con una DX muchísimo más fluida.
Comparte gran parte de la API de Jest, pero funciona usando el motor de Vite, lo que lo hace extremadamente rápido en modo watch, ideal para proyectos React, Vue, Svelte y TS modernos.

⭐ Puntos importantes

1️⃣ Velocidad incomparable, Vitest usa Vite por debajo:
→ Arranque instantáneo
→ Watch ultra rápido
→ HMR para tests

2️⃣ API familiar (90% compatible con Jest)
→ Si ya usas Jest vitest tiene la misma sintaxis.
→ Mocking con vi.fn() y vi.spyOn()
→ Snapshots disponibles

3️⃣ Integración nativa con TypeScript
→ Sin configuraciones raras, sin ts-jest, sin babel.
→ Vitest transpila TS al vuelo con esbuild.

4️⃣ Pensado para proyectos modernos
→ El ecosistema actual se mueve hacia Vite.
→ Vitest encaja de forma natural en esa arquitectura.

💡 TIP

Si vienes de Jest, empieza migrando tests sin mocks complejos.
Vitest es compatible con la mayoría, pero es mejor empezar por lo sencillo para detectar diferencias rápido.

En el siguiente post tocaremos la configuración base de Vitest en un proyecto moderno (Vite + React).

![vt-01](../../img/vitest/vt-01.jpg)