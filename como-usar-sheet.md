# 📊 Cómo armar tu Google Sheet de seguimiento

Tenés 2 formas: **rápida (importando el CSV)** o **manual (a mano en Sheets)**. Elegí la que te sirva.

---

## 🚀 Opción 1 — Importar el CSV (recomendada, 30 segundos)

1. Entrá a https://sheets.google.com y creá una hoja nueva en blanco.
2. En el menú: **Archivo → Importar → Subir**.
3. Arrastrá el archivo `tracking-prospectos.csv`.
4. Elegí: **"Reemplazar hoja de cálculo"** y tipo de separador **"Coma"**.
5. Clic en **Importar datos**. ¡Listo!

---

## ✅ Transformar la columna "Enviado" en checkboxes (para tachar)

Una vez importado:

1. Seleccioná la columna **A** (desde A2 hasta A21).
2. Menú: **Insertar → Casilla de verificación**.
3. Listo — los `FALSE` se convierten en checkboxes ☐ que podés tildar ☑.

---

## 🎨 Bonus: que se tache la fila cuando lo marques como enviado

Para que cuando tildes la casilla la fila se ponga gris y tachada:

1. Seleccioná el rango **A2:N21** (toda la tabla con datos).
2. Menú: **Formato → Formato condicional**.
3. En "Reglas de formato" elegí: **La fórmula personalizada es…**
4. Pegá esta fórmula:
   ```
   =$A2=TRUE
   ```
5. En estilo: color de fondo gris claro + activá la opción de **tachado** (icono de la "S" tachada).
6. Clic en **Listo**.

Ahora cada vez que tildes la casilla, esa fila entera se ve tachada y gris 🎉

---

## 📋 Qué significa cada columna

| Columna | Qué va |
|---|---|
| **Enviado** | ☑ cuando ya mandaste el mensaje |
| **Negocio** | Nombre del local |
| **Rubro** | Plomería, brunch, peluquería, etc. |
| **Zona** | Barrio o ciudad (útil para SEO local) |
| **Contacto (nombre)** | Nombre del dueño/a si lo sabés |
| **Canal** | WhatsApp / Instagram / Email |
| **Link Google/IG** | URL de la ficha de Google o Instagram (referencia rápida) |
| **Fecha envío** | Día que mandaste el primer mensaje |
| **Respondió** | ☐ / ☑ — si te contestaron |
| **Llamada agendada** | Día y hora de la llamada de 10 min |
| **Preview enviada** | ☐ / ☑ — si ya le mandaste la preview gratis |
| **Cerrado** | ☐ / ☑ — si cerraste venta |
| **Monto** | Precio final acordado |
| **Notas** | Cualquier cosa que te sirva recordar |

> 💡 Si querés, también podés convertir en checkboxes las columnas **Respondió**, **Preview enviada** y **Cerrado** (mismo paso que antes).

---

## 📈 Bonus extra: contador de avance

En una celda vacía (por ejemplo P1) pegá:

```
=CONTAR.SI(A2:A21;TRUE)&" / 20 enviados"
```

Y en P2:

```
=CONTAR.SI(L2:L21;TRUE)&" / 20 cerrados"
```

Así vas viendo el progreso de un vistazo 👀
