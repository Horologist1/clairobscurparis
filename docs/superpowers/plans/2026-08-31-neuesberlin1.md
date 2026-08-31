# Neues Berlin Nº 1 (neuesberlin1.html) — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Crear `neuesberlin1.html` — primer número del periódico berlinés *Neues Berlin* (Montag, 18. November 1907), solo en español — y enlazarlo con todo el sitio, commiteando además el dossier `berlin.html` y sus retratos.

**Architecture:** Página estática HTML autocontenida (CSS/JS inline), copiada del andamio de `noticias34.html` y des-bilingüizada (sin toggle, sin pares `.lang-fr`/`.lang-es`). Cabecera fraktur. Enlace «Prensa de Berlín» insertado por script en las 33 ediciones parisinas usando el ancla `    <nav class="date-navigation">` (verificada exacta y única en los 33 archivos). Spec: `docs/superpowers/specs/2026-08-31-neuesberlin1-design.md`.

**Tech Stack:** HTML/CSS estático, Google Fonts (`@import`), PowerShell para la propagación de enlaces, imágenes PD de Wikimedia (Higgsfield CLI como respaldo).

**Contexto del worktree:** se trabaja en `C:\Users\Usuario\Downloads\clairobscurparis\.claude\worktrees\neuesberlin1` (rama `worktree-neuesberlin1`). `berlin.html` y `personajes_imagenes\berlin\` NO están en el worktree (sin trackear en el checkout padre `C:\Users\Usuario\Downloads\clairobscurparis`): la Task 1 los copia.

**Registro de la prosa (aplica a TODAS las tareas de contenido):** *Neues Berlin* es un diario orgulloso y semi-oficial, cercano al trono. Lo inquietante se reporta con entusiasmo patriótico sin notar que es inquietante ("genio logístico", "curiosidad administrativa"). Nada de ironía republicana. La única voz mordaz es «Eine Berliner Schnauze» (cotilleo). Lo sobrenatural jamás se confirma ni se "nota". Español de registro periodístico de época, florido pero sobrio.

---

### Task 1: Copiar el dossier de Berlín al worktree y commitear

**Files:**
- Create (copia): `berlin.html`, `personajes_imagenes/berlin/` (29 archivos)

- [ ] **Step 1: Copiar desde el checkout padre**

```bash
cd "C:/Users/Usuario/Downloads/clairobscurparis/.claude/worktrees/neuesberlin1"
cp "C:/Users/Usuario/Downloads/clairobscurparis/berlin.html" .
cp -r "C:/Users/Usuario/Downloads/clairobscurparis/personajes_imagenes/berlin" personajes_imagenes/
```

- [ ] **Step 2: Verificar**

Run: `ls personajes_imagenes/berlin | wc -l && ls berlin.html`
Expected: `29` y `berlin.html`

- [ ] **Step 3: Commit**

```bash
git add berlin.html personajes_imagenes/berlin
git commit -m "berlin: dossier Kaiserzeit 1907 y 29 retratos de personajes"
```

---

### Task 2: Andamio de neuesberlin1.html (cabecera, fuentes, sin toggle, nav propia)

**Files:**
- Create: `neuesberlin1.html` (copia de `noticias34.html`)

- [ ] **Step 1: Copiar el andamio**

```bash
cp noticias34.html neuesberlin1.html
```

- [ ] **Step 2: Título y fuente fraktur**

En `neuesberlin1.html`, cambiar el `<title>` (línea ~6):

```html
    <title>Neues Berlin — Kaiserzeit</title>
```

Y añadir UnifrakturMaguntia al `@import` (línea ~8), reemplazando la línea entera por:

```css
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700;900&family=Crimson+Text:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=UnifrakturMaguntia&display=swap');
```

- [ ] **Step 3: Eliminar la maquinaria de idioma**

1. Borrar el bloque CSS de idioma (líneas ~492-507): las reglas `.lang-es { display: none; }`, `body.spanish .lang-fr`, `body.spanish .lang-es` y `body.spanish .lang-es.inline`.
2. Borrar del `<header>` el bloque del botón:

```html
            <div class="translate-button-container">
                <button class="translate-button" onclick="toggleLanguage()" title="Traducir / Translate">🔍</button>
            </div>
