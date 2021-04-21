---
title: Vista general del Centro de seguridad de Microsoft 365
description: Ventajas en el centro de seguridad de Microsoft 365, que combina Microsoft Defender para Office 365 (MDO) y Microsoft Defender para endpoint (MDE), con Microsoft Defender for Identity (MDI) y Microsoft Cloud App Security (MCAS). En este artículo se describen los avances del Centro de seguridad de Microsoft 365 para administradores.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, identidades, datos, dispositivos, aplicaciones
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/07/2021
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
ms.openlocfilehash: 2e1553b231692d184146897ddc05e11930ed1bf0
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903979"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Información general del centro de seguridad unificado de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).

El centro de seguridad mejorado de **Microsoft 365** ( ) combina protección, detección, investigación y respuesta a las amenazas de correo electrónico, colaboración, identidad y [https://security.microsoft.com](https://security.microsoft.com) dispositivos en un portal central.    

El Centro de seguridad de Microsoft 365 reúne las funciones de los portales de seguridad de Microsoft existentes, como el Centro de seguridad de Microsoft Defender y el Centro de & seguridad de Office 365. El centro de seguridad hace hincapié en el acceso rápido a la información, diseños más sencillos y reunir información relacionada para un uso más fácil. Este centro incluye:

- **[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender para Office 365 ayuda a las organizaciones a proteger su empresa con un conjunto de características de prevención, detección, investigación y búsqueda para proteger el correo electrónico y los recursos de Office 365.
- **[Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** proporciona protección preventiva, detección posterior a la infracción, investigación automatizada y respuesta para dispositivos de su organización.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** forma parte de la solución de detección y respuesta extendida (XDR) de Microsoft que aprovecha la cartera de seguridad de Microsoft 365 para analizar automáticamente los datos de amenazas entre dominios y crear una imagen de un ataque en un único panel. 

Si necesita información sobre lo que ha cambiado desde el Centro de seguridad de Office 365 & cumplimiento o el Centro de seguridad de Microsoft Defender, vea:

- [Defender para Office 365 en el Centro de seguridad de Microsoft 365.](microsoft-365-security-center-mdo.md)
- [Defender para punto de conexión en el Centro de seguridad de Microsoft 365.](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Qué esperar

Todo el contenido de seguridad que use en el Centro de seguridad y cumplimiento de Office 365 (protection.office.com) y el Centro de seguridad de Microsoft Defender (securitycenter.microsoft.com) ahora puede encontrarse en el Centro de seguridad de *Microsoft 365*.

El Centro de seguridad de Microsoft 365 ayuda a los equipos de seguridad a investigar y responder a los ataques al incorporar señales de diferentes cargas de trabajo en un conjunto de experiencias unificadas para:

- Alertas de & incidentes
- Búsqueda
- Centro de actividades
- Análisis de amenazas

El Centro de seguridad de Microsoft 365 enfatiza la *unidad,* la claridad y los objetivos comunes a medida que combina Microsoft Defender para Office 365 y Microsoft Defender para endpoint. La combinación se basó en las prioridades enumeradas a continuación y se realizó sin sacrificar las capacidades que cada conjunto de seguridad trajo a la combinación de:

- Bloques de creación comunes
- Terminología común
- Entidades comunes
- Paridad de características con otras cargas de trabajo

## <a name="unified-investigations"></a>Investigaciones unificadas

Los centros de seguridad convergentes crean un único lugar para investigar incidentes de seguridad en Microsoft 365. Un ejemplo principal son **los incidentes** en incidentes **& alertas** en el inicio rápido del centro de seguridad de Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Página Incidentes en el Centro de seguridad de Microsoft 365.":::

Al seleccionar un nombre de incidente, se muestra una página que muestra el valor de los centros de seguridad convergentes.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Ejemplo de la página Resumen de un incidente en el Centro de seguridad de Microsoft 365":::

<!--
![Example of the Summary page for an incident in the Microsoft 365 security center](../../media/converged-incident-info-3.png)
--> 

En la parte superior de una página de incidentes, verá las pestañas **Resumen** **,** Alertas , **Dispositivos**, **Usuarios,** **Buzones, Investigaciones** **y** Evidencia.  Seleccione estas pestañas para obtener información más detallada. Por ejemplo,  la pestaña Usuarios muestra información para los usuarios de cargas de trabajo convergentes (Microsoft Defender para endpoint, Microsoft Defender para Identidad y Microsoft Cloud App Security) y una amplia variedad de orígenes, como servicios de dominio de Active Directory (AD DS), Azure Active Directory (Azure AD) y proveedores de identidades de terceros. Para obtener más información, vea [investigar usuarios](investigate-users.md).

Tómese el tiempo para revisar los incidentes de su entorno, profundizar en estas pestañas y practicar la creación de una comprensión de cómo obtener acceso a la información proporcionada para incidentes para distintos tipos de amenazas.

Para obtener más información, vea incidentes en el Centro de seguridad de [Microsoft 365](incidents-overview.md).

## <a name="improved-processes"></a>Procesos mejorados

Los controles y el contenido comunes aparecen en el mismo lugar o se condensan en una fuente de datos, lo que facilita la búsqueda. Por ejemplo, configuración unificada.

### <a name="unified-settings"></a>Configuración unificada

![Hizo clic en "Roles" y abrió la página Configuración, que incluye Configuración general, Permisos, API y Reglas. Abra Permisos y, a continuación, Roles. Muestra todos los roles](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Permisos & roles

![Permissions & Roles que muestra roles de puntos de conexión & grupos, roles y grupos de dispositivos.](../../media/converged-roles-5.png)

 Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles. For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/assign-portal-access). For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Obtenga más información sobre cómo [administrar el acceso a Microsoft 365 Defender](m365d-permissions.md)
- Obtenga más información sobre cómo [crear roles personalizados](custom-roles.md) en el Centro de seguridad de Microsoft 365

> [!NOTE]
> Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365 admite la concesión de acceso a proveedores de servicios de seguridad administrados [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) del mismo modo que se concede acceso en el Centro de seguridad de [Microsoft Defender.](./mssp-access.md)

### <a name="integrated-reports"></a>Informes integrados

Los informes también están unificados en el Centro de seguridad de Microsoft 365. Los administradores pueden empezar con un informe de seguridad general y bifurcarse en informes específicos sobre puntos de conexión, correo electrónico & colaboración. Los vínculos aquí se generan dinámicamente en función de la configuración de la carga de trabajo.

### <a name="quickly-view-your-microsoft-365-environment"></a>Ver rápidamente el entorno de Microsoft 365

La **página** principal muestra muchas de las tarjetas comunes que necesitan los equipos de seguridad. La composición de tarjetas y datos depende del rol de usuario. Dado que el Centro de seguridad de Microsoft 365 usa control de acceso basado en roles, los roles diferentes verán tarjetas que sean más significativas para sus trabajos diarios.  

Esta información de un vistazo le ayuda a mantenerse al día con las actividades más recientes de su organización. El Centro de seguridad de Microsoft 365 reúne señales de diferentes orígenes para presentar una vista holística de su entorno de Microsoft 365.

Las tarjetas entran en estas categorías:

- **Identidades:** supervise las identidades de su organización y realice un seguimiento de comportamientos sospechosos o arriesgados. [Obtenga más información sobre la protección de identidades.](/azure/active-directory/identity-protection/overview-identity-protection)
- **Datos:** ayuda a realizar un seguimiento de la actividad del usuario que podría provocar la divulgación de datos no autorizados.
- **Dispositivos:** obtenga información actualizada sobre alertas, actividad de infracción y otras amenazas en sus dispositivos.
- **Aplicaciones:** obtenga información sobre cómo se usan las aplicaciones en la nube en su organización. [Obtenga más información sobre las aplicaciones detectadas de Cloud App Security](/cloud-app-security/discovered-apps).

## <a name="threat-analytics-with-better-data-coverage"></a>Análisis de amenazas con mejor cobertura de datos
Realice un seguimiento y responda a las amenazas emergentes con la siguiente experiencia integrada de análisis de amenazas de Microsoft 365 Defender:

- Mejor cobertura de datos entre Microsoft Defender para Endpoint y Microsoft Defender para Office 365, lo que hace posible la administración combinada de incidentes, la investigación automática, la corrección y la búsqueda proactiva o reactiva de amenazas en todo el dominio. 
- Detecciones y mitigaciones relacionadas con el correo electrónico de Microsoft Defender para Office 365, además de los datos de punto de conexión que ya están disponibles en Microsoft Defender para Endpoint.
- Una vista de incidentes relacionados con amenazas que agregan alertas en casos de ataques de extremo a extremo en Microsoft Defender para Endpoint y Microsoft Defender para Office 365 para reducir la cola de trabajo, así como simplificar y acelerar la investigación.
- Intentos de ataque detectados y bloqueados por soluciones de Microsoft 365 Defender. También hay datos que puede usar para impulsar acciones de prevención que mitiguen el riesgo de una mayor exposición y aumenten la resistencia. 
- Diseño mejorado que pone la información útil en el punto de mira para ayudarle a identificar rápidamente los datos para centrarse urgentemente en los informes, investigarlos y aprovecharlos.

## <a name="a-centralized-learning-hub"></a>Un centro de aprendizaje centralizado

El Centro de seguridad de Microsoft 365 incluye un centro de aprendizaje que proporciona instrucciones oficiales de recursos como el blog de seguridad de Microsoft, la comunidad de seguridad de Microsoft en YouTube y la documentación oficial de docs.microsoft.com.

Dentro del centro de aprendizaje, las instrucciones de colaboración de Correo electrónico & (Microsoft Defender para Office 365 o MDO) están en paralelo con Endpoint (Microsoft Defender para endpoint o MDE) y recursos de aprendizaje de Microsoft 365 Defender.

El centro de aprendizaje se abre con rutas de aprendizaje organizadas en torno a temas como "¿Cómo investigar con Microsoft 365 Defender?" y "Procedimientos recomendados de Microsoft Defender para Office 365". Esta sección está actualmente curada por el Grupo de productos de seguridad dentro de Microsoft. Cada ruta de aprendizaje refleja un tiempo proyectado que se tarda en superar los conceptos. Por ejemplo, "Pasos a seguir cuando se pone en peligro una cuenta de usuario de Microsoft Defender para Office 365" se prevé que tarde 8 minutos y es un aprendizaje valioso sobre la marcha.

Después de hacer clic en el contenido, puede ser útil marcar este sitio y organizar los marcadores en una carpeta "Seguridad" o "Crítica". Para ver todas las rutas de aprendizaje, haga clic en el vínculo Mostrar todo en el panel principal.

> [!NOTE]
> Hay filtros  útiles en la parte superior del centro de aprendizaje del centro de seguridad de Microsoft 365 que le permitirán elegir entre productos (actualmente Microsoft 365 Defender, Microsoft Defender para endpoint y Microsoft Defender para Office 365). Observe que se muestra el número de recursos de aprendizaje para cada sección, lo que puede ayudar a los alumnos a realizar un seguimiento de cuántos recursos tienen disponibles para la formación y el aprendizaje.
>
> Junto con el filtro Producto, se enumeran los temas actuales, los tipos de recursos (desde vídeos hasta seminarios web), los niveles de familiaridad o experiencia con las áreas de seguridad, los roles de seguridad y las características del producto.

> [!TIP]
> Hay muchas otras oportunidades de aprendizaje en [Microsoft Learn](https://docs.microsoft.com/e/learn/). Encontrará formación en certificación, como el curso [MS-500T02-A: Implementar La](https://docs.microsoft.com/learn/certifications/courses/ms-500t02)protección contra amenazas de Microsoft 365 .

## <a name="send-us-your-feedback"></a>Envíenos sus comentarios

Necesitamos sus comentarios. Siempre estamos buscando mejorar, por lo que si hay algo que le gustaría ver, envíenos sus comentarios de [Microsoft 365 Defender](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

También puede dejar comentarios de este artículo. En la sección "Comentarios" al final de "Enviar y ver comentarios para", las opciones son *Este producto* o *Esta página*.

Use el **botón Este producto** para obtener comentarios *sobre* el producto:

1. Seleccione *Este producto* en la parte inferior del artículo.
    1. Haz clic con el botón derecho en el botón y "Abrir en una pestaña nueva" si quieres seguir leyendo estas instrucciones.
2. Esto navegará al foro **UserVoice**.
3. Tiene 2 opciones:
    1. Desplácese hacia abajo hasta el cuadro de texto ¿Cómo podemos mejorar el cumplimiento o proteger mejor a los usuarios en *Office 365?* y pegue en el Centro de seguridad *de Microsoft 365*. Puedes buscar en los resultados una idea como la tuya y votarla por arriba, o usar el botón **para Publicar una nueva idea**.
    1. Si estás seguro de que este problema ya está notificado y quieres aumentar  su perfil con un voto (o votos), usa el cuadro Enviar comentarios a la derecha de UserVoice. Busque el *Centro de seguridad de Microsoft 365,* busque el problema y use el botón de **voto** para aumentar su estado.

Use *esta página para* obtener comentarios sobre el propio artículo. Gracias por sus comentarios. Su voz nos ayuda a mejorar los productos.

### <a name="explore-what-the-security-center-has-to-offer"></a>Explorar lo que el centro de seguridad tiene que ofrecer

Siga explorando las características y capacidades del Centro de seguridad de Microsoft 365:

- [Administrar incidentes y alertas](manage-incidents.md)
- [Seguimiento y respuesta a amenazas emergentes con análisis de amenazas](threat-analytics.md)
- [El centro de actividades](m365d-action-center.md)
- [Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](./advanced-hunting-query-emails-devices.md)
- [Reglas de detección personalizada](./custom-detection-rules.md)
- [Alertas de colaboración y correos electrónicos](../../compliance/alert-policies.md#default-alert-policies)
- [Crear una simulación de ataque de suplantación de identidad (phishing)](../office-365-security/attack-simulation-training.md) y [crear una carga útil para entrenar a los equipos](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Información relacionada
- [Centro de seguridad de Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Office 365 en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mde.md)
- [Redirigir cuentas de Microsoft Defender para endpoint al Centro de seguridad de Microsoft 365](microsoft-365-security-mde-redirection.md)