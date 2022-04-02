---
title: Microsoft 365 Defender
description: Microsoft 365 Defender es una solución coordinada de protección contra amenazas diseñada para proteger dispositivos, identidad, datos y aplicaciones
keywords: introducción a MMicrosoft 365 Defender, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365-defender
- m365solution-scenario
- m365solution-overview
ms.custom:
- admindeeplinkDEFENDER
- intro-overview
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15f4d179d3bc5590e014a15622e462932e8dea7c
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498723"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender es un conjunto de aplicaciones unificado de defensa empresarial previa y posterior a la vulneración que coordina de forma nativa la detección, prevención, investigación y respuesta entre extremos, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados.

Con la solución Microsoft 365 Defender integrada, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos recibe y determinar el alcance completo y el impacto de la amenaza; cómo entró en el entorno, qué está afectado y cómo afecta actualmente a la organización. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto-sanar los buzones, puntos de conexión e identidades de usuario afectados.

<center><h2>Las API de Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>Microsoft Defender para endpoint</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender para Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender para la identidad</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Defender para aplicaciones en la nube</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender guía interactiva

En esta guía interactiva, aprenderá a proteger su organización con Microsoft 365 Defender. Verá cómo Microsoft 365 Defender puede ayudarle a detectar riesgos de seguridad, investigar ataques a su organización y evitar actividades nocivas automáticamente.

[Eche un vistazo a la guía interactiva](https://aka.ms/M365Defender-InteractiveGuide)

## <a name="microsoft-365-defender-protection"></a>Microsoft 365 Defender protección

Microsoft 365 Defender protegen:

- **Endpoints with Defender for Endpoint** : Defender for Endpoint es una plataforma de extremo unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta.
- **Correo electrónico y colaboración con Defender para Office 365**: Defender para Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración.
- **Identities with Defender for Identity and Azure Active Directory (Azure AD) Identity Protection**: Defender for Identity usa las señales locales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. Azure AD Identity Protection automatiza la detección y corrección de riesgos basados en identidades en el entorno basado en la nube Azure AD.
- **Aplicaciones con Microsoft Defender** para aplicaciones en la nube: Microsoft Defender para aplicaciones en la nube es una solución completa entre SaaS que ofrece una visibilidad profunda, controles de datos sólidos y una protección contra amenazas mejorada para las aplicaciones en la nube.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww]

Microsoft 365 Defender la capa entre productos única de Microsoft 365 Defender aumenta los componentes de servicio individuales para:

- Ayuda a proteger contra ataques y coordinar respuestas defensivas en todos los servicios a través del uso compartido de señales y acciones automatizadas.
- Narra la historia completa del ataque en alertas de productos, comportamientos y contexto para los equipos de seguridad uniendo datos de alertas, eventos sospechosos y activos afectados a "incidentes".
- Automatice la respuesta al riesgo desencadenando la recuperación automática de activos afectados a través de la corrección automatizada.
- Permitir que los equipos de seguridad realicen búsquedas de amenazas detalladas y eficaces en los puntos de conexión y Office datos.

Este es un ejemplo de cómo el portal de Microsoft 365 Defender correlaciona todas las alertas relacionadas entre productos en un solo incidente.

:::image type="content" source="../../media/overview-incident.png" alt-text="Página de información general sobre incidentes" lightbox="../../media/overview-incident.png":::

Este es un ejemplo de la lista de alertas relacionadas para un incidente.

:::image type="content" source="../../media/incident-list.png" alt-text="La lista de alertas de un incidente" lightbox="../../media/incident-list.png":::

Este es un ejemplo de búsqueda basada en consultas en la parte superior de los datos sin procesar de correo electrónico y punto de conexión.

:::image type="content" source="../../media/advanced-hunting.png" alt-text=" La página Búsqueda avanzada con detalles de consulta" lightbox="../../media/advanced-hunting.png":::

Microsoft 365 Defender características entre productos incluyen:

- Panel único de vidrio entre productos en el **portal de Microsoft 365 Defender**: una vista central para toda la información sobre detecciones, activos afectados, acciones automatizadas realizadas y pruebas relacionadas en una sola cola y un único panel en Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal</a>. 
- Cola de incidentes **combinados**: para ayudar a los profesionales de seguridad a centrarse en lo que es fundamental al garantizar que el ámbito de ataque completo, los activos afectados y las acciones de corrección automatizadas se agrupan y se ponen a la superficie de forma oportuna. 
- **Respuesta automática a las amenazas**: la información crítica de amenazas se comparte en tiempo real entre los productos Microsoft 365 Defender para ayudar a detener la progresión de un ataque. 

   Por ejemplo, si se detecta un archivo malintencionado en un extremo protegido por Defender para endpoint, le indicará a Defender que Office 365 analice y quite el archivo de todos los mensajes de correo electrónico. Todo el conjunto de seguridad del conjunto de Microsoft 365 bloqueará el archivo a la vista.

