---
title: Ver informes de Defender para Office 365
f1.keywords:
- CSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a buscar y usar los informes de Defender para Office 365 que están disponibles en el portal de Microsoft 365 Defender.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed83064d1686d1cf556e0b2dcca5766556c5fa3
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64970955"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Ver informes de Defender para Office 365 en el portal de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender para Office 365 organizaciones (por ejemplo, Microsoft 365 E5 suscripciones o Microsoft Defender para Office 365 Plan 1 o Microsoft Defender para Office 365 complementos del plan 2) contienen una variedad de informes relacionados con la seguridad. Si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), puede ver y descargar estos informes en el portal de Microsoft 365 Defender.

## <a name="view-and-download-reports"></a>Ver o descargar informes

### <a name="view-reports"></a>Ver informes

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> **correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. Para ir directamente a la página **De informes de colaboración & correo electrónico** , use <https://security.microsoft.com/emailandcollabreport>.

1. Elija el informe que desea ver y, a continuación, seleccione **Ver detalles**.

### <a name="download-reports"></a>Descargar informes

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **InformesEmail**  >  & informes de colaboración \> **para su descarga**. Para ir directamente a la página **Informes para descarga** , use <https://security.microsoft.com/ReportsForDownload?viewid=custom>.

:::image type="content" source="../../media/email-collaboration-download-reports.png" alt-text="La página Informes de colaboración por correo electrónico & en el portal de Microsoft 365 Defender" lightbox="../../media/email-collaboration-download-reports.png":::

> [!NOTE]
>
> Los informes de seguridad de correo electrónico que no requieren Defender para Office 365 se describen en [Ver informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](view-email-security-reports.md).
>
> Los informes relacionados con el flujo de correo están ahora en el centro de administración de Exchange (EAC). Para obtener más información sobre estos informes, consulte [Informes de flujo de correo en el nuevo centro de administración de Exchange](/exchange/monitoring/mail-flow-reports/mail-flow-reports).

## <a name="safe-attachments-file-types-report"></a>informe de tipos de archivo de datos adjuntos de Caja fuerte

