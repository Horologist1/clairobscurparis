# Diseño — *Paris Nouveau*, noticias35.html (18 Novembre 1907) + re-datado del *Neues Berlin*

## Resumen

Doble entrega aprobada por el usuario:

**A)** Re-datar `neuesberlin1.html` del lunes 18 de noviembre al **miércoles 20 de noviembre de 1907** («Mittwoch, 20. November 1907»), porque el jugador de Alemania se incorpora en una o dos semanas reales y la mesa parisina avanza ~1 día de ficción por sesión. El desfile pasa a ser «ayer» martes 19; todas las referencias internas son relativas y no requieren reescritura.

**B)** Crear `noticias35.html` — *Paris Nouveau* del **lunes 18 de noviembre de 1907** (Lundi/Lunes; el 16 era sábado). Portada: un crimen atroz cerrado por el **Concilio de las Luces** (FR: **Conseil des Lumières**). Resto de artículos: inventados sobre noticias reales de París 1907-1910, con el tinte del mundo de juego. **Bilingüe FR/ES en todos los bloques** (patrón estándar de las ediciones parisinas, con toggle).

- Rama de trabajo: `worktree-neuesberlin1` (mismo draft PR #1; actualizar título/cuerpo del PR al final).
- Fecha real del spec: 2026-08-31.

## A) Re-datado de neuesberlin1.html (20 nov 1907)

1. Cabecera: `Montag, 18. November 1907` → `Mittwoch, 20. November 1907` (mismo «Preis: 10 Pfennig»).
2. Datas internas: los dos «Berlín, 18 de noviembre» (portada y Senado) → «Berlín, 20 de noviembre».
3. Navegación propia: `<span>18. November 1907</span>` → `<span>20. November 1907</span>`.
4. «Carta de París»: añadir data al arranque del primer párrafo — «París, 18 de noviembre.» delante de «De nuestro corresponsal» (mantiene «El domingo» = 17 nov y las vísperas electorales ancladas).
5. Enlace «Presse de Paris · Prensa de París» de su nav: `noticias34.html` → `noticias35.html`.
6. `index.html`: etiqueta «Prensa de Berlín (18 de noviembre de 1907)» → «(20 de noviembre de 1907)».
7. `berlin.html`: etiqueta «Neues Berlin (18. November 1907)» → «(20. November 1907)».

## B) noticias35.html — maqueta

Andamio: copia de `noticias34.html` (hereda toggle de idioma, bloque «Prensa de Berlín» y anatomía). Anatomía: portada + 2 secundarios + feature lateral + breves + sumario. Sin Solteros, sin Florista, **sin Carta de Berlín** (descartada por el usuario para este número).

### 1. Portada — «El Concilio pone término a una serie atroz» · L. Moreau

- FR: «Le Conseil des Lumières met un terme à une série atroce» · ES: «El Concilio de las Luces pone término a una serie atroz».
- Subtítulo: cuatro vidas; el autor, un enfermo, ajusticiado; la alerta, levantada; y una advertencia de esta redacción.
- Imagen 16:9: foto PD sobria (agentes/Prefectura de policía de París, época). NO escena truculenta.
- Beats (5-6 párrafos, registro sobrio, contención deliberada):
  1. Data «París, 18 de noviembre» — esta madrugada, agentes del Concilio de las Luces pusieron término al suceso que ha costado **cuatro vidas** en los últimos días.
  2. Negativa explícita al detalle: por decencia y a petición de la Prefectura. Única miga para jugadores: «lo que los agentes encontraron en aquel **taller** no pertenece a la crónica, sino a la patología». Nada más se describe.
  3. El autor: un hombre **enfermo**, que actuaba **solo**, **sin afiliación a sociedad, partido ni causa alguna** (negación explícita — que nadie lo atribuya a magnicidas ni a masones luditas). Ha sido **ajusticiado**; «la justicia fue tan rápida como discreta». No se cuestiona al Concilio (o una sola línea mesurada).
  4. La ciudadanía **no debe seguir en alerta**: la Prefectura levanta las recomendaciones de los últimos días.
  5. Giro editorial final: en vísperas electorales, que nadie convierta el miedo en argumento; **la situación política no debe escalar a la violencia**; el crimen de un enfermo no es bandera de nadie.
  6. Cierre breve y digno.

### 2. Secundario 1 — «Farman rueda hacia el kilómetro» · É. Garnier

- Real: Henri Farman y su biplano Voisin en Issy-les-Moulineaux (oct-nov 1907, 771 m; a la caza del Grand Prix Deutsch-Archdeacon: 1 km en circuito cerrado, 50.000 francos).
- Imagen 5:4: foto PD real de Farman/Voisin en Issy.
- Tinte: la máquina vuela **sin arte** — cita de ingeniero: «no hay misterio, señores: hay gasolina»; algunos Maestros asisten en silencio desde el borde del campo; el diario lo registra sin sacar conclusiones. 3-4 párrafos.

### 3. Secundario 2 — «Los bailarines que cruzan Europa» · H. Dubois

- Adelanto tintado de los Ballets Russes: bailarines y músicos que dejan la Rusia-cuartel del Zar llegan a la Gare du Nord; **el señor Diaghilev** (real: conciertos rusos en París, mayo 1907) prepara una «temporada rusa».
- Imagen 5:4: foto PD (Gare du Nord de época o bailarina rusa ~1905-09).
- Tinte: pasaportes que dicen «coristas»; el Zar los tiene por desertores; un baúl «que pesa más de lo que debiera» (una sola pincelada, sin desarrollo). Conecta con el motivo de refugiados (España, ed. 33-34). 3-4 párrafos.

### 4. Feature lateral — «Los cubos del Salón de Otoño» · L. Roy

- Real: retrospectiva de Cézanne en el Salón de Otoño (oct 1907); jóvenes que pintan «con cubitos» (Braque/Vauxcelles, adelantado un año).
- Imagen vertical 3:4: Grand Palais de época o un Cézanne PD.
- Tinte oblicuo: qué le hace a lo mirado una escuela que aprende a mirar así; «pura geometría, nos aseguran». Registro de crítica cultural mesurada. 3-4 párrafos.

### 5. Breves de la Semana (5 ítems, FR/ES)

1. **El Cullinan:** el diamante mayor del mundo, entregado al rey Eduardo VII (real, 9 nov 1907); el tallado se encomienda a Ámsterdam; los talladores piden «meses y silencio» — la piedra, dicen, «no se deja».
2. **La Torre habla:** ensayos de telegrafía sin hilos en la Torre Eiffel (real 1907-08); señales horarias; «hay quien pregunta a quién más escucha la Torre».
3. **El Sena:** los hidrólogos advierten crecidas si el invierno viene húmedo (presagio de la crecida real de enero de 1910).
4. **Adiós cumplido a Pinocho:** la gala de despedida se celebró anoche en el teatro de la Belle Époque (continuidad con la ed. 34, que la anunciaba «esta semana»).
5. **La campaña, en silencio:** los tres candidatos suspenden sus actos del lunes en señal de duelo por las víctimas (cose portada y elecciones).

### 6. Sumario

Títulos + firmas: L. Moreau, É. Garnier, H. Dubois, L. Roy (sin apellidos repetidos; pool establecido del periódico).

## Guardarraíles de canon

- Nombres del organismo: FR **Conseil des Lumières** · ES **Concilio de las Luces** (forma que usa el usuario; convive con «Consejo» en ediciones previas).
- El crimen NO se atribuye a magnicidas ni a masones luditas — negación explícita en el texto.
- Lo sobrenatural, nunca confirmado; miga única y muda: el «taller».
- Bilingüe obligatorio: cada bloque nuevo con par `.lang-fr` + `.lang-es`.
- Voz de la Florista: no aparece (no hay sección de cotilleo en este número).
- Imágenes frescas PD (Wikimedia/LOC/Gallica), verificadas viéndolas; Higgsfield como respaldo; centrado con `object-position`.

## Mecánica de nueva edición (checklist estándar + este caso)

1. `cp noticias34.html noticias35.html`; el `<title>` se mantiene («Paris Nouveau - Belle Époque»); fecha de cabecera FR/ES a «Lundi, 18 Novembre 1907» / «Lunes, 18 de Noviembre de 1907».
2. Nuevo `<li class="date-item">` «18 Novembre 1907» / «18 de Noviembre de 1907» insertado por script al inicio de `<ul class="date-list">` en **todos** los `noticias*.html` (34 archivos, incluido el 35). En noticias35: el nuevo `<li>` lleva `active` y el de «17 Novembre 1907» lo pierde. Verificar el ancla `        <ul class="date-list">` en 34/34 antes de aplicar.
3. `index.html`: enlace «Noticias» → `noticias35.html` «(18 de noviembre de 1907)».
4. `berlin.html`: enlace «Noticias» → `noticias35.html` «(18 de noviembre de 1907)».
5. El bloque «Prensa de Berlín» se hereda del andamio (no duplicar).
6. Al final: actualizar título/cuerpo del draft PR #1 para reflejar que incluye ambas ediciones; verificación visual en navegador de noticias35, neuesberlin1 re-datado, y una edición antigua.

## Fuera de alcance

- «Carta de Berlín» en el *Paris Nouveau* (queda para una edición futura, cuando el usuario la pida).
- No se toca la prosa del *Neues Berlin* más allá de fechas y la data de la Carta de París.
- No se resuelven las elecciones ni se da fecha del escrutinio.
- No se confirma ningún poder sobrenatural.
