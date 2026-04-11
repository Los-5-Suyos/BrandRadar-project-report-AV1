[← Capítulo III](./capitulo-3.md) &nbsp;|&nbsp; [← Volver al índice](../../README.md)

---

<div align="center">

# Capítulo IV: Product Design

</div>

---

## 4.1. Style Guidelines

### 4.1.1. General Style Guidelines

*(Explicar las decisiones y referencias visuales sobre conceptos generales: Branding, Typography, Colors, Spacing y tono de comunicación)*

**Branding**

*(Descripción del branding de BrandRadar: logo, isotipo, naming, y principios de identidad visual)*

**Typography**

| Tipo | Fuente | Uso |
|:-----|:------:|:----|
| Display / Heading | `[Fuente principal]` | Títulos y encabezados |
| Body | `[Fuente secundaria]` | Texto de contenido |
| Monospace | `[Fuente monoespaciada]` | Código y datos técnicos |

**Colors**

| Nombre | Hex | Uso |
|:-------|:---:|:----|
| Primary | `#XXXXXX` | Color principal de la marca |
| Secondary | `#XXXXXX` | Color de apoyo |
| Accent | `#XXXXXX` | Énfasis y llamados a la acción |
| Background | `#XXXXXX` | Fondo general |
| Text | `#XXXXXX` | Texto principal |
| Error | `#XXXXXX` | Estados de error |
| Success | `#XXXXXX` | Estados de éxito |

**Spacing**

*(Describir el sistema de espaciado y las unidades base utilizadas)*

**Tono de comunicación**

| Dimensión | Selección |
|:----------|:---------:|
| Divertido / Serio | *(indicar posición en la escala)* |
| Formal / Casual | *(indicar posición en la escala)* |
| Respetuoso / Irreverente | *(indicar posición en la escala)* |
| Entusiasta / Sereno | *(indicar posición en la escala)* |

---

### 4.1.2. Web Style Guidelines

*(Decisiones sobre los estándares visuales y de interacción para responsive web interfaces)*

*(Incluir capturas o especificaciones visuales del Design System basado en Material Design y Angular Material)*

---

## 4.2. Information Architecture


### 4.2.1. Organization Systems

*(Organización Secuencial (Step-by-Step to Accomplish):
Se utiliza en procesos clave como la configuración inicial de monitoreo de una marca y la generación de reportes. La plataforma guía al usuario paso a paso para configurar alertas, conectar fuentes de datos (redes sociales, Google Maps, sitio web propio) y generar informes de reputación. Esto asegura que el usuario complete la configuración de manera eficiente y ordenada, desde la adición de keywords y marcas hasta la activación de notificaciones en tiempo real y la revisión de análisis de sentimiento.)*

### 4.2.2. Labeling Systems

*(Se procura evitar confusiones y que las etiquetas utilizadas sean descriptivas, simples y consistentes con la identidad de BrandRadar.
Etiquetas para la Navbar (Barra de navegación principal):

Dashboard: Muestra una vista general en tiempo real del estado de la reputación digital de la marca, incluyendo alertas recientes, puntuación general y tendencias de sentimiento.
Monitoreo: En esta sección se visualizan todas las menciones, reseñas y comentarios detectados en redes sociales, Google Maps y la web.
Análisis de Sentimiento: Aquí se muestran los resultados del procesamiento de lenguaje natural (positivo, negativo o neutro) junto con tendencias e insights accionables.
Alertas: En esta sección el usuario puede configurar y revisar notificaciones por reseñas negativas, caídas del sitio web u otras crisis reputacionales.
Reportes: Permite generar y descargar informes claros y visuales con datos consolidados para la toma de decisiones.
Fuentes: Gestión de las integraciones con APIs externas (redes sociales, Google, etc.) y configuración de keywords/marcas a monitorear.
Perfil: Acceso a la cuenta del usuario, suscripción, equipo y configuración de notificaciones personales.

Etiquetas para el cuerpo de la web / secciones principales:

Menciones Recientes: Lista cronológica de todas las menciones detectadas con filtros por plataforma y sentimiento.
Reseñas: Muestra calificaciones y comentarios de Google Maps, Facebook, TripAdvisor y otras plataformas de reseñas.
Tendencias: Gráficos y resúmenes de evolución de la reputación a lo largo del tiempo.
Crisis Detectadas: Sección dedicada a alertas críticas y posibles riesgos reputacionales.
Insights: Recomendaciones accionables basadas en el análisis automático de datos.)*