> [!NOTE]
> Este informe ha quedado en desuso. La misma información está disponible en el [informe de estado de protección contra amenazas](#threat-protection-status-report).

## <a name="safe-attachments-message-disposition-report"></a>Caja fuerte informe de eliminación de mensajes de datos adjuntos

> [!NOTE]
> Este informe ha quedado en desuso. La misma información está disponible en el [informe de estado de protección contra amenazas](#threat-protection-status-report).

## <a name="mail-latency-report"></a>Informe de latencia de correo

El **informe Latencia de correo** muestra una vista agregada de la latencia de entrega y detonación de correo experimentada en su organización. Los tiempos de entrega de correo en el servicio se ven afectados por una serie de factores, y el tiempo de entrega absoluto en segundos no suele ser un buen indicador de éxito o problema. Un tiempo de entrega lento en un día podría considerarse un tiempo medio de entrega en otro día, o viceversa. Esto intenta calificar la entrega de mensajes en función de los datos estadísticos sobre los tiempos de entrega observados de otros mensajes.

No se incluyen el lado cliente ni la latencia de red.

Para ver el informe, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. Para ir directamente a la página **De informes de colaboración & correo electrónico** , use <https://security.microsoft.com/emailandcollabreport>.

En la página **Informes de colaboración por correo electrónico &** , busque **Informe de latencia de correo** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, use <https://security.microsoft.com/mailLatencyReport>.

:::image type="content" source="../../media/mail-latency-report-widget.png" alt-text="Widget Informe de latencia de correo en la página Informes de colaboración de & correo electrónico" lightbox="../../media/mail-latency-report-widget.png":::

En la página **Informe de latencia de correo** , las pestañas siguientes están disponibles en la página **Informe de latencia de correo** :

- **Percentil 50**: este es el medio para los tiempos de entrega de mensajes. Puede considerar este valor como un tiempo medio de entrega. Esta pestaña está seleccionada de forma predeterminada.
- **Percentil 90**: indica una latencia alta para la entrega de mensajes. Solo el 10 % de los mensajes tardó más que este valor en entregarse.
- **Percentil 99**: indica la latencia más alta para la entrega de mensajes.

Independientemente de la pestaña que seleccione, el gráfico muestra los mensajes organizados en las categorías siguientes:

- **En general**
- **Detonación**

Al mantener el puntero sobre una categoría del gráfico, puede ver un desglose de la latencia en cada categoría.

:::image type="content" source="../../media/mail-latency-report-50th-percentile-view.png" alt-text="Vista de percentil 50 del informe de latencia de correo" lightbox="../../media/mail-latency-report-50th-percentile-view.png":::

Si hace clic en **Filtrar**, puede filtrar el gráfico y la tabla de detalles por los siguientes valores:

- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**
- **Vista de mensajes**: uno de los siguientes valores:
  - **Todos los mensajes**
  - **Mensajes detonados**: uno de los siguientes valores:
    - **Detonación en línea**: incluye mensajes que se prueban completamente antes de la entrega.
    - **Detonación asincrónica**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Fecha (UTC)**
- **Latencia**
- **Recuento de mensajes**
- **Percentil 50**
- **Percentil 90**
- **Percentil 99**

En la página principal del informe, el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **[El botón Exportar](view-email-security-reports.md#export-report)** está disponible.

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El informe **de estado de protección contra amenazas** es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y Microsoft Defender para Office 365. Para obtener más información, consulte [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).

## <a name="top-senders-and-recipients-report"></a>Informe de remitentes y destinatarios principales

El informe **Principales remitentes y destinatarios** muestra los destinatarios principales de las características de protección de EOP y Defender para Office 365. Para obtener más información, vea [Informe de remitentes y destinatarios principales](view-email-security-reports.md#top-senders-and-recipients-report).

## <a name="url-protection-report"></a>Informe de protección de direcciones URL

El **informe de protección de direcciones URL** proporciona vistas de resumen y tendencias para las amenazas detectadas y las acciones realizadas en los clics de dirección URL como parte de [Caja fuerte Vínculos](safe-links.md). Este informe no tendrá datos de clic de usuarios en los que se aplicó la directiva de vínculos de Caja fuerte cuando no está seleccionada la opción **Seguimiento de clics del usuario**.

Para ver el informe, abra el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración de & por correo electrónico** , busque **la página Protección de direcciones URL** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/URLProtectionActionReport>.

:::image type="content" source="../../media/url-protection-report-widget.png" alt-text="Widget de informe de protección de direcciones URL en la página Informes de colaboración & correo electrónico" lightbox="../../media/url-protection-report-widget.png":::

Las vistas disponibles en la página del informe **de protección de direcciones URL** se describen en las secciones siguientes.

> [!NOTE]
> Se trata de un *informe de tendencias de protección*, lo que significa que los datos representan tendencias en un conjunto de datos mayor. Como resultado, los datos de los gráficos no están disponibles en tiempo real aquí, pero los datos de la tabla de detalles son, por lo que es posible que vea una ligera discrepancia entre los dos. Los gráficos se actualizan una vez cada cuatro horas y contienen datos de los últimos 90 días.

### <a name="view-data-by-url-click-protection-action"></a>Ver datos por acción de protección de clics de dirección URL

:::image type="content" source="../../media/url-threat-protection-report-url-click-protection-action-view.png" alt-text="La vista, es decir, la acción de protección de clics de dirección URL en el informe de protección de direcciones URL" lightbox="../../media/url-threat-protection-report-url-click-protection-action-view.png":::

En la vista **Ver datos por acción de protección de clics de dirección URL** se muestra el número de clics de dirección URL por parte de los usuarios de la organización y los resultados del clic:

- **Permitido**: se permiten clics.
- **Permitido por el administrador de inquilinos**: se permiten clics en las directivas de vínculos de Caja fuerte.
- **Bloqueado**: haga clic en Bloqueado.
- **Bloqueado por el administrador de inquilinos**: los clics bloqueados en las directivas de vínculos de Caja fuerte.
- **Bloqueado y en el que se ha hecho clic**: clics bloqueados en los que los usuarios hacen clic en la dirección URL bloqueada.
- **Bloqueado por el administrador de inquilinos y ha hecho clic en**: el administrador ha bloqueado el vínculo, pero el usuario ha hecho clic a través de.
- **Se ha hecho clic durante el examen**: hace clic en el lugar donde los usuarios hacen clic en la página de examen pendiente en la dirección URL.
- **Examen pendiente**: hace clic en las direcciones URL que están pendientes de un veredicto de examen.

Un clic indica que el usuario ha hecho clic a través de la página de bloque en el sitio web malintencionado (los administradores pueden deshabilitar hacer clic en las directivas de vínculos de Caja fuerte).

Si hace clic en **Filtros**, puede modificar el informe y la tabla de detalles seleccionando uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**
- **Acción**:
  - **Permitido**
  - **Bloqueado**
  - **Permitido por el administrador de inquilinos**
  - **Bloqueado y en el que se hace clic**
  - **Bloqueado por el administrador de inquilinos y en el que se ha hecho clic**
  - **Se ha hecho clic durante el examen**
  - **Examen pendiente**
- **Dominios**: los dominios de dirección URL que aparecen en los resultados del informe.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

La tabla de detalles debajo del gráfico proporciona la siguiente vista casi en tiempo real de todos los clics que se han producido en la organización durante los últimos 7 días:

- **Tiempo de clic**
- **User**
- **URL**
- **Action**
- **Aplicación**

En la página principal del informe, el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](view-email-security-reports.md#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](view-email-security-reports.md#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](view-email-security-reports.md#export-report)** están disponibles.

### <a name="view-data-by-url-click-by-application"></a>Visualización de datos por url clic por aplicación

:::image type="content" source="../../media/url-threat-protection-report-url-click-by-application-view.png" alt-text="Vista de acción de protección de clics de dirección URL en el informe de protección de direcciones URL" lightbox="../../media/url-threat-protection-report-url-click-by-application-view.png":::

En **la vista Ver datos por dirección URL clic por aplicación** se muestra el número de clics de dirección URL por las aplicaciones que admiten vínculos de Caja fuerte:

- **Cliente de correo electrónico**
- **documento de Office**
- **Teams**

Si hace clic en **Filtros**, puede modificar el informe y la tabla de detalles seleccionando uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**
- **Detección**: aplicaciones disponibles en el gráfico.
- **Dominios**: los dominios de dirección URL que aparecen en los resultados del informe.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

La tabla de detalles debajo del gráfico proporciona la siguiente vista casi en tiempo real de todos los clics que se han producido en la organización durante los últimos 7 días:

- **Tiempo de clic**
- **User**
- **URL**
- **Action**
- **Aplicación**

En la página principal del informe, el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](view-email-security-reports.md#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](view-email-security-reports.md#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](view-email-security-reports.md#export-report)** están disponibles.

## <a name="additional-reports-to-view"></a>Informes adicionales que se van a ver

Además de los informes descritos en este artículo, hay varios informes disponibles, como se describe en la tabla siguiente:

|Informe|Tema|
|---|---|
|**Explorador** (Microsoft Defender para Office 365 Plan 2) o **detecciones en tiempo real** (Microsoft Defender para Office 365 Plan 1)|[Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md)|
|Informes de seguridad de correo electrónico que no requieren Defender para Office 365|[Visualización de informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](view-email-security-reports.md)|
|Informes de flujo de correo en el Centro de administración de Exchange (EAC)|[Informes de flujo de correo en el nuevo centro de administración de Exchange](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|

Cmdlets de informes de PowerShell:

|Informe|Tema|
|---|---|
|Destinatarios y remitentes principales|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|Malware principal|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|Tráfico de correo|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|Vínculos seguros|[Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|Usuarios en peligro|[Get-CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [Get-CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|Estado del flujo de correo|[Get-MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|Usuarios suplantados|[Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport)|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>¿Qué permisos se necesitan para ver los informes de Defender para Office 365?

Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el portal de Microsoft 365 Defender:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

**Nota**: Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características en Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en los informes de Defender para Office 365, compruebe que las directivas están configuradas correctamente. Su organización debe tener definidas [directivas de vínculos de Caja fuerte](set-up-safe-links-policies.md) y [directivas de datos adjuntos de Caja fuerte](set-up-safe-attachments-policies.md) para que Defender para Office 365 protección esté en vigor. Consulte también [Protección contra correo no deseado y antimalware](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Temas relacionados

[Informes inteligentes e información en el portal de Microsoft 365 Defender](reports-and-insights-in-security-and-compliance.md)

[Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)
