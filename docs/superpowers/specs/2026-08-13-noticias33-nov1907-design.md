# Diseño — *Paris Nouveau*, noticias33.html (16 Novembre 1907)

## Resumen

Nuevo número del periódico in-fiction *Paris Nouveau* para la campaña **Clair Obscur: Belle Époque**. Es el **primer número ambientado en 1907** — un salto de 2 años sobre `noticias32.html` (16 Nov 1905). El mundo "art-punk" ha entrado en convulsión global; este número cubre sobre todo tres frentes exteriores y ancla un hilo "en casa" en Francia.

- **Archivo nuevo:** `noticias33.html` (siguiente índice; no existe noticias33 aún).
- **Fecha in-fiction:** **Samedi 16 Novembre 1907** (sábado verificado: 16 Nov 1905 = jueves → +2 años no bisiestos = sábado). Aniversario redondo del último número.
- **Andamio:** copiar `noticias32.html` y reescribir contenido; conservar todo el CSS/JS y la anatomía de secciones.
- **Fecha real del spec:** 2026-08-13.

## Decisiones de marco (aprobadas por el usuario)

1. **Francia — "tocada pero aguantando":** llegan ecos del caos (huelgas, refugiados españoles, tensión); el diario informa con inquietud contenida pero funciona con normalidad. Habrá un hilo "en casa".
2. **Registro sobrenatural — oblicuo y escéptico:** los prodigios (derviches invulnerables, La Santa, La Doncella de Hierro, estatuas-dioses) se reportan como **rumor, fanatismo o propaganda extranjera**, nunca confirmados. Regla de canon vigente.
3. **Continuidad — mundial con guiños ligeros:** primer plano al tablero exterior; uno o dos regresos del elenco de 1905, alojados en la Crónica de Sociedad.
4. **Portada — la invasión frustrada de Turquía.**

## Toggles (aprobados)

- **Ilustración central de Émile Labord:** NO en este número.
- **Cartas al Director:** NO en este número (se omite la sección entera).
- **Solteros a Seguir:** se **copia tal cual** la lista de `noticias32.html`, sin modificar de momento.

## Guardarraíles de canon (obligatorios)

- **Voz de la Florista solo para cotilleo.** Todo lo demás: reportaje sobrio, tercera persona (registro de L. Moreau). Ver `feedback_newspaper-tone`.
- **Magnicidas ≠ masones luditas** — no fusionar las dos facciones si se mencionan.
- **La obra inaugural de André Lèfevre queda sin nombrar** (no es «Promenade à minuit», que es la novela por entregas de Chloé/C. Müller). No hace falta tocar a André en este número.
- **Variar las por-líneas:** no firmar dos piezas con el mismo apellido. Pool en `periodistas_pool.md`.
- **Lo sobrenatural, nunca confirmado:** atribuir siempre a fanatismo, moral de tropa, propaganda, terreno, superstición.
- **Bilingüe siempre:** cada bloque con su par `.lang-fr` y `.lang-es`. Un par ausente renderiza en blanco.

## Contexto alt-histórico 1907 (para coherencia de la prosa)

El escenario diverge de la historia real. Estado del mundo en Nov 1907 (solo se detallan a fondo los tres focos + casa; el resto entra en Brèves):

- **Rusia:** tras aplastar los disturbios de 1905 (motín de Sebastopol, etc., ya narrados en noticias32), Nicolás II ha convertido Rusia en un **estado militar total**. Sobreextendida, lanzó una invasión hacia territorio otomano.
- **Turquía (foco / portada):** el avance ruso ha sido **frenado por fuerzas irregulares organizadas en torno a cofradías de derviches** (sufíes). Boletines otomanos hablan de derviches que giran entre el fuego sin caer y de columnas presas del pánico → el diario lo trata como fanatismo/propaganda/moral.
- **España (foco / secundario 1):** **guerra civil** entre **carlistas** (tradicionalistas) y la **revolución gaudista** nacida en Barcelona (revolución estético-social que toma el nombre de Gaudí). El frente de **Galicia** se inclina al lado gaudista. Dos íconos místicos que la tropa gaudista lleva como estandartes: **La Santa** (mujer pintada como mártir al óleo renacentista) y **La Doncella de Hierro** (virgen en bronce); los soldados juran que "se mueven"/protegen → propaganda/superstición. **Refugiados** cruzan los Pirineos hacia Francia (ancla del marco "casa").
- **Italia y Grecia (foco / secundario 2):** movimiento de **restauración helénico-romana** — se rehabilitan templos, se revive la fe antigua, se restaura la antigüedad **desde el arte y el misticismo**. Artistas/eruditos repintan estatuas antiguas con su policromía original; una franja mística las **adora como dioses** y corre el rumor de que "segregan" divinidad y otorgan poderes → el diario lo trata como un fervor estético-religioso, con distancia escéptica. (Es el foco más próximo al núcleo "Maestros del Arte / arte-como-poder" de la campaña, mantenido oblicuo.)
- **Inglaterra (feature):** movimiento literario de los **"alarmistas"** — novelistas/ensayistas que advierten del peligro de estos cambios extremos.
- **Solo para Brèves (sin desarrollar):** **EE. UU.** en revolución democrática inspirada por la Internacional Obrera; **China** con una revolución cultural que devuelve la tradición al poder; **Austria** tras su fracasada marcha sobre Alemania (repelida).

## Maqueta (anatomía heredada de noticias32)

### Columna izquierda