```

3. Borrar del `<script>` final la función `toggleLanguage()` completa y el `window.addEventListener('DOMContentLoaded', …)` que lee `newspaperLanguage`. Conservar el resto del script (modal de imágenes).

- [ ] **Step 4: Reescribir la cabecera del periódico**

Reemplazar dentro de `<header class="newspaper-header">` el título, subtítulo y las dos líneas de fecha por:

```html
            <h1 class="newspaper-title" style="font-family: 'UnifrakturMaguntia', 'Playfair Display', serif;">Neues Berlin</h1>
            <p class="newspaper-subtitle">Nachrichten aus der Reichshauptstadt · Noticias de la Capital Imperial</p>
```

y (tras la línea ornamental de rombos):

```html
            <p class="newspaper-date">Montag, 18. November 1907 — Preis: 10 Pfennig</p>
```

(Se conservan las `ornamental-line` tal cual.)

- [ ] **Step 5: Reemplazar la barra lateral por la navegación berlinesa**

Sustituir TODO el bloque `<nav class="date-navigation">…</nav>` (en noticias34 ocupa ~las líneas 728-931) por:

```html
    <nav class="date-navigation">
        <h3>Ausgaben · Ediciones</h3>
        <ul class="date-list">
            <li class="date-item">
                <a href="neuesberlin1.html" class="date-link active">
                    <span>18. November 1907</span>
                </a>
            </li>
            <li class="date-item">
                <a href="berlin.html" class="date-link">
                    <span>✠ Dossier: Berlín</span>
                </a>
            </li>
            <li class="date-item">
                <a href="noticias34.html" class="date-link">
                    <span>Presse de Paris · Prensa de París</span>
                </a>
            </li>
            <li class="date-item">
                <a href="index.html" class="date-link">
                    <span>Índice</span>
                </a>
            </li>
        </ul>
    </nav>
```

- [ ] **Step 6: Verificar y commit**

Run: `grep -c "toggleLanguage\|translate-button\|newspaperLanguage" neuesberlin1.html`
Expected: `0`

```bash
git add neuesberlin1.html
git commit -m "neuesberlin1: andamio (cabecera fraktur, solo español, nav berlinesa)"
```

Nota: el cuerpo aún contiene los artículos parisinos bilingües; se reemplazan en las Tasks 4-7.

---

### Task 3: Imágenes de dominio público

**Files:**
- Create: `news/berlin_desfile_brandeburgo.jpg`, `news/berlin_pariser_platz.jpg`, `news/berlin_ubahn.jpg`, `news/paris_boulevard_carta.jpg`

- [ ] **Step 1: Buscar y descargar 4 fotos PD frescas (no recicladas del repo)**

Objetivos y consultas sugeridas (WebSearch + Wikimedia Commons; descargar con `curl -L "https://commons.wikimedia.org/wiki/Special:FilePath/<NOMBRE DE ARCHIVO>?width=1600" -o news/<destino>`):

1. **Desfile (portada, 16:9):** desfile militar ante la Puerta de Brandeburgo / Unter den Linden. Consultas: `Brandenburger Tor Einzug Truppen 1871 photograph`, `Parade Unter den Linden Kaiser photograph 1900s`. → `news/berlin_desfile_brandeburgo.jpg`
2. **Senado (secundario, 5:4):** Pariser Platz / Academia de las Artes hacia 1900. Consulta: `Pariser Platz Berlin 1900 photograph`. → `news/berlin_pariser_platz.jpg`
3. **Elektropolis (secundario, 5:4):** U-Bahn/Hochbahn de Berlín 1902-1907 o nave industrial. Consultas: `Hochbahnhof Bülowstraße 1903`, `Berlin Hochbahn 1902 photograph`. → `news/berlin_ubahn.jpg`
4. **Carta de París (sidebar, vertical 3:4):** calle parisina con multitud, ~1900 (NO reutilizar `arc_triomphe_foule.jpg` ni nada del repo). Consultas: `Boulevard des Italiens 1900 photograph`, `Paris street crowd 1905 agence Rol`. → `news/paris_boulevard_carta.jpg`

- [ ] **Step 2: Verificar CADA imagen viéndola**

Abrir cada archivo con la herramienta Read (visualización) y comprobar: es una foto de época real, sujeto reconocible, sin marcas de agua. Si alguna no aparece o no encaja, generarla con el **Higgsfield CLI** (skill `higgsfield-generate`), estilo fotografía de época en blanco y negro.

- [ ] **Step 3: Commit**

```bash
git add news/berlin_desfile_brandeburgo.jpg news/berlin_pariser_platz.jpg news/berlin_ubahn.jpg news/paris_boulevard_carta.jpg
git commit -m "neuesberlin1: imagenes PD (desfile, Pariser Platz, U-Bahn, Paris)"
```

---

### Task 4: Portada — «La victoria desfila bajo los Tilos»

**Files:**
- Modify: `neuesberlin1.html` (bloque `<article class="main-article">`)

- [ ] **Step 1: Reescribir el artículo principal**

Sustituir el contenido del `<article class="main-article">` copiado de noticias34: conservar la estructura de etiquetas/clases, borrar todos los elementos `.lang-fr` y quitar las clases `lang-es` de los que queden (marcado plano en español). Titular, firma e imagen:

- Titular: **«La victoria desfila bajo los Tilos»** · antetítulo o subtítulo: *Der Siegeszug · El desfile de la victoria*
- Firma: **K. Hoffmann** (crónica mayor, solemne)
- Imagen:

```html
                    <div class="article-image">
                        <img src="news/berlin_desfile_brandeburgo.jpg" alt="Desfile militar ante la Puerta de Brandeburgo — fotografía de época (dominio público)." class="placeholder" style="object-position: center 40%;">
                    </div>
