---
title: Microsoft Defender para Office 365 en Microsoft 365 Defender
description: Obtenga información sobre los cambios del Centro de seguridad & cumplimiento a Microsoft 365 Defender.
keywords: Microsoft 365 seguridad, Introducción a Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para endpoint, MDO, MDE, panel único de cristal, nuevo portal de seguridad, nuevo portal de seguridad de defender
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: 219689783dbd98c1b6dfa09a2164cc4d350ffd9c
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029638"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft Defender para Office 365 en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Referencia rápida

En la tabla siguiente se enumeran los cambios en la navegación entre el Centro de seguridad & cumplimiento y Microsoft 365 Defender.

<br>

****

|[Centro de seguridad y cumplimiento](https://protection.office.com)|[Microsoft 365 Defender](https://security.microsoft.com)|[Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)|[Centro de administración de Exchange](https://admin.exchange.microsoft.com)|
|---|---|---|---|
|Alertas|<ul><li>[Directivas de alerta](https://security.microsoft.com/alertpolicies)</li><li>[Alertas de & incidentes](https://security.microsoft.com/alerts)</li></ul>|[Página alertas](https://compliance.microsoft.com/homepage)||
|Clasificación||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Prevención de pérdida de datos||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Administración de registros||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Información de gobierno||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Administración de amenazas|[Colaboración & correo electrónico](https://security.microsoft.com/homepage)|||
|Permissions|[Permisos & roles](https://security.microsoft.com/emailandcollabpermissions)|Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Flujo de correo|||Consulta [Exchange de administración](https://admin.exchange.microsoft.com/#/)|
|Privacidad de datos||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Búsqueda|[Auditoría](https://security.microsoft.com/auditlogsearch?viewid=Async%20Search)|Búsqueda (búsqueda de contenido)||
|Informes|[Informe](https://security.microsoft.com/emailandcollabreport)|||
|Garantía de servicio||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|Supervisión||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|eDiscovery||Vea [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage)||
|||||

[Microsoft 365 Defender](./overview-security-center.md) combina las capacidades de seguridad de los portales de seguridad de Microsoft existentes, incluido el Centro de <https://security.microsoft.com> seguridad & cumplimiento. Este centro mejorado ayuda a los equipos de seguridad a proteger a su organización ante las amenazas de manera más eficaz y eficiente.

Si está familiarizado con el Centro de seguridad & cumplimiento (protection.office.com), en este artículo se describen algunos de los cambios y mejoras de Microsoft 365 Defender.

Obtenga más información sobre las ventajas: [Información general sobre Microsoft 365 Defender](overview-security-center.md)

Si está buscando elementos relacionados con el cumplimiento, visite el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage).

## <a name="new-and-improved-capabilities"></a>Capacidades nuevas y mejoradas

La navegación izquierda o la barra de inicio rápido tienen un aspecto familiar. Sin embargo, hay algunos elementos nuevos y actualizados en este centro de seguridad.

Con la solución Microsoft 365 Defender unificada, puede unir las señales de amenaza y determinar el ámbito completo y el impacto de la amenaza, y cómo afecta actualmente a la organización.

:::image type="content" source="../../media/M365-defender-converge-experience.png" alt-text="Imagen de Microsoft 365 Defender experiencia convergente":::

Defender for Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración.

:::image type="content" source="../../media/Defender-for-O365.png" alt-text="Imagen de Defender para Office 365":::

### <a name="incidents-and-alerts"></a>Incidentes y alertas

Aúna la administración de incidentes y de alertas en todos sus correos electrónicos, dispositivos e identidades. Las alertas están ahora disponibles en el nodo de Investigación y ayudan a ofrecer una vista más amplia de un ataque. La página de alertas ofrece el contexto completo de la alerta, ya que combina señales de ataque para construir una historia más detallada. Anteriormente, las alertas eran específicas de diferentes cargas de trabajo. Esta experiencia nueva y unificada aúna una vista congruente de alertas en las cargas de trabajo. Puede realizar una evaluación, investigar y tomar acciones eficaces con rapidez.

- [Más información acerca de las Investigaciones](incidents-overview.md)
- [Obtenga más información sobre cómo administrar alertas](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![La barra de inicio rápido de alertas y acciones](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Búsqueda

Busque de manera proactiva amenazas, malware y actividad malintencionada en todos sus puntos de conexión, buzones de Office 365 y más gracias a las [consultas de búsqueda avanzada de amenazas](advanced-hunting-overview.md). Estas consultas eficaces se pueden usar para buscar y revisar indicadores y entidades de amenazas para encontrar amenazas conocidas y potenciales.

[Las reglas de](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) detección personalizadas se pueden crear a partir de consultas de búsqueda avanzadas para ayudarle a ver de forma proactiva los eventos que pueden ser indicativos de actividad de infracciones y dispositivos mal configurados.

Este es un [ejemplo sobre la búsqueda avanzada](advanced-hunting-example.md) en Microsoft Defender para Office 365.

### <a name="action-center"></a>Centro de actividades

El Centro de actividades le muestra las investigaciones creadas por las capacidades de investigación y respuesta automatizadas. Esta capacidad de recuperación automática de Microsoft 365 Defender puede ayudar a los equipos de seguridad, ya que responde de manera automática a eventos específicos.

Obtenga más información sobre [el Centro de acciones](m365d-action-center.md).

#### <a name="threat-analytics"></a>Análisis de amenazas

Obtenga inteligencia sobre amenazas de investigadores expertos de Seguridad de Microsoft. El análisis de amenazas ayuda a los equipos de seguridad a ser más eficientes a la hora de enfrentarse a amenazas emergentes. El análisis de amenazas incluye:

- Detecciones y mitigaciones relacionadas con correos electrónicos de Microsoft Defender para Office 365. Estos se suman a los datos del punto de conexión ya disponibles de Microsoft Defender para punto de conexión.
- Vista de incidentes relacionados con las amenazas.
- Experiencia mejorada para identificar con rapidez y usar información accionable en los informes.

Puedes acceder al análisis de amenazas desde la barra de navegación superior izquierda de Microsoft 365 Defender, o desde una tarjeta de panel dedicada que muestra las principales amenazas de la organización.

Obtenga más información sobre cómo [realizar un seguimiento y responder a las amenazas emergentes con análisis de amenazas.](./threat-analytics.md)

### <a name="email--collaboration"></a>Colaboración y correos electrónicos

Supervise e investigue amenazas para los correos electrónicos, campañas de supervisión, etc., de sus usuarios. Si ha usado el Centro de seguridad & cumplimiento, esto será familiar.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Menú de inicio rápido para Correo & Collab (o MSDO), en el lado izquierdo de Microsoft 365 Defender.":::

#### <a name="email-entity-page"></a>Página de la entidad de correo electrónico

La [página Entidad de correo](../office-365-security/mdo-email-entity-page.md) electrónico *unifica* la información de correo electrónico que se había dispersado en diferentes páginas o vistas en el pasado. Se ha *centralizado* la investigación de correos electrónicos para encontrar amenazas y tendencias. La información del encabezado y la vista previa del correo electrónico son accesibles desde la misma página de correo electrónico, junto con más información útil relacionada con correos electrónicos. Igualmente, el estado de detonación de direcciones URL o archivos adjuntos malintencionados se puede encontrar en una pestaña en la misma página. La página de entidad de correo electrónico ofrece a los administradores y equipos de operaciones de seguridad los recursos necesarios para permitirles entender con rapidez una amenaza de correo electrónico y su estado, para que puedan decidir de inmediato qué acciones tomar.

### <a name="access-and-reports"></a>Accesos e informes

Ver informes, cambiar la configuración y modificar roles de usuario.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Menú de inicio rápido para Microsoft 365 Defender permisos e informes, en el lado izquierdo del centro de seguridad.":::

> [!NOTE]
> DomainKeys Identified Mail (DKIM) garantiza que los sistemas de correo electrónico de destino confíen en los mensajes enviados salientes desde el dominio personalizado.
> Para defender para Office 365 usuarios, ahora puede administrar y girar claves *DKIM* a través de Microsoft 365 Defender: , o navegar a directiva & reglas de amenazas Sección reglas <https://security.microsoft.com/threatpolicy>  \>  \> \>  \> **DKIM**.
>
> Para obtener más información, vea [Use DKIM to validate outbound email sent from your custom domain](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email).

## <a name="whats-changed"></a>Modificaciones

Esta tabla es una referencia rápida de la administración de amenazas en la que se han producido cambios entre el Centro de seguridad **& cumplimiento** y el portal **de Microsoft 365 Defender** amenazas. Haga clic en los siguientes vínculos para obtener más información sobre estos ámbitos.

<br>

****

|Área|Descripción de cambio|
|---|---|
|[Investigación](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-microsoft-365-defender-portal)|Aúna capacidades de AIR en [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) y [Microsoft Defender para punto de conexión](../defender-endpoint/automated-investigations.md). Con estas actualizaciones y mejoras, su equipo de operaciones de seguridad podrá ver detalles sobre investigaciones automatizadas y acciones de corrección en todos sus correos electrónicos, contenido de colaboración, cuentas de usuario y dispositivos, todo en un mismo sitio.|
|[Cola de alertas](../../compliance/alert-policies.md)|El **panel desplegable Ver alertas** en el Centro de seguridad & cumplimiento ahora incluye vínculos a Microsoft 365 Defender. Haga clic en el **vínculo Abrir página de** alerta y Microsoft 365 Defender se abrirá. Puede acceder la página **Ver alertas** si hace clic en cualquier alerta de Office 365 en la cola de Alertas.|
|[Aprendizaje de simulación de ataque](../office-365-security/attack-simulation-training-insights.md)|Use el aprendizaje de simulación de ataque para ejecutar escenarios realistas de ataque en su organización. Estos ataques simulados pueden ayudar a formar a su personal antes de que un ataque real impacte a su organización. El aprendizaje de simulación de ataque incluye más opciones, informes mejorados y flujos de aprendizaje mejorados que contribuyen a que resulte más sencillo llevar a cabo y administrar la simulación de ataque y los escenarios de aprendizaje.|
|

No se han realizado cambios en estos ámbitos:

- [Explorador](../office-365-security/threat-explorer.md)
- [Directivas y reglas](../../compliance/alert-policies.md)
- [Campaña](../office-365-security/campaigns.md)
- [Envíos](../office-365-security/admin-submission.md)
- [Revisar](./m365d-action-center.md)
- [Rastreador de amenazas](../office-365-security/threat-trackers.md)

Asimismo, eche un vistazo a la sección **Información relacionada** al final de este artículo.

> [!IMPORTANT]
> El portal Microsoft 365 Defender <https://security.microsoft.com> ( ) combina características de seguridad en <https://securitycenter.windows.com> y <https://protection.office.com> . Sin embargo, lo que vea dependerá de su suscripción. Por ejemplo, si solo tiene el plan 1 o 2 de Microsoft Defender para Office 365 como suscripción independiente, no verá funciones de Seguridad para puntos de conexión y los clientes del plan 1 de Defender para Office no verán elementos como el análisis de amenazas.

> [!TIP]
> Todas Exchange Online Protection (EOP) se incluirán en Microsoft 365 Defender, ya que EOP es un elemento principal de Defender para Office 365.

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365 Defender Página principal

La página principal del portal muestra información de resumen importante sobre el estado de seguridad del entorno Microsoft 365 web.

Si usa el **Tour guiado**, podrá hacer un tour rápido de las páginas de punto de conexión o de correo electrónico y colaboración. Tenga en cuenta que lo que vea aquí dependerá de si tiene la licencia de Microsoft Defender para Office 365 o de Defender para punto de conexión.

También se incluye un vínculo al Centro de **seguridad & cumplimiento para** su comparación. El último vínculo lleva a la página **Novedades**, que muestra actualizaciones recientes.

## <a name="related-information"></a>Información relacionada

- [Redirigir el Centro de seguridad & cumplimiento a Microsoft 365 Defender](microsoft-365-security-mdo-redirection.md)
- [El centro de actividades](./m365d-action-center.md)
- [Alertas de colaboración y correos electrónicos](../../compliance/alert-policies.md#default-alert-policies)
- [Reglas de detección personalizada](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Crear una simulación de ataque de phishing](../office-365-security/attack-simulation-training.md) y [crear una carga útil para formar a su personal](../office-365-security/attack-simulation-training-payloads.md)