### 4.2.3. SEO Tags and Meta Tags

**Landing Page**
```html
<title>BrandRadar - Monitoreo de Reputación Digital en Tiempo Real</title>
<meta name="description" content="BrandRadar monitorea constantemente tu huella digital en redes sociales, Google Maps y la web. Recibe alertas instantáneas por reseñas negativas, caídas de sitio web y protege la imagen de tu marca con análisis de sentimiento en tiempo real." />
<meta name="keywords" content="monitoreo de reputación digital, reputación online, social listening, análisis de sentimiento, alertas de marca, gestión de reseñas, BrandRadar, protección de imagen corporativa, monitoreo Google Maps, crisis reputacional" />
<meta name="author" content="BrandRadar" />
```

**Web Application**
```html
<title>BrandRadar - Dashboard de Reputación Digital</title>
<meta name="description" content="Plataforma profesional de monitoreo en tiempo real de menciones, reseñas y sentimiento de marca. Alertas automáticas, análisis con IA y reportes accionables para PyMEs y agencias digitales." />
<meta name="keywords" content="monitoreo de marca, análisis de sentimiento, alertas reputacionales, social media monitoring, google maps reseñas, gestión de crisis online, herramienta de reputación digital, brand monitoring, brandradar" />
<meta name="author" content="BrandRadar" />
```

### 4.2.4. Searching Systems

*(Se expondrán los sistemas de búsqueda implementados para ayudar a los usuarios (dueños de PyMEs y account managers de agencias) a encontrar rápidamente la información que necesitan sobre su huella digital.
En la Landing Page, los sistemas de búsqueda son estáticos y se centran en la navegación intuitiva hacia las secciones de beneficios, precios y contacto.
En la aplicación web se implementan los siguientes métodos avanzados de búsqueda y filtrado:

Método de búsqueda por barra: Búsqueda libre por nombre de marca, keyword, frase específica o URL del sitio web.
Filtrado de búsqueda:
Por plataforma (Instagram, Facebook, Google Maps, Twitter/X, TripAdvisor, web general, etc.)
Por sentimiento (positivo, negativo, neutro)
Por rango de fecha o período de tiempo
Por tipo de mención (reseña, comentario, noticia, mención en redes)
Por nivel de criticidad (alertas altas, medias, bajas)
Por fuente específica o competidor (para benchmarking)


Estos filtros combinados permiten a los usuarios aislar rápidamente menciones negativas, crisis emergentes o tendencias positivas.)*

### 4.2.5. Navigation Systems

*(BrandRadar ha implementado un enfoque intuitivo, limpio y eficiente para guiar a los usuarios a través de la plataforma. La barra de navegación superior es fija y está organizada por prioridad de uso (Dashboard primero, luego Monitoreo y Alertas), facilitando el acceso rápido a las funciones más críticas como las alertas en tiempo real.
Adicionalmente, se incluye:

Navegación lateral (sidebar) en el Dashboard para acceder rápidamente a resúmenes por marca o cliente.
Breadcrumbs (migas de pan) en páginas profundas para mostrar la ruta (ejemplo: Dashboard > Monitoreo > Reseñas Google Maps).
Botones de acción contextuales (como “Ver todas las alertas” o “Generar reporte”) en cada sección para reducir clics y mejorar la experiencia.

La navegación está diseñada pensando en dos segmentos principales: dueños de PyMEs (experiencia simple y visual) y account managers de agencias (capacidad de gestionar múltiples marcas desde un solo panel centralizado).)*

---

## 4.3. Landing Page UI Design

*(Introducción explicando cómo se traducen las decisiones de diseño y arquitectura de información)*

### 4.3.1. Landing Page Wireframe

*(Wireframes del Landing Page para Desktop Web Browser y Mobile Web Browser)*

**Desktop Web Browser**

![Landing Page Wireframe Desktop](../assets/landing-page/wireframe-desktop.png)

**Mobile Web Browser**

![Landing Page Wireframe Mobile](../assets/landing-page/wireframe-mobile.png)

### 4.3.2. Landing Page Mock-up

*(Mock-ups del Landing Page para Desktop y Mobile, con Design System aplicado)*

**Desktop Web Browser**

![Landing Page Mockup Desktop](../assets/landing-page/mockup-desktop.png)

**Mobile Web Browser**

![Landing Page Mockup Mobile](../assets/landing-page/mockup-mobile.png)

---

## 4.4. Web Applications UX/UI Design

*(Propuesta visual y de interacción para las aplicaciones web)*

### 4.4.1. Web Applications Wireframes