**1. Artículo principal — portada · por-línea: L. Moreau (político sénior, sobrio)**
- Título de trabajo — FR: «La poussée russe brisée aux portes de l'Anatolie» · ES: «El empuje ruso, quebrado a las puertas de Anatolia».
- Beats: Rusia militarizada de Nicolás II se excede en una invasión otomana; el avance se detiene ante una resistencia irregular de cofradías de derviches; el diario recoge los "prodigios" (invulnerabilidad, pánico) para **descartarlos** como fanatismo/propaganda/terreno/logística; Francia observa, vieja amistad con Rusia tensada por el militarismo del Zar; inquietud por el equilibrio europeo.
- Imagen `.article-image` 16:9: **derviches giróvagos (mevleví) de Constantinopla**, foto de época PD (Wikimedia). Alt: tropas otomanas / paisaje del Cáucaso. `object-position` centrado al sujeto.

**2. Secundario 1 — Guerra civil en España · por-línea: H. Dubois (sobrio)**
- Título — FR: «Guerre civile en Espagne : la Galice bascule» · ES: «Guerra civil en España: Galicia se inclina».
- Beats: carlistas vs revolución gaudista (Barcelona); el vuelco de Galicia; **La Santa** y **La Doncella de Hierro** como estandartes que la tropa jura vivos → propaganda/superstición, nunca confirmado; cola con **refugiados por los Pirineos** hacia Francia (engancha el marco "casa").
- Imagen `.article-image` 5:4 (secundario): **Sagrada Família en construcción** (Gaudí, Barcelona), foto de época PD. Alt: paisaje gallego. `object-position` ajustado.

**3. Secundario 2 — Restauración helénico-romana (Italia y Grecia) · por-línea: L. Roy (arte/cultura, sobrio)**
- Título de trabajo — FR: «Le réveil des dieux anciens» · ES: «El despertar de los dioses antiguos».
- Beats: templos rehabilitados, fe antigua revivida, antigüedad restaurada desde el arte y el misticismo; policromía repintada; la franja que **adora las estatuas como dioses** y el rumor de poderes → tratado como fervor estético-religioso con distancia escéptica.
- Imagen `.article-image` 5:4: **Partenón (Atenas)** foto de época PD. Alt: reconstrucción de estatua policromada (Augusto de Prima Porta / kore). `object-position` ajustado.

**4. Crónicas de Sociedad — La Florista (única pieza con voz irónica)**
- Guiño ligero al elenco de 1905: **una** hebra de 1905 avanzada dos años, en su voz, breve.
- Recomendado: **Luís Filipe de Portugal**, dos años después, en su exilio junto al parc Monceau (resuena con el ánimo de "tronos que caen" del número). Alt: el cierre del enredo Nœud-Papillon / Lucile Roy.
- Mantener el retrato canon del personaje si se ilustra (excepción de imágenes: los personajes de campaña conservan su retrato del repo).

**(Sin Cartas al Director en este número.)**

### Columna derecha (aside)

**5. Feature — Los "alarmistas" de Londres · por-línea: É. Garnier (cultural, sobrio)**
- FR: «Les alarmistes de Londres» · ES: «Los alarmistas de Londres».
- Beats: escritores ingleses que advierten del peligro de estos cambios extremos; panfletos/novelas; recepción; registro de reportaje cultural mesurado.
- Imagen `.vertical-image.sidebar-portrait` 3:4: **paisaje/atmósfera de Londres de época** (niebla del Támesis / Fleet Street), foto PD — NO un retrato real, porque el movimiento es ficticio (regla de imágenes: ficción → escenario/atmósfera).

**6. Brèves de la Semaine — barrido del resto, con variedad (≤1 guiño de continuidad)**
1. **EE. UU.:** revolución democrática inspirada por la Internacional Obrera.
2. **China:** revolución cultural que devuelve la tradición al poder.
3. **Austria:** su fracasada marcha sobre Alemania, repelida.
4. **Misterio artístico oblicuo (único guiño de continuidad):** el "retrato sin dueño" del Louvre de noticias32, que sigue sin dueño.
5. **Ítem ligero de ciencia/técnica** (aviación/curiosidad parisina) para variedad de dominio.

**7. Sumario** — títulos + por-líneas del número (L. Moreau, H. Dubois, L. Roy, É. Garnier, La Florista).

**8. Solteros a Seguir (Potins & Cancans)** — **copiar íntegra la lista de noticias32**, sin cambios.

## Checklist mecánico (proceso estándar de nueva edición)

1. Crear `noticias33.html` copiando `noticias32.html`; actualizar fecha de cabecera (FR/ES) y el estado `active` del nav interno al nuevo `<li>`.
2. Autoría bilingüe `.lang-fr` + `.lang-es` en **cada** bloque nuevo.
3. Propagar el nuevo `<li class="date-item">` en la `.date-navigation` de **todos** los `noticias*.html` (orden cronológico inverso; solo la página actual con `active`). **Incluir el año "1907"** también en la etiqueta ES del nuevo ítem para evitar ambigüedad con el "16 de Noviembre" de 1905.
4. Actualizar el enlace único "Noticias" de `index.html` a `noticias33.html` con etiqueta "(16 de noviembre de 1907)".
5. Imágenes: frescas de dominio público (Wikimedia), bien centradas con `object-position`, orientación acorde al hueco (16:9 principal, 5:4 secundario, 3:4 sidebar). **La Santa / La Doncella de Hierro**: usar foto de una **pintura de mártir renacentista** y de una **estatua de virgen en bronce** reales de dominio público como los "íconos", o generar con Higgsfield si no encaja. Verificar cada imagen viéndola antes de usarla.
6. Verificar el sitio en vivo (github.io), no solo el push.

## Fuera de alcance

- No se reescribe la lista de Solteros (se copia).
- No se tocan editions anteriores salvo la propagación del `<li>` de navegación.
- No se nombra la obra inaugural de André Lèfevre; no hace falta tocar a André.
- No se confirma ningún poder sobrenatural en la prosa.
