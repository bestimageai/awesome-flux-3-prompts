<p align="center">
  <a href="https://bestimage.ai/"><img src="assets/bestimage-ai-logo.svg" width="72" height="72" alt="Logotipo de bestimage.ai"></a>
</p>

# Awesome FLUX 3 Prompts

<p align="center">
  <img src="assets/flux-3-prompts-hero.png" alt="Un farero coloca una linterna ámbar sobre un puerto oscuro" width="100%">
</p>

84 prompts completos de vídeo para historias, vídeos de producto, animación, educación y escenas controladas mediante referencias. Una colección seleccionada y mantenida por el equipo de [bestimage.ai](https://bestimage.ai/).

[English](README.md) · [简体中文](README_zh-CN.md) · [日本語](README_ja-JP.md) · Español · [Cobertura de idiomas](i18n/README.md)

[![Sitio web](https://img.shields.io/badge/Website-bestimage.ai-4C52FE)](https://bestimage.ai/)
[![API de FLUX 3](https://img.shields.io/badge/FLUX_3-API-111827)](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/)
[![API de GPT Image 2](https://img.shields.io/badge/GPT_Image_2-API-111827)](https://bestimage.ai/models/openai/gpt-image-2/)

## Empieza por una escena que puedas dirigir

1. Explora el [índice de 84 prompts](prompts/README.md) o la [matriz de casos de uso](docs/use-case-matrix.md).
2. Elige un texto, un primer fotograma aprobado, dos fotogramas inicial y final aprobados o un clip de origen.
3. Copia el bloque completo del prompt. Ajusta las variables indicadas, respetando el número de objetos y la continuidad.
4. Utiliza la [guía de prompts](docs/prompting-guide.md) para revisar el resultado antes de ampliar la escena.

Usa estas especificaciones creativas como punto de partida para tus propias escenas. Pedir un movimiento de cámara, una frase exacta o la coincidencia con los fotogramas inicial y final no garantiza obtener ese resultado.

## Crea con bestimage.ai

El equipo de bestimage.ai mantiene esta biblioteca independiente de prompts y organiza flujos prácticos de preparación de imagen a vídeo y de uso de API. No es un repositorio oficial de Black Forest Labs.

| Material de partida | Acceso en bestimage.ai | Finalidad |
| --- | --- | --- |
| Una escena escrita | [FLUX 3: de texto a vídeo](https://bestimage.ai/models/black-forest-labs/flux-3-text-to-video/) | Explorar una escena nueva, un diálogo o una explicación visual |
| Una imagen aprobada | [FLUX 3: de imagen a vídeo](https://bestimage.ai/models/black-forest-labs/flux-3-image-to-video/) | Animar la composición del primer fotograma proporcionado |
| Imágenes de apertura y cierre | [FLUX 3: de fotogramas inicial y final a vídeo](https://bestimage.ai/models/black-forest-labs/flux-3-start-end-to-video/) | Solicitar una transición controlada entre dos fotogramas |
| Un clip existente | [FLUX 3: extensión de vídeo](https://bestimage.ai/models/black-forest-labs/flux-3-video-extend/) | Continuar el movimiento, el estado de la escena y el ambiente del clip de origen |
| Una descripción para un guion gráfico o un fotograma de referencia | [API de GPT Image 2](https://bestimage.ai/models/openai/gpt-image-2/) | Preparar o revisar **imágenes estáticas** antes de una etapa de vídeo independiente |

GPT Image 2 es un flujo de imágenes independiente, no un punto de acceso de vídeo de FLUX 3. Aprueba la imagen y comprueba sus derechos de uso antes de proporcionarla como referencia de vídeo. Generar un fotograma útil no verifica la calidad del vídeo resultante.

Las [12 propuestas orientadas a la API](prompts/bestimage-api-workflows.md) corresponden a los identificadores de modelo y campos multimedia documentados. La [guía de integración](docs/bestimage-ai-flux-3-api.md) utiliza **`https://api.flaq.ai`, el servidor de API de bestimage.ai**. Usa una clave de API emitida desde tu cuenta de bestimage.ai.

## Biblioteca de prompts

| Colección | Prompts | Útil para |
| --- | ---: | --- |
| [Narrativa cinematográfica](prompts/cinematic-storytelling.md) | 6 | Historias breves, orientación espacial en pantalla y ritmo de montaje |
| [Publicidad y UGC](prompts/advertising-ugc.md) | 6 | Interacciones con productos, contenido de creadores y escenas de servicio |
| [Documental y naturaleza](prompts/documentary-nature.md) | 6 | Escenas editoriales sintéticas y observación pausada |
| [Animación y diseño](prompts/animation-design.md) | 6 | Papel, fieltro, arcilla, tipografía y movimiento de personajes originales |
| [Audio multilingüe](prompts/multilingual-audio.md) | 6 | Diálogos exactos, turnos de palabra e interpretaciones vocales originales |
| [Flujos con referencias](prompts/reference-workflows.md) | 6 | Identidad del primer fotograma, fotogramas inicial y final, y continuidad |
| [Comercio electrónico y producto](prompts/ecommerce-product.md) | 6 | Número de piezas, embalaje, materiales y geometría del producto |
| [Viajes y hostelería](prompts/travel-hospitality.md) | 6 | Encuentros respetuosos, encuadre de alojamientos y servicio |
| [Deporte y bienestar](prompts/sports-wellness.md) | 6 | Movimientos de bajo riesgo y momentos comunitarios inclusivos |
| [Educación y ciencia](prompts/education-science.md) | 6 | Lecciones breves y verificables e instrucciones claras |
| [Arquitectura y movilidad](prompts/architecture-mobility.md) | 6 | Espacios visibles, recorridos y logística |
| [Social y experimental](prompts/social-experimental.md) | 6 | Humor impasible, diálogos entre creadores, conceptos de juegos y planos para composición |
| [Flujos de API de bestimage.ai](prompts/bestimage-api-workflows.md) | 12 | Tres propuestas para cada uno de los cuatro modos de vídeo documentados |

Cada entrada incluye un caso de uso, un modo, una secuencia temporal, acciones visibles, un plan de sonido, elementos que deben mantenerse, exclusiones y límites de ajuste. Las referencias deben tener una función explícita; no permitas que una imagen de estilo redefina el producto o la persona de referencia.

## Prompts destacados

Escena de portada: [C01 — El relevo de la linterna](prompts/cinematic-storytelling.md#c01): una pequeña señal luminosa de una fuente presente en la escena introduce un mundo costero ficticio.

La portada y las cinco ilustraciones son conceptos estáticos originales, no vídeos generados con FLUX 3. Consulta los [prompts de imagen y su procedencia](assets/IMAGE_PROMPTS.md).

### [A01 — Luz a través del lino](prompts/advertising-ugc.md#a01)

Conserva la geometría de una lámpara mientras un único interruptor cambia su iluminación.

<p align="center">
  <img src="assets/featured/light-through-linen.png" alt="Una lámpara con pantalla de lino plisado, base de terracota y un interruptor en el cable" width="58%">
</p>

### [N01 — El observatorio del botón](prompts/animation-design.md#n01)

Una historia en miniatura de textura tangible, con un telescopio de cartón y un astrónomo de fieltro.

<p align="center">
  <img src="assets/featured/button-observatory.png" alt="Un astrónomo de fieltro examina un botón blanco de cuatro agujeros junto a un telescopio de cartón" width="100%">
</p>

### [E01 — Dos separadores, un sitio](prompts/ecommerce-product.md#e01)

Una propuesta de montaje que distingue las tres piezas del producto del cuaderno utilizado como atrezo.

<p align="center">
  <img src="assets/featured/two-dividers.png" alt="Un organizador de madera con dos separadores sostiene un cuaderno azul cerrado" width="100%">
</p>

### [L01 — Mover la tarjeta, no la luz](prompts/education-science.md#l01)

Una demostración clara de las sombras con la luz y la pantalla fijas.

<p align="center">
  <img src="assets/featured/shadow-card.png" alt="Una lámpara y una tarjeta cuadrada opaca proyectan una sombra ampliada sobre una pantalla blanca" width="100%">
</p>

### [X01 — Una frase útil](prompts/social-experimental.md#x01)

Diálogo exacto, una pausa de cinco segundos y ningún remate adicional.

<p align="center">
  <img src="assets/featured/one-useful-sentence.png" alt="Una persona con jersey gris dirige una reunión ante un micrófono de mesa y un cuaderno cerrado" width="58%">
</p>

## Capacidades del modelo frente a esta integración

Black Forest Labs describe FLUX 3 como un modelo multimodal y documenta la generación de vídeo con referencias de texto, imagen y vídeo, fotogramas clave, continuación y audio nativo. Sus componentes de vídeo, imagen, acción y pesos abiertos se encuentran en fases de lanzamiento distintas. Consulta la [página oficial del modelo](https://bfl.ai/models/flux-3) y la [presentación del lanzamiento](https://bfl.ai/blog/flux-3) antes de dar por hecho el acceso o las capacidades.

Esa descripción general del modelo no demuestra que todos los proveedores ofrezcan todas las entradas. La colección de flujos de bestimage.ai de esta biblioteca utiliza únicamente los cuatro modos de vídeo documentados. En particular, un primer fotograma proporcionado mediante un único `image_url` no equivale a una lista general de múltiples referencias.

## Cobertura de idiomas

- Cuatro archivos README de presentación: inglés, chino simplificado, japonés y español.
- Once archivos de escenas en idiomas distintos del inglés: chino, japonés, español, francés, alemán, coreano, portugués de Brasil, italiano, árabe, ruso e indonesio.
- Cada archivo de escenas traduce las mismas tres escenas de referencia: X01, E01 y L01. Estas 33 traducciones **no son 33 prompts originales adicionales**.
- La colección completa de 84 prompts y las guías de producción se mantienen en inglés. Los archivos por idioma no constituyen traducciones de toda la biblioteca.

Consulta el [directorio de idiomas](i18n/README.md) para conocer los archivos y su alcance exacto.

## Revisa el resultado antes de publicarlo

Utiliza imágenes de referencia autorizadas e identidades y voces con el consentimiento correspondiente. Revisa el movimiento, la anatomía, el número de objetos, el diálogo, el texto y la continuidad de los fotogramas inicial y final. Las demostraciones sintéticas de productos no prueban su rendimiento; las escenas de establecimientos ficticios no demuestran la disponibilidad real de sus servicios. Añade en posproducción los textos esenciales para el negocio y las medidas verificadas.

## Contribuciones

Comparte prompts, ejemplos o traducciones útiles siguiendo la [guía de contribución](CONTRIBUTING.md).

## Acerca de bestimage.ai

El equipo de [bestimage.ai](https://bestimage.ai/) selecciona y mantiene esta biblioteca de prompts, que conecta flujos de trabajo creativos con API de modelos de imagen y vídeo.

## Gana con el programa de afiliados de bestimage.ai

¿Publicas tutoriales, prompts o integraciones de API? Únete al [programa de afiliados de bestimage.ai](https://bestimage.ai/affiliate-program/) y gana comisiones al recomendar bestimage.ai a tu audiencia.

- **20 %** sobre el primer pedido de pago válido de cada usuario referido.
- **10 %** sobre sus pedidos de pago válidos posteriores, realizados durante los **60 días siguientes a su registro**.

Los requisitos de los pedidos y los pagos se rigen por el [acuerdo de afiliación vigente](https://bestimage.ai/affiliate-agreement/).

## Licencia

[MIT](LICENSE).
