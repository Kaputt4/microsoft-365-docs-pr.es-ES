---
title: Microsoft Defender para punto de conexión en Microsoft 365 Defender
description: Obtenga información sobre los cambios de la Centro de seguridad de Microsoft Defender a Microsoft 365 Defender
keywords: Introducción a Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para punto de conexión, MDO, MDE, portal de seguridad, portal de seguridad de Defender
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 23e79f77c3ef84cd464a4425953311ddf179b86e
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072665"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a>Microsoft Defender para punto de conexión en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a>Referencia rápida

La imagen y la tabla siguiente muestran los cambios en la navegación entre el Centro de seguridad de Microsoft Defender y el Microsoft 365 Defender.

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/mde-m3d-security-center.png" alt-text="Nuevas ubicaciones en el portal de Microsoft 365 Defender" lightbox="../../media/mde-m3d-security-center.png":::

| Centro de seguridad de Microsoft Defender | Microsoft 365 Defender |
|---------|---------|
| Paneles <ul><li>Operaciones de seguridad</li><li>Análisis de amenazas</li></ul>  |Home <ul><li>Análisis de amenazas</li></ul>   |
| Incidentes | Incidentes & alertas |
| Inventario de dispositivos | Inventario de dispositivos |
| Cola de alertas | Incidentes & alertas |
| Investigaciones automatizadas | Centro de actividades |
| Búsqueda avanzada de amenazas | Búsqueda |
| Informes | Informes |
| API de & asociados | API de & asociados |
| Administración de vulnerabilidades de Microsoft Defender | Administración de amenazas y vulnerabilidades |
| Evaluación y tutoriales | Tutoriales de evaluación & |
| Administración de la configuración | Administración de la configuración |
| Configuración | Configuración | 

La [Microsoft 365 Defender](microsoft-365-defender-portal.md) mejorada de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a> combina funcionalidades de seguridad que protegen, detectan, investigan y responden a amenazas de correo electrónico, colaboración, identidad y dispositivo. Esto reúne la funcionalidad de los portales de seguridad de Microsoft existentes, incluidos Centro de seguridad de Microsoft Defender y el Centro de cumplimiento de seguridad & de Office 365.

Si está familiarizado con la Centro de seguridad de Microsoft Defender, en este artículo se describen algunos de los cambios y mejoras de Microsoft 365 Defender. Sin embargo, hay algunos elementos nuevos y actualizados que debe tener en cuenta.

Históricamente, el [Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) ha sido el hogar de Microsoft Defender para punto de conexión. Los equipos de seguridad empresariales lo han usado para supervisar y ayudar a responder a alertas de posibles infracciones de datos o actividad de amenazas persistentes avanzadas. Para ayudar a reducir el número de portales, Microsoft 365 Defender será el hogar para supervisar y administrar la seguridad en las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura de Microsoft.

