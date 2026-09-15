# Plantilla-fallback — landing de servicio

Proyecto base **estático** (HTML + CSS, sin dependencias ni build) para rescatar a un alumno atascado: un coach lo despliega y personaliza en **menos de 15 minutos**.

## Desplegar (1 comando)

Desde esta carpeta, con la cuenta de Vercel **del alumno** ya autenticada:

```bash
npx vercel --prod --yes
```

Vercel detecta que es un sitio estático y lo publica. Te devuelve la URL pública. **Listo: el alumno ya tiene URL.**

## Personalizar (lo que hace que sea SU negocio)

Abre `index.html` y reemplaza todo lo que está [entre corchetes] por lo del alumno. O, mejor, pídeselo a Claude Code:

```
Esta es una landing de servicio. Personalízala para mi negocio:
soy [nombre] y ofrezco [servicio] en [ciudad]. Cambia los textos
[entre corchetes], pon mis 3 servicios reales y mis colores de marca.
Luego vuelve a publicar en Vercel.
```

Para cambiar el color de marca a mano: edita `--accent` en `styles.css`.

## Que el formulario te llegue por correo (opcional)

El formulario **ya funciona**: al enviar muestra un mensaje de gracias. Para que además te **llegue por correo**, elige una:

- **Opción A (sin código):** en `index.html`, en la etiqueta `<form>`, agrega:
  `action="https://formsubmit.co/TU-CORREO@ejemplo.com" method="POST"`
  y borra el bloque de `<script>` que intercepta el envío. La primera vez, FormSubmit te manda un correo de confirmación.
- **Opción B:** pídele a Claude Code que conecte el envío del formulario por correo.

## Archivos

- `index.html` — la página (estructura + textos a personalizar).
- `styles.css` — estilos (cambia `--accent` para tu color de marca).
- No hay `package.json` ni build: es estático a propósito, para que **nunca falle** en un rescate.
