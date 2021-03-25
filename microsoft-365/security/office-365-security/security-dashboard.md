---
title: Introducción al panel de seguridad
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Use el nuevo Panel de seguridad para revisar el estado de protección contra amenazas de Office 365 y ver y actuar en alertas de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7114776f686d25808c141a07b8cb2868cc67615d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205646"
---
# <a name="security-dashboard"></a>Panel de seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Funciones básicas y cómo abrir el Panel de seguridad

El [Centro de & seguridad permite a](../../compliance/microsoft-365-compliance-center.md) su organización administrar la protección y el cumplimiento de datos. Suponiendo que tiene los permisos necesarios, el Panel de seguridad le permite revisar el estado de protección contra amenazas, así como ver y actuar en alertas de seguridad.

Vea el vídeo para obtener información general y, a continuación, lea este artículo para obtener más información.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Según lo que incluya la suscripción de su organización, el Panel de seguridad incluye varios widgets, como resumen de administración de amenazas, estado de protección contra amenazas, detecciones semanales globales de amenazas, malware y mucho más, como se describe en las secciones siguientes.

Para ver el Panel de seguridad, en el Centro de [seguridad & cumplimiento,](../../compliance/microsoft-365-compliance-center.md)vaya al Panel **de administración de** \> **amenazas.**

> [!NOTE]
> Debe ser un administrador global, un administrador de seguridad o un lector de seguridad para ver el Panel de seguridad. Algunos widgets requieren permisos adicionales para verlos. Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="threat-management-summary"></a>Resumen de administración de amenazas

El widget Resumen de administración de amenazas le indica de un vistazo cómo su organización se protegió de las amenazas en los últimos siete (7) días.

![Panel de seguridad: widget resumen de administración de amenazas](../../media/SecDash-ThreatMgmtSummary.png)

La información que verá en el Resumen de administración de amenazas depende de lo que incluya la suscripción. En la tabla siguiente se describe qué información se incluye para Office 365 E3 y Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Mensajes de malware bloqueados<br>Mensajes de suplantación de identidad bloqueados<br>Mensajes notificados por usuarios<br><br><br><br>|Mensajes de malware bloqueados<br>Mensajes de suplantación de identidad bloqueados<br>Mensajes notificados por usuarios<br>Malware de día cero bloqueado<br>Mensajes de phishing avanzados detectados<br>Direcciones URL malintencionadas bloqueadas|