Microsoft Defender para punto de conexión en Microsoft 365 Defender admite [la concesión de acceso a proveedores de servicios de seguridad administrados (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de la misma manera [que se concede acceso en el Centro de seguridad de Microsoft Defender](mssp-access.md).

> [!IMPORTANT]
> Lo que vea en Microsoft 365 Defender depende de las suscripciones actuales. Por ejemplo, si no tiene una licencia para Microsoft Defender para Office 365, no se mostrará la sección colaboración de Email &.

> [!Note]
> Microsoft 365 Defender no está disponible para:
>- Us Government Community Cloud (GCC)
>- US Government Community Cloud High (GCC High)
>- Departamento de Defensa de EE. UU.
>- Todas las instituciones gubernamentales de EE. UU. con licencias comerciales

Eche un vistazo a Microsoft 365 Defender en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>.

Más información sobre las ventajas: [Introducción a Microsoft 365 Defender](microsoft-365-defender.md)

## <a name="whats-changed"></a>Modificaciones

Esta tabla es una referencia rápida de los cambios entre el Centro de seguridad de Microsoft Defender y el Microsoft 365 Defender.

### <a name="alerts-and-actions"></a>Alertas y acciones

| Área | Descripción de cambio |
|---------|---------|
| [Alertas de & incidentes](incidents-overview.md)  | En Microsoft 365 Defender, puede administrar incidentes y alertas en todos los puntos de conexión, correo electrónico e identidades. Hemos convergedo la experiencia para ayudarle a encontrar eventos relacionados más fácilmente. Para obtener más información, consulte [Información general sobre incidentes](incidents-overview.md).   |
| [Búsqueda](advanced-hunting-overview.md)  |  Modificar las reglas de detección personalizadas creadas en Microsoft Defender para punto de conexión para incluir tablas de identidad y correo electrónico las mueve automáticamente a Microsoft 365 Defender. Sus alertas correspondientes también aparecerán en Microsoft 365 Defender. Para obtener más información sobre estos cambios, consulte [Migración de reglas de detección personalizadas](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules). <br><br>La `DeviceAlertEvents` tabla para la búsqueda avanzada no está disponible en Microsoft 365 Defender. Para consultar información de alertas específicas del dispositivo en Microsoft 365 Defender, puede usar las `AlertInfo` tablas y `AlertEvidence` para dar cabida a más información de un conjunto diverso de orígenes. Diseñe la siguiente consulta relacionada con el dispositivo siguiendo [Las consultas de escritura sin DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).|
|[Centro de acciones](m365d-action-center.md)    | Enumera las acciones pendientes y completadas que se realizaron después de investigaciones automatizadas y acciones de corrección. Anteriormente, el Centro de acciones del Centro de seguridad de Microsoft Defender enumeraba las acciones pendientes y completadas para las acciones de corrección realizadas solo en los dispositivos, mientras que las investigaciones automatizadas enumeraban alertas y estado. En la Microsoft 365 Defender mejorada, el Centro de acciones reúne acciones de corrección e investigaciones en el correo electrónico, los dispositivos y los usuarios, todo en una sola ubicación.  |
| [Análisis de amenazas](threat-analytics.md) |  Se ha movido a la parte superior de la barra de navegación para facilitar la detección y el uso. Ahora incluye información sobre amenazas tanto para los puntos de conexión como para el correo electrónico y la colaboración.    |

### <a name="endpoints"></a>Puntos de conexión

| Área | Descripción de cambio |
|---------|---------|
|Búsqueda   |  La barra de búsqueda se encuentra en la parte superior de la página. Las sugerencias se proporcionan a medida que escribe. Puede buscar en las siguientes entidades en Defender para punto de conexión y Defender for Identity: <br><br> - **Dispositivos** : compatible con Defender para punto de conexión y Defender for Identity. Incluso puede usar operadores de búsqueda, por ejemplo, puede usar "contains" para buscar parte de un nombre de host. <br><br> - **Usuarios** : compatible con Defender para punto de conexión y Defender for Identity. <br><br> - **Archivos, direcciones IP y direcciones URL:** las mismas funcionalidades que en Defender para punto de conexión. <br> NOTA: *Las búsquedas de DIRECCIONES IP y URL coinciden exactamente y no aparecen en la página de resultados de búsqueda; conducen directamente a la página de entidad.  <br><br> - **MDVM** : las mismas funcionalidades que en Defender para punto de conexión (vulnerabilidades, software y recomendaciones). <br><br>  La página de resultados de búsqueda mejorada centraliza los resultados de todas las entidades.  |
|[Panel](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Este es el panel de operaciones de seguridad. Consulte información general sobre cuántas alertas activas se desencadenaron, qué dispositivos están en riesgo, qué usuarios están en riesgo y el nivel de gravedad de las alertas, dispositivos y usuarios. También puede ver si algún dispositivo tiene problemas con el sensor, el estado general del servicio y cómo se detectaron alertas sin resolver. |
|Inventario de dispositivos | Sin cambios. |
|[Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    El nombre se acortó para ajustarse al panel de navegación. Es lo mismo que la sección Administración de vulnerabilidades de Microsoft Defender, con todas las páginas debajo.     |
| Asociados y API | Sin cambios. |
| Evaluaciones & tutoriales    |     Nuevas funcionalidades de pruebas y aprendizaje.     |
| Administración de la configuración   |  Sin cambios.  |

> [!NOTE]
> **La investigación y corrección automáticas** ahora forman parte de los incidentes. Puede ver Eventos de investigación y corrección automatizados en la pestaña **Investigación de incidentes >** .

> [!TIP]
> La búsqueda de dispositivos se realiza desde Puntos de conexión > Búsqueda.

### <a name="access-and-reporting"></a>Acceso e informes

| Área | Descripción de cambio |
|---------|---------|
| Informes  | Consulte los informes de puntos de conexión y correo electrónico & colaboración, incluida la protección contra amenazas, el estado y el cumplimiento de dispositivos y los dispositivos vulnerables. |
| Mantenimiento  |  Actualmente se vincula a la página "Estado del servicio" del [Centro de administración de Microsoft 365](https://admin.microsoft.com/). |
| Configuración |  Administre la configuración de Microsoft 365 Defender, puntos de conexión, colaboración Email &, identidades y detección de dispositivos.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Navegación y funcionalidades de seguridad de Microsoft 365

La navegación izquierda o la barra de inicio rápido tienen un aspecto familiar. Sin embargo, hay algunos elementos nuevos y actualizados en Microsoft 365 Defender portal. 

### <a name="incidents-and-alerts"></a>Incidentes y alertas

Aúna la administración de incidentes y de alertas en todos sus correos electrónicos, dispositivos e identidades. La página de alerta proporciona contexto completo a la alerta mediante la combinación de señales de ataque para construir una historia detallada. Esta experiencia nueva y unificada aúna una vista congruente de alertas en las cargas de trabajo. Puede realizar una evaluación, investigar y tomar acciones eficaces con rapidez.

- [Más información sobre los incidentes](incidents-overview.md)
- [Obtenga más información sobre cómo administrar alertas](investigate-alerts.md)

:::image type="content" source="../../media/converge-1-alerts-and-actions.png" alt-text="Barra de inicio rápido de alertas y acciones en el portal de Microsoft 365 Defender" lightbox="../../media/converge-1-alerts-and-actions.png":::

### <a name="hunting"></a>Búsqueda

Busque de manera proactiva amenazas, malware y actividad malintencionada en todos sus puntos de conexión, buzones de Office 365 y más gracias a las [consultas de búsqueda avanzada de amenazas](advanced-hunting-overview.md). Estas consultas eficaces se pueden usar para buscar y revisar indicadores de amenazas y entidades para las amenazas conocidas y potenciales.

[Las reglas de detección personalizadas](custom-detection-rules.md) se pueden crear a partir de consultas de búsqueda avanzadas para ayudarle a observar de forma proactiva los eventos que podrían indicar la actividad de infracción y los dispositivos mal configurados.


### <a name="action-center"></a>Centro de actividades

El Centro de actividades le muestra las investigaciones creadas por las capacidades de investigación y respuesta automatizadas. Esta capacidad de recuperación automática de Microsoft 365 Defender puede ayudar a los equipos de seguridad, ya que responde de manera automática a eventos específicos.

[Obtenga más información sobre el Centro de acciones](m365d-action-center.md).

### <a name="threat-analytics"></a>Análisis de amenazas

Obtenga inteligencia sobre amenazas de investigadores expertos de Seguridad de Microsoft. El análisis de amenazas ayuda a los equipos de seguridad a ser más eficientes a la hora de enfrentarse a amenazas emergentes. El análisis de amenazas incluye:

- Detecciones y mitigaciones relacionadas con correos electrónicos de Microsoft Defender para Office 365. Estos se suman a los datos del punto de conexión ya disponibles de Microsoft Defender para punto de conexión.
- Vista de incidentes relacionados con las amenazas.
- Experiencia mejorada para identificar con rapidez y usar información accionable en los informes.

Puede acceder al análisis de amenazas desde la barra de navegación superior izquierda de Microsoft 365 Defender o desde una tarjeta de panel dedicada que muestre las principales amenazas de su organización.

Obtenga más información sobre cómo [realizar un seguimiento y responder a las amenazas emergentes con el análisis de amenazas](./threat-analytics.md).

### <a name="endpoints-section"></a>Sección Puntos de conexión

Vea y administre la seguridad de los puntos de conexión de su organización. Si ha usado el Centro de seguridad de Microsoft Defender, le resultará familiar.

:::image type="content" source="../../media/converge-2-endpoints.png" alt-text="Barra de inicio rápido de puntos de conexión en el portal de Microsoft 365 Defender" lightbox="../../media/converge-2-endpoints.png":::

### <a name="access-and-reports"></a>Acceso e informes

Ver informes, cambiar la configuración y modificar roles de usuario.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Barra de inicio rápido de Access and Reporting en el portal de Microsoft 365 Defender" lightbox="../../media/converge-4-access-and-reporting-new.png":::

### <a name="siem-api-connections"></a>Conexiones de API SIEM

Si usa la [API SIEM de Defender para punto de conexión](../defender-endpoint/enable-siem-integration.md), puede seguir haciéndolo. Hemos agregado nuevos vínculos en la carga de la API que apuntan a la página de alertas o a la página de incidentes en el portal de seguridad de Microsoft 365. Los nuevos campos de API incluyen LinkToMTP e IncidentLinkToMTP. Para obtener más información, vea [Redirigir cuentas de Microsoft Defender para punto de conexión a Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).

### <a name="email-alerts"></a>alertas de Email

Puede seguir usando alertas de correo electrónico para Defender para punto de conexión. Hemos agregado nuevos vínculos en los correos electrónicos que apuntan a la página de alerta o a la página de incidentes de Microsoft 365 Defender. Para obtener más información, vea [Redirigir cuentas de Microsoft Defender para punto de conexión a Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).

### <a name="managed-security-service-providers-mssp"></a>Proveedores de servicios de seguridad administrados (MSSP)

Actualmente no se admite el inicio de sesión en varios inquilinos simultáneamente en la misma sesión de exploración en el portal unificado. Para no participar en el redireccionamiento automático, [revierta al portal de Microsoft Defender para punto de conexión anterior](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal) para mantener esta funcionalidad hasta que se resuelva el problema.

## <a name="related-information"></a>Información relacionada

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Redirigir cuentas de Microsoft Defender para punto de conexión a Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)
