[← Capítulo II](./capitulo-2.md) &nbsp;|&nbsp; [← Volver al índice](../../README.md)

---

<div align="center">

# Capítulo III: Requirements Specification

</div>

---

## 3.1. User Stories

*(Introducción a los User Stories y Epics definidos para BrandRadar)*

> **Nota:** Los criterios de aceptación se redactan en tiempo presente, tercera persona, sin referencia a detalles de interfaz de usuario, y siguen la estructura **Gherkin (Given-When-Then)**.

| Epic / Story ID | Título | Descripción | Criterios de Aceptación | Relacionado con (Epic ID) |
|:---------------:|:------:|:------------|:------------------------|:-------------------------:|
| **EP01** | `Real-Time Monitoring & Data Collection` | Sistema de recolección automatizada de datos desde redes sociales y fuentes digitales. | — | — |
| US01 | `Integración de APIs Externas` | Como `Analista`, quiero `conectar APIs de Twitter e Instagram`, para `recolectar menciones automáticamente`. | **Scenario 1:** Vínculo exitoso. **Given** credenciales válidas **When** se conecta la API **Then** inicia la sincronización. <br> **Scenario 2:** Token expirado. **Given** una conexión previa **When** el token vence **Then** el sistema pide re-autenticación. | EP01 |
| US02 | `Filtrado de Exclusión` | Como `Emprendedor`, quiero `excluir keywords irrelevantes`, para `evitar ruido de marcas homónimas`. | **Scenario 1:** Filtro activo. **Given** ruido de homónimos **When** se añade la palabra al "Blacklist" **Then** el feed se limpia. <br> **Scenario 2:** Validación. **Given** intento de keyword vacía **When** se guarda **Then** muestra error de campo obligatorio. | EP01 |
| US03 | `Live Feed Monitor` | Como `Community Manager`, quiero `ver un feed en vivo`, para `reaccionar de inmediato`. | **Scenario 1:** Update dinámico. **Given** dashboard abierto **When** entra mención **Then** aparece al inicio sin recargar. <br> **Scenario 2:** Pausa de flujo. **Given** alto volumen **When** se presiona "Pausa" **Then** el feed se detiene para lectura. | EP01 |
| US04 | `Uso de Webhooks` | Como `Desarrollador`, quiero `usar Webhooks`, para `reducir la latencia de alertas`. | **Scenario 1:** Registro. **Given** URL de escucha **When** se registra en el panel **Then** el sistema envía un JSON de prueba. <br> **Scenario 2:** Reintento. **Given** server destino caído **When** falla el envío **Then** el sistema reintenta 3 veces. | EP01 |
| **EP02** | `AI Sentiment Analysis` | Módulo de procesamiento de lenguaje natural para categorizar el tono emocional. | — | — |
| US05 | `Detección de Sarcasmo` | Como `Gerente`, quiero `identificar sarcasmo`, para `evitar falsos positivos`. | **Scenario 1:** Tono irónico. **Given** frase "Excelente demora" **When** la IA procesa **Then** clasifica como "Negativo". <br> **Scenario 2:** Confianza baja. **Given** frase ambigua **When** IA duda **Then** etiqueta como "Para revisión manual". | EP02 |
| US06 | `Ajuste Manual` | Como `Analista`, quiero `corregir la polaridad manualmente`, para `entrenar mejor a la IA`. | **Scenario 1:** Corrección. **Given** mención mal clasificada **When** se cambia a "Negativo" **Then** se actualiza el dashboard. <br> **Scenario 2:** Log de cambios. **Given** una edición **When** se guarda **Then** registra qué usuario hizo el cambio. | EP02 |
| US07 | `Word Cloud de Sentimiento` | Como `Usuario`, quiero `ver nubes de palabras por sentimiento`, para `identificar temas críticos`. | **Scenario 1:** Filtro negativo. **Given** filtro "Negativo" activo **When** carga nube **Then** muestra términos de queja más frecuentes. <br> **Scenario 2:** Drill-down. **Given** una palabra en la nube **When** se clickea **Then** muestra los posts que la contienen. | EP02 |
| **EP03** | `Crisis Management & Alerts` | Herramientas de detección temprana y protocolos ante incidentes reputacionales. | — | — |
| US08 | `Semáforo de Crisis` | Como `Jefe de PR`, quiero `un semáforo configurable`, para `saber cuándo intervenir legalmente`. | **Scenario 1:** Alerta Roja. **Given** umbral de 50 quejas/hora **When** se alcanza **Then** el dashboard se pone rojo. <br> **Scenario 2:** Personalización. **Given** ajustes de alerta **When** se cambia el límite **Then** el sistema aplica la nueva regla. | EP03 |
| US09 | `Alertas en Telegram/WhatsApp` | Como `Usuario`, quiero `alertas móviles`, para `estar enterado fuera de la oficina`. | **Scenario 1:** Notificación móvil. **Given** crisis detectada **When** usuario vinculado **Then** llega mensaje instantáneo con link. <br> **Scenario 2:** Silent mode. **Given** horario nocturno **When** llega alerta no crítica **Then** el sistema la encola para la mañana. | EP03 |
| US10 | `Asignación de Tickets` | Como `Soporte`, quiero `asignar menciones a miembros del equipo`, para `gestión inmediata`. | **Scenario 1:** Derivación. **Given** queja crítica **When** se asigna a un agente **Then** este recibe notificación de tarea. <br> **Scenario 2:** Cierre de ticket. **Given** ticket resuelto **When** se marca "Finalizado" **Then** sale del flujo de pendientes. | EP03 |
| **EP04** | `Competitive Intelligence` | Análisis comparativo frente a competidores directos. | — | — |
| US11 | `Share of Sentiment` | Como `Gerente`, quiero `ver mi sentimiento vs competencia`, para `saber mi posición en el mercado`. | **Scenario 1:** Gráfico barras. **Given** 2 competidores **When** se genera reporte **Then** muestra ratio comparativo de positividad. <br> **Scenario 2:** Exportación. **Given** gráfico listo **When** se descarga **Then** genera un PNG de alta calidad. | EP04 |
| US12 | `Rastreo de Hashtags Competidores` | Como `Analista`, quiero `monitorear hashtags de competencia`, para `entender sus estrategias`. | **Scenario 1:** Monitor campaña. **Given** hashtag nuevo de competencia **When** se añade **Then** inicia medición de volumen. <br> **Scenario 2:** Alerta viral. **Given** hashtag competidor **When** crece 200% **Then** notifica "Campaña Viral Detectada". | EP04 |
| **EP05** | `Advanced Analytics & Reporting` | Generación de reportes y filtrado profundo de datos. | — | — |
| US13 | `Reportes PDF Programados` | Como `Ejecutivo`, quiero `reportes semanales automáticos`, para `ahorrar tiempo de gestión`. | **Scenario 1:** Envío lunes. **Given** Lunes 8am **When** cronjob corre **Then** envía PDF por correo. <br> **Scenario 2:** Error log. **Given** fallo en PDF **When** falla envío **Then** reintenta en 1 hora y avisa al admin. | EP05 |
| US14 | `Filtro por Alcance (Influencers)` | Como `Usuario`, quiero `filtrar por número de seguidores`, para `priorizar respuestas críticas`. | **Scenario 1:** Filtro 10k. **Given** feed lleno **When** se filtra ">10k fans" **Then** solo muestra cuentas influyentes. <br> **Scenario 2:** Badge dorado. **Given** mención nueva **When** autor tiene >50k fans **Then** marca el post con icono especial. | EP05 |
| US15 | `Heatmap Horario` | Como `Estratega`, quiero `ver horas pico de quejas`, para `ajustar turnos de moderación`. | **Scenario 1:** Generación mapa. **Given** data de 30 días **When** se abre "Insights" **Then** muestra cuadrícula 24/7 de calor. <br> **Scenario 2:** Filtro finde. **Given** heatmap mensual **When** se marca "Sáb/Dom" **Then** actualiza solo para esos días. | EP05 |
| US16 | `Exportación CSV/JSON` | Como `Admin`, quiero `exportar data cruda`, para `análisis en Power BI`. | **Scenario 1:** Exportación. **Given** rango fechas **When** se presiona "Exportar" **Then** descarga CSV con todos los campos. <br> **Scenario 2:** Fondo. **Given** data masiva **When** se exporta **Then** procesa en background y avisa al terminar. | EP05 |
| **EP06** | `User Experience & Collaboration` | Gestión de interfaz, flujos internos y acceso multiplataforma. | — | — |
| US17 | `Onboarding Interactivo` | Como `Usuario nuevo`, quiero `un tutorial guiado`, para `configurar el sistema sin soporte`. | **Scenario 1:** Inicio tour. **Given** login #1 **When** entra dashboard **Then** resalta botones clave con explicación. <br> **Scenario 2:** Skip. **Given** tour activo **When** presiona "Omitir" **Then** cierra tutorial y no vuelve a aparecer. | EP06 |
| US18 | `Notas Internas` | Como `Líder`, quiero `dejar comentarios en menciones`, para `coordinar respuestas con el equipo`. | **Scenario 1:** Nota privada. **Given** mención crítica **When** líder comenta **Then** solo el equipo interno ve la nota. <br> **Scenario 2:** Mención @usuario. **Given** nota interna **When** se usa @nombre **Then** el usuario recibe alerta de mención. | EP06 |
| US19 | `Selector de Workspaces` | Como `Agencia`, quiero `cambiar entre marcas`, para `mantener datos separados`. | **Scenario 1:** Cambio marca. **Given** 2 clientes **When** cambia en el menú lateral **Then** carga métricas de la nueva marca. <br> **Scenario 2:** Independencia. **Given** 2 workspaces **When** cambia keyword en uno **Then** el otro no se ve afectado. | EP06 |
| US20 | `Interfaz Responsiva` | Como `Usuario móvil`, quiero `un diseño adaptable`, para `monitorear desde el celular`. | **Scenario 1:** Vista móvil. **Given** resolución smartphone **When** carga web **Then** los gráficos se apilan verticalmente. <br> **Scenario 2:** Touch target. **Given** interfaz móvil **When** hay botones de acción **Then** tienen tamaño mín de 44px para dedos. | EP06 |
| **EP07** | `Industry Specific Insights (New)` | Basado en entrevistas de Alfredo, Jenifer, Karim, Romina y Esteban. | — | — |
| US21 | `Galería de Casos de Éxito (Alfredo)` | Como `Gerente de Muebles`, quiero `subir fotos de problemas resueltos`, para `mejorar mi imagen ante clientes`. | **Scenario 1:** Subir evidencia. **Given** caso cerrado **When** sube foto de solución **Then** se añade a la galería pública. <br> **Scenario 2:** Tagging. **Given** foto nueva **When** se etiqueta como "Retail" **Then** aparece en el filtro de ese sector. | EP07 |
| US22 | `Monitor de Google Maps (Karim)` | Como `Dueño de Cafetería`, quiero `sincronizar reseñas de Google Maps`, para `no enterarme tarde de quejas de servicio`. | **Scenario 1:** Pull reseñas. **Given** local vinculado **When** entra reseña 1 estrella **Then** el sistema dispara alerta inmediata. <br> **Scenario 2:** Reply direct. **Given** reseña nueva **When** usuario escribe respuesta **Then** se publica en Google Maps desde BrandRadar. | EP07 |
| US23 | `Sugerencia de "Hooks" (Esteban)` | Como `Marketer Audiovisual`, quiero `sugerencias de ganchos basados en tendencias`, para `retener audiencia en los primeros 3 segundos`. | **Scenario 1:** Analizar video. **Given** video con poco alcance **When** pide sugerencia **Then** IA propone 3 ganchos tipo "Sabías que...". <br> **Scenario 2:** Comparativa hooks. **Given** 2 videos con distintos ganchos **When** compara performance **Then** indica cuál retuvo más gente. | EP07 |
| US24 | `Bot de Respuesta de Contingencia (Jenifer)` | Como `Dueña de Boutique`, quiero `respuestas automáticas de cortesía`, para `atender al cliente mientras estoy ocupada`. | **Scenario 1:** Out of office. **Given** queja recibida 2am **When** bot activo **Then** responde "Estamos revisando tu caso, te contactamos en breve". <br> **Scenario 2:** Desactivación. **Given** horario laboral **When** entra mención **Then** el bot se inhibe para permitir respuesta humana. | EP07 |
| US25 | `Tracking de Conversión (Esteban)` | Como `Jefe de Marketing`, quiero `conectar clics en menciones con ventas`, para `medir el ROI de mi estrategia digital`. | **Scenario 1:** UTM Tracking. **Given** link de respuesta **When** cliente clickea y compra **Then** el dashboard marca "Conversión Exitosa". <br> **Scenario 2:** Reporte ROI. **Given** campaña de mes **When** genera reporte **Then** indica costo por mención positiva vs venta. | EP07 |
| US26 | `Monitor de Múltiples Sucursales (Karim)` | Como `Dueño de múltiples locales`, quiero `ver datos de San Isidro y Miraflores por separado`, para `evaluar qué equipo atiende mejor`. | **Scenario 1:** Filtro local. **Given** 2 locales **When** selecciona "Miraflores" **Then** muestra solo sentimientos de esa sede. <br> **Scenario 2:** Ranking interno. **Given** datos de todas las sedes **When** abre reporte global **Then** rankea locales por estrellas promedio. | EP07 |
| US27 | `Detección de Caída de Web (Jenifer)` | Como `E-commerce owner`, quiero `alerta de inactividad de página web`, para `no perder ventas por errores técnicos`. | **Scenario 1:** Web Down. **Given** monitoreo de URL activo **When** sitio devuelve error 404/500 **Then** envía alerta "Sitio Caído". <br> **Scenario 2:** Restore alert. **Given** web caída **When** el servicio vuelve a estar online **Then** envía confirmación "Sitio Recuperado". | EP07 |
| US28 | `Análisis de Campaña Política (Romina)` | Como `Freelance en política`, quiero `monitorear keywords de candidatos específicos`, para `gestionar comunidades municipales`. | **Scenario 1:** Tracking candidato. **Given** keyword "Alcalde X" **When** entra mención **Then** clasifica si es apoyo o denuncia ciudadana. <br> **Scenario 2:** Reporte de vecinos. **Given** menciones de zona **When** genera reporte **Then** agrupa quejas por distritos. | EP07 |
| US29 | `Detección de Competencia Desleal (Jenifer)` | Como `Dueña de Boutique`, quiero `alerta de marcas con precios excesivamente bajos`, para `ajustar mi estrategia competitiva`. | **Scenario 1:** Price drop alert. **Given** monitoreo de competencia **When** detecta post con precios 50% menores **Then** envía alerta de mercado. <br> **Scenario 2:** Comparativa catálogo. **Given** post de competencia **When** IA analiza prenda **Then** indica si es similar a mi stock actual. | EP07 |
| US30 | `Fidelización de Clientes (Karim)` | Como `Gerente de Cafetería`, quiero `identificar clientes frecuentes que dejan reseñas`, para `ofrecerles compensaciones o regalos`. | **Scenario 1:** Identificar fan. **Given** usuario que comenta por 3ra vez **When** publica reseña **Then** el sistema lo marca como "Cliente VIP". <br> **Scenario 2:** Cupón automático. **Given** reseña positiva de VIP **When** se aprueba respuesta **Then** envía código de descuento vía DM. | EP07 |
| US31 | `Archivo de Crisis Pasadas (Alfredo)` | Como `Socio de Empresa`, quiero `ver un histórico de cómo se resolvieron crisis anteriores`, para `no repetir errores del pasado`. | **Scenario 1:** Búsqueda histórica. **Given** crisis nueva **When** busca por "Tipo: Calidad" **Then** muestra cómo se resolvió el caso similar en 2025. <br> **Scenario 2:** Lecciones aprendidas. **Given** caso cerrado **When** se añade "Lección" **Then** se guarda en la wiki interna del equipo. | EP07 |
| US32 | `Optimización de Scripts de Venta (Jenifer)` | Como `Usuario de WhatsApp Business`, quiero `sugerencias de frases para cerrar ventas`, para `evitar carritos abandonados`. | **Scenario 1:** Sugerencia cierre. **Given** chat estancado **When** pide ayuda **Then** IA sugiere "¡Solo nos queda una unidad en tu talla!". <br> **Scenario 2:** A/B Testing frases. **Given** 2 tipos de cierre **When** analiza ventas finalizadas **Then** indica cuál frase convierte más. | EP07 |
| US33 | `Monitor de "Voz del Cliente" (Alfredo)` | Como `Gerente Comercial`, quiero `un reporte de sugerencias de mejora de productos`, para `priorizar la fabricación de muebles`. | **Scenario 1:** Agrupación pedidos. **Given** menciones tipo "Deseo que sea más alto" **When** IA agrupa **Then** muestra "Mejora en altura" como tendencia. <br> **Scenario 2:** Feedback loop. **Given** nueva característica lanzada **When** entran menciones **Then** compara satisfacción vs modelo previo. | EP07 |
| US34 | `Dashboard de Tiempo de Respuesta (Romina)` | Como `Freelance`, quiero `medir cuánto tardo en responder cada mención`, para `cumplir con mis KPIs de atención`. | **Scenario 1:** Tiempo promedio. **Given** 10 respuestas hoy **When** abre reporte operativo **Then** muestra "Tiempo medio: 12 minutos". <br> **Scenario 2:** Alerta demora. **Given** mención negativa sin responder **When** pasan 30 minutos **Then** envía recordatorio "Atención pendiente". | EP07 |
| US35 | `Análisis de "Hooks" de Competencia (Esteban)` | Como `Editor Audiovisual`, quiero `saber qué ganchos están usando otras clínicas dentales`, para `diferenciar mi contenido`. | **Scenario 1:** Benchmarking ganchos. **Given** video de competencia viral **When** IA analiza audio/texto **Then** extrae el hook utilizado. <br> **Scenario 2:** Reporte originalidad. **Given** mi guion nuevo **When** compara con sector **Then** indica si el gancho ya fue muy usado. | EP07 |
| US36 | `Integración de TikTok Metrics (Esteban)` | Como `Marketer`, quiero `ver visualizaciones vs comentarios en TikTok`, para `entender por qué un video no despega`. | **Scenario 1:** Ratio engagement. **Given** video posteado **When** carga data **Then** calcula % de interacción sobre vistas totales. <br> **Scenario 2:** Diagnóstico video. **Given** bajo ratio **When** solicita análisis **Then** IA indica si el problema es el gancho o el desarrollo. | EP07 |
| US37 | `Filtro de "Intención de Compra" (Jenifer)` | Como `Dueña de Boutique`, quiero `detectar usuarios que preguntan por precios/tallas`, para `priorizar su atención sobre otros comentarios`. | **Scenario 1:** Tagging automático. **Given** comentario "¿Precio?" **When** entra al sistema **Then** le asigna etiqueta "Lead Caliente". <br> **Scenario 2:** Alerta venta. **Given** comentario de intención de compra **When** no se responde en 5 min **Then** lanza alerta push sonora. | EP07 |
| US38 | `Reporte de Sentimiento de Empleados (Karim)` | Como `Gerente`, quiero `monitorear menciones sobre la atención de mi personal`, para `gestionar la rotación y capacitación`. | **Scenario 1:** Mención nombre empleado. **Given** reseña "Juan me atendió mal" **When** detecta nombre **Then** vincula la queja al perfil del empleado. <br> **Scenario 2:** Tendencia trato. **Given** datos del mes **When** genera reporte RRHH **Then** indica si las quejas son por "actitud" o "lentitud". | EP07 |
| US39 | `Detección de Influencers del Rubro (Alfredo)` | Como `Socio`, quiero `identificar arquitectos o diseñadores influyentes`, para `proponerles alianzas comerciales`. | **Scenario 1:** Ranking sectorial. **Given** keywords de "Mobiliario" **When** analiza autores **Then** muestra ranking de los más seguidos en ese nicho. <br> **Scenario 2:** Contact info. **Given** perfil identificado **When** se clickea **Then** muestra links a sus webs y perfiles profesionales. | EP07 |
| US40 | `Sugerencia de Respuestas Empáticas (Karim)` | Como `Gerente de Cafetería`, quiero `que la IA redacte disculpas personalizadas`, para `calmar a clientes molestos por mal servicio`. | **Scenario 1:** Borrador disculpa. **Given** queja por café frío **When** presiona "Sugerir respuesta" **Then** redacta: "Lamentamos lo ocurrido, Karim quiere invitarte el próximo...". <br> **Scenario 2:** Ajuste tono. **Given** respuesta sugerida **When** usuario elige "Tono: Formal" **Then** reescribe la disculpa con lenguaje institucional. | EP07 |
| US41 | `Monitor de Proveedores (Alfredo)` | Como `Gerente Comercial`, quiero `monitorear menciones de mis proveedores críticos`, para `anticipar problemas en mi cadena de suministro`. | **Scenario 1:** Alerta proveedor. **Given** proveedor de madera en crisis **When** entra noticia negativa **Then** envía alerta "Riesgo en Suministro". <br> **Scenario 2:** Reputación aliados. **Given** 3 proveedores **When** compara sentimiento **Then** sugiere con quién es más seguro trabajar. | EP07 |
| US42 | `Archivo Visual de Vitrinas (Jenifer)` | Como `Dueña de Boutique`, quiero `guardar fotos de cómo lucían mis redes en fechas de alta venta`, para `replicar el éxito el próximo año`. | **Scenario 1:** Snapshot estacional. **Given** campaña "Día de la Madre" **When** termina el mes **Then** guarda collage de los mejores posts. <br> **Scenario 2:** Comparativa anual. **Given** campaña actual **When** compara con archivo 2025 **Then** indica qué cambios hubo en la recepción del público. | EP07 |
| US43 | `Detección de "Trending Topics" Locales (Romina)` | Como `Gestora Municipal`, quiero `saber qué temas preocupan a los vecinos de Arequipa`, para `orientar la comunicación del alcalde`. | **Scenario 1:** Top temas distrito. **Given** ubicación: Arequipa **When** analiza menciones locales **Then** reporta "Inseguridad" o "Baches" como temas #1. <br> **Scenario 2:** Sentimiento por barrio. **Given** data distrital **When** filtra por zona **Then** muestra qué barrio tiene más quejas actualmente. | EP07 |
| US44 | `Simulador de Impacto de Respuesta (Piero - PR)` | Como `Gerente de PR`, quiero `predecir cómo reaccionará la gente a mi comunicado`, para `evitar que la crisis empeore`. | **Scenario 1:** Test de comunicado. **Given** borrador de respuesta **When** pasa por simulador **Then** indica "Probabilidad de aceptación: 70%". <br> **Scenario 2:** Red flags. **Given** texto de respuesta **When** contiene palabras agresivas **Then** el sistema las resalta y sugiere cambios. | EP07 |
| US45 | `Dashboard de Retención (Esteban)` | Como `Marketer`, quiero `ver en qué segundo exacto los usuarios dejan de ver mis videos`, para `mejorar el montaje audiovisual`. | **Scenario 1:** Punto de fuga. **Given** video de TikTok **When** analiza data de retención **Then** marca con punto rojo el segundo donde el 50% se fue. <br> **Scenario 2:** Sugerencia edición. **Given** punto de fuga detectado **When** pide mejora **Then** sugiere: "Añadir texto dinámico o cambio de plano aquí". | EP07 |