*(Wireframes de las aplicaciones web con principios de diseño inclusivo y arquitectura de información aplicados)*

![Web App Wireframes](../assets/web-app/wireframes.png)

### 4.4.2. Web Applications Wireflow Diagrams

*(Un Wireflow por cada User goal, considerando los User Personas definidos)*

**User goal: `[Nombre del User goal]`**

*(Descripción del flujo especificado)*

![Wireflow Diagrama 1](../assets/web-app/wireflow-1.png)

---

**User goal: `[Nombre del User goal]`**

*(Descripción del flujo especificado)*

![Wireflow Diagrama 2](../assets/web-app/wireflow-2.png)

### 4.4.3. Web Applications Mock-ups

*(Mock-ups de las aplicaciones web con Design System aplicado)*

![Web App Mockups](../assets/web-app/mockups.png)

### 4.4.4. Web Applications User Flow Diagrams

*(User Flows incluyendo Mock-ups de vistas, happy paths y unhappy paths)*

**User goal: `[Nombre del User goal]`**

*(Descripción de los flujos y condiciones especificadas)*

![User Flow Diagrama 1](../assets/web-app/user-flow-1.png)

---

## 4.5. Web Applications Prototyping

*(Introducción explicando los principales criterios para las decisiones de interacción)*

*(Prototipos de UI para Desktop y Mobile Web Browser con simulación de interacción y navegación)*

**Prototipo Desktop**

![Screenshot Prototipo Desktop](../assets/prototypes/prototype-desktop-screenshot.png)

[Ver video de prototipo Desktop en Microsoft Stream](`URL`)

**Prototipo Mobile**

![Screenshot Prototipo Mobile](../assets/prototypes/prototype-mobile-screenshot.png)

[Ver video de prototipo Mobile en Microsoft Stream](`URL`)

---

## 4.6. Domain-Driven Software Architecture

### 4.6.1. Design-Level Event Storming

*(Introducción y explicación del proceso de Design-Level EventStorming realizado. Referencia: https://bit.ly/dles-guide)*

*(Capturas del Event Storming elaborado en LucidChart / Miro)*

![Design Level Event Storming](../assets/event-storming/design-level-event-storming.png)

*(Identificación de Bounded Contexts, Aggregates, Events, Commands and Queries)*

### 4.6.2. Software Architecture Context Diagram

*(Introducción y explicación del Context Diagram — C4 Model elaborado en Structurizr)*

*(El sistema como recuadro central, rodeado por usuarios y sistemas externos con los que interactúa)*

![Software Architecture Context Diagram](../assets/architecture/context-diagram.png)

*(Explicación del diagrama)*

### 4.6.3. Software Architecture Container Diagrams

*(Introducción y explicación del Container Diagram — C4 Model)*

*(Elementos de alto nivel de la arquitectura, distribución de responsabilidades, tecnologías y comunicación entre containers)*

![Software Architecture Container Diagram](../assets/architecture/container-diagram.png)

*(Explicación del diagrama)*

### 4.6.4. Software Architecture Components Diagrams

*(Component Diagrams para cada Container identificado — C4 Model)*

**Bounded Context: `[Nombre del Bounded Context]`**

![Component Diagram BC1](../assets/architecture/component-diagram-bc1.png)

*(Explicación de los components, sus responsabilidades y detalles de implementación/tecnología)*

---

## 4.7. Software Object-Oriented Design

*(Introducción resumiendo las principales características de los diagramas)*

### 4.7.1. Class Diagrams

*(Class Diagrams UML para cada bounded context, incluyendo clases, interfaces, enumeraciones, atributos, métodos, scope y relaciones con multiplicidad)*

**Bounded Context: `[Nombre del Bounded Context]`**

![Class Diagram BC1](../assets/class-diagrams/class-diagram-bc1.png)

*(Explicación del Class Diagram)*

---

## 4.8. Database Design

*(Introducción resumiendo las principales características de los Database Diagrams)*

### 4.8.1. Database Diagrams

*(Database Diagrams para cada bounded context — tablas, columnas, constraints, relaciones)*

**Bounded Context: `[Nombre del Bounded Context]`**

![Database Diagram BC1](../assets/database/database-diagram-bc1.png)

*(Explicación del Database Diagram)*

---

<div align="center">

[← Capítulo III](./capitulo-3.md) &nbsp;|&nbsp; [Capítulo V →](./capitulo-5.md) &nbsp;|&nbsp; [← Volver al índice](../README.md)

</div>