```

(Ajustar `object-position` tras ver la foto real.)

Prosa: 5-6 párrafos con estos beats, en este orden:
1. Las tropas vuelven del frente austríaco y cruzan la Puerta de Brandeburgo; Unter den Linden engalanada; multitud, banderas, la Cuadriga arriba "que ya volvió una vez de París".
2. El Káiser preside con uniforme de gala; revista a los regimientos; frase atribuida sobre el Imperio como obra.
3. **El Kronprinz reaparece en público con su cicatriz** — primera gran aparición desde "la noche de París de hace dos años"; la multitud lo aclama más fuerte que a nadie; él saluda "con una sonrisa que no llega a los ojos". No nombrar a los magnicidas más que como "los asesinos de aquella noche".
4. Elogio del "genio logístico" del Gran Estado Mayor y de Moltke: la campaña ganada "antes de librarse".
5. Detalles orgullosos-inquietantes (sin notar que lo son): regimientos llegados por líneas que no figuran en los horarios civiles; la tribuna de honor sin los Maestros Arquitectos ("ocupados, se nos dice, en obras de mayor calado"); una marcha militar nueva que las bandas ejecutaron a la perfección "sin que conste ensayo".
6. Cierre: Berlín celebra; Europa toma nota; "la paz, como el desfile, es cuestión de compás".

- [ ] **Step 2: Verificar en navegador**

Abrir `neuesberlin1.html` en el navegador (o Playwright) y comprobar que la portada renderiza con imagen y sin restos de francés.

- [ ] **Step 3: Commit**

```bash
git add neuesberlin1.html
git commit -m "neuesberlin1: portada del desfile de la victoria"
```

---

### Task 5: Secundarios — «El Senado reparte laureles» y «Elektropolis no duerme» + Gesellschafts-Chronik

**Files:**
- Modify: `neuesberlin1.html` (bloque `<div class="secondary-articles">`)

- [ ] **Step 1: Reescribir el secundario 1 — «El Senado reparte laureles»**

Firma: **F. Weber** (política artística, cortesano). Imagen: `news/berlin_pariser_platz.jpg` (mismo patrón `.article-image`). Prosa: 4 párrafos:
1. Sesión de gala en el palacio de la Pariser Platz tras la victoria; medallas y encargos conmemorativos; von Werner preside "con la profesionalidad absoluta de la lealtad".
2. Encargo estrella: un ciclo pictórico de la campaña de otoño; se da por hecho que la versión de von Werner "será la que recuerde el Imperio".
3. Un dardo elegante de Liebermann desde el asiento consultivo (una sola frase, ingeniosa, sobre pintar victorias "del natural o de memoria"); risas incómodas.
4. Ausencias: Käthe Kollwitz, "no invitada, una vez más"; los dos asientos consultivos de los Escritores, presentes y "tan callados que se les oía". Cerrar sin editorializar.

- [ ] **Step 2: Reescribir el secundario 2 — «Elektropolis no duerme»**

Firma: **E. Krüger** (técnica/industria, entusiasta). Imagen: `news/berlin_ubahn.jpg`. Prosa: 4 párrafos:
1. Nuevo tramo del U-Bahn inaugurado/en obras; cifras de crecimiento; "cinco años más joven que el Metro de París, y ya más puntual".
2. La nave de turbinas de la AEG y Peter Behrens: "la fábrica es la catedral del siglo"; turbinas "dibujadas como si respiraran" (citado como elogio estético).
3. Las Bauhütten como contratistas de los túneles, mencionadas con respeto gremial; "el contrato, custodiado en la Pariser Platz, con sus anexos de rigor".
4. Curiosidad administrativa (tono de servicio al lector): una estación "que no figura en el plano de bolsillo, por razones de servicio"; los maquinistas del último turno "tienen instrucciones precisas". Cerrar con orgullo eléctrico.

- [ ] **Step 3: Añadir la Gesellschafts-Chronik**

Añadir un tercer bloque de artículo tras los dos secundarios, clonando la estructura de un secundario pero SIN imagen. Título: **«Gesellschafts-Chronik · Crónica de Sociedad»**. Firma: **«Eine Berliner Schnauze»** (única voz mordaz del número). Prosa: 3-4 párrafos:
1. La inauguración del Hotel Adlon: "media Europa coronada" en el vestíbulo; el Káiser encantado de que Berlín "por fin sepa ser lujosa"; alguna pulla a un príncipe menor que confundió el ascensor con un gabinete.
2. La princesa **Cecilia de Mecklemburgo** como nueva estrella de la corte; los salones se disputan su presencia; el Kronprinz "sonríe más desde el desfile, lo cual, tratándose de él, es casi una proclama".
3. **Tilla Durieux** y sus retratos: colecciona sus propias efigies "porque le gusta saber dónde viven todas sus versiones"; anécdota de un pintor que se negó a venderle la suya.
4. Cierre Schnauze: mordaz con todos, prudente solo con el Káiser ("por respeto, naturalmente, y por la Oficina de Lectura").

- [ ] **Step 4: Verificar y commit**

Comprobar en navegador que los tres bloques renderizan. Luego:

```bash
git add neuesberlin1.html
git commit -m "neuesberlin1: Senado, Elektropolis y Gesellschafts-Chronik"
```

---

### Task 6: Aside — «Carta de París» y «Kurznachrichten · Breves»

**Files:**
- Modify: `neuesberlin1.html` (primeros dos `<article class="sidebar-article">` del `<aside class="right-column">`)

- [ ] **Step 1: Reescribir el primer sidebar-article — «Carta de París»**

Encabezado: **«Brief aus Paris · Carta de París»** · "de nuestro corresponsal" · Firma: **H. Vogel**. Imagen vertical:

```html
                    <div class="vertical-image sidebar-portrait" style="margin-bottom: 1em;">
                        <img src="news/paris_boulevard_carta.jpg" alt="Bulevar parisino hacia 1900 — fotografía de época (dominio público)." class="placeholder" style="object-position: center 30%;">
                    </div>