Para ver o tener acceso al widget Resumen de administración de amenazas, debe tener permisos para ver informes de Defender para Office 365. Para obtener más información, vea ¿Qué permisos son necesarios para ver los informes de [Defender para Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Estado de protección contra amenazas

El widget Estado de protección contra amenazas muestra la eficacia de la protección contra amenazas con una vista detallada y actual de la suplantación de identidad (phish) y malware.

![Widget de estado de protección contra amenazas](../../media/tpswidget.png)

Los detalles dependen de si su suscripción a Microsoft 365 incluye [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) con o sin Microsoft Defender para Office [365](defender-for-office-365.md).

|Si la suscripción incluye...|Verá estos detalles|
|---|---|
|EOP pero no Microsoft Defender para Office 365|Correo electrónico malintencionado detectado y bloqueado por EOP.<p> Consulte [Informe de estado de protección contra amenazas (EOP).](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender para Office 365|Contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por EOP y Defender para Office 365 <p> Recuento agregado de mensajes de correo electrónico únicos con contenido malintencionado bloqueado por el motor antimalware, purga automática [](safe-attachments.md)de cero horas y características de Defender para Office 365 (incluidos vínculos [seguros,](safe-links.md)datos adjuntos seguros y anti phishing en Defender para [Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)). [](zero-hour-auto-purge.md) <p> Consulte [Informe de estado de protección contra amenazas](view-reports-for-mdo.md#threat-protection-status-report).|

Para ver o obtener acceso al widget Estado de protección contra amenazas, debe tener permisos para ver informes de Defender para Office 365. Para obtener más información, vea ¿Qué permisos son necesarios para ver los informes de [Defender para Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Detecciones semanales globales de amenazas

El widget Detecciones semanales globales de amenazas muestra cuántas amenazas se detectaron en los mensajes de correo electrónico en los últimos siete (7) días.

![Widget Global Weekly Threat Detections](../../media/globalweeklythreatdetections.png)

Las métricas se calculan como se describe en la tabla siguiente:

|Métrica|Cómo se calcula|
|---|---|
|Mensajes analizados|Número de mensajes de correo electrónico analizados multiplicado por el número de destinatarios|
|Amenazas detenidas|Número de mensajes de correo electrónico identificados como que contienen malware multiplicado por el número de destinatarios|
|Bloqueado por [Defender para Office 365 ](defender-for-office-365.md)|Número de mensajes de correo electrónico bloqueados por Defender para Office 365 multiplicado por el número de destinatarios|
|Eliminado después de la entrega|Número de mensajes eliminados por purga automática de [cero](zero-hour-auto-purge.md) horas multiplicado por el número de destinatarios|

## <a name="malware"></a>Malware

Los widgets de malware muestran detalles sobre tendencias de malware y tipos de familia de malware en los últimos siete (7) días.

![Tendencias de malware y tipos de familia](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Enfoques

Las insights no solo son problemas fundamentales de superficie que debes revisar, sino que también incluyen recomendaciones y acciones que debes tener en cuenta.

![Información inteligente](../../media/smartinsights.png)

Por ejemplo, es posible que vea que los mensajes de correo electrónico de suplantación de identidad se están entregando porque algunos usuarios han deshabilitado sus opciones de correo no deseado. Para obtener más información sobre cómo funcionan las [perspectivas,](reports-and-insights-in-security-and-compliance.md)vea Informes y perspectivas en el Centro de seguridad & cumplimiento .

## <a name="threat-investigation-and-response"></a>Investigación y respuesta de amenazas

Si la suscripción de su organización incluye  [Microsoft Defender para Office 365 Plan 2,](office-365-ti.md)el Panel de seguridad tiene una sección que incluye herramientas avanzadas de investigación y respuesta de amenazas. Estas herramientas incluyen [capacidades automatizadas de investigación y respuesta.](automated-investigation-response-office.md) La investigación y respuesta automatizadas pueden ser útiles en escenarios como el abordamiento rápido de cuentas [de usuario comprometidas.](address-compromised-users-quickly.md)

Para obtener más información, vea [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).

## <a name="trends"></a>Tendencias

Cerca de la parte inferior del Panel de seguridad hay **una sección Tendencias,** que resume las tendencias de flujo de correo electrónico de su organización. Los informes proporcionan información sobre el correo electrónico categorizado como correo no deseado, malware, intentos de suplantación de identidad y correo electrónico bueno. Haga clic en un icono para ver información más detallada en el informe.

![La sección Tendencias resume las tendencias de flujo de correo electrónico de la organización](../../media/trends.png)

Y, si la suscripción de su organización incluye [Defender para Office 365 Plan 2,](office-365-ti.md)también tendrá un informe de alertas de administración de amenazas recientes en esta sección que permite al equipo de seguridad ver y tomar medidas en alertas de seguridad de alta prioridad. 

Para ver o tener acceso al widget Correo electrónico enviado y recibido, debe tener permisos para ver informes de Defender para Office 365. Para obtener más información, vea ¿Qué permisos son necesarios para ver los informes de [Defender para Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Para ver o tener acceso al widget Alertas de administración de amenazas recientes, debe tener permisos para ver alertas. Para obtener más información, vea [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-topics"></a>Temas relacionados

[Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento](view-email-security-reports.md)

[Ver informes de Microsoft Defender para Office 365](view-reports-for-mdo.md)

[Defender para Office 365](defender-for-office-365.md)

[Investigación y respuesta de amenazas de Office 365](office-365-ti.md)