<!--
| Epic / Story ID | Título | Descripción | Criterios de Aceptación | Relacionado con (Epic ID) |
|:---------------:|:------:|:------------|:------------------------|:-------------------------:|
| **EP01** | `Real-Time Monitoring & Data Collection` | *(Descripción del Epic)* | — | — |
| US01 | `[Título de User Story]` | Como `Analista de Marketing`, quiero `conectar las API de Twitter e Instagram al sistema`, para `recolectar menciones de mi marca de forma automatizada.`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| US02 | `[Título de User Story]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| **EP02** | `[Título del Epic 2]` | *(Descripción del Epic)* | — | — |
| US03 | `[Título de User Story]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP02 |
| **EP0n** | `[Landing Page Epic]` | *(Epic para user stories del sitio estático)* | — | — |
| US0n | `[User Story Landing Page]` | Como visitante, deseo `[acción]`, para `[beneficio]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP0n |
| **TS01** | `[Technical Story — API]` | Como Developer, deseo `[endpoint]`, para `[propósito]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[request context]` <br> **When** `[se llama al endpoint]` <br> **Then** `[response esperado]` | — |
-->
---

## 3.2. Impact Mapping

*(Introducción y capturas del Impact Mapping elaborado en la herramienta indicada — UXPressia)*

*(Business Goals deben cumplir criterios SMART. Ejemplo: "Alcanzar los 600 usuarios suscritos al plan A en el lapso de 8 meses.")*

![Impact Map](../assets/impact-mapping/impact-map.png)

*(Explicación del Impact Map: Business Goals, Actors/Personas, Impacts, Deliverables y User Stories)*

---

## 3.3. Product Backlog

*(Introducción al Product Backlog de BrandRadar)*

> **Herramienta utilizada:** `[Pivotal Tracker / JetBrains YouTrack / Jira / Trello]`
>
> **URL del Product Backlog:** [`[URL pública del Product Backlog]`](`[URL]`)

*(Captura del Product Backlog en la herramienta indicada)*

![Product Backlog](../assets/product-backlog/product-backlog.png)

| # Orden | User Story ID | Título | Descripción | Story Points |
|:-------:|:-------------:|:------:|:------------|:------------:|
| 1 | US01 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | `1 / 2 / 3 / 5 / 8` |
| 2 | US02 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| 3 | US03 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| 4 | US04 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| 5 | US05 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| n | TS01 | `[Technical Story]` | Como Developer, deseo `[endpoint]`, para `[propósito]`. | |

---

<div align="center">

[← Capítulo II](./capitulo-2.md) &nbsp;|&nbsp; [Capítulo IV →](./capitulo-4.md) &nbsp;|&nbsp; [← Volver al índice](../../README.md)

</div>
