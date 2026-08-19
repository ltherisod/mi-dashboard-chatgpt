# Dashboard de gastos con ChatGPT 🤖

Un dashboard que convierte un CSV de tres columnas en totales, gráficos y filtros. Un solo archivo HTML, sin librerías, sin instalación y sin servidor: se abre en el navegador y funciona.

**[Ver el dashboard](https://ltherisod.github.io/mi-dashboard-chatgpt/)** 

Hecho en el workshop **"De tu planilla a un dashboard"** de Coderhouse, íntegramente con prompts en lenguaje natural.

[PPTS](https://docs.google.com/presentation/d/1Ec68O_UqjIba7l6TDteBqxZgxwNveXz-/edit?usp=sharing&ouid=113418615753555271633&rtpof=true&sd=true)

---

## Qué hace

- **Tres totales arriba:** suma, cantidad de registros y promedio
- **Gráfico de barras** con el total por categoría, ordenado de mayor a menor
- **Filtros** por categoría y por rango de fechas: todo se recalcula al instante, sin botón de "aplicar"
- **Tabla de detalle** ordenable haciendo clic en cada encabezado
- **Carga de archivos:** elegí tu CSV o arrastralo sobre la página

---

## Cómo usarlo

1. Entrá al link de arriba (o abrí `index.html` con doble clic si lo descargaste).
2. Arrastrá tu archivo CSV sobre la página, o usá el botón **Elegir archivo CSV**.
3. Filtrá por categoría o por fechas. Los números y el gráfico se actualizan solos.

### Formato del CSV

Tres columnas, con la primera fila de encabezados:

```csv
fecha,categoria,monto
2026-05-08,Salud,26000
2026-05-09,Comida,22700
2026-06-02,Servicios,31200
```

| Columna | Qué es | Formato |
|---|---|---|
| `fecha` | Cuándo pasó | `AAAA-MM-DD` |
| `categoria` | Texto que se repite, sirve para agrupar | Cualquiera |
| `monto` | El número que se suma | Entero, sin símbolos |

Acepta coma o punto y coma como separador, y montos con puntos de miles. Las filas mal formadas se saltean sin romper el resto.

> El nombre de las columnas es lo único que cambia según el caso: **horas de trabajo** (fecha, proyecto, horas), **tickets** (fecha, tipo, cantidad), **ventas** (fecha, producto, importe). El método es el mismo.

---

## Privacidad

El archivo se lee **en tu propio navegador**. No hay servidor, no hay base de datos y tus datos no se suben a ningún lado.

⚠️ Si dejás datos escritos dentro del `index.html` y el repositorio es público, esos datos quedan visibles para cualquiera. Para información sensible, publicá el dashboard vacío y cargá el CSV desde tu computadora cada vez.

---

## Publicarlo en GitHub Pages

1. Subí el archivo al repositorio con el nombre exacto **`index.html`**, en minúscula.
2. Andá a **Settings → Pages**.
3. En *Branch* elegí `main` y la carpeta `/ (root)`. Guardá.
4. Esperá un minuto y entrá a `https://tuusuario.github.io/nombre-del-repo`.

**¿Te da 404?** Casi siempre es una de tres cosas: el archivo no se llama `index.html`, todavía no pasó el minuto de publicación, o el repositorio es privado.

---

## Cómo está hecho

HTML, CSS y JavaScript en un solo archivo. Sin frameworks, sin CDN y sin dependencias: por eso funciona sin internet y no se rompe con el tiempo.

El código lo escribió una IA a partir de una secuencia de prompts en castellano. La lógica es siempre la misma —**leer** el CSV, **calcular** los totales, **dibujar** las barras— y cada prompt fue agregando una capa sobre la anterior.

---

## Adaptarlo

Podés pedirle a cualquier IA (Claude, ChatGPT, Gemini) que lo modifique. Pegá el contenido de `index.html` y describí el cambio que querés, siempre uno por vez:

```
Problema: [qué ves mal]. Esperaba: [qué querías].
Arreglá solo eso, sin cambiar el resto del diseño ni del código.
```

Algunas ideas: exportar el CSV filtrado, comparar contra el período anterior, marcar un presupuesto máximo en el gráfico.

---

## Licencia

MIT. Usalo, modificalo y compartilo libremente.
