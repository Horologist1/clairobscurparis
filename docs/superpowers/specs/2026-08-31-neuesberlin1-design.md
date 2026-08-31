# Diseño — *Neues Berlin*, neuesberlin1.html (Montag, 18. November 1907)

## Resumen

Primer número del periódico berlinés in-fiction **_Neues Berlin_**, gemelo alemán del *Paris Nouveau*, para la campaña **Clair Obscur: Belle Époque / Kaiserzeit**. Su función es **fijar el paisaje y el ánimo de la Alemania de 1907** (el dossier `berlin.html`) y servir de ventana cruzada entre las dos mesas: los jugadores de Alemania leen su propio diario (con una «Carta de París» dentro), y los de París pueden asomarse a Berlín por el enlace «Prensa de Berlín».

- **Archivo nuevo:** `neuesberlin1.html`.
- **Fecha in-fiction:** **Montag, 18. November 1907** — el día siguiente a `noticias34.html` (17 nov, ya jugada). El desfile de la victoria sobre Austria es plausible en esta fecha: la cronología de `berlin.html` sitúa la marcha austríaca repelida en noviembre de 1907 y el *Paris Nouveau* del 17 aún la daba como noticia fresca («Viena vuelve a casa»).
- **Andamio:** copiar una edición parisina reciente (p. ej. `noticias34.html`) y conservar la anatomía de dos columnas y el CSS del "papel"; retirar lo que no aplica (ver *Decisiones*).
- **Fecha real del spec:** 2026-08-31.

## Decisiones de marco (aprobadas por el usuario)

1. **Cabecera: «Neues Berlin»** — espejo consciente del *Paris Nouveau*: cada capital presume de ser la ciudad nueva.
2. **Solo español.** Sin botón de idioma y sin pares `.lang-fr`/`.lang-es`: el contenido se escribe en marcado plano en español. Se elimina el toggle (botón + JS) del andamio. La regla bilingüe de CLAUDE.md aplica al *Paris Nouveau*, no a este diario.
3. **Sabor alemán sin traducción completa:** cabecera en tipografía fraktur (webfont, p. ej. UnifrakturMaguntia, cargada igual que el resto de fuentes del sitio), fecha en alemán («Montag, 18. November 1907»), y rótulos de sección bilingües DE/ES como decoración («Kurznachrichten · Breves», «Gesellschafts-Chronik · Crónica de Sociedad»). El papel sigue siendo crema: mismo artefacto físico "periódico", inconfundiblemente alemán.
4. **Portada: el desfile de la victoria** (opción 1). La ceremonia del Senado (opción 3) se recicla como secundario.
5. **Publicación «hermana + corresponsales»:** página propia enlazada desde todas las ediciones parisinas e `index.html`; corresponsalías cruzadas en la ficción. La «Carta de Berlín» recíproca en el *Paris Nouveau* queda para `noticias35` (fuera de alcance aquí).
6. **Commit conjunto:** `berlin.html` y `personajes_imagenes/berlin/` (29 retratos, hoy sin trackear) se commitean junto con el nuevo número, porque el diario enlaza con el dossier.

## Tono editorial (clave del número)

*Neues Berlin* es un diario **orgulloso y semi-oficial**, cercano al trono. Donde el *Paris Nouveau* esconde lo sobrenatural bajo el escepticismo, aquí se esconde **bajo el orgullo patriótico**: el diario reporta con entusiasmo detalles inquietantes sin notar que lo son. Nada de ironía republicana; sí el *Berliner Schnauze* (ingenio local mordaz), pero solo en la sección de cotilleo.

## Guardarraíles de canon (obligatorios)

- **Lo sobrenatural, nunca confirmado** — aquí, además, nunca *notado*: se envuelve en orgullo, logística y protocolo ("genio logístico", "curiosidad administrativa").
- **Canon de `berlin.html` / memoria `berlin-canon`:** el Senado de las Artes **no tiene poder político** (medallas, encargos, carreras); el poder real es corona, corte y Gran Estado Mayor; el eje artístico-político es salones (nobleza) vs redacciones (escritores disconformes); el **Kronprinz fue herido por los magnicidas la noche del 5 de noviembre de 1905** en París; la marcha austríaca fue repelida en noviembre de 1907 con una movilización inexplicable de la que los Maestros Arquitectos callan.
- **Magnicidas ≠ masones luditas** — si se alude al atentado de 1905, la autoría es de los «magnicidas».
- **Kollwitz vetada:** el Káiser vetó en persona su medalla (1898) y "no ha olvidado que ella siguió grabando" — su ausencia en la ceremonia del Senado es canon, no invención.
- **Firmas nuevas alemanas, sin repetir apellido** en el número (pool nuevo, no reutilizar `periodistas_pool.md` parisino).
- **Retratos de personajes canon** salen de `personajes_imagenes/berlin/`; el resto de imágenes, frescas de dominio público (Wikimedia), bien centradas; Higgsfield como respaldo.

## Maqueta (anatomía heredada de noticias34)

### Columna izquierda

**1. Portada — «La victoria desfila bajo los Tilos» · firma: K. Hoffmann (crónica mayor, solemne)**
- Beats: las tropas vuelven del frente austríaco y desfilan por la Puerta de Brandeburgo y Unter den Linden; el Káiser preside; **el Kronprinz reaparece en público con su cicatriz** (primera aparición grande desde el atentado — siembra el gancho de venganza sin nombrarlo); elogio del "genio logístico" de Moltke; detalles reportados con orgullo e inquietantes para el lector atento: regimientos llegados por líneas que no figuran en los horarios civiles, la tribuna de honor sin los Maestros Arquitectos, una marcha militar que nadie recuerda haber ensayado.
- Imagen `.article-image` 16:9: foto de época PD de desfile militar ante la Puerta de Brandeburgo (Wikimedia). Alt: tropas en Unter den Linden.

