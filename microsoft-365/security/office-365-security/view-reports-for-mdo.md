---
title: Ver informes de Defender para Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a buscar y usar defender para Office 365 informes que están disponibles en el portal Microsoft 365 Defender web.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7eab856f22ac1c2282e83897db6e3f93d4d97e6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083517"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Ver Defender para obtener Office 365 informes en el portal Microsoft 365 Defender web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender para organizaciones Office 365 (por ejemplo, suscripciones Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 1 o Microsoft Defender para complementos del Plan 2 de Office 365) contienen una variedad de informes relacionados con la seguridad. Si tiene los [permisos](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)necesarios, puede ver estos informes en el  portal de Microsoft 365 Defender yendo a Informes de correo electrónico & colaboración Correo electrónico & informes \>  \> **de colaboración**. Para ir directamente a la página **Informes de colaboración & correo** electrónico, abra <https://security.microsoft.com/emailandcollabreport> .

![Página & informes de colaboración de correo electrónico en el portal de Microsoft 365 Defender web](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> Los informes de seguridad de correo electrónico que no requieren Defender para Office 365 se describen en Ver informes de seguridad de correo electrónico [en el portal Microsoft 365 Defender correo](view-email-security-reports.md)electrónico .
>
> Los informes relacionados con el flujo de correo se encuentran ahora en el Centro Exchange administración (EAC). Para obtener más información acerca de estos informes, vea Informes de flujo de correo [en el nuevo centro Exchange administración.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

## <a name="safe-attachments-file-types-report"></a>Caja fuerte Informe de tipos de archivo de datos adjuntos

> [!NOTE]
> El **informe Caja fuerte tipos de archivos adjuntos** desaparecerá finalmente. La misma información está disponible en el informe [de estado de protección contra amenazas](#threat-protection-status-report).

## <a name="safe-attachments-message-disposition-report"></a>Caja fuerte Informe de eliminación de mensajes de datos adjuntos

> [!NOTE]
> El **Caja fuerte de eliminación** de mensajes de datos adjuntos desaparecerá. La misma información está disponible en el informe [de estado de protección contra amenazas](#threat-protection-status-report).

## <a name="mail-latency-report"></a>Informe de latencia de correo

El **informe de latencia de** correo muestra una vista agregada de la latencia de entrega y detonación de correo experimentada en su organización. Los tiempos de entrega de correo en el servicio se ven afectados por una serie de factores y el tiempo de entrega absoluto en segundos a menudo no es un buen indicador de éxito o un problema. Un tiempo de entrega lento en un día puede considerarse un promedio de tiempo de entrega en otro día, o viceversa. Esto intenta calificar la entrega de mensajes en función de datos estadísticos sobre los tiempos de entrega observados de otros mensajes.

La latencia de red y del lado cliente no se incluyen.

Para ver el informe, abra el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración.** En la página **Informes de colaboración &** correo electrónico, busque Informe de latencia **de** correo y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/mailLatencyReport> .

![Widget de informe de latencia de correo en la página Informes de colaboración & correo electrónico](../../media/mail-latency-report-widget.png)

En la **página Informe de latencia de** correo, las pestañas siguientes están disponibles en la página Informe de latencia **de** correo:

- **Percentil 50:** este es el medio para los tiempos de entrega de mensajes. Puede considerar este valor como un tiempo medio de entrega. Esta pestaña está seleccionada de forma predeterminada.
- **Percentil 90:** esto indica una latencia alta para la entrega de mensajes. Solo el 10 % de los mensajes tardaron más de este valor en entregarse.
- **Percentil 99:** indica la latencia más alta para la entrega de mensajes.

Independientemente de la pestaña que seleccione, el gráfico muestra los mensajes organizados en las siguientes categorías:

- **Latencia de entrega de correo**
- **Detonaciones**

Al pasar el mouse sobre una categoría del gráfico, puede ver un desglose de la latencia en cada categoría.

![Vista percentil 50 del informe de latencia de correo](../../media/mail-latency-report-50th-percentile-view.png)

Si hace clic **en Filtrar,** puede filtrar el gráfico y la tabla de detalles por los siguientes valores:

- **Fecha (UTC):** **fecha de inicio y** fecha de **finalización**
- **Vista de** mensaje: uno de los siguientes valores:
  - **Todos los mensajes**
  - **Mensajes que contienen datos adjuntos o direcciones URL**
  - **Mensajes detonados**

Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Fecha (UTC)**
- **Percentiles:** **50**, **90** o **99**
- **Recuento de mensajes**
- **Latencia general**

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El **informe de estado** de protección contra amenazas es una única vista que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y Microsoft Defender para Office 365. Para obtener más información, vea [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Informe de protección contra amenazas de url

El **informe de protección contra** amenazas url proporciona vistas de resumen y tendencias para las amenazas detectadas y las acciones realizadas en los clics de dirección URL como parte de Caja fuerte [vínculos](safe-links.md). Este informe no tendrá los datos de clic de los usuarios en los que la directiva de vínculos de Caja fuerte tiene seleccionada la opción No realizar seguimiento de los **clics del** usuario.

Para ver el informe, abra el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración.** En la página **Informes de colaboración &** correo electrónico, busque la página protección de direcciones **URL** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/URLProtectionActionReport> .

![Widget de informe de protección de direcciones URL en la página Informes de & de colaboración](../../media/url-protection-report-widget.png)

Las vistas disponibles en la página **informe de protección contra** amenazas de url se describen en las secciones siguientes.

> [!NOTE]
> Se trata de un *informe de tendencias de protección,* lo que significa que los datos representan tendencias en un conjunto de datos más grande. Como resultado, los datos de los gráficos no están disponibles en tiempo real aquí, pero los datos de la tabla de detalles lo son, por lo que puede ver una ligera discrepancia entre los dos. Los gráficos se actualizan una vez cada cuatro horas y contienen datos de los últimos 90 días.

### <a name="view-data-by-url-click-protection-action"></a>Ver datos por acción de protección de clics de dirección URL

![Vista de acción de protección de clic de url en el informe de protección contra amenazas de url](../../media/url-threat-protection-report-url-click-protection-action-view.png)

La **vista Ver datos por acción** de protección de clics de dirección URL muestra el número de clics de dirección URL de los usuarios de la organización y los resultados del clic:

- **Permitido:** se le permitió al usuario navegar a la dirección URL.
- **Bloqueado:** se bloqueó al usuario para que no navegara a la dirección URL.
- **Bloqueado y hecho clic en:** el usuario ha elegido continuar navegando a la dirección URL.
- **Se ha hecho clic durante el examen:** el usuario ha hecho clic en el vínculo antes de completar el examen.

Un clic indica que el usuario ha hecho clic a través de la página de bloqueo en el sitio web malintencionado (los administradores pueden deshabilitar el clic en las directivas de vínculos Caja fuerte usuario).

Si hace clic **en Filtros,** puede modificar el informe y la tabla de detalles seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:

- **Fecha (UTC):** **fecha de inicio y** fecha de **finalización**
- **Detección**:
  - **Permitido**
  - **Bloqueado**
  - **Bloqueado y hecho clic**
  - **Se ha hecho clic durante el examen**
- **Dominios:** los dominios url enumerados en los resultados del informe.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.

La tabla de detalles debajo del gráfico proporciona la siguiente vista casi en tiempo real de todos los clics que se han producido en la organización durante los últimos 7 días:

- **Hora de hacer clic**
- **Usuario**
- **URL**
- **Action**
- **Aplicación**

### <a name="view-data-by-url-click-by-application"></a>Ver datos por dirección URL hacer clic por aplicación

![Url click by application view in the URL threat protection report](../../media/url-threat-protection-report-url-click-by-application-view.png)

La **vista Ver datos por dirección URL clic** por aplicación muestra el número de clics de dirección URL de las aplicaciones que admiten Caja fuerte vínculos:

- **Cliente de correo electrónico**
- **PowerPoint**
- **Word**
- **Excel**
- **OneNote**
- **Visio**
- **Teams**
- **Otros**

Si hace clic **en Filtros,** puede modificar el informe y la tabla de detalles seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:

- **Fecha (UTC):** **fecha de inicio y** fecha de **finalización**
- **Detección:** aplicaciones disponibles del gráfico.
- **Dominios:** los dominios url enumerados en los resultados del informe.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.

La tabla de detalles debajo del gráfico proporciona la siguiente vista casi en tiempo real de todos los clics que se han producido en la organización durante los últimos 7 días:

- **Hora de hacer clic**
- **Usuario**
- **URL**
- **Action**
- **Aplicación**

## <a name="additional-reports-to-view"></a>Informes adicionales para ver

Además de los informes descritos en este artículo, hay otros informes disponibles, como se describe en la tabla siguiente:

<br>

****

|Informe|Tema|
|---|---|
|**Explorer** (Microsoft Defender para Office 365 plan 2) o detecciones en tiempo **real** (Microsoft Defender para Office 365 Plan 1)|[Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md)|
|**Informes de seguridad de** correo electrónico, como el informe de remitentes y destinatarios principales, el informe de correo suplantación de identidad y el informe de detecciones de correo no deseado.|[Ver informes de seguridad de correo electrónico en el portal Microsoft 365 Defender correo electrónico](view-email-security-reports.md)|
|**Informes de flujo de** correo, como el informe de reenvío, el informe de estado de flujo de correo y el informe Principales remitentes y destinatarios.|[Informes de flujo de correo en el nuevo centro Exchange administración](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|**Seguimiento de direcciones URL para Caja fuerte (solo** PowerShell). El resultado de este cmdlet muestra los resultados de las acciones Caja fuerte links en los últimos siete días.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**Resultados de tráfico de correo para EOP** y Microsoft Defender para Office 365 (solo PowerShell). El resultado de este cmdlet contiene información sobre Dominio, Fecha, Tipo de evento, Dirección, Acción y Recuento de mensajes.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**Informes de detalles de correo para EOP y Defender para Office 365 (solo** PowerShell). El resultado de este cmdlet contiene detalles sobre archivos o direcciones URL malintencionados, intentos de suplantación, suplantación y otras amenazas potenciales en el correo electrónico o los archivos.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>¿Qué permisos se necesitan para ver el Defender para Office 365 informes?

Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el portal de Microsoft 365 Defender web:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

**Nota:** Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en defender para los informes Office 365, compruebe que las directivas están configuradas correctamente. Su organización debe tener definidas [Caja fuerte de](set-up-safe-links-policies.md) vínculos y Caja fuerte [de](set-up-safe-attachments-policies.md) datos adjuntos para que Defender Office 365 protección esté en su lugar. Vea también Protección contra correo no deseado y [antimalware.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Temas relacionados

[Informes e información inteligentes en el portal Microsoft 365 Defender web](reports-and-insights-in-security-and-compliance.md)

[Permisos de función (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
