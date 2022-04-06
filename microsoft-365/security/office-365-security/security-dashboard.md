---
title: Introducción al panel de seguridad
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
description: Use el nuevo Panel de seguridad para revisar Office 365 estado de protección contra amenazas y ver y actuar en alertas de seguridad.
ms.technology: mdo
ms.prod: m365-security
---

# <a name="security-dashboard-in-the-security--compliance-center"></a>Panel de seguridad en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Funciones básicas y cómo abrir el panel de seguridad

El Centro de seguridad & cumplimiento en <https://protection.office.com> permite a su organización administrar la protección y el cumplimiento de datos. Suponiendo que tiene los permisos necesarios, el Panel de seguridad le permite revisar el estado de protección contra amenazas, así como ver y actuar en alertas de seguridad.

Vea el vídeo para obtener información general y, a continuación, lea este artículo para obtener más información.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Según lo que incluya la suscripción de su organización, el Panel de seguridad incluye varios widgets, como resumen de administración de amenazas, estado de protección contra amenazas, detecciones semanales globales de amenazas, malware y mucho más, como se describe en las secciones siguientes.

Para ver el Panel de seguridad en el Centro de seguridad & cumplimiento, vaya a Panel **de administración de** \> **amenazas**. Para ir directamente al panel seguridad, use <https://protection.office.com/searchandinvestigation/dashboard>.