**2. Secundario 1 — «El Senado reparte laureles» · firma: F. Weber (política artística, cortesano)**
- Beats: sesión de medallas en el palacio de la Pariser Platz tras la victoria; von Werner preside con "profesionalidad absoluta de la lealtad"; un dardo elegante de Liebermann desde el asiento consultivo; la ausencia —otra vez— de Käthe Kollwitz; los dos asientos consultivos de los Escritores, tan callados que se notan. Retrata salones vs redacciones sin editorializar.
- Imagen `.article-image` 5:4: foto PD de la Pariser Platz / Academia de las Artes o interior de gala.

**3. Secundario 2 — «Elektropolis no duerme» · firma: E. Krüger (técnica/industria, entusiasta)**
- Beats: nuevo tramo del U-Bahn y la nave de turbinas de la AEG (Behrens); cifras de crecimiento, orgullo del "cinco años más joven que el Metro de París"; deslizadas como curiosidad administrativa: los túneles cavados por las Bauhütten y una estación "que no figura en el plano de bolsillo, por razones de servicio".
- Imagen `.article-image` 5:4: foto PD de estación del U-Bahn de Berlín (~1902-1907) o nave industrial de la AEG.

**4. Gesellschafts-Chronik · Crónica de Sociedad — firma: «Eine Berliner Schnauze» (única voz irónica del número)**
- Beats: la inauguración del Hotel Adlon con "media Europa coronada" en el vestíbulo; la princesa **Cecilia de Mecklemburgo** como nueva estrella de la corte; una anécdota de **Tilla Durieux** y sus retratos ("le gusta saber dónde viven todas sus versiones"). Cotilleo mordaz, cariñoso con la ciudad, irreverente con todos menos con el Káiser (por prudencia evidente, no por respeto).

### Columna derecha (aside)

**5. Feature — «Carta de París» · "de nuestro corresponsal", firma: H. Vogel**
- La ventana del jugador alemán a la otra mesa. Beats: la marcha orleanista bajo el Arco de Triunfo; las elecciones a tres bandas ("un rey, un constructor, una artesana"); los refugiados españoles en las estaciones del Mediodía. Mirada berlinesa: fascinación y sorna hacia la República ("París discute quién manda; Berlín ya lo sabe"), con una nota fría al recordar "la noche de noviembre de hace dos años" (el atentado — sin detallar).
- Imagen `.vertical-image.sidebar-portrait` 3:4: foto PD de París (Arco de Triunfo / multitud de época).

**6. Kurznachrichten · Breves — barrido del paisaje (4-5 ítems)**
1. **Múnich:** fundación del Deutscher Werkbund (octubre) — "el arte entra en nómina de la industria".
2. **Bayreuth:** nota sobre Cosima Wagner y la negativa a liberar *Parsifal*.
3. **Essen:** los nuevos aceros de Krupp superan las pruebas "con resultados que la casa no publica".
4. **Berlín:** demostración del Biophon de Messter — "las imágenes hablan; los cantantes, a veces, siguen".
5. **Dresde:** escándalo menor de Die Brücke (una exposición clausurada / vecinos que se quejan de "los colores").

**7. Sumario** — títulos + firmas del número (K. Hoffmann, F. Weber, E. Krüger, H. Vogel, Eine Berliner Schnauze).

**8. «Figuras de la temporada»** — espejo berlinés de los «Solteros a Seguir»: 3-4 fichas breves con retrato desde `personajes_imagenes/berlin/` — p. ej. **Max Reinhardt** (el mago del Deutsches Theater), **Richard Strauss** (el emperador secreto de la música), **Tilla Durieux** (la primera actriz), opcionalmente **Käthe Kollwitz** (la ausente más comentada, cerrando el eco del artículo del Senado).

## Integración con el sitio

1. **`neuesberlin1.html`**: navegación propia mínima en la barra lateral — enlace al dossier **`berlin.html`** («Dossier: Berlín») y a **`noticias34.html`** («Presse de Paris · Prensa de París»). Sin la lista completa de ediciones parisinas.
2. **Todas las `noticias*.html`**: añadir un bloque/enlace destacado **«Presse de Berlin · Prensa de Berlín»** junto a la `.date-navigation` (misma posición en todas), apuntando a `neuesberlin1.html`. No se toca nada más de las ediciones.
3. **`index.html`**: añadir enlace «Prensa de Berlín (18 de noviembre de 1907)» junto al enlace de Noticias (checklist de nuevas ediciones: index.html siempre se actualiza).
4. **`berlin.html`**: añadir enlace al periódico desde el dossier.
5. **Commit conjunto** de `berlin.html` + `personajes_imagenes/berlin/` + `neuesberlin1.html` + enlaces.
6. **Verificar el sitio en vivo** (github.io) tras el push, no solo el push.

## Fuera de alcance

- La «Carta de Berlín» recíproca en el *Paris Nouveau* (irá en `noticias35`, cuando toque).
- No se toca el contenido de las ediciones parisinas más allá del enlace «Prensa de Berlín».
- No se confirma ningún poder sobrenatural en la prosa; ningún personaje "nota" lo extraño.
- No se crea serie de navegación berlinesa (fechas futuras) hasta que exista un segundo número.
