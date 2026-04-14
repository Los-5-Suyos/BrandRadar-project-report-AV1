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
| **EP01** | `Real-Time Monitoring & Data Collection` | *(Descripción del Epic)* | — | — |
| US01 | `[Título de User Story]` | Como `Analista de Marketing`, quiero `conectar las API de Twitter e Instagram al sistema`, para `recolectar menciones de mi marca de forma automatizada`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| US02 | `[Título de User Story]` | Como `Dueño de un pequeño negocio`, quiero `definir palabras clave de exclusión (keywords negativas)`, para `evitar que el sistema capture ruido o menciones irrelevantes que no pertenecen a mi marca`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| US03 | `[Título de User Story]` | Como `Community Manager`, quiero `ver un feed en vivo de las publicaciones recolectadas`, para `tener una visión inmediata de la conversación actual`. | **Scenario 1:** `[Nombre]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| US04 | `[Título de User Story]` | Como `Desarrollador`, quiero `que el sistema use Webhooks para las notificaciones`, para `asegurar que la latencia entre la publicación y la alerta sea mínima`. | **Scenario 1:** `[Nombre]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |

|:---------------:|:------:|:------------|:------------------------|:-------------------------:|
| **EP02** | `AI Sentiment Analysis` | *(Descripción del Epic)* | — | — |
| US05 | `[Título de User Story]` | Como `Gerente de Marca`, quiero `que el sistema identifique el sarcasmo en los comentarios`, para `que el análisis de sentimiento sea preciso y no arroje falsos positivos`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP02 |
| US06 | `[User Story Landing Page]` | Como `Analista de Datos`, quiero `poder corregir manualmente la polaridad de un comentario (cambiar de neutro a negativo)`, para `entrenar al modelo de IA con contextos específicos de mi industria`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP02 |
| US07 | `[User Story Landing Page]` | Como `Usuario del sistema`, quiero `ver una nube de palabras (word cloud) basada en sentimientos`, para `identificar qué conceptos específicos están asociados a la frustración o alegría del cliente`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP02 |


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