- Recuperación automática para dispositivos **, identidades** de usuario y buzones en peligro: Microsoft 365 Defender usa acciones automáticas con tecnología de IA y libros de reproducción para corregir los activos afectados de nuevo a un estado seguro. Microsoft 365 Defender aprovecha las capacidades de corrección automática de los productos del conjunto de programas para garantizar que todos los activos afectados relacionados con un incidente se remedian automáticamente siempre que sea posible.
- **Búsqueda de amenazas** entre productos: los equipos de seguridad pueden aprovechar sus conocimientos organizativos únicos para buscar signos de peligro mediante la creación de sus propias consultas personalizadas sobre los datos sin procesar recopilados por los distintos productos de protección. Microsoft 365 Defender acceso basado en consultas a 30 días de señales sin procesar históricas y datos de alerta en el punto de conexión y Defender para obtener Office 365 datos.

## <a name="get-started"></a>Introducción

Microsoft 365 Defender requisitos de licencia deben cumplirse antes de habilitar el servicio en el portal <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> de Microsoft 365 Defender en Para obtener más información, vea:

- [Requisitos de licencia](prerequisites.md#licensing-requirements)
- [Activar Microsoft 365 Defender](m365d-enable.md)

## <a name="the-microsoft-365-defender-portal"></a>El portal de Microsoft 365 Defender incluye:

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender combina</a> protección, detección, investigación y respuesta a las amenazas  de correo *electrónico,* colaboración *, identidad**, dispositivo* y aplicación, en un lugar central.

Este único panel de cristal reúne las funciones de los portales de seguridad de Microsoft existentes, como el portal de Microsoft 365 Defender y el centro de Office 365 seguridad & cumplimiento. El Microsoft 365 Defender hace hincapié en el acceso rápido a la información, diseños más sencillos y reunir información relacionada para un uso más fácil. Incluye:

- **[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender para Office 365 ayuda a las organizaciones a proteger su empresa con un conjunto de características de prevención, detección, investigación y búsqueda para proteger el correo electrónico y Office 365 recursos.
- **[Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** proporciona protección preventiva, detección posterior a la infracción, investigación automatizada y respuesta para dispositivos de su organización.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** forma parte de la solución de detección y *respuesta extendida (* XDR) de Microsoft que aprovecha la cartera de seguridad de Microsoft 365 para analizar automáticamente los datos de amenazas entre dominios y crear una imagen de un ataque en un único panel.
- **[Microsoft Defender para aplicaciones en](/cloud-app-security/)** la nube es una solución completa entre SaaS y PaaS que ofrece una visibilidad profunda, controles de datos sólidos y protección contra amenazas mejorada para las aplicaciones en la nube.

Si necesita información Office 365 sobre lo que ha cambiado desde el Centro de seguridad & cumplimiento o el portal de Microsoft 365 Defender, vea:

- [Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para punto de conexión en Microsoft 365 Defender](microsoft-365-security-center-mde.md)

> [!NOTE]
> El Microsoft 365 Defender usa y aplica el acceso basado en roles existente y moverá cada modelo de seguridad al portal unificado. Cada carga de trabajo convergente tiene su propio acceso basado en roles. Los roles que ya están en los productos se convergerán en el portal de Microsoft 365 Defender automáticamente. Sin embargo, Microsoft Defender para Aplicaciones en la nube seguirá administrando sus propios roles y permisos.

### <a name="what-to-expect"></a>Qué esperar

Todo el contenido de seguridad que use en el Centro de seguridad de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 & y</a> el centro de seguridad de Microsoft 365 ahora se puede encontrar en el portal de Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">seguridad</a>.

El portal Microsoft 365 Defender ayuda a los equipos de seguridad a investigar y responder a los ataques al incorporar señales de diferentes cargas de trabajo en un conjunto de experiencias unificadas para:

- Incidentes & alertas
- Búsqueda
- Centro de actividades
- Análisis de amenazas

Microsoft 365 Defender enfatiza la *unidad, la claridad* y los objetivos comunes, ya que combina Microsoft Defender para Office 365 y Microsoft Defender para endpoint. La combinación se basó en las prioridades enumeradas a continuación y se realizó sin sacrificar las capacidades que cada conjunto de seguridad trajo a la combinación de:

- Bloques de creación comunes
- Terminología común
- Entidades comunes
- Paridad de características con otras cargas de trabajo

> [!NOTE]
> El Microsoft 365 Defender es accesible sin necesidad de que los clientes tomen pasos de migración o compren una nueva licencia. Por ejemplo, este nuevo portal es accesible para los administradores con una suscripción E3, al igual que para aquellos con Microsoft Defender para el Plan 1 y el Plan 2 de Office 365; sin embargo, Exchange Online Protection o Defender para los clientes del Plan 1 de Office 365 solo ven las características de seguridad que admiten sus licencias de suscripción. El objetivo del portal es centralizar la seguridad.

### <a name="unified-investigations"></a>Investigaciones unificadas

La centralización de la información de seguridad crea un único lugar para investigar incidentes de seguridad en Microsoft 365. Un ejemplo principal son **los incidentes en** **incidentes & alertas** en el inicio rápido de Microsoft 365 Defender.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="La página Incidentes del portal de Microsoft 365 Defender web" lightbox="../../media/converged-incidents-2.png.png":::

Al seleccionar un nombre de incidente se muestra una página que muestra el valor de centralizar la información de seguridad.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="La página Resumen de un incidente en el portal de Microsoft 365 Defender web" lightbox="../../media/converged-incident-info-3.png":::

En la parte superior de una página de incidentes, verá las pestañas **Resumen****,** Alertas **,** Dispositivos, **Usuarios****,** **Buzones**, **Investigaciones, Evidencia** y respuesta, y **Graph datos.** Seleccione estas pestañas para obtener información más detallada. Por ejemplo, la  pestaña Usuarios muestra información para usuarios de cargas de trabajo convergentes (Microsoft Defender para endpoint, Microsoft Defender para identidades y Microsoft Defender para aplicaciones en la nube) y una variedad de orígenes, como servicios de dominio de Active Directory (AD DS), proveedores de identidades de terceros y Azure AD locales. Para obtener más información, vea [Investigar usuarios](investigate-users.md).

Tómese el tiempo para revisar los incidentes de su entorno, profundizar en estas pestañas y practicar la creación de una comprensión de cómo obtener acceso a la información proporcionada para incidentes para distintos tipos de amenazas.

Para obtener más información, [vea incidents in Microsoft 365 Defender](incidents-overview.md).

### <a name="improved-processes"></a>Procesos mejorados

Los controles y el contenido comunes aparecen en el mismo lugar o se condensan en una fuente de datos, lo que facilita la búsqueda. Por ejemplo, configuración unificada.

#### <a name="unified-settings"></a>Configuración unificada

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="La Configuración en el portal de Microsoft 365 Defender web" lightbox="../../media/converged-add-role-9.png":::

#### <a name="permissions--roles"></a>Permisos & roles

:::image type="content" source="../../media/converged-roles-5.png" alt-text="Los roles de extremos & grupos que se muestran en la página Permisos & roles" lightbox="../../media/converged-roles-5.png":::

El acceso a Microsoft 365 Defender se configura con Azure AD globales o mediante roles personalizados. For Defender for Endpoint, see [Assign user access to the Microsoft 365 Defender portal](/microsoft-365/security/defender-endpoint/assign-portal-access). For Defender for Office 365, see [Permissions in the Centro de cumplimiento de Microsoft 365 and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Obtenga más información sobre cómo [administrar el acceso a Microsoft 365 Defender](m365d-permissions.md)
- Obtenga más información sobre cómo [crear roles personalizados](custom-roles.md) en Microsoft 365 Defender

> [!NOTE]
> Microsoft Defender para endpoint en Microsoft 365 Defender admite la concesión de acceso a proveedores de servicios de seguridad [administrados (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) del mismo modo que se concede acceso en el [portal de Microsoft 365 Defender administración](./mssp-access.md).

#### <a name="integrated-reports"></a>Informes integrados

Los informes también se unifican en Microsoft 365 Defender. Los administradores pueden empezar con un informe de seguridad general y bifurcarse en informes específicos sobre puntos de conexión, correo electrónico & colaboración. Los vínculos aquí se generan dinámicamente en función de la configuración de la carga de trabajo.

#### <a name="quickly-view-your-microsoft-365-environment"></a>Ver rápidamente el entorno Microsoft 365 web

La **página** principal muestra muchas de las tarjetas comunes que necesitan los equipos de seguridad. La composición de tarjetas y datos depende del rol de usuario. Dado que Microsoft 365 Defender portal usa control de acceso basado en roles, diferentes roles verán tarjetas que son más significativas para sus trabajos diarios.

Esta información de un vistazo le ayuda a mantenerse al día con las actividades más recientes de su organización. Microsoft 365 Defender reúne señales de diferentes orígenes para presentar una vista holística de su Microsoft 365 entorno.

Las tarjetas entran en estas categorías:

- **Identidades**: supervise las identidades de su organización y realice un seguimiento de comportamientos sospechosos o arriesgados. [Obtenga más información sobre la protección de identidades](/azure/active-directory/identity-protection/overview-identity-protection).
- **Datos** : ayuda a realizar un seguimiento de la actividad del usuario que podría provocar la divulgación de datos no autorizados.
- **Dispositivos** : obtenga información actualizada sobre alertas, actividad de infracción y otras amenazas en sus dispositivos.
- **Aplicaciones** : obtenga información sobre cómo se usan las aplicaciones en la nube en su organización. [Obtén más información sobre las aplicaciones detectadas en Defender para aplicaciones en la nube](/cloud-app-security/discovered-apps).


#### <a name="search-across-entities-preview"></a>Búsqueda entre entidades (versión preliminar)

>[!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.
La barra de búsqueda se encuentra en la parte superior de la página. A medida que escribe, se proporcionan sugerencias para que sea más fácil encontrar entidades. La página de resultados de búsqueda mejorada centraliza los resultados de todas las entidades.

Puede buscar en las siguientes entidades en Defender for Endpoint y Defender for Identity: 

- **Dispositivos** : compatibles con Defender para Endpoint y Defender para Identity. Admite el uso de operadores de búsqueda. 
- **Usuarios** : compatible con Defender for Endpoint, Defender for Identity y Defender for Cloud Apps. 
- **Archivos, DIRECCIONES IP y direcciones URL** : las mismas capacidades que en Defender para endpoint.

    >[!NOTE]
    >Las búsquedas de DIRECCIONES IP y URL coinciden exactamente y no aparecen en la página de resultados de búsqueda: llevan directamente a la página de entidad. 

- **TVM** : las mismas capacidades que en Defender for Endpoint (vulnerabilidades, software y recomendaciones). 

 





### <a name="threat-analytics-with-better-data-coverage"></a>Análisis de amenazas con mejor cobertura de datos

Realice un seguimiento y responda a las amenazas emergentes con la Microsoft 365 Defender de análisis de amenazas integrada:

- Mejor cobertura de datos entre Microsoft Defender para Endpoint y Microsoft Defender para Office 365, haciendo posible la administración combinada de incidentes, la investigación automática, la corrección y la búsqueda proactiva o reactiva de amenazas en todo el dominio.
- Detecciones y mitigaciones relacionadas con el correo electrónico de Microsoft Defender para Office 365, además de los datos de punto de conexión que ya están disponibles en Microsoft Defender para Endpoint.
- Una vista de incidentes relacionados con amenazas que agregan alertas en casos de ataques de extremo a extremo en Microsoft Defender para Endpoint y Microsoft Defender para Office 365 para reducir la cola de trabajo, así como simplificar y acelerar la investigación.
- Los intentos de ataque detectados y bloqueados por Microsoft 365 Defender soluciones. También hay datos que puede usar para impulsar acciones de prevención que mitiguen el riesgo de una mayor exposición y aumenten la resistencia.
- Diseño mejorado que pone la información útil en el punto de mira para ayudarle a identificar rápidamente los datos para centrarse urgentemente en los informes, investigarlos y aprovecharlos.

### <a name="a-centralized-learning-hub"></a>Un concentrador de Learning centralizado

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal de aprendizaje</a> incluye un centro de aprendizaje que proporciona instrucciones oficiales de recursos como el blog de seguridad de Microsoft, la comunidad de seguridad de Microsoft en YouTube y la documentación oficial de docs.microsoft.com.

Dentro del centro de aprendizaje, las instrucciones de colaboración de correo electrónico & (Microsoft Defender para Office 365) están en paralelo con Endpoint (Microsoft Defender para endpoint) y Microsoft 365 Defender aprendizaje.

El centro de aprendizaje se abre con Learning rutas de acceso organizadas en torno a temas como "¿Cómo investigar con Microsoft 365 Defender?" y "Microsoft Defender para Office 365 procedimientos recomendados". Esta sección está actualmente curada por el Grupo de productos de seguridad dentro de Microsoft. Cada Learning de acceso refleja un tiempo proyectado que se tarda en superar los conceptos. Por ejemplo, "Pasos a seguir cuando una cuenta de usuario de Microsoft Defender para Office 365 está en peligro" se prevé que tarde 8 minutos y es un aprendizaje valioso sobre la marcha.

Después de hacer clic en el contenido, puede ser útil marcar este sitio y organizar los marcadores en una carpeta "Seguridad" o "Crítica". Para ver todas Learning rutas de acceso, haga clic en el vínculo Mostrar todo en el panel principal.

> [!NOTE]
> Hay filtros **útiles** en la parte superior del centro de aprendizaje de Microsoft 365 Defender que te permitirán elegir entre productos (actualmente Microsoft 365 Defender, Microsoft Defender para endpoint y Microsoft Defender para Office 365). Observe que se muestra el número de recursos de aprendizaje para cada sección, lo que puede ayudar a los alumnos a realizar un seguimiento de cuántos recursos tienen disponibles para la formación y el aprendizaje.
>
> Junto con el filtro Producto, se enumeran los temas actuales, los tipos de recursos (desde vídeos hasta seminarios web), los niveles de familiaridad o experiencia con las áreas de seguridad, los roles de seguridad y las características del producto.

> [!TIP]
> Hay muchas otras oportunidades de aprendizaje en [Microsoft Learn](/learn/). Encontrará formación en certificación, como el curso [MS-500T02-A: Implementar Microsoft 365 protección contra amenazas](/learn/certifications/courses/ms-500t02).

### <a name="send-us-your-feedback"></a>Envíenos sus comentarios

Necesitamos sus comentarios. We're always looking to improve, so if there's something you'd like to see, [watch this video to find out how you can trust us to read your feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

También puede dejar comentarios de este artículo. En la sección "Comentarios" al final de "Enviar y ver comentarios para", las *opciones son Este* producto o *Esta página*.

Use el **botón Este producto** para obtener comentarios *sobre* el producto:

1. Seleccione *Este producto* en la parte inferior del artículo.
    1. Haz clic con el botón derecho en el botón y "Abrir en una pestaña nueva" si quieres seguir leyendo estas instrucciones.
2. Esto navegará al foro **UserVoice**.
3. Tiene 2 opciones:
    1. Desplácese hacia abajo hasta el cuadro de texto ¿Cómo podemos mejorar el cumplimiento o proteger mejor a los usuarios en Office 365 *?* y pegue en *Microsoft 365 Defender*. Puedes buscar en los resultados una idea como la tuya y votarla por arriba, o usar el botón para **Publicar una nueva idea**.
    1. Si estás seguro de que este problema ya está notificado y quieres aumentar su perfil con un voto (o votos), usa el cuadro  Enviar comentarios a la derecha de UserVoice. Busque *Microsoft 365 Defender,* **busque el problema y use el botón de voto** para aumentar su estado.

Use *esta página para* obtener comentarios sobre el propio artículo. Gracias por sus comentarios. Su voz nos ayuda a mejorar los productos.

### <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>Explorar lo que el portal Microsoft 365 Defender tiene que ofrecer

Siga explorando las características y capacidades de Microsoft 365 Defender:

- [Administrar incidentes y alertas](manage-incidents.md)
- [Hacer seguimiento y responder a amenazas emergentes con el análisis de amenazas](threat-analytics.md)
- [El centro de actividades](m365d-action-center.md)
- [Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](./advanced-hunting-query-emails-devices.md)
- [Reglas de detección personalizada](./custom-detection-rules.md)
- [Alertas de colaboración y correos electrónicos](../../compliance/alert-policies.md#default-alert-policies)
- [Crear una simulación de ataque de suplantación de identidad (phishing)](../office-365-security/attack-simulation-training.md) y [crear una carga útil para entrenar a los equipos](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>Aprendizaje para analistas de seguridad

Con esta ruta de aprendizaje de Microsoft Learn, puede comprender Microsoft 365 Defender y cómo puede ayudar a identificar, controlar y corregir las amenazas de seguridad.

|Aprendizaje:|Detectar y responder a ataques cibernéticos con Microsoft 365 Defender|
|---|---|
|![Icono de aprendizaje de Microsoft 365 Defender.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender unifica las señales de amenazas entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar una protección integrada frente ataques cibernéticos sofisticados. Microsoft 365 Defender es una experiencia central desde la cual investigar y responder a incidentes y buscar proactivamente actividades de ciberseguridad malintencionadas en curso.<p> 1 h 38 min - Learning path - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>Vea también

- [Novedades de Microsoft 365 Defender](whats-new.md)
- [Microsoft Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para endpoint en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