```

Prosa: 4-5 párrafos (la ventana del jugador alemán a París):
1. París en vísperas electorales; los quioscos arden; "la República discute quién manda; Berlín ya lo sabe" (sorna suave).
2. La marcha orleanista bajo el Arco de Triunfo: música, cuadros vivos, emoción fabricada; el corresponsal nota que "el arte francés ha descubierto la instrucción de tiro".
3. Las tres candidaturas: "un rey, un constructor, una artesana" (Orleans/Maurras, Charles Garnier, Anaïs Vernier) — explicadas en dos frases cada una, con distancia berlinesa.
4. Los refugiados españoles en las estaciones del Mediodía; Francia "acoge con una mano y cuenta con la otra".
5. Nota fría final: el corresponsal evita cierta calle cerca del parque Monceau "desde la noche de noviembre de hace dos años". Sin más detalle.

- [ ] **Step 2: Reescribir el segundo sidebar-article — Breves**

Título: **«Kurznachrichten · Breves»** (mismo patrón de `<h3 class="secondary-title" style="…">` que el andamio, sin par de idioma). Ítems `<p><strong>• Título:</strong> texto…</p>`, 2-3 frases cada uno:
1. **• Múnich:** fundación del Deutscher Werkbund — "el arte entra en nómina de la industria, y la industria en el gusto de la nación".
2. **• Bayreuth:** Cosima Wagner reitera que *Parsifal* no saldrá del Festspielhaus; "las razones de la casa son de la casa".
3. **• Essen:** los nuevos aceros de Krupp superan todas las pruebas "con resultados que la casa no publica, por modestia industrial".
4. **• Berlín:** demostración del Biophon de Messter ante oficiales; "las imágenes hablan; algún cantante, dicen los presentes, siguió articulando tras el corte".
5. **• Dresde:** clausurada una exposición del grupo Die Brücke tras quejas vecinales "relativas a los colores"; los jóvenes prometen volver "con puentes más largos".

- [ ] **Step 3: Commit**

```bash
git add neuesberlin1.html
git commit -m "neuesberlin1: Carta de Paris y Kurznachrichten"
```

---

### Task 7: Aside — Sumario y «Figuras de la temporada»

**Files:**
- Modify: `neuesberlin1.html` (tercer `<article class="sidebar-article">` y bloque nuevo al final del aside)

- [ ] **Step 1: Reescribir el Sumario**

Título: **«Inhalt · Sumario»**. Entradas `<p><strong>Título:</strong><br>Firma</p>`:

```
La victoria desfila bajo los Tilos: K. Hoffmann
El Senado reparte laureles: F. Weber
Elektropolis no duerme: E. Krüger
Gesellschafts-Chronik: Eine Berliner Schnauze
Carta de París: H. Vogel
```

- [ ] **Step 2: Añadir «Figuras de la temporada»**

Nuevo `<article class="sidebar-article">` al final del aside, con el marcado de fichas de los «Solteros» (el CSS `.gossip-*` ya está en el andamio):

```html
                <article class="sidebar-article">
                    <h3 class="sidebar-title">Gestalten der Saison · Figuras de la Temporada</h3>
                    <ul class="gossip-list">
                        <li class="gossip-item">
                            <div class="gossip-photo">
                                <img src="personajes_imagenes/berlin/max_reinhardt.jpg" alt="Max Reinhardt" onclick="openImageModal(this.src, this.alt)">
                            </div>
                            <div class="gossip-info">
                                <div class="gossip-name">Max Reinhardt</div>
                                <div class="gossip-text">…</div>
                            </div>
                        </li>
                        <!-- + 3 fichas más con el mismo patrón -->
                    </ul>
                </article>
