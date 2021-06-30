---
title: Microsoft 365 Defender información general, que combina MDO, MDE, MDI y MCAS
description: Ventajas en Microsoft 365 Defender, combinando Microsoft Defender para Office 365 (MDO) y Microsoft Defender para endpoint (MDE), con Microsoft Defender for Identity (MDI) y Microsoft Cloud App Security (MCAS). En este artículo se describen Microsoft 365 Defender para los administradores.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, identidades, datos, dispositivos, aplicaciones
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8e37572b07c6d81abc531e204a8cb060f1f6402c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53195002"
---
# <a name="microsoft-365-defender-overview"></a>Microsoft 365 Defender introducción

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).

**Microsoft 365 Defender** ( ) combina protección, detección, investigación y respuesta a correo electrónico, colaboración, identidad y amenazas [https://security.microsoft.com](https://security.microsoft.com) de dispositivos, en un portal central.    

Microsoft 365 Defender reúne las funciones de los portales de seguridad de Microsoft existentes, como Centro de seguridad de Microsoft Defender y el Centro de Office 365 seguridad & cumplimiento. El centro de seguridad hace hincapié en el acceso rápido a la información, diseños más sencillos y reunir información relacionada para un uso más fácil. Este centro incluye:

- **[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender para Office 365 ayuda a las organizaciones a proteger su empresa con un conjunto de características de prevención, detección, investigación y búsqueda para proteger el correo electrónico y Office 365 recursos.
- **[Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** proporciona protección preventiva, detección posterior a la infracción, investigación automatizada y respuesta para dispositivos de su organización.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** forma parte de la  solución de detección y respuesta extendida (XDR) de Microsoft que aprovecha la cartera de seguridad de Microsoft 365 para analizar automáticamente los datos de amenazas entre dominios y crear una imagen de un ataque en un único panel.

Si necesita información sobre lo que ha cambiado desde el Centro de seguridad Office 365 & seguridad o el centro de Centro de seguridad de Microsoft Defender, vea:

- [Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para punto de conexión en Microsoft 365 Defender](microsoft-365-security-center-mde.md)

> [!NOTE]
> El Microsoft 365 de seguridad usa y aplica el acceso basado en roles existente y moverá cada modelo de seguridad al portal unificado. Cada carga de trabajo convergente tiene su propio acceso basado en roles. Los roles que ya están en los productos se convergerán en el portal de seguridad Microsoft 365, automáticamente. Sin embargo, los roles y permisos para MCAS seguirán controlados en MCAS.

## <a name="what-to-expect"></a>Qué esperar

Todo el contenido de seguridad que use en el Centro de seguridad y cumplimiento de Office 365 (protection.office.com) y el Centro de seguridad de Microsoft Defender (securitycenter.microsoft.com) ahora se puede encontrar en el *Microsoft 365 Defender*.

Microsoft 365 Defender ayuda a los equipos de seguridad a investigar y responder a los ataques al incorporar señales de diferentes cargas de trabajo en un conjunto de experiencias unificadas para:

- Alertas de & incidentes
- Búsqueda
- Centro de actividades
- Análisis de amenazas

Microsoft 365 Defender enfatiza la *unidad,* la claridad y los objetivos comunes, ya que combina Microsoft Defender para Office 365 y Microsoft Defender para endpoint. La combinación se basó en las prioridades enumeradas a continuación y se realizó sin sacrificar las capacidades que cada conjunto de seguridad trajo a la combinación de:

- Bloques de creación comunes
- Terminología común
- Entidades comunes
- Paridad de características con otras cargas de trabajo

> [!NOTE]
> Microsoft 365 Defender será accesible sin necesidad de que los clientes tomen medidas de migración o compren una nueva licencia. Por ejemplo, este nuevo portal será accesible para los administradores con una suscripción A3, al igual que para aquellos con Microsoft Defender para Office 365 Plan 1 y Plan 2; sin embargo, Exchange Online Protection o Defender para Office 365 los clientes del Plan 1 solo verán las características de seguridad que admite su licencia de suscripción. El objetivo del nuevo centro es centralizar la seguridad.

## <a name="unified-investigations"></a>Investigaciones unificadas

Los centros de seguridad convergentes crean un único lugar para investigar incidentes de seguridad en Microsoft 365. Un ejemplo principal son **los incidentes en** incidentes & **alertas** en el inicio rápido de Microsoft 365 Defender.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="La página Incidentes de Microsoft 365 Defender.":::

Al seleccionar un nombre de incidente, se muestra una página que muestra el valor de los centros de seguridad convergentes.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Ejemplo de la página Resumen de un incidente en Microsoft 365 Defender":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender](../../media/converged-incident-info-3.png)
--> 

En la parte superior de una página de incidentes, verá las pestañas **Resumen** **,** Alertas , **Dispositivos**, **Usuarios,** **Buzones, Investigaciones** **y** Evidencia.  Seleccione estas pestañas para obtener información más detallada. Por ejemplo,  la pestaña Usuarios muestra información para los usuarios de cargas de trabajo convergentes (Microsoft Defender para endpoint, Microsoft Defender para identidad y Microsoft Cloud App Security) y una amplia variedad de orígenes, como servicios de dominio locales de Active Directory (AD DS), Azure Active Directory (Azure AD) y proveedores de identidades de terceros. Para obtener más información, vea [investigar usuarios](investigate-users.md).

Tómese el tiempo para revisar los incidentes de su entorno, profundizar en estas pestañas y practicar la creación de una comprensión de cómo obtener acceso a la información proporcionada para incidentes para distintos tipos de amenazas.

Para obtener más información, [vea incidents in Microsoft 365 Defender](incidents-overview.md).

## <a name="improved-processes"></a>Procesos mejorados

Los controles y el contenido comunes aparecen en el mismo lugar o se condensan en una fuente de datos, lo que facilita la búsqueda. Por ejemplo, configuración unificada.

### <a name="unified-settings"></a>Configuración unificada

![Hizo clic en "Roles" y abrió la página Configuración, que incluye configuración general, permisos, API y reglas. Abra Permisos y, a continuación, Roles. Muestra todos los roles](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Permisos & roles

![Permissions & Roles que muestra roles de puntos de conexión & grupos, roles y grupos de dispositivos.](../../media/converged-roles-5.png)

 El acceso a Microsoft 365 Defender se configura con Azure Active Directory globales o mediante roles personalizados. Para Defender for Endpoint, vea [Assign user access to Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/assign-portal-access). For Defender for Office 365, see [Permissions in the Centro de cumplimiento de Microsoft 365 and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Obtenga más información sobre cómo [administrar el acceso a Microsoft 365 Defender](m365d-permissions.md)
- Obtenga más información sobre cómo [crear roles personalizados](custom-roles.md) en Microsoft 365 Defender

> [!NOTE]
> Microsoft Defender para endpoint en Microsoft 365 Defender admite la concesión de acceso a proveedores de servicios de seguridad [administrados (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) del mismo modo que se concede acceso en el Centro de seguridad [de Microsoft Defender](./mssp-access.md).

### <a name="integrated-reports"></a>Informes integrados

Los informes también se unifican en Microsoft 365 Defender. Los administradores pueden empezar con un informe de seguridad general y bifurcarse en informes específicos sobre puntos de conexión, correo electrónico & colaboración. Los vínculos aquí se generan dinámicamente en función de la configuración de la carga de trabajo.

### <a name="quickly-view-your-microsoft-365-environment"></a>Ver rápidamente el entorno Microsoft 365 web

La **página** principal muestra muchas de las tarjetas comunes que necesitan los equipos de seguridad. La composición de tarjetas y datos depende del rol de usuario. Dado Microsoft 365 centro de seguridad usa control de acceso basado en roles, diferentes roles verán tarjetas que son más significativas para sus trabajos diarios.  

Esta información de un vistazo le ayuda a mantenerse al día con las actividades más recientes de su organización. Microsoft 365 Defender reúne señales de diferentes orígenes para presentar una vista holística de su Microsoft 365 entorno.

Las tarjetas entran en estas categorías:

- **Identidades:** supervise las identidades de su organización y realice un seguimiento de comportamientos sospechosos o arriesgados. [Obtenga más información sobre la protección de identidades.](/azure/active-directory/identity-protection/overview-identity-protection)
- **Datos:** ayuda a realizar un seguimiento de la actividad del usuario que podría provocar la divulgación de datos no autorizados.
- **Dispositivos:** obtenga información actualizada sobre alertas, actividad de infracción y otras amenazas en sus dispositivos.
- **Aplicaciones:** obtenga información sobre cómo se usan las aplicaciones en la nube en su organización. [Obtenga más información sobre Cloud App Security aplicaciones detectadas.](/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Análisis de amenazas con mejor cobertura de datos
Realice un seguimiento y responda a las amenazas emergentes con la Microsoft 365 Defender de análisis de amenazas integrada:

- Mejor cobertura de datos entre Microsoft Defender para Endpoint y Microsoft Defender para Office 365, lo que permite la administración combinada de incidentes, la investigación automática, la corrección y la búsqueda proactiva o reactiva de amenazas en todo el dominio. 
- Detecciones y mitigaciones relacionadas con el correo electrónico de Microsoft Defender para Office 365, además de los datos de punto de conexión que ya están disponibles en Microsoft Defender para Endpoint.
- Una vista de incidentes relacionados con amenazas que agregan alertas en casos de ataques de extremo a extremo en Microsoft Defender para Endpoint y Microsoft Defender para Office 365 para reducir la cola de trabajo, así como simplificar y acelerar la investigación.
- Los intentos de ataque detectados y bloqueados por Microsoft 365 Defender soluciones. También hay datos que puede usar para impulsar acciones de prevención que mitiguen el riesgo de una mayor exposición y aumenten la resistencia. 
- Diseño mejorado que pone la información útil en el punto de mira para ayudarle a identificar rápidamente los datos para centrarse urgentemente en los informes, investigarlos y aprovecharlos.

## <a name="a-centralized-learning-hub"></a>Un concentrador de Learning centralizado

Microsoft 365 centro de seguridad incluye un centro de aprendizaje que proporciona instrucciones oficiales de recursos como el blog de seguridad de Microsoft, la comunidad de seguridad de Microsoft en YouTube y la documentación oficial en docs.microsoft.com.

Dentro del centro de aprendizaje, las instrucciones de colaboración de correo electrónico & (Microsoft Defender para Office 365) están en paralelo con Endpoint (Microsoft Defender para endpoint) y Microsoft 365 Defender de aprendizaje.

El centro de aprendizaje se abre con Learning rutas de acceso organizadas en torno a temas como "¿Cómo investigar con Microsoft 365 Defender?" y "Microsoft Defender para Office 365 procedimientos recomendados". Esta sección está actualmente curada por el Grupo de productos de seguridad dentro de Microsoft. Cada Learning de acceso refleja un tiempo proyectado que se tarda en pasar por los conceptos. Por ejemplo, 'Pasos que debe seguir cuando se pone en peligro una cuenta de usuario de Microsoft Defender para Office 365' se prevé que tarde 8 minutos y es un aprendizaje valioso sobre la marcha.

Después de hacer clic en el contenido, puede ser útil marcar este sitio y organizar los marcadores en una carpeta "Seguridad" o "Crítica". Para ver todas las Learning rutas de acceso, haga clic en el vínculo Mostrar todo en el panel principal.

> [!NOTE]
> Hay filtros **útiles** en la parte superior del centro de aprendizaje de Microsoft 365 Defender que te permitirán elegir entre productos (actualmente Microsoft 365 Defender, Microsoft Defender para endpoint y Microsoft Defender para Office 365). Observe que se muestra el número de recursos de aprendizaje para cada sección, lo que puede ayudar a los alumnos a realizar un seguimiento de cuántos recursos tienen disponibles para la formación y el aprendizaje.
>
> Junto con el filtro Producto, se enumeran los temas actuales, los tipos de recursos (desde vídeos hasta seminarios web), los niveles de familiaridad o experiencia con las áreas de seguridad, los roles de seguridad y las características del producto.

> [!TIP]
> Hay muchas otras oportunidades de aprendizaje en [Microsoft Learn](/e/learn/). Encontrará formación en certificación, como el curso [MS-500T02-A: Implementar](/learn/certifications/courses/ms-500t02)Microsoft 365 protección contra amenazas .

## <a name="send-us-your-feedback"></a>Envíenos sus comentarios

Necesitamos sus comentarios. Siempre estamos buscando mejorar, por lo que si hay algo que le gustaría ver, envíenos sus [Microsoft 365 Defender comentarios.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

También puede dejar comentarios de este artículo. En la sección "Comentarios" al final de "Enviar y ver comentarios para", las opciones son *Este producto* o *Esta página*.

Use el **botón Este producto** para obtener comentarios *sobre* el producto:

1. Seleccione *Este producto* en la parte inferior del artículo.
    1. Haz clic con el botón derecho en el botón y "Abrir en una pestaña nueva" si quieres seguir leyendo estas instrucciones.
2. Esto navegará al foro **UserVoice**.
3. Tiene 2 opciones:
    1. Desplácese hacia abajo hasta el cuadro de texto ¿Cómo podemos mejorar el cumplimiento o proteger mejor a los usuarios en *Office 365?* y pegue en *Microsoft 365 Defender*. Puedes buscar en los resultados una idea como la tuya y votarla por arriba, o usar el botón **para Publicar una nueva idea**.
    1. Si estás seguro de que este problema ya está notificado y quieres aumentar  su perfil con un voto (o votos), usa el cuadro Enviar comentarios a la derecha de UserVoice. Busque *Microsoft 365 Defender*, **busque el problema y use el botón de voto** para aumentar su estado.

Use *esta página para* obtener comentarios sobre el propio artículo. Gracias por sus comentarios. Su voz nos ayuda a mejorar los productos.

### <a name="explore-what-the-security-center-has-to-offer"></a>Explorar lo que el centro de seguridad tiene que ofrecer

Siga explorando las características y capacidades de Microsoft 365 Defender:

- [Administrar incidentes y alertas](manage-incidents.md)
- [Seguimiento y respuesta a amenazas emergentes con análisis de amenazas](threat-analytics.md)
- [El centro de actividades](m365d-action-center.md)
- [Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](./advanced-hunting-query-emails-devices.md)
- [Reglas de detección personalizada](./custom-detection-rules.md)
- [Alertas de colaboración y correos electrónicos](../../compliance/alert-policies.md#default-alert-policies)
- [Crear una simulación de ataque de suplantación de identidad (phishing)](../office-365-security/attack-simulation-training.md) y [crear una carga útil para entrenar a los equipos](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Información relacionada
- [Microsoft Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para endpoint en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Redirigir cuentas de Microsoft Defender para endpoint a Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)