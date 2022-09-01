---
title: Información general del panel de seguridad
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Use el nuevo panel de seguridad para revisar Office 365 estado de protección contra amenazas y ver y actuar sobre las alertas de seguridad.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f417c64329b0a8e276e34e65520b56f7d788171b
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497299"
---
# <a name="security-dashboard-in-the-security--compliance-center"></a>Panel de seguridad en el Centro de cumplimiento de & de seguridad

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Funciones básicas y cómo abrir el panel de seguridad

El Centro de cumplimiento de seguridad & en <https://protection.office.com> permite a su organización administrar la protección y el cumplimiento de datos. Suponiendo que tiene los permisos necesarios, el panel de seguridad le permite revisar el estado de protección contra amenazas, así como ver y actuar en alertas de seguridad.

Vea el vídeo para obtener información general y, a continuación, lea este artículo para obtener más información.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

En función de lo que incluya la suscripción de su organización, el panel de seguridad incluye varios widgets, como Resumen de administración de amenazas, Estado de protección contra amenazas, Detecciones de amenazas semanales globales, Malware, etc., como se describe en las secciones siguientes.

Para ver el panel de seguridad en el Centro de cumplimiento de seguridad &, vaya al **Panel** de **administración de** \> amenazas. Para ir directamente al panel seguridad, use <https://protection.office.com/searchandinvestigation/dashboard>.

