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
| **EP01** | `Real-Time Monitoring & Data Collection` | Sistema de recolección automatizada de datos desde redes sociales y fuentes digitales para el monitoreo de marcas. | — | — |
| US01 | `Integración de APIs Externas` | Como `Analista de Marketing`, quiero `conectar las API de Twitter e Instagram al sistema`, para `recolectar menciones de mi marca de forma automatizada`. | **Scenario 1:** Vincular cuenta exitosamente <br> **Given** que el usuario está en la sección de integraciones <br> **When** ingresa las credenciales válidas de la API <br> **Then** el sistema confirma la conexión y empieza a sincronizar menciones. <br> **Scenario 2:** Credenciales expiradas <br> **Given** que una cuenta ya estaba vinculada <br> **When** el token de la API expira <br> **Then** el sistema envía una notificación al usuario solicitando la re-autenticación. | EP01 |
| US02 | `Filtrado de Exclusión` | Como `Dueño de un pequeño negocio`, quiero `definir palabras clave de exclusión (keywords negativas)`, para `evitar que el sistema capture ruido o menciones irrelevantes que no pertenecen a mi marca`. | **Scenario 1:** Agregar keyword de exclusión <br> **Given** que existen menciones de homónimos irrelevantes <br> **When** el usuario añade la palabra al "Blacklist" <br> **Then** el feed deja de mostrar publicaciones que contengan dicho término. <br> **Scenario 2:** Validación de palabras clave <br> **Given** que el usuario intenta agregar una keyword vacía <br> **When** presiona el botón de guardar <br> **Then** el sistema muestra un error indicando que el campo es obligatorio. | EP01 |
| US03 | `Live Feed Monitor` | Como `Community Manager`, quiero `ver un feed en vivo de las publicaciones recolectadas`, para `tener una visión inmediata de la conversación actual`. | **Scenario 1:** Actualización dinámica <br> **Given** que el usuario tiene abierto el dashboard principal <br> **When** una nueva mención es detectada por el backend <br> **Then** la interfaz se actualiza automáticamente mostrando el nuevo post al inicio. <br> **Scenario 2:** Pausa de feed <br> **Given** un flujo masivo de menciones <br> **When** el usuario activa el botón de "Pausa" <br> **Then** el feed deja de desplazarse para permitir la lectura de un post específico. | EP01 |
| US04 | `Implementación de Webhooks` | Como `Desarrollador`, quiero `que el sistema use Webhooks para las notificaciones`, para `asegurar que la latencia entre la publicación y la alerta sea mínima`. | **Scenario 1:** Registro de Endpoint <br> **Given** que el desarrollador tiene una URL de escucha configurada <br> **When** registra el Webhook en el panel de BrandRadar <br> **Then** el sistema envía un paquete JSON de prueba para validar la conexión. <br> **Scenario 2:** Reintento por fallo de servidor <br> **Given** que el servidor de destino devuelve un error 500 <br> **When** el Webhook intenta enviar datos <br> **Then** el sistema aplica una política de reintento exponencial antes de desactivar el webhook. | EP01 |
| **EP02** | `AI Sentiment Analysis` | Módulo de procesamiento de lenguaje natural (NLP) encargado de categorizar el tono emocional de las menciones recolectadas. | — | — |
| US05 | `Detección de Sarcasmo e Ironía` | Como `Gerente de Marca`, quiero `que el sistema identifique el sarcasmo en los comentarios`, para `que el análisis de sentimiento sea preciso y no arroje falsos positivos`. | **Scenario 1:** Clasificación de tono irónico <br> **Given** un comentario con palabras positivas pero contexto negativo <br> **When** el motor de IA procesa el texto <br> **Then** lo clasifica correctamente como "Negativo" basándose en el análisis de contexto. <br> **Scenario 2:** Reporte de confianza <br> **Given** una frase extremadamente ambigua <br> **When** la IA procesa el texto <br> **Then** el sistema asigna una etiqueta de "Sentimiento Incierto" para revisión manual. | EP02 |
| US06 | `Ajuste Manual de Polaridad` | Como `Analista de Datos`, quiero `poder corregir manualmente la polaridad de un comentario (cambiar de neutro a negativo)`, para `entrenar al modelo de IA con contextos específicos de mi industria`. | **Scenario 1:** Corrección de etiqueta <br> **Given** una mención mal categorizada por el sistema <br> **When** el analista selecciona la opción "Corregir Sentimiento" <br> **Then** el sistema actualiza la métrica y guarda la corrección para mejorar el algoritmo. <br> **Scenario 2:** Historial de cambios <br> **Given** que un comentario fue corregido <br> **When** se consulta el detalle de la mención <br> **Then** se muestra un registro de quién realizó el cambio y la fecha. | EP02 |
| US07 | `Visualización de Word Cloud` | Como `Usuario del sistema`, quiero `ver una nube de palabras (word cloud) basada en sentimientos`, para `identificar qué conceptos específicos están asociados a la frustración o alegría del cliente`. | **Scenario 1:** Generación de nube por sentimiento <br> **Given** que el usuario selecciona el filtro "Sentimiento Negativo" <br> **When** carga el reporte visual <br> **Then** se muestran los términos más repetidos en las quejas con un tamaño proporcional a su frecuencia. <br> **Scenario 2:** Navegación desde la nube <br> **Given** una palabra resaltada en la nube <br> **When** el usuario hace clic sobre ella <br> **Then** el sistema filtra el feed para mostrar solo los comentarios que contienen esa palabra. | EP02 |
| **EP03** | `Crisis Management & Alerts` | Herramientas de detección temprana y protocolos de acción ante incidentes que pongan en riesgo la reputación de la marca. | — | — |
| US08 | `Configuración de Semáforo de Crisis` | Como `Jefe de PR`, quiero `establecer un "Semáforo de Crisis" configurable`, para `que el equipo sepa visualmente cuándo la situación requiere intervención legal o corporativa`. | **Scenario 1:** Activación de Alerta Roja <br> **Given** un umbral de 50 menciones negativas en menos de una hora <br> **When** se alcanza o supera dicho límite <br> **Then** el dashboard principal cambia a color rojo y emite una alerta visual persistente. <br> **Scenario 2:** Personalización de umbrales <br> **Given** que el usuario está en ajustes de alerta <br> **When** modifica el valor de alerta "Ámbar" a 20 menciones <br> **Then** el sistema guarda la nueva regla para ese workspace específico. | EP03 |
| US09 | `Alertas Multicanal en Móvil` | Como `Usuario`, quiero `recibir alertas de crisis vía Telegram o WhatsApp`, para `estar enterado incluso si no estoy frente a la computadora`. | **Scenario 1:** Notificación externa inmediata <br> **Given** que el sistema detecta una anomalía reputacional <br> **When** el usuario tiene vinculado su perfil de mensajería <br> **Then** recibe un mensaje instantáneo con el resumen de la crisis y un enlace de acceso rápido. <br> **Scenario 2:** Desactivación temporal <br> **Given** que el usuario está fuera de horario laboral <br> **When** activa el modo "No molestar" en la app <br> **Then** el sistema silencia las notificaciones externas hasta que se desactive el modo. | EP03 |
| US10 | `Asignación de Tickets de Respuesta` | Como `Operador de Soporte`, quiero `asignar una mención negativa a un miembro específico del equipo`, para `que se gestione como un ticket de atención al cliente de forma inmediata`. | **Scenario 1:** Derivación de caso crítico <br> **Given** una mención negativa detectada <br> **When** el operador selecciona a un responsable del equipo de atención <br> **Then** el sistema crea un ticket y notifica al responsable para su resolución. <br> **Scenario 2:** Reasignación de ticket <br> **Given** un ticket ya asignado a un usuario inactivo <br> **When** el supervisor cambia el responsable <br> **Then** el nuevo asignado recibe la notificación y el anterior pierde el acceso de edición. | EP03 |
| **EP04** | `Competitive Intelligence` | Análisis comparativo de presencia y sentimiento frente a competidores directos en el mercado digital. | — | — |
| US11 | `Gráfico de Share of Sentiment` | Como `Gerente Comercial`, quiero `ver un gráfico de "Share of Sentiment" frente a la competencia`, para `saber si mi marca es más querida o criticada que el líder del sector`. | **Scenario 1:** Comparación de positividad <br> **Given** que el usuario ha configurado 2 marcas competidoras <br> **When** visualiza el dashboard comparativo <br> **Then** el sistema muestra un gráfico de barras con el ratio de menciones positivas/negativas de cada empresa. <br> **Scenario 2:** Exportación de comparativa <br> **Given** el gráfico de Share of Sentiment generado <br> **When** el usuario selecciona "Descargar imagen" <br> **Then** el sistema exporta el gráfico en formato PNG de alta resolución. | EP04 |
| US12 | `Rastreo de Hashtags Competidores` | Como `Analista`, quiero `rastrear los hashtags de las campañas de mis competidores`, para `entender qué estrategias les están funcionando mejor`. | **Scenario 1:** Monitor de campaña externa <br> **Given** que la competencia lanza un nuevo hashtag <br> **When** el analista lo añade a la lista de seguimiento <br> **Then** el sistema empieza a medir el alcance y volumen de dicho hashtag en tiempo real. <br> **Scenario 2:** Alerta de tendencia competidora <br> **Given** un hashtag de competencia bajo monitoreo <br> **When** su volumen de uso crece un 200% en un día <br> **Then** el sistema envía una alerta de "Campaña Viral Detectada". | EP04 |
| **EP05** | `Advanced Analytics & Reporting` | Generación de reportes detallados y filtrado profundo de grandes volúmenes de datos para la toma de decisiones. | — | — |
| US13 | `Reportes Automatizados PDF` | Como `Ejecutivo`, quiero `programar el envío automático de reportes semanales a mi correo`, para `no tener que entrar manualmente a la plataforma para estar informado`. | **Scenario 1:** Envío de resumen semanal <br> **Given** que es lunes a las 08:00 AM <br> **When** se cumple el horario de reporte programado <br> **Then** el sistema genera un PDF con los KPIs de la semana anterior y lo envía al correo registrado. <br> **Scenario 2:** Fallo en generación de reporte <br> **Given** un error técnico en el servidor de PDF <br> **When** el sistema intenta enviar el reporte programado <br> **Then** se registra el error y se reintenta el envío una hora después notificando al administrador. | EP05 |
| US14 | `Filtro por Alcance de Influencer` | Como `Usuario`, quiero `filtrar los datos por "Influencia del Autor"`, para `priorizar la respuesta a aquellos usuarios que tienen más de 10,000 seguidores`. | **Scenario 1:** Identificación de cuentas clave <br> **Given** una lista extensa de menciones <br> **When** el usuario activa el filtro de ">10k seguidores" <br> **Then** el sistema muestra únicamente los posts realizados por cuentas con ese nivel de influencia. <br> **Scenario 2:** Ordenamiento por seguidores <br> **Given** el feed filtrado por influencia <br> **When** el usuario selecciona "Ordenar de mayor a menor" <br> **Then** el sistema posiciona las menciones de los perfiles con más seguidores en la parte superior. | EP05 |
| US15 | `Heatmap de Menciones Negativas` | Como `Estratega de Contenido`, quiero `visualizar en qué horas del día se producen más menciones negativas`, para `ajustar mis horarios de publicación y moderación`. | **Scenario 1:** Análisis de horas pico <br> **Given** un set de datos de los últimos 30 día <br> **When** se genera el mapa de calor <br> **Then** el sistema resalta visualmente los bloques horarios con mayor frecuencia de quejas de usuarios. <br> **Scenario 2:** Filtrado por día de la semana <br> **Given** un mapa de calor mensual <br> **When** el usuario selecciona solo "Sábados y Domingos" <br> **Then** el mapa se actualiza para mostrar el comportamiento de crisis únicamente en fines de semana. | EP05 |
| US16 | `Exportación de Data Cruda (JSON/CSV)` | Como `Administrador`, quiero `exportar los datos crudos en formato CSV o JSON`, para `poder procesarlos en otras herramientas de Business Intelligence`. | **Scenario 1:** Exportación para análisis externo <br> **Given** que el administrador necesita los datos en PowerBI <br> **When** selecciona el rango de fechas y presiona "Exportar" <br> **Then** el sistema genera un archivo CSV con todos los metadatos de las menciones seleccionadas. <br> **Scenario 2:** Límite de registros para exportación <br> **Given** una solicitud de exportación de más de 100,000 filas <br> **When** el proceso es muy pesado <br> **Then** el sistema procesa el archivo en segundo plano y envía un link de descarga al correo cuando está listo. | EP05 |
| **EP06** | `User Experience & Collaboration` | Gestión de interfaz de usuario, flujos de trabajo internos y acceso multiplataforma. | — | — |
| US17 | `Onboarding de Usuario Nuevo` | Como `Usuario nuevo`, quiero `tener un tutorial interactivo (Onboarding) al ingresar por primera vez`, para `aprender a configurar mis tableros sin necesidad de soporte técnico`. | **Scenario 1:** Inicio de tour guiado <br> **Given** que es el primer login del usuario <br> **When** carga el dashboard principal <br> **Then** el sistema resalta los botones de configuración de keywords y muestra una breve explicación de su uso. <br> **Scenario 2:** Omitir tutorial <br> **Given** el inicio del tour interactivo <br> **When** el usuario presiona el botón "Saltar tutorial" <br> **Then** el sistema cierra el tour y marca la tarea como completada para que no vuelva a aparecer. | EP06 |
| US18 | `Comentarios Internos de Equipo` | Como `Líder de Equipo`, quiero `dejar comentarios internos en las menciones guardadas`, para `coordinar con mis compañeros la mejor respuesta a un cliente`. | **Scenario 1:** Colaboración en respuesta <br> **Given** una mención negativa de alta importancia <br> **When** el líder escribe una nota interna en el panel de detalle <br> **Then** la nota es visible para el equipo de soporte sin que el cliente final pueda verla. <br> **Scenario 2:** Notificación de mención en nota <br> **Given** un hilo de comentarios internos <br> **When** un miembro etiqueta a otro usando "@nombre" <br> **Then** el usuario etiquetado recibe una notificación interna para revisar la mención. | EP06 |
| US19 | `Selector de Multiespacio (Workspaces)` | Como `Usuario con varias marcas`, quiero `cambiar entre diferentes espacios de trabajo (workspaces)`, para `mantener la información de mis distintos clientes separada`. | **Scenario 1:** Cambio de contexto de cliente <br> **Given** que el usuario maneja dos marcas distintas <br> **When** selecciona el Workspace B en el menú lateral <br> **Then** el sistema oculta los datos de la Marca A y carga exclusivamente las métricas de la Marca B. <br> **Scenario 2:** Creación de nuevo Workspace <br> **Given** la necesidad de monitorear un nuevo proyecto <br> **When** el usuario completa el nombre y configuración del nuevo workspace <br> **Then** el sistema crea un entorno vacío e independiente para la nueva marca. | EP06 |
| US20 | `Optimización de Interfaz Móvil` | Como `Usuario móvil`, quiero `que la interfaz del dashboard sea totalmente responsiva`, para `revisar las métricas desde mi smartphone con comodidad`. | **Scenario 1:** Navegación en pantalla pequeña <br> **Given** que el usuario accede desde un navegador móvil <br> **When** visualiza los gráficos de sentimiento <br> **Then** el diseño se adapta verticalmente permitiendo una lectura fluida sin necesidad de zoom horizontal. <br> **Scenario 2:** Accesibilidad táctil <br> **Given** la interfaz móvil <br> **When** el usuario interactúa con botones de acción rápida <br> **Then** el tamaño de los elementos táctiles es de al menos 44x44px para evitar errores de selección. | EP06 |


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