> [!NOTE]
> Debe ser un administrador global, un administrador de seguridad o un lector de seguridad para ver el Panel de seguridad. Algunos widgets requieren permisos adicionales para verlos. Para obtener más información, [vea Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)[.

## <a name="threat-management-summary"></a>Resumen de administración de amenazas

El widget Resumen de administración de amenazas le indica de un vistazo cómo su organización se protegió de las amenazas en los últimos siete (7) días.

![Panel de seguridad: widget resumen de administración de amenazas.](../../media/SecDash-ThreatMgmtSummary.png)

La información que verá en el Resumen de administración de amenazas depende de lo que incluya la suscripción. En la tabla siguiente se describe qué información se incluye Office 365 E3 y Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Mensajes de malware bloqueados<br>Mensajes de suplantación de identidad bloqueados<br>Mensajes notificados por usuarios<br><br><br><br>|Mensajes de malware bloqueados<br>Mensajes de suplantación de identidad bloqueados<br>Mensajes notificados por usuarios<br>Malware de día cero bloqueado<br>Mensajes de phishing avanzados detectados<br>Direcciones URL malintencionadas bloqueadas|

Para ver o obtener acceso al widget Resumen de administración de amenazas, debe tener permisos para ver Defender para Office 365 informes. Para obtener más información, vea [¿Qué permisos son necesarios para ver los informes de Defender Office 365 datos?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Estado de protección contra amenazas

El widget Estado de protección contra amenazas muestra la eficacia de la protección contra amenazas con una vista detallada y actual de la suplantación de identidad (phish) y malware.

![Widget de estado de protección contra amenazas.](../../media/tpswidget.png)

Los detalles dependen de si su suscripción Microsoft 365 incluye [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) con [o sin Microsoft Defender para Office 365](defender-for-office-365.md).

|Si la suscripción incluye...|Verá estos detalles|
|---|---|
|EOP pero no Microsoft Defender para Office 365|Correo electrónico malintencionado detectado y bloqueado por EOP.<p> Consulte [Informe de estado de protección contra amenazas (EOP).](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender para Office 365|Contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por EOP y Defender para Office 365 <p> Recuento agregado de mensajes de correo electrónico únicos con contenido malintencionado bloqueado por el motor antimalware[, purga](zero-hour-auto-purge.md) automática de cero horas y Defender para características de [Office 365](safe-links.md) (incluidos los vínculos de Caja fuerte, los datos adjuntos de [Caja fuerte](safe-attachments.md) y la suplantación de identidad en [Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)). <p> Consulte [Informe de estado de protección contra amenazas](view-reports-for-mdo.md#threat-protection-status-report).|

Para ver o tener acceso al widget Estado de protección contra amenazas, debe tener permisos para ver Defender para Office 365 informes. Para obtener más información, vea [¿Qué permisos son necesarios para ver los informes de Defender para Office 365 informes?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Detecciones semanales globales de amenazas

El widget Detecciones semanales globales de amenazas muestra cuántas amenazas se detectaron en los mensajes de correo electrónico en los últimos siete (7) días.

![Widget Global Weekly Threat Detections.](../../media/globalweeklythreatdetections.png)

Las métricas se calculan como se describe en la tabla siguiente:

|Métrica|Cómo se calcula|
|---|---|
|Mensajes analizados|Número de mensajes de correo electrónico analizados multiplicado por el número de destinatarios|
|Amenazas detenidas|Número de mensajes de correo electrónico identificados como que contienen malware multiplicado por el número de destinatarios|
|Bloqueado por [Defender para Office 365](defender-for-office-365.md)|Número de mensajes de correo electrónico bloqueados por Defender Office 365 multiplicado por el número de destinatarios|
|Eliminado después de la entrega|Número de mensajes eliminados por purga [automática de cero horas (ZAP)](zero-hour-auto-purge.md) multiplicado por el número de destinatarios|

## <a name="malware"></a>Malware

Los widgets de malware muestran detalles sobre tendencias de malware y tipos de familia de malware en los últimos siete (7) días.

![Tendencias de malware y tipos de familia.](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Insights

Ideas los problemas principales de superficie que debes revisar, también incluyen recomendaciones y acciones que debes tener en cuenta.

![Información inteligente.](../../media/smartinsights.png)

Por ejemplo, es posible que vea que los mensajes de correo electrónico de suplantación de identidad se están entregando porque algunos usuarios han deshabilitado sus opciones de correo no deseado. Para obtener más información sobre cómo funcionan las [perspectivas, vea Informes y perspectivas en el Centro de seguridad & cumplimiento](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Investigación y respuesta de amenazas

Si la suscripción de su organización incluye [Microsoft Defender para Office 365 Plan 2](office-365-ti.md), el Panel de seguridad tiene una sección que incluye herramientas avanzadas de investigación y respuesta de amenazas. Estas herramientas incluyen [capacidades automatizadas de investigación y respuesta](automated-investigation-response-office.md). La investigación y respuesta automatizadas pueden ser útiles en escenarios como el abordamiento [rápido de cuentas de usuario comprometidas](address-compromised-users-quickly.md).

Para obtener más información, vea [Introducción al uso de la investigación y respuesta automatizadas (AIR) en Office 365](office-365-air.md).

## <a name="trends"></a>Tendencias

Cerca de la parte inferior del Panel de seguridad hay **una sección Tendencias** , que resume las tendencias de flujo de correo electrónico de su organización. Los informes proporcionan información sobre el correo electrónico categorizado como correo no deseado, malware, intentos de suplantación de identidad y correo electrónico bueno. Haga clic en un icono para ver información más detallada en el informe.

![En la sección Tendencias se resumen las tendencias de flujo de correo electrónico de la organización.](../../media/trends.png)

Y, si la suscripción de su organización incluye el [Plan 2 de Defender para Office 365](office-365-ti.md), también tendrá un informe de alertas  de administración de amenazas recientes en esta sección que permite al equipo de seguridad ver y tomar medidas en alertas de seguridad de alta prioridad.

Para ver o tener acceso al widget Correo electrónico enviado y recibido, debe tener permisos para ver Defender para Office 365 informes. Para obtener más información, vea [¿Qué permisos son necesarios para ver los informes de Defender Office 365 datos?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Para ver o tener acceso al widget Alertas de administración de amenazas recientes, debe tener permisos para ver alertas. Para obtener más información, consulte [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-articles"></a>Artículos relacionados

[Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento](view-email-security-reports.md)

[Ver informes de Microsoft Defender para Office 365](view-reports-for-mdo.md)

[Defender para Office 365](defender-for-office-365.md)

[Office 365 investigación y respuesta de amenazas](office-365-ti.md)