```

Las 4 fichas (retratos de `personajes_imagenes/berlin/`, 2-3 frases cada una, tono de crónica social admirativa):
1. **Max Reinhardt** (`max_reinhardt.jpg`) — el mago del Deutsches Theater; sus Kammerspiele agotan localidades; "dice que el teatro no representa mundos: los fabrica".
2. **Richard Strauss** (`richard_strauss.jpg`) — el emperador secreto de la música; entre la Ópera Real y sus negocios, "el único Maestro al que el Káiser escucha dos veces".
3. **Tilla Durieux** (`tilla_durieux.jpg`) — la primera actriz de la capital; los pintores hacen cola; ella elige.
4. **Käthe Kollwitz** (`kathe_kollwitz.jpg`) — la ausente más comentada de la temporada; no pisa los salones y los salones no hablan de otra cosa; "sigue grabando".

- [ ] **Step 3: Verificación de des-bilingüización completa**

Run: `grep -c "lang-fr\|lang-es" neuesberlin1.html`
Expected: `0`

- [ ] **Step 4: Commit**

```bash
git add neuesberlin1.html
git commit -m "neuesberlin1: Sumario y Figuras de la temporada"
```

---

### Task 8: Enlaces cruzados en todo el sitio

**Files:**
- Modify: los 33 `noticias*.html`, `index.html`, `berlin.html`

- [ ] **Step 1: Insertar «Prensa de Berlín» en las 33 ediciones parisinas (script)**

Ejecutar en PowerShell desde la raíz del worktree:

```powershell
$anchor = '    <nav class="date-navigation">'
$block = @'
        <p style="margin: 0 0 12px 0; text-align: center; border: 1px solid #8b7355; padding: 6px 4px;">
            <a href="neuesberlin1.html" class="date-link" style="font-weight: bold;">
                <span class="lang-fr">✠ Presse de Berlin</span>
                <span class="lang-es">✠ Prensa de Berlín</span>
            </a>
        </p>
