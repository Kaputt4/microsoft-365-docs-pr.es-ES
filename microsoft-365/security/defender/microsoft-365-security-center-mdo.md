---
title: Microsoft Defender para Office 365 en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre cambios del Centro de seguridad y cumplimiento de Office 365 y del Centro de seguridad de Microsoft 365.
keywords: Seguridad de Microsoft 365, Introducción al Centro de seguridad de Microsoft 365, Microsoft Defender para Office 365, Microsoft Defender para endpoint, MDO, MDE, panel único de cristal, nuevo portal de seguridad, nuevo portal de seguridad de defender
ms.date: 02/02/2021
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
ms.openlocfilehash: 980a384d3c4fd44a368f35d6f885ea0c8288376a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935418"
---
# <a name="microsoft-defender-for-office-365-in-the-microsoft-365-security-center"></a>Microsoft Defender para Office 365 en el Centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

El [Centro mejorado de seguridad de Microsoft 365](./overview-security-center.md) en [https://security.microsoft.com](https://security.microsoft.com) combina funciones de seguridad de portales ya existentes de seguridad de Microsoft, incluidos el Centro de seguridad de Microsoft Defender y el Centro de seguridad y cumplimiento de Office 365. Este centro mejorado ayuda a los equipos de seguridad a proteger a su organización ante las amenazas de manera más eficaz y eficiente.

Si conoce el portal de Seguridad y cumplimiento de Office 365 (protection.office.com), este artículo le resultará útil, ya que describe algunos de los cambios y mejoras que se han realizado en el Centro de seguridad de Microsoft 365.

Más información sobre las ventajas: [Información general sobre el Centro de Seguridad de Microsoft 365](overview-security-center.md)

Si está buscando elementos relacionados con el cumplimiento, visite el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/homepage).

## <a name="whats-changed"></a>Modificaciones

Esta tabla es una referencia rápida de ámbitos relacionados con el correo electrónico y la colaboración en los que han tenido lugar cambios entre el **Centro de seguridad y cumplimiento** y el portal de **Seguridad de Microsoft 365** Haga clic en los siguientes vínculos para obtener más información sobre estos ámbitos.

|**Área**  |**Descripción del cambio**  |
|---------|---------|
| [Página de la entidad de correo electrónico](../office-365-security/mdo-email-entity-page.md) | Esta página **unifica** la información sobre correos electrónicos que se ido publicando en diferentes páginas o vistas en el pasado. Se ha *centralizado* la investigación de correos electrónicos para encontrar amenazas y tendencias. La información del encabezado y la vista previa del correo electrónico son accesibles desde la misma página de correo electrónico, junto con más información útil relacionada con correos electrónicos. Igualmente, el estado de detonación de direcciones URL o archivos adjuntos malintencionados se puede encontrar en una pestaña en la misma página. La página de entidad de correo electrónico ofrece a los administradores y equipos de operaciones de seguridad los recursos necesarios para permitirles entender con rapidez una amenaza de correo electrónico y su estado, para que puedan decidir de inmediato qué acciones tomar.  |
| [Investigación](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center) | Aúna capacidades de AIR en [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) y [Microsoft Defender para punto de conexión](../defender-endpoint/automated-investigations.md). Con estas actualizaciones y mejoras, su equipo de operaciones de seguridad podrá ver detalles sobre investigaciones automatizadas y acciones de corrección en todos sus correos electrónicos, contenido de colaboración, cuentas de usuario y dispositivos, todo en un mismo sitio.  | 
| [Vista de alertas](../../compliance/alert-policies.md) | El panel flotante **Ver alertas** en el Centro de seguridad y cumplimiento de Office incluye ahora vínculos al Centro de seguridad de Microsoft 365. Haga clic en el vínculo de **Abrir página de alertas** y se abrirá el Centro de seguridad de Microsoft 365. Puede acceder la página **Ver alertas** si hace clic en cualquier alerta de Office 365 en la cola de Alertas. |
| [Aprendizaje de simulación de ataque](../office-365-security/attack-simulation-training-insights.md)   | Use el aprendizaje de simulación de ataque para ejecutar escenarios realistas de ataque en su organización. Estos ataques simulados pueden ayudar a formar a su personal antes de que un ataque real impacte a su organización. El aprendizaje de simulación de ataque incluye más opciones, informes mejorados y flujos de aprendizaje mejorados que contribuyen a que resulte más sencillo llevar a cabo y administrar la simulación de ataque y los escenarios de aprendizaje.  |

