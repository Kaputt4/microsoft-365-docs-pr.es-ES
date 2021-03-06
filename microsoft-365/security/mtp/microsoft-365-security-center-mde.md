---
title: Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre los cambios del Centro de seguridad de Microsoft Defender al Centro de seguridad de Microsoft 365
keywords: Introducción al Centro de seguridad de Microsoft 365, OATP, MDATP, MDO, MDE, panel único de cristal, portal convergente, portal de seguridad, portal de seguridad, portal de seguridad de defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 63f40ff12972695e391bd25973fd9a7195fab5b1
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515033"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

El centro de seguridad mejorado de [Microsoft 365](overview-security-center.md) combina capacidades de seguridad que protegen, detectan, investigan y responden a las amenazas de correo electrónico, colaboración, identidad [https://security.microsoft.com](https://security.microsoft.com) y dispositivo. Este centro de seguridad reúne las funciones de los portales de seguridad de Microsoft existentes, incluidos el Centro de seguridad de Microsoft Defender y el Centro de seguridad & cumplimiento de Office 365.

Si está familiarizado con el Centro de seguridad de Microsoft Defender, este artículo ayuda a describir algunos de los cambios y mejoras del centro de seguridad mejorado de Microsoft 365. Sin embargo, hay algunos elementos nuevos y actualizados que debe tener en cuenta.

Históricamente, el [Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) ha sido el hogar de Microsoft Defender para Endpoint. Los equipos de seguridad empresariales lo han usado para supervisar y ayudar a responder a alertas de posibles infracciones de datos o actividad de amenazas persistentes avanzada. Para ayudar a reducir el número de portales, el Centro de seguridad de Microsoft 365 será el hogar para supervisar y administrar la seguridad en todas las identidades, datos, dispositivos, aplicaciones e infraestructura de Microsoft.

Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365 admite la concesión de acceso a proveedores de servicios de seguridad administrados [(MSSP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) del mismo modo que se concede acceso en el centro de seguridad de [Microsoft Defender.](mssp-access.md)


> [!IMPORTANT]
> Lo que se ve en el Centro de seguridad de Microsoft 365 depende de las suscripciones actuales. Por ejemplo, si no tiene una licencia para Microsoft Defender para Office 365, no se mostrará la sección Email & Collaboration.

>[!Note]
>El nuevo portal unificado no está disponible para: US Government Community Cloud (GCC) US Government Community Cloud High (GCC High) US Department of Defense All US government institutions with commercial licenses

Echa un vistazo al centro de seguridad mejorado de Microsoft 365: [https://security.microsoft.com](https://security.microsoft.com) .

Más información sobre las ventajas: Información general del Centro de seguridad de [Microsoft 365](overview-security-center.md)

## <a name="whats-changed"></a>Qué ha cambiado

Esta tabla es una referencia rápida de los cambios entre el Centro de seguridad de Microsoft Defender y el Centro de seguridad de Microsoft 365.

### <a name="alerts-and-actions"></a>Alertas y acciones

|**Área**  |**Descripción del cambio**  |
|---------|---------|
| [Alertas de & incidentes](incidents-overview.md)  | En el Centro de seguridad de Microsoft 365, puede administrar incidentes y alertas en todos los puntos de conexión, correo electrónico e identidades. Hemos convergedo la experiencia para ayudarle a encontrar eventos relacionados con más facilidad. Para obtener más información, vea [Incidents Overview](incidents-overview.md).   |
| [Búsqueda](advanced-hunting-overview.md)  |  La modificación de reglas de detección personalizadas creadas en Microsoft Defender para endpoint para incluir tablas de identidad y correo electrónico las mueve automáticamente a Microsoft 365 Defender. Sus alertas correspondientes también aparecerán en Microsoft 365 Defender. Para obtener más información acerca de estos cambios, lea [Migrar reglas de detección personalizadas](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules). La `DeviceAlertEvents` tabla de búsqueda avanzada no está disponible en Microsoft 365 Defender. Para consultar información de alerta específica del dispositivo en Microsoft 365 Defender, puede usar las tablas y para dar cabida a más información de un conjunto diverso `AlertInfo` `AlertEvidence` de orígenes. Crea la siguiente consulta relacionada con el dispositivo siguiendo [Escribir consultas sin DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).|
|[Centro de acciones](mtp-action-center.md)    | Enumera las acciones pendientes y completadas que se llevaron a cabo después de las investigaciones automatizadas y las acciones de corrección. Anteriormente, el Centro de acción del Centro de seguridad de Microsoft Defender enumeraba las acciones pendientes y completadas para las acciones de corrección realizadas solo en dispositivos, mientras que las investigaciones automatizadas enumeraban alertas y estado. En el centro de seguridad mejorado de Microsoft 365, el Centro de acciones reúne acciones e investigaciones de corrección entre correo electrónico, dispositivos y usuarios, todo en una ubicación.  |
| [Análisis de amenazas](threat-analytics.md) |  Se ha movido a la parte superior de la barra de navegación para facilitar la detección y el uso. Ahora incluye información sobre amenazas para puntos de conexión y correo electrónico y colaboración.    |

### <a name="endpoints"></a>Puntos de conexión

|**Área**  |**Descripción del cambio**  |
|---------|---------|
|Búsqueda   |  En lugar de estar en el encabezado, la barra de búsqueda de Microsoft Defender para puntos de conexión se mueve en la sección Puntos de conexión. Puede seguir buscando dispositivos, archivos, usuarios, direcciones URL, IP, vulnerabilidades, software y recomendaciones.  |
|[Panel](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Este es el panel de operaciones de seguridad. Consulta información general sobre cuántas alertas activas se desencadenaron, qué dispositivos están en riesgo, qué usuarios están en riesgo y nivel de gravedad para alertas, dispositivos y usuarios. También puedes ver si algún dispositivo tiene problemas con el sensor, el estado general del servicio y cómo se detectaron las alertas no resueltas. |
|Inventario de dispositivos | Sin cambios. |
|[Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    El nombre se acortó para caber en el panel de navegación. Es igual que la sección de administración de amenazas y vulnerabilidades, con todas las páginas debajo.     |
| Partners y API | Sin cambios. |
| Evaluaciones & tutoriales    |     Nuevas capacidades de prueba y aprendizaje.     |
| Administración de la configuración   |  Sin cambios.  |

> [!NOTE]
> **Ahora, la investigación y** la corrección automáticas forman parte de los incidentes. Puede ver Eventos automatizados de investigación y corrección en la pestaña **Investigación de >** incidentes.

### <a name="access-and-reporting"></a>Acceso e informes

|**Área**  |**Descripción del cambio**  |
|---------|---------|
| Informes  | Consulta informes de puntos de conexión y correo & colaboración, incluida la protección contra amenazas, el estado y cumplimiento del dispositivo y los dispositivos vulnerables. |
| Salud  |  Actualmente se vincula a la página "Estado del servicio" en el Centro de administración [de Microsoft 365](https://admin.microsoft.com/). |
| Configuración |  Administra la configuración del Centro de seguridad de Microsoft 365, Microsoft 365 Defender, Endpoints, Email & colaboración, Identidades y detección de dispositivos.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Capacidades y navegación de seguridad de Microsoft 365

La barra de navegación izquierda o de inicio rápido será familiar. Sin embargo, hay algunos elementos nuevos y actualizados en este centro de seguridad.

### <a name="incidents-and-alerts"></a>Incidentes y alertas

Reúne la administración de incidentes y alertas en el correo electrónico, los dispositivos y las identidades. La página de alerta proporciona un contexto completo a la alerta mediante la combinación de señales de ataque para crear un artículo detallado. Ahora, una nueva experiencia unificada reúne una vista coherente de las alertas en todas las cargas de trabajo. Puede realizar triajes, investigar y tomar medidas eficaces rápidamente.

- [Más información sobre incidentes](incidents-overview.md)
- [Más información sobre cómo administrar alertas](investigate-alerts.md)

![La barra de inicio rápido Alertas y acciones](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Búsqueda

Busque de forma proactiva amenazas, malware y actividad malintencionada en los puntos de conexión, buzones de Office 365 y más mediante consultas de búsqueda [avanzadas.](advanced-hunting-overview.md) Estas consultas eficaces se pueden usar para localizar y revisar indicadores de amenazas y entidades para amenazas conocidas y potenciales.

[Las reglas de](custom-detection-rules.md) detección personalizadas se pueden crear a partir de consultas de búsqueda avanzadas para ayudarle a ver de forma proactiva los eventos que pueden ser indicativos de actividad de infracciones y dispositivos mal configurados.


### <a name="action-center"></a>Centro de acciones

El Centro de acciones muestra las investigaciones creadas por las capacidades automatizadas de investigación y respuesta. Esta recuperación automática y automática en Microsoft 365 Defender puede ayudar a los equipos de seguridad respondiendo automáticamente a eventos específicos.

[Más información sobre el Centro de actividades](mtp-action-center.md)

### <a name="threat-analytics"></a>Análisis de amenazas

Obtenga inteligencia de amenazas de investigadores expertos en seguridad de Microsoft. Threat Analytics ayuda a los equipos de seguridad a ser más eficientes cuando se enfrentan a amenazas emergentes. Análisis de amenazas incluye:

- Detecciones y mitigaciones relacionadas con el correo electrónico de Microsoft Defender para Office 365. Esto se suma a los datos del punto de conexión que ya están disponibles en Microsoft Defender para endpoint.
- Vista Incidentes relacionados con las amenazas.
- Experiencia mejorada para identificar y usar rápidamente información que se puede usar en los informes.

Puede acceder al análisis de amenazas desde la barra de navegación superior izquierda del centro de seguridad de Microsoft 365 o desde una tarjeta de panel dedicada que muestre las principales amenazas de su organización.

Obtenga más información sobre cómo [realizar un seguimiento y responder a las amenazas emergentes con análisis de amenazas](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>Sección Puntos de conexión

Ver y administrar la seguridad de los puntos de conexión en la organización. Si has usado el Centro de seguridad de Microsoft Defender, será familiar.

![La barra de inicio rápido de puntos de conexión](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Acceso e informes

Ver informes, cambiar la configuración y modificar roles de usuario.

![La barra de inicio rápido de Access e Reporting](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>Conexiones de LA API siem

Si usa la [API DE SIEM de Defender para](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)endpoint, puede seguir haciendo esto. Hemos agregado nuevos vínculos en la carga de la API que apuntan a la página de alerta o a la página de incidentes en el portal de seguridad de Microsoft 365. Los nuevos campos de API incluyen LinkToMTP e IncidentLinkToMTP. Para obtener más información, vea [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).

### <a name="email-alerts"></a>Alertas de correo electrónico

Puedes seguir usando alertas de correo electrónico para Defender para Endpoint. Hemos agregado nuevos vínculos en los correos electrónicos que apuntan a la página de alerta o a la página de incidentes en el Centro de seguridad de Microsoft 365. Para obtener más información, vea [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).

## <a name="related-information"></a>Información relacionada

- [Centro de seguridad de Microsoft 365](overview-security-center.md)
- [Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mde.md)
- [Redirigir cuentas de Microsoft Defender para endpoint al Centro de seguridad de Microsoft 365](microsoft-365-security-mde-redirection.md)