'@
Get-ChildItem -Filter 'noticias*.html' | ForEach-Object {
    $c = [IO.File]::ReadAllText($_.FullName)
    if ($c.Contains('neuesberlin1.html')) { return }
    $c = $c.Replace($anchor, $anchor + "`r`n" + $block)
    [IO.File]::WriteAllText($_.FullName, $c, [Text.UTF8Encoding]::new($false))
}
```

(El ancla aparece exactamente una vez por archivo en los 33; el guard `Contains` hace el script idempotente. Los `span` llevan par `lang-fr`/`lang-es` porque las ediciones parisinas SÍ conmutan idioma.)

- [ ] **Step 2: Verificar la inserción**

Run (PowerShell): `(Get-ChildItem -Filter 'noticias*.html' | Select-String -List 'neuesberlin1.html').Count`
Expected: `33`

Abrir una edición cualquiera (p. ej. `noticias34.html`) en el navegador y comprobar el enlace en ambos idiomas.

- [ ] **Step 3: index.html**

Tras la línea:

```html
            <li><a href="./noticias34.html" target="_blank">Noticias (17 de noviembre de 1907)</a></li>
```

añadir:

```html
            <li><a href="./neuesberlin1.html" target="_blank">Prensa de Berlín (18 de noviembre de 1907)</a></li>
```

- [ ] **Step 4: berlin.html**

En la `sidebar-nav`, tras la línea equivalente del enlace a `./noticias34.html`, añadir:

```html
            <li><a href="./neuesberlin1.html" target="_blank">Neues Berlin (18. November 1907)</a></li>
```

- [ ] **Step 5: Commit**

```bash
git add noticias*.html index.html berlin.html
git commit -m "neuesberlin1: enlace Prensa de Berlin en las 33 ediciones, index y dossier"
```

---

### Task 9: Verificación final y PR

- [ ] **Step 1: Revisión visual completa**

Con Playwright (o navegador): abrir `neuesberlin1.html`; comprobar cabecera fraktur, fecha alemana, 4 imágenes renderizando (ajustar `object-position` si algún encuadre corta cabezas), fichas con retratos, y navegación lateral (4 enlaces funcionan). Comprobar también `noticias34.html` (enlace Berlín en FR y ES), `index.html` y `berlin.html`.

**Tamaños de fuente:** el andamio hereda los del sitio; verificar que ningún texto nuevo baje de los tamaños existentes (cuerpo ≥16px inline donde el andamio lo marca; no introducir tamaños menores).

- [ ] **Step 2: Repaso de canon**

Checklist sobre el texto final: ¿algún poder sobrenatural confirmado o "notado"? ¿Se nombra a los magnicidas correctamente (nunca "masones luditas")? ¿Firmas sin apellidos repetidos (Hoffmann, Weber, Krüger, Vogel, Schnauze)? ¿La voz mordaz solo en la Gesellschafts-Chronik? ¿Kronprinz herido el 5 de noviembre de 1905?

- [ ] **Step 3: Push y draft PR**

```bash
git push -u origin worktree-neuesberlin1
gh pr create --draft --title "Neues Berlin N.1 (18 nov 1907) + dossier de Berlin" --body "Primer numero del periodico berlines, dossier berlin.html y retratos, enlaces cruzados en todo el sitio.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

https://claude.ai/code/session_01HdzsX7t2Tz4v5oErkT7t6o"
```

- [ ] **Step 4: Nota post-merge**

Tras el merge, verificar el sitio en vivo (github.io), no solo el push — incluir recordatorio en el mensaje final al usuario.