> [!NOTE]
> Debe ser administrador global, administrador de seguridad o lector de seguridad para ver el panel de seguridad. Algunos widgets requieren permisos adicionales para ver. Para obtener más información, consulte [Permisos en el Centro de cumplimiento de seguridad &](permissions-in-the-security-and-compliance-center.md)[.

## <a name="threat-management-summary"></a>Resumen de administración de amenazas

El widget Resumen de administración de amenazas le indica de un vistazo cómo se protegió su organización frente a amenazas en los últimos siete (7) días.

:::image type="content" source="../../media/SecDash-ThreatMgmtSummary.png" alt-text="El widget Panel de seguridad: resumen de administración de amenazas" lightbox="../../media/SecDash-ThreatMgmtSummary.png":::

La información que verá en el Resumen de administración de amenazas depende de lo que incluya su suscripción. En la tabla siguiente se describe qué información se incluye para Office 365 E3 y Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Mensajes de malware bloqueados<br>Mensajes de phishing bloqueados<br>Mensajes notificados por los usuarios<br><br><br><br>|Mensajes de malware bloqueados<br>Mensajes de phishing bloqueados<br>Mensajes notificados por los usuarios<br>Malware de día cero bloqueado<br>Se detectaron mensajes de suplantación de identidad avanzados<br>Direcciones URL malintencionadas bloqueadas|

Para ver o acceder al widget Resumen de administración de amenazas, debe tener permisos para ver Defender para Office 365 informes. Para obtener más información, consulte [¿Qué permisos se necesitan para ver los informes de Defender para Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Estado de protección contra amenazas

El widget Estado de protección contra amenazas muestra la eficacia de la protección contra amenazas con una vista tendencial y detallada de phish y malware.

:::image type="content" source="../../media/tpswidget.png" alt-text="Widget de estado de protección contra amenazas" lightbox="../../media/tpswidget.png":::

Los detalles dependen de si la suscripción de Microsoft 365 incluye [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) con o sin [Microsoft Defender para Office 365](defender-for-office-365.md).

|Si la suscripción incluye...|Verá estos detalles.|
|---|---|
|EOP pero no Microsoft Defender para Office 365|Correo electrónico malintencionado detectado y bloqueado por EOP.<p> Consulte [Informe de estado de protección contra amenazas (EOP).](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender para Office 365|EOP y Defender para Office 365 detectan y bloquean el contenido malintencionado y el correo electrónico malintencionado <p> Recuento agregado de mensajes de correo electrónico únicos con contenido malintencionado bloqueado por el motor antimalware, [purga automática de cero horas](zero-hour-auto-purge.md) y características de Defender para Office 365 ([incluidos Vínculos seguros](safe-links.md), [Datos adjuntos seguros](safe-attachments.md) y [Anti-phishing en Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)). <p> Consulte [Informe de estado de protección contra amenazas](view-reports-for-mdo.md#threat-protection-status-report).|

Para ver o acceder al widget Estado de protección contra amenazas, debe tener permisos para ver Defender para Office 365 informes. Para obtener más información, consulte [¿Qué permisos se necesitan para ver los informes de Defender para Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Detecciones de amenazas semanales globales

El widget Global Weekly Threat Detections (Detecciones de amenazas semanales globales) muestra cuántas amenazas se detectaron en los mensajes de correo electrónico en los últimos siete (7) días.

:::image type="content" source="../../media/globalweeklythreatdetections.png" alt-text="Widget Global Weekly Threat Detections (Detecciones de amenazas semanales globales)" lightbox="../../media/globalweeklythreatdetections.png":::

Las métricas se calculan como se describe en la tabla siguiente:

|Métrica|Cómo se calcula|
|---|---|
|Mensajes examinados|Número de mensajes de correo electrónico examinados multiplicado por el número de destinatarios|
|Amenazas detenidas|Número de mensajes de correo electrónico identificados como que contienen malware multiplicado por el número de destinatarios|
|Bloqueado por [Defender para Office 365](defender-for-office-365.md)|Número de mensajes de correo electrónico bloqueados por Defender para Office 365 multiplicado por el número de destinatarios|
|Se quitó después de la entrega|Número de mensajes quitados por [purga automática de cero horas (ZAP)](zero-hour-auto-purge.md) multiplicado por el número de destinatarios|

## <a name="malware"></a>Malware

Los widgets de malware muestran detalles sobre las tendencias de malware y los tipos de familia de malware en los últimos siete (7) días.

:::image type="content" source="../../media/malwarewidgetatpe5.png" alt-text="Tendencias de malware y tipos de familia" lightbox="../../media/malwarewidgetatpe5.png":::

## <a name="insights"></a>Insights

Las conclusiones no solo exponen los problemas clave que debe revisar, sino que también incluyen recomendaciones y acciones que se deben tener en cuenta.

:::image type="content" source="../../media/smartinsights.png" alt-text="La información inteligente" lightbox="../../media/smartinsights.png":::

Por ejemplo, es posible que vea que los mensajes de correo electrónico de phishing se entregan porque algunos usuarios han deshabilitado sus opciones de correo no deseado. Para obtener más información sobre cómo funcionan las conclusiones, consulte [Informes e información en el Centro de cumplimiento de seguridad &](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Investigación y respuesta de amenazas

Si la suscripción de su organización incluye [Microsoft Defender para Office 365 plan 2](office-365-ti.md), el panel de seguridad tiene una sección que incluye herramientas avanzadas de investigación y respuesta de amenazas. Estas herramientas incluyen [funcionalidades automatizadas de investigación y respuesta](automated-investigation-response-office.md). La investigación y la respuesta automatizadas pueden ser útiles en escenarios como [abordar rápidamente las cuentas de usuario en peligro](address-compromised-users-quickly.md).

Para obtener más información, consulte [Introducción al uso de la investigación y respuesta automatizadas (AIR) en Office 365](office-365-air.md).

## <a name="trends"></a>Tendencias

Cerca de la parte inferior del panel de seguridad hay una sección **Tendencias** , que resume las tendencias de flujo de correo electrónico de su organización. Los informes proporcionan información sobre el correo electrónico clasificado como correo no deseado, malware, intentos de suplantación de identidad (phishing) y un buen correo electrónico. Haga clic en un icono para ver información más detallada en el informe.

:::image type="content" source="../../media/trends.png" alt-text="La sección Tendencias que resume las tendencias de flujo de correo electrónico de la organización" lightbox="../../media/trends.png":::

Y, si la suscripción de su organización incluye [Defender para Office 365 plan 2](office-365-ti.md), también tendrá un informe de **alertas de administración de amenazas recientes** en esta sección que permite al equipo de seguridad ver y tomar medidas en alertas de seguridad de prioridad alta.

Para ver o acceder al widget de Email enviado y recibido, debe tener permisos para ver Defender para Office 365 informes. Para obtener más información, consulte [¿Qué permisos se necesitan para ver los informes de Defender para Office 365?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Para ver o acceder al widget Alertas de administración de amenazas recientes, debe tener permisos para ver las alertas. Para obtener más información, consulte [Permisos de RBAC necesarios para ver las alertas](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-articles"></a>Artículos relacionados

[Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento](view-email-security-reports.md)

[Ver informes para Microsoft Defender para Office 365](view-reports-for-mdo.md)

[Defender para Office 365](defender-for-office-365.md)

[Office 365 Investigación y respuesta de amenazas](office-365-ti.md)