No se han realizado cambios en estos ámbitos:
- [Explorador](../office-365-security/threat-explorer.md)
- [Directivas y reglas](../../compliance/alert-policies.md)
- [Campaña](../office-365-security/campaigns.md)
- [Envíos](../office-365-security/admin-submission.md)
- [Revisar](./m365d-action-center.md)
- [Rastreador de amenazas](../office-365-security/threat-trackers.md)

Asimismo, eche un vistazo a la sección **Información relacionada** al final de este artículo.

> [!IMPORTANT]
> El portal de Seguridad de Microsoft 365 (https://security.microsoft.com) combina características de seguridad en https://securitycenter.windows.com y https://protection.office.com). Sin embargo, lo que vea dependerá de su suscripción. Por ejemplo, si solo tiene el plan 1 o 2 de Microsoft Defender para Office 365 como suscripción independiente, no verá funciones de Seguridad para puntos de conexión y los clientes del plan 1 de Defender para Office no verán elementos como el análisis de amenazas.

## <a name="microsoft-365-security-center-home-page"></a>Página principal del Centro de seguridad de Microsoft 365

La página principal del portal muestra:

- Puntuaciones de seguridad
- el número de usuarios y de dispositivos en riesgo
- listas de incidentes activos
- listas de aplicaciones de OAuth con privilegios
- Datos de estado del dispositivo
- Tweets de la fuente de Twitter de la inteligencia de seguridad de Microsoft
- y más información de resumen

Si usa el **Tour guiado**, podrá hacer un tour rápido de las páginas de punto de conexión o de correo electrónico y colaboración. Tenga en cuenta que lo que vea aquí dependerá de si tiene la licencia de Microsoft Defender para Office 365 o de Defender para punto de conexión.  

Además, se incluye un vínculo al **Centro de seguridad y cumplimiento de Office 365** para que pueda compararlos. El último vínculo lleva a la página **Novedades**, que muestra actualizaciones recientes.

## <a name="improved-capabilities"></a>Capacidades mejoradas

La navegación izquierda o la barra de inicio rápido tienen un aspecto familiar. Sin embargo, hay algunos elementos nuevos y actualizados en este centro de seguridad.

### <a name="incidents-and-alerts"></a>Incidentes y alertas
Aúna la administración de incidentes y de alertas en todos sus correos electrónicos, dispositivos e identidades. Las alertas están ahora disponibles en el nodo de Investigación y ayudan a ofrecer una vista más amplia de un ataque. La página de alertas ofrece el contexto completo de la alerta, ya que combina señales de ataque para construir una historia más detallada. Anteriormente, las alertas eran específicas de diferentes cargas de trabajo. Esta experiencia nueva y unificada aúna una vista congruente de alertas en las cargas de trabajo. Puede realizar una evaluación, investigar y tomar acciones eficaces con rapidez.

- [Más información acerca de las Investigaciones](incidents-overview.md)
- [Obtenga más información sobre cómo administrar alertas](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![La barra de inicio rápido de alertas y acciones](../../media/converge-1-alerts-and-actions.png)


### <a name="hunting"></a>Búsqueda
Busque de manera proactiva amenazas, malware y actividad malintencionada en todos sus puntos de conexión, buzones de Office 365 y más gracias a las [consultas de búsqueda avanzada de amenazas](advanced-hunting-overview.md). Estas consultas eficaces se pueden usar para buscar y revisar indicadores y entidades de amenazas para encontrar amenazas conocidas y potenciales.

Se pueden crear [reglas de detección personalizadas](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) desde las consultas de búsqueda avanzada de amenazas para ayudarle a vigilar de manera proactiva eventos que puedan indicar una posible actividad de vulneración y dispositivos mal configurados.

### <a name="action-center"></a>Centro de actividades

El Centro de actividades le muestra las investigaciones creadas por las capacidades de investigación y respuesta automatizadas. Esta capacidad de recuperación automática de Microsoft 365 Defender puede ayudar a los equipos de seguridad, ya que responde de manera automática a eventos específicos.

[Más información sobre el Centro de actividades](m365d-action-center.md)

#### <a name="threat-analytics"></a>Análisis de amenazas
Obtenga inteligencia sobre amenazas de investigadores expertos de Seguridad de Microsoft. El análisis de amenazas ayuda a los equipos de seguridad a ser más eficientes a la hora de enfrentarse a amenazas emergentes. El análisis de amenazas incluye:

- Detecciones y mitigaciones relacionadas con correos electrónicos de Microsoft Defender para Office 365. Estos se suman a los datos del punto de conexión ya disponibles de Microsoft Defender para punto de conexión.
- Vista de incidentes relacionados con las amenazas. 
- Experiencia mejorada para identificar con rapidez y usar información accionable en los informes. Puede acceder al análisis de amenazas desde la barra de navegación en la esquina superior izquierda del Centro de seguridad de Microsoft 365 o desde una tarjeta de panel dedicado que muestra las principales amenazas de su organización. 

Obtenga más información sobre cómo [Supervisar amenazas emergentes y responder a las mismas con el análisis de amenazas](./threat-analytics.md)

### <a name="email--collaboration"></a>Colaboración y correos electrónicos

Supervise e investigue amenazas para los correos electrónicos, campañas de supervisión, etc., de sus usuarios. Si ya ha usado el Centro de seguridad y cumplimiento de Office 365, esto le resultará familiar.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="El menú de inicio rápido para correos electrónicos y colaboración (o MSDO) en el lado izquierdo del Centro de seguridad de Microsoft 365":::.

### <a name="access-and-reports"></a>Accesos e informes

Ver informes, cambiar la configuración y modificar roles de usuario.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="El menú de inicio rápido de los permisos y creación de informes del Centro de seguridad de Microsoft 365, en el lado izquierdo del Centro de seguridad":::.


> [!NOTE]
> Para los usuarios de Defender para Office 365, ahora puede *administrar y rotar* claves de DomainKeys Identified Mail (DKIM) a través del Centro de seguridad de Microsoft 365: https://security.microsoft.com/threatpolicy, o vaya a **Directiva y reglas > Directivas de amenazas > DKIM**.

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Ejemplo de búsqueda avanzada de amenazas para Microsoft Defender para Office 365
¿Quiere empezar a buscar amenazas para correos electrónicos mediante la búsqueda avanzada de amenazas? Pruebe esto:

La sección [Introducción](/microsoft-365/security/office-365-security/defender-for-office-365.md#getting-started) del [artículo de Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) tiene fragmentos lógicos de configuración temprana que tienen este aspecto:

1. Configure todo con "anti" en el nombre.
- antimalware
- anti-phishing
- anti-spam (protección contra correo electrónico no deseado)
2. Configure todo con "seguro" en el nombre.
- vínculos seguros
- archivos adjuntos seguros
3. Defender las cargas de trabajo (ej. SharePoint Online, OneDrive y Teams)
4. Proteger con la purga automática

Junto con un [vínculo](../office-365-security/protect-against-threats.md) para entrar directamente y establecer la configuración el primer día.

El último paso de la **Introducción** es proteger a los usuarios con la **Purga automática**, también conocida como ZAP. Puede ser muy importante saber si sus esfuerzos para purgar de manera automática correos electrónicos sospechosos o malintencionados, tras el envío, han tenido éxito.

Poder ir rápidamente al lenguaje de consulta Kusto para buscar problemas es una ventaja de unificar estos dos centros de seguridad. Los equipos de seguridad pueden supervisar fallos de ZAP si siguen los siguientes pasos [aquí](https://security.microsoft.com/advanced-hunting) en **Búsqueda** > **Búsqueda avanzada de amenazas**.

1. En la página de Búsqueda avanzada de amenazas, haga clic en Consulta.
1. Copie la consulta siguiente en la ventana de consulta:
1. Seleccione Ejecutar consulta.


```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="La página de Búsqueda avanzada de amenazas (en Búsqueda) con Consulta seleccionada en la parte superior del panel de consulta y ejecutar una consulta Kusto para capturar acciones de ZAP en los últimos 7 días":::.

Los datos de esta consulta aparecerán en el panel de resultados bajo la propia consulta. Los resultados incluyen información como "DeviceName", "AccountDisplayName" y "ZapTime" en un conjunto de resultados que se puede personalizar. Los resultados también se pueden exportar para sus registros. Si se trata de una consulta que volverá a necesitar, seleccione **Guardar** > **Guardar como** y agregue la consulta a su lista de consultadas, compartidas o consultas de comunidad.

## <a name="related-information"></a>Información relacionada
- [Microsoft Defender para Office 365 en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mdo.md)
- [El centro de actividades](./m365d-action-center.md)
- [Alertas de colaboración y correos electrónicos](../../compliance/alert-policies.md#default-alert-policies)
- [Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](./advanced-hunting-query-emails-devices.md)
- [Reglas de detección personalizada](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Crear una simulación de ataque de phishing](../office-365-security/attack-simulation-training.md) y [crear una carga útil para formar a su personal](../office-365-security/attack-simulation-training-payloads.md)
