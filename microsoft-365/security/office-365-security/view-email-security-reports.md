---
title: Ver informes de seguridad de correo electrónico
f1.keywords:
- NOCSH
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
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a buscar y usar los informes de seguridad de correo electrónico que están disponibles en el portal de Microsoft 365 Defender.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d97442fc2c3767a30c1ea98dc4a1ee7a38e56b45
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64971009"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>Visualización de informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hay varios informes disponibles en el portal de Microsoft 365 Defender en <https://security.microsoft.com> para ayudarle a ver cómo las características de seguridad del correo electrónico, como las características contra correo no deseado y antimalware en Microsoft 365 protegen su organización. Si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver y descargar estos informes como se describe en este artículo.

> [!NOTE]
>
> Algunos de los informes de la página **Informes de colaboración de & por correo electrónico** requieren Microsoft Defender para Office 365. Para obtener información sobre estos informes, vea [Ver informes de Defender para Office 365 en el portal de Microsoft 365 Defender](view-reports-for-mdo.md).
>
> Los informes relacionados con el flujo de correo están ahora en el centro de administración de Exchange. Para obtener más información sobre estos informes, consulte [Informes de flujo de correo en el nuevo centro de administración de Exchange](/exchange/monitoring/mail-flow-reports/mail-flow-reports).

## <a name="email-security-report-changes-in-the-microsoft-365-defender-portal"></a>Cambios en el informe de seguridad de correo electrónico en el portal de Microsoft 365 Defender

En la tabla siguiente se describen los informes Exchange Online Protection (EOP) y Microsoft Defender para Office 365 del portal de Microsoft 365 Defender que se han reemplazado, movido o en desuso.

|Cmdlets y informes en desuso|Nuevos informes y cmdlets|Identificador del Centro de mensajes|Fecha|
|---|---|:---:|:---:|
|**Seguimiento de URL** <p> Get-URLTrace|[Informe de protección de direcciones URL](view-reports-for-mdo.md#url-protection-report) <p> [Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <br> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|MC239999|Junio de 2021|
|**Informe de correo electrónico enviado y recibido** <p> Get-MailTrafficReport <br> Get-MailDetailReport|[Informe de estado de protección contra amenazas](#threat-protection-status-report) <br> [Informe de estado de flujo de correo](#mailflow-status-report) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <br> [Get-MailFlowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|MC236025|Junio de 2021|
|**Informe de reenvío** <p> sin cmdlets|[Informe de mensajes reenviados automáticamente en el EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) <p> sin cmdlets|MC250533|Junio de 2021|
|**informe de tipos de archivo de datos adjuntos de Caja fuerte** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[Informe de estado de protección contra amenazas: Visualización de datos por malware por correo electrónico \>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250532|Junio de 2021|
|**Caja fuerte informe de eliminación de mensajes de datos adjuntos** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[Informe de estado de protección contra amenazas: Visualización de datos por malware por correo electrónico \>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250531|Junio de 2021|
|**Malware detectado en el informe de correo electrónico** <p> Get-MailTrafficReport <br> Get-MailDetailMalwareReport|[Informe de estado de protección contra amenazas: Visualización de datos por malware por correo electrónico \>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250530|Junio de 2021|
|**Informe de detección de correo no deseado** <p> Get-MailTrafficReport <br> Get-MailDetailSpamReport|[Informe de estado de protección contra amenazas: Visualización de datos por correo no deseado por correo electrónico \>](#view-data-by-email--spam-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250529|Octubre de 2021|
|Get-AdvancedThreatProtectionDocumentReport <p> Get-AdvancedThreatProtectionDocumentDetail|[Get-ContentMalwareMdoAggregateReport](/powershell/module/exchange/get-contentmalwaremdoaggregatereport) <p> [Get-ContentMalwareMdoDetailReport](/powershell/module/exchange/get-contentmalwaremdodetailreport)|TBA|Mayo de 2022|
|**Exchange informe de reglas de transporte** <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|[Exchange informe de reglas de transporte en el EAC](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report) <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|MC316157|Abril de 2022|
|Get-MailTrafficTopReport|[Informe de estado de protección contra amenazas: Visualización de datos por malware por correo electrónico \>](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <p> **Nota**: No hay ningún reemplazo para las funcionalidades de informes de cifrado en Get-MailTrafficTopReport.|MC315742|Abril de 2022|

## <a name="compromised-users-report"></a>Informe de usuarios en peligro

> [!NOTE]
> Este informe está disponible en Microsoft 365 organizaciones con buzones de Exchange Online. No está disponible en organizaciones independientes de Exchange Online Protection (EOP).

El informe **Usuarios en peligro** muestra el número de cuentas de usuario marcadas como **Sospechosas** o **Restringidas** en los últimos 7 días. Las cuentas de cualquiera de estos estados son problemáticas o incluso están en peligro. Con el uso frecuente, puede usar el informe para detectar picos, e incluso tendencias, en cuentas sospechosas o restringidas. Para obtener más información sobre los usuarios en peligro, vea [Responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).

:::image type="content" source="../../media/compromised-users-report-widget.png" alt-text="Widget Usuarios en peligro en la página Informes de colaboración & correo electrónico" lightbox="../../media/compromised-users-report-widget.png":::

La vista de agregado muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.

Para ver el informe en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración de & por correo electrónico** , busque **Usuarios en peligro** y haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/CompromisedUsers>.

En la página **Usuarios en peligro** , el gráfico muestra la siguiente información para el intervalo de fechas especificado:

- **Restringido**: se ha restringido el envío de correo electrónico a la cuenta de usuario debido a patrones altamente sospechosos.
- **Sospechoso**: la cuenta de usuario ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restrinja el envío de correo electrónico.

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Tiempo de creación**
- **Nombre de usuario**
- **Action**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**.
- **Actividad**: **restringida** o **sospechosa**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Usuarios en peligro** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

:::image type="content" source="../../media/compromised-users-report-activity-view.png" alt-text="Vista Informe del informe Usuarios en peligro" lightbox="../../media/compromised-users-report-activity-view.png":::

## <a name="exchange-transport-rule-report"></a>Exchange informe de reglas de transporte

El informe **Exchange regla de transporte** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.

Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración por correo electrónico &**, busque **Exchange regla de transporte** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/ETRRuleReport>.

:::image type="content" source="../../media/transport-rule-report-widget.png" alt-text="Widget Exchange regla de transporte en la página Informes de colaboración & correo electrónico" lightbox="../../media/transport-rule-report-widget.png":::

En la página **Exchange informe de reglas de transporte**, los gráficos y los datos disponibles se describen en las secciones siguientes.
> [!NOTE]
> El **informe Exchange regla de transporte** ya está disponible en el EAC. Para obtener más información, vea [Exchange informe de reglas de transporte en el nuevo EAC](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report).

### <a name="chart-breakdown-by-direction"></a>Desglose del gráfico por dirección

:::image type="content" source="../../media/transport-rule-report-etr-direction-view.png" alt-text="La vista Dirección de las reglas de transporte de Exchange en el informe de reglas de transporte de Exchange" lightbox="../../media/transport-rule-report-etr-direction-view.png":::

Si selecciona **Desglose de gráficos por dirección**, están disponibles los siguientes gráficos:

- **Ver datos por Exchange reglas de transporte**: el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de flujo de correo.
- **Ver datos por las reglas de transporte de Exchange DLP**: el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de flujo de correo de prevención de pérdida de datos (DLP).

La siguiente información se muestra en la tabla de detalles debajo del gráfico:

- **Date**
- **Directiva DLP** (solo **ver datos mediante reglas de transporte Exchange DLP**)
- **Regla de transporte**
- **Subject**
- **Dirección del remitente**
- **Dirección del destinatario**
- **Gravedad**
- **Dirección**

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**.
- **Dirección**: **saliente** y **entrante**.
- **Gravedad**: **gravedad alta**, **gravedad media** y **gravedad baja**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Exchange informe de reglas de transporte**, el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="chart-breakdown-by-severity"></a>Desglose del gráfico por gravedad

:::image type="content" source="../../media/transport-rule-report-etr-severity-view.png" alt-text="Vista gravedad de las reglas de transporte de Exchange en el informe de reglas de transporte de Exchange" lightbox="../../media/transport-rule-report-etr-severity-view.png":::

Si selecciona **Desglose del gráfico por gravedad**, están disponibles los siguientes gráficos:

- **Ver datos por Exchange reglas de transporte**: el número de mensajes de **gravedad alta**, **gravedad media** y **gravedad baja**. Establezca el nivel de gravedad como una acción en la regla (**Audite esta regla con el nivel de gravedad** o _SetAuditSeverity_). Para obtener más información, vea [Acciones de regla de flujo de correo en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Ver datos por las reglas de transporte de Exchange DLP**: el número de mensajes de **gravedad alta**, **gravedad media** y **baja** que se vieron afectados por las reglas de flujo de correo DLP.

La siguiente información se muestra en la tabla de detalles debajo del gráfico:

- **Date**
- **Directiva DLP** (solo **ver datos mediante reglas de transporte Exchange DLP**)
- **Regla de transporte**
- **Subject**
- **Dirección del remitente**
- **Dirección del destinatario**
- **Gravedad**
- **Dirección**

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Dirección**: **saliente** y **entrante**
- **Gravedad**: **gravedad alta**, **gravedad media** y **gravedad baja**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Exchange informe de reglas de transporte**, el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

## <a name="forwarding-report"></a>Informe de reenvío

> [!NOTE]
> Este informe ya está disponible en el EAC. Para obtener más información, vea [Informe de mensajes reenviados automáticamente en el nuevo EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).

## <a name="mailflow-status-report"></a>Informe de estado de flujo de correo

El **informe de estado de Flujo** de correo es un informe inteligente que muestra información sobre correo electrónico entrante y saliente, detecciones de correo no deseado, malware, correo electrónico identificado como "bueno" e información sobre el correo electrónico permitido o bloqueado en el perímetro. Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que se le permita entrar en el servicio para su evaluación por Exchange Online Protection (EOP). Es importante comprender que si se envía un mensaje a cinco destinatarios, lo contamos como cinco mensajes diferentes y no como un mensaje.

Para ver el informe en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración por correo electrónico &** , busque **Resumen de estado de Flujo de correo** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/mailflowStatusReport>.

:::image type="content" source="../../media/mail-flow-status-report-widget.png" alt-text="El widget de resumen de estado de Mailflow en la página Informes de colaboración & correo electrónico" lightbox="../../media/mail-flow-status-report-widget.png":::

### <a name="type-view-for-the-mailflow-status-report"></a>Vista de tipos para el informe de estado de Flujo de correo

:::image type="content" source="../../media/mail-flow-status-report-type-view.png" alt-text="Vista Tipo en el informe de estado de Flujo de correo" lightbox="../../media/mail-flow-status-report-type-view.png":::

En la página **Informe de estado de Flujo de correo** , la pestaña **Tipo** está seleccionada de forma predeterminada. El gráfico muestra la siguiente información para el intervalo de fechas especificado:

- **Correo electrónico correcto**: correo electrónico que se determina que no es correo no deseado o que las directivas de usuario o organización permiten.
- **Total**
- **Malware**: correo electrónico bloqueado como malware por varios filtros.
- **Correo electrónico de suplantación de identidad**: correo electrónico bloqueado como suplantación de identidad (phishing) por varios filtros.
- **Correo no deseado**: correo electrónico bloqueado como correo no deseado por varios filtros.
- **Protección perimetral**: correo electrónico que se rechaza en el perímetro o perímetro antes de ser evaluado por EOP o Defender para Office 365.
- **Mensajes de regla**: mensajes de correo electrónico sobre los que se han actuado mediante reglas de flujo de correo (también conocidas como reglas de transporte).

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Dirección**
- **Tipo**
- **24 horas**
- **3 días**
- **7 días**
- **15 días**
- **30 días**

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**.
- **Dirección del correo**: **entrante** y **saliente**.
- **Tipo**:
  - **Buen correo**
  - **Malware**
  - **Correo no deseado**
  - **Protección perimetral**
  - **Mensajes de regla**
  - **Correo de suplantación de identidad**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

De nuevo en la página **Informe de estado de Flujo de correo** , si hace clic en **Elegir una categoría para obtener más detalles**, puede seleccionar entre los valores siguientes:

- **Correo electrónico de phishing**: esta selección le lleva al [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- **Malware en el correo electrónico**: esta selección le lleva al [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- **Detecciones de correo no deseado**: esta selección le lleva al [informe Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).
- **Correo no deseado bloqueado** perimetral: esta selección le lleva al [informe Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).

En la página **Informe de estado de Flujo de correo** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)** y ![exportar icono.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="direction-view-for-the-mailflow-status-report"></a>Vista de dirección para el informe de estado de Flujo de correo

:::image type="content" source="../../media/mail-flow-status-report-direction-view.png" alt-text="Vista Dirección en el informe de estado de Flujo de correo" lightbox="../../media/mail-flow-status-report-direction-view.png":::

Si hace clic en la pestaña **Dirección** , el gráfico muestra la siguiente información para el intervalo de fechas especificado:

- **Entrantes**
- **Salida**

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**.
- **Dirección del correo**: **entrante** y **saliente**.
- **Tipo**:
  - **Buen correo**
  - **Malware**
  - **Correo no deseado**
  - **Protección perimetral**
  - **Mensajes de regla**
  - **Correo de suplantación de identidad**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

De nuevo en la página **Informe de estado de Flujo de correo** , si hace clic en **Elegir una categoría para obtener más detalles**, puede seleccionar entre los valores siguientes:

- **Correo electrónico de phishing**: esta selección le lleva al [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- **Malware en el correo electrónico**: esta selección le lleva al [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- **Detecciones de correo no deseado**: esta selección le lleva al [informe Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).
- **Correo no deseado bloqueado** perimetral: esta selección le lleva al [informe Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).

En la página **Informe de estado de Flujo de correo** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **Crear programación** y ![exportar icono.](../../media/m365-cc-sc-download-icon.png) Los botones **de exportación** están disponibles.

### <a name="mailflow-view-for-the-mailflow-status-report"></a>Vista de flujo de correo para el informe de estado de Flujo de correo

La vista **Flujo de correo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo electrónico entrante y saliente de su organización. Esta vista usa un diagrama de flujo horizontal (conocido como diagrama _de Sankey_ ) para proporcionar detalles sobre el recuento total de correo electrónico y cómo afectan a este recuento las características de protección contra amenazas configuradas, incluida la protección perimetral, el antimalware, el anti-phishing, el correo no deseado y la protección contra la suplantación de identidad.

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view.png" alt-text="La vista Flujo de correo en el informe de estado de Flujo de correo" lightbox="../../media/mail-flow-status-report-mailflow-view.png":::

La vista de agregado y la vista de tabla de detalles permiten 90 días de filtrado.

La información del diagrama está codificada por colores mediante **tecnologías EOP** o **Defender para Office 365**.

El diagrama se organiza en las siguientes bandas horizontales:

- **Banda de correo electrónico total** : este valor siempre se muestra primero.
- **Bloque perimetral** y banda **procesada** :
  - **Bloque perimetral**: mensajes filtrados en el perímetro e identificados como Protección perimetral.
  - **Procesado**: mensajes que controla la pila de filtrado.
- Banda de resultados:
  - **Bloque de reglas**: mensajes procesados por Exchange reglas de flujo de correo (reglas de transporte).
  - **Bloque de malware**: mensajes identificados como malware por varios filtros.<sup>\*</sup>
  - **Bloque phish**: mensajes identificados como phish durante el procesamiento por varios filtros.<sup>\*</sup>
  - **Bloque de correo no deseado**: mensajes identificados como correo no deseado durante el procesamiento por varios filtros.<sup>\*</sup>
  - **Bloque de suplantación**: mensajes detectados como suplantación de usuario o suplantación de dominio en Defender para Office 365.<sup>\*</sup>
  - **Bloque de detonación**: mensajes detectados durante la detonación de archivos o direcciones URL mediante directivas de datos adjuntos Caja fuerte o directivas de vínculos de Caja fuerte en Defender para Office 365.<sup>\*</sup>
  - **ZAP quitado**: mensajes que se quitan mediante la purga automática de cero horas (ZAP).<sup>\*</sup>
  - **Entregado**: mensajes entregados a los usuarios debido a una concesión.<sup>\*</sup>

Si mantiene el puntero sobre una banda horizontal en el diagrama, verá el número de mensajes relacionados.

<sup>\*</sup> Si hace clic en este elemento, el diagrama se expande para mostrar más detalles. Para obtener una descripción de cada elemento de los nodos expandidos, consulte [Tecnologías de detección](/office/office-365-management-api/office-365-management-activity-api-schema#detection-technologies).

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view-details.png" alt-text="Detalles del bloque de suplantación de identidad en la vista Flujo de correo en el informe de estado de Flujo de correo" lightbox="../../media/mail-flow-status-report-mailflow-view-details.png":::

En la tabla de detalles debajo del diagrama se muestra la siguiente información:

- **Date**
- **Correo electrónico total**
- **Borde filtrado**
- **Mensajes de regla**
- **Motor antimalware, datos adjuntos Caja fuerte, regla filtrada**
- **Suplantación de DMARC, suplantación de identidad, suplantación de identidad filtrada**
- **Detección de detonaciones**
- **Antispam filtrado**
- **ZAP quitado**
- **Mensajes en los que no se detectaron amenazas**

Si selecciona una fila en la tabla de detalles, se muestra un desglose adicional de los recuentos de correo electrónico en el control flotante de detalles que aparece.

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**.
- **Dirección**: **saliente** y **entrante**.

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

De nuevo en la página **Informe de estado de flujo de correo** , puede hacer clic en **Mostrar tendencias** para ver los gráficos de tendencias en el control flotante **Tendencias de flujo de correo** que aparece.

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view-show-trends.png" alt-text="Control flotante Tendencias de flujo de correo en la vista Flujo de correo en el informe de estado de Flujo de correo" lightbox="../../media/mail-flow-status-report-mailflow-view-show-trends.png":::

En la página **Informe de estado de Flujo de correo** , el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **El botón Exportar** está disponible.

## <a name="malware-detections-report"></a>Informe de detecciones de malware

> [!NOTE]
> Este informe ha quedado en desuso. La misma información está disponible en el [informe de estado de protección contra amenazas](#threat-protection-status-report).

## <a name="mail-latency-report"></a>Informe de latencia de correo

El **informe latencia de correo** de Defender para Office 365 contiene información sobre la latencia de entrega y detonación de correo experimentada en su organización. Para obtener más información, vea [Informe de latencia de correo](view-reports-for-mdo.md#mail-latency-report).

## <a name="spam-detections-report"></a>Informe de detecciones de correo no deseado

> [!NOTE]
> Este informe ha quedado en desuso. La misma información está disponible en el [informe de estado de protección contra amenazas](#threat-protection-status-report).

## <a name="spoof-detections-report"></a>Informe de detecciones de suplantación de identidad

El informe **de detecciones de suplantación** de identidad muestra información sobre los mensajes bloqueados o permitidos debido a la suplantación de identidad. Para obtener más información sobre la suplantación de identidad, vea [Protección contra la suplantación de identidad en EOP](anti-spoofing-protection.md).

La vista de agregado del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite diez días de filtrado.

Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración de & de correo electrónico** , busque **Detecciones de suplantación de identidad** y haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/SpoofMailReport>.

:::image type="content" source="../../media/spoof-detections-widget.png" alt-text="Widget Detecciones de suplantación de identidad en la página Informes de colaboración & correo electrónico" lightbox="../../media/spoof-detections-widget.png":::

El gráfico muestra la siguiente información:

- **Pasar**
- **Fallar**
- **SoftPass**
- **Ninguna**
- **Otros**

Al mantener el puntero sobre un día (punto de datos) en el gráfico, puede ver cuántos mensajes suplantados se detectaron y por qué.

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Resultado**:
  - **Pasar**
  - **Fallar**
  - **SoftPass**
  - **Ninguna**
  - **Otros**
- **Tipo de suplantación de identidad**: **interno** y **externo**

:::image type="content" source="../../media/spoof-detections-report-page.png" alt-text="Página del informe de correo de suplantación de identidad en el portal de Microsoft 365 Defender" lightbox="../../media/spoof-detections-report-page.png":::

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Date**
- **Usuario suplantado**
- **Infraestructura de envío**
- **Tipo de suplantación de identidad**
- **Resultado**
- **Código de resultado**
- **SPF**
- **DKIM**
- **DMARC**
- **Recuento de mensajes**

Para obtener más información sobre los códigos de resultado de autenticación compuesta, consulte [Encabezados de mensajes antispam en Microsoft 365](anti-spam-message-headers.md).

En la página **Detecciones de suplantación de identidad** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

## <a name="submissions-report"></a>Informe de envíos

El informe **Envíos** muestra información sobre los elementos que los administradores han notificado a Microsoft para su análisis. Para obtener más información, consulte [Uso del envío de administrador para enviar sospechas de correo no deseado, fish, direcciones URL y archivos a Microsoft](admin-submission.md).

Para ver el informe en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración & correo electrónico** , busque **Envíos** y haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/adminSubmissionReport>. Para ir a [los envíos de administrador en el portal de Microsoft 365 Defender](admin-submission.md), haga clic en **Ir a envíos**. Los administradores podrán ver el informe durante los últimos 30 días.

:::image type="content" source="../../media/submissions-report-widget.png" alt-text="Widget Envíos en la página Informes de colaboración & correo electrónico" lightbox="../../media/submissions-report-widget.png":::

El gráfico muestra la siguiente información:

- **Pendiente**
- **Completed**

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha notificada**: **Hora de inicio** y **Hora de finalización**
- **Tipo de envío**:
  - **Correo electrónico**
  - **URL**
  - **Archivo**
- **Id. de envío**
- **Identificador de mensaje de red**
- **Sender**
- **Nombre**
- **Enviado por**
- **Motivo para enviar**:
  - **No basura**
  - **Suplantación de identidad**
  - **Malware**
  - **Correo no deseado**
- **Estado de reescaneo**:
  - **Pendiente**
  - **Completed**

La tabla de detalles debajo del gráfico muestra la misma información y tiene las mismas opciones **De grupo** o **Personalizar columnas** que en la pestaña **Enviado para análisis** en **Envíos** de **correo electrónico & colaboración**\>. Para obtener más información, consulte [Ver envíos de administradores a Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).

En la página **Envíos** , el botón **[Exportar](#export-report)** está disponible.

:::image type="content" source="../../media/submissions-report-page.png" alt-text="Página del informe Envíos en el portal de Microsoft 365 Defender" lightbox="../../media/submissions-report-page.png":::

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El informe **de estado de protección contra amenazas** está disponible en EOP y Defender para Office 365; sin embargo, los informes contienen datos diferentes. Por ejemplo, los clientes de EOP pueden ver información sobre el malware detectado en el correo electrónico, pero no información sobre los archivos [malintencionados detectados por Caja fuerte Datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

El informe proporciona el recuento de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones url del sitio web bloqueados por el motor antimalware, [purga automática de cero horas (ZAP)](zero-hour-auto-purge.md) y características de Defender para Office 365 como [vínculos de Caja fuerte](safe-links.md), [datos adjuntos Caja fuerte](safe-attachments.md) y [características de protección contra suplantación en anti phishing directivas](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Puede usar esta información para identificar tendencias o determinar si es necesario ajustar las directivas de la organización.

**Nota**: Es importante comprender que, si se envía un mensaje a cinco destinatarios, lo contamos como cinco mensajes diferentes y no como un mensaje.

Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración & correo electrónico** , busque **Estado de protección contra amenazas** y haga clic en **Ver detalles**. Para ir directamente al informe, abra una de las siguientes direcciones URL:

- Defender para Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP>
- EOP: <https://security.microsoft.com/reports/TPSAggregateReport>

:::image type="content" source="../../media/threat-protection-status-report-widget.png" alt-text="Widget De estado de protección contra amenazas en la página Informes de colaboración & correo electrónico" lightbox="../../media/threat-protection-status-report-widget.png":::

De forma predeterminada, el gráfico muestra los datos de los últimos 7 días. Si hace clic en **Filtrar** en la página **Informe de estado de protección contra amenazas** , puede seleccionar un intervalo de fechas de 90 días (es posible que las suscripciones de prueba estén limitadas a 30 días). La tabla de detalles permite filtrar hasta 30 días.

Las vistas disponibles se describen en las secciones siguientes.

### <a name="view-data-by-overview"></a>Visualización de datos por información general

:::image type="content" source="../../media/threat-protection-status-report-overview-view.png" alt-text="La vista Información general del informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-overview-view.png":::

En la vista **Ver datos por información general** , se muestra la siguiente información de detección en el gráfico:

- **Malware por correo electrónico**
- **Phish de correo electrónico**
- **Correo no deseado por correo electrónico**
- **Malware de contenido**

No hay ninguna tabla de detalles disponible debajo del gráfico.

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**.
- **Detección**:
  - **Malware por correo electrónico**
  - **Phish de correo electrónico**
  - **Correo no deseado por correo electrónico**
  - **Malware de contenido**
- **Protegido por**: **MDO** (Defender para Office 365) y **EOP**.
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **Archivos adjuntos seguros**
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a>Visualización de datos por correo electrónico \> y desglose de gráficos por tecnología de detección

:::image type="content" source="../../media/threat-protection-status-report-phishing-detection-tech-view.png" alt-text="Vista de tecnología de detección para correo electrónico de suplantación de identidad (phishing) en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-phishing-detection-tech-view.png":::

> [!NOTE]
> A partir de mayo de 2021, se actualizaron las detecciones de suplantación de identidad en el correo electrónico para incluir **datos adjuntos de mensajes** que contienen direcciones URL de phishing. Este cambio podría desplazar parte del volumen de detección de la vista **Ver datos por malware por correo electrónico \>** y a la vista **Ver datos por correo electrónico\>.** En otras palabras, los datos adjuntos de mensajes con direcciones URL de phishing que tradicionalmente se identificaban como malware ahora podrían identificarse como phishing en su lugar.

En la vista **Ver datos por correo electrónico \> y** **Desglose del gráfico por tecnología de detección** , se muestra la siguiente información en el gráfico:

- **Reputación malintencionada**<sup>\*</sup> de direcciones URL: reputación de direcciones URL malintencionadas generada a partir de detonaciones de Defender para Office 365 en otros clientes Microsoft 365.
- **Filtro avanzado**: señales de suplantación de identidad basadas en el aprendizaje automático.
- **Filtro general**: señales de suplantación de identidad basadas en reglas de analista.
- **Suplantación de identidad entre organizaciones**: el remitente está intentando suplantar el dominio del destinatario.
- **Suplantación de dominio externo**: el remitente está intentando suplantar algún otro dominio.
- **Spoof DMARC**: error de autenticación de DMARC en los mensajes.
- **Marca de suplantación**: suplantación de marcas conocidas basadas en remitentes.
- **Detección de análisis mixto**
- **Reputación de los archivos**
- **Coincidencia de huella digital**
- **Reputación de detonación de direcciones URL**<sup>\*</sup>
- **Detonación de direcciones URL**<sup>\*</sup>
- **Usuario de suplantación**<sup>\*</sup>
- **Dominio de suplantación**<sup>\*</sup>: suplantación de dominios que el cliente posee o define.
- **Suplantación de inteligencia de buzones**<sup>\*</sup>: suplantación de usuarios definidos por el administrador o aprendidos a través de la inteligencia del buzón de correo.
- **Detonación de archivos**<sup>\*</sup>
- **Reputación de detonación de archivos**<sup>\*</sup>
- **Campaña**<sup>\*</sup>

<sup>\*</sup>solo Defender para Office 365

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Subject**
- **Remitente**
- **Destinatarios**
- **Tecnología de detección**
- **Estado de entrega**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Detección**: los mismos valores que en el gráfico.
- **Protegido por**: **MDO** (Defender para Office 365) o **EOP**
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **Archivos adjuntos seguros**
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**
- **Nombre de la directiva (solo la vista de tabla de detalles):** **todo** o la directiva especificada.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="view-data-by-email--spam-and-chart-breakdown-by-detection-technology"></a>Visualización de datos por correo no deseado por correo electrónico \> y desglose de gráficos por tecnología de detección

:::image type="content" source="../../media/threat-protection-status-report-spam-detection-tech-view.png" alt-text="Vista de tecnología de detección de correo no deseado en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-spam-detection-tech-view.png":::

En la vista **Ver datos por correo no deseado por correo electrónico \>** y **Desglose del gráfico por tecnología de detección**, se muestra la siguiente información en el gráfico:

- **Reputación malintencionada de URL**
- **Filtro avanzado**
- **Filtro general**
- **Detección de análisis mixto**: varios filtros contribuyeron al veredicto del mensaje.
- **Coincidencia de huellas digitales**: el mensaje se ha marcado como incorrecto debido a mensajes anteriores.
- **Reputación del dominio**: este mensaje se consideró spam en función de la reputación del dominio del remitente.
- **Bulk**: elementos detectados como que superan la configuración masiva para el usuario.
- **Reputación de IP**: el mensaje se consideró spam en función de la reputación de la dirección IP de envío.

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Subject**
- **Remitente**
- **Destinatarios**
- **Tecnología de detección**
- **Estado de entrega**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Detección**: los mismos valores que en el gráfico.
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **Archivos adjuntos seguros**
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**
- **Nombre de la directiva (solo la vista de tabla de detalles):** **todo** o la directiva especificada.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a>Visualización de datos por correo electrónico \> Malware y desglose de gráficos por tecnología de detección

:::image type="content" source="../../media/threat-protection-status-report-malware-detection-tech-view.png" alt-text="Vista de tecnología de detección de malware en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-malware-detection-tech-view.png":::

> [!NOTE]
> A partir de mayo de 2021, se actualizaron las detecciones de malware en el correo electrónico para incluir **direcciones URL dañinas** en los datos adjuntos de los mensajes. Este cambio podría desplazar parte del volumen de detección de la vista **Ver datos por correo electrónico \> y** a la vista **Ver datos por malware por correo electrónico\>**. En otras palabras, las direcciones URL dañinas en los datos adjuntos de mensajes que tradicionalmente se identificaban como phishing ahora podrían identificarse como malware en su lugar.

En la vista **Ver datos por correo electrónico \> Malware** y **Desglose del gráfico por tecnología de detección** , se muestra la siguiente información en el gráfico:

- **Detonación**<sup>\*</sup> de archivos: detección por Caja fuerte datos adjuntos.
- Reputación <sup>\*</sup>**de detonación de** archivos: toda la reputación de archivos malintencionados generada por Defender para Office 365 detonaciones.
- **Reputación de los archivos**
- **Motor antimalware**<sup>\*</sup>: detección de motores antimalware.
- **Bloque de tipo de archivo de directiva antimalware**: son mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.
- **Reputación malintencionada de direcciones URL**<sup>\*</sup>
- **Detonación de direcciones URL**<sup>\*</sup>
- **Reputación de detonación de direcciones URL**<sup>\*</sup>
- **Campaña**<sup>\*</sup>

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Asunto**
- **Remitente**
- **Destinatarios**
- **Tecnología de detección**
- **Estado de entrega**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Detección**: los mismos valores que en el gráfico.
- **Protegido por**: **MDO** (Defender para Office 365) o **EOP**
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **Archivos adjuntos seguros**
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**
- **Nombre de la directiva (solo la vista de tabla de detalles):** **todo** o la directiva especificada.
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de la protección deThreat** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="chart-breakdown-by-policy-type"></a>Desglose del gráfico por tipo de directiva

:::image type="content" source="../../media/threat-protection-status-report-phishing-policy-type-view.png" alt-text="La vista Tipo de directiva para correo electrónico de suplantación de identidad (phishing), correo electrónico no deseado o correo electrónico de malware en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-phishing-policy-type-view.png":::

En **Las vistas Ver datos por correo electrónico \> phish**, **Ver datos por correo no \> deseado** o **Ver datos por correo electrónico \> Malware** , al seleccionar **Desglose del gráfico por tipo de directiva** se muestra la siguiente información en el gráfico:

- **Antimalware**
- **datos adjuntos de Caja fuerte**<sup>\*</sup>
- **Anti-phish**
- **Antispam**
- **Regla de flujo de correo** (también conocida como regla de transporte)
- **Otros**

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Subject**
- **Remitente**
- **Destinatarios**
- **Tecnología de detección**
- **Estado de entrega**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Detección**:
  - **Reputación malintencionada**<sup>\*</sup> de direcciones URL: reputación de direcciones URL malintencionadas generada a partir de detonaciones de Defender para Office 365 en otros clientes Microsoft 365.
  - **Filtro avanzado**: señales de suplantación de identidad basadas en el aprendizaje automático.
  - **Filtro general**: señales de suplantación de identidad basadas en reglas de analista.
  - **Suplantación de identidad entre organizaciones**: el remitente está intentando suplantar el dominio del destinatario.
  - **Suplantación de dominio externo**: el remitente está intentando suplantar algún otro dominio.
  - **Spoof DMARC**: error de autenticación de DMARC en los mensajes.
  - **Marca de suplantación**: suplantación de marcas conocidas basadas en remitentes.
  - **Detección de análisis mixto**
  - **Reputación de los archivos**
  - **Coincidencia de huella digital**
  - **Reputación de detonación de direcciones URL**<sup>\*</sup>
  - **Detonación de direcciones URL**<sup>\*</sup>
  - **Usuario de suplantación**<sup>\*</sup>
  - **Dominio de suplantación**<sup>\*</sup>: suplantación de dominios que el cliente posee o define.
  - **Suplantación de inteligencia de buzones**<sup>\*</sup>: suplantación de usuarios definidos por el administrador o aprendidos a través de la inteligencia del buzón de correo.
  - **Detonación de archivos**<sup>\*</sup>
  - **Reputación de detonación de archivos**<sup>\*</sup>
  - **Campaña**<sup>\*</sup>
- **Protegido por**: **MDO** (Defender para Office 365) o **EOP**
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **Archivos adjuntos seguros**
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**
- **Nombre de la directiva (solo la vista de tabla de detalles):** **todo** o la directiva especificada.
- **Destinatarios**

<sup>\*</sup>solo Defender para Office 365

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="chart-breakdown-by-delivery-status"></a>Desglose del gráfico por estado de entrega

:::image type="content" source="../../media/threat-protection-status-report-phishing-delivery-status-view.png" alt-text="La vista Estado de entrega del correo electrónico de suplantación de identidad (phishing) y el correo electrónico de malware en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-phishing-delivery-status-view.png":::

En **Las vistas Ver datos por correo electrónico \> phish**, **Ver datos por correo no \> deseado** o **Ver datos por correo electrónico \> Malware** , al seleccionar **Desglose del gráfico por estado de entrega** se muestra la siguiente información en el gráfico:

- **Buzón hospedado: Bandeja de entrada**
- **Buzón hospedado: correo no deseado**
- **Buzón hospedado: carpeta personalizada**
- **Buzón hospedado: elementos eliminados**
- **Reenviado**
- **Servidor local: entregado**
- **Cuarentena**
- **Error de entrega**
- **Cayó**

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Subject**
- **Remitente**
- **Destinatarios**
- **Tecnología de detección**
- **Estado de entrega**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Detección**:
  - **Reputación malintencionada**<sup>\*</sup> de direcciones URL: reputación de direcciones URL malintencionadas generada a partir de detonaciones de Defender para Office 365 en otros clientes Microsoft 365.
  - **Filtro avanzado**: señales de suplantación de identidad basadas en el aprendizaje automático.
  - **Filtro general**: señales de suplantación de identidad basadas en reglas de analista.
  - **Suplantación de identidad entre organizaciones**: el remitente está intentando suplantar el dominio del destinatario.
  - **Suplantación de dominio externo**: el remitente está intentando suplantar algún otro dominio.
  - **Spoof DMARC**: error de autenticación de DMARC en los mensajes.
  - **Marca de suplantación**: suplantación de marcas conocidas basadas en remitentes.
  - **Detección de análisis mixto**
  - **Reputación de los archivos**
  - **Coincidencia de huella digital**
  - **Reputación de detonación de direcciones URL**<sup>\*</sup>
  - **Detonación de direcciones URL**<sup>\*</sup>
  - **Usuario de suplantación**<sup>\*</sup>
  - **Dominio de suplantación**<sup>\*</sup>: suplantación de dominios que el cliente posee o define.
  - **Suplantación de inteligencia de buzones**<sup>\*</sup>: suplantación de usuarios definidos por el administrador o aprendidos a través de la inteligencia del buzón de correo.
  - **Detonación de archivos**<sup>\*</sup>
  - **Reputación de detonación de archivos**<sup>\*</sup>
  - **Campaña**<sup>\*</sup>
- **Protegido por**: **MDO** (Defender para Office 365) o **EOP**
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **Archivos adjuntos seguros**
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**
- **Nombre de la directiva (solo la vista de tabla de detalles):** **todo** o la directiva especificada.
- **Destinatarios**

<sup>\*</sup>solo Defender para Office 365

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="view-data-by-content--malware"></a>Visualización de datos por malware de contenido \>

:::image type="content" source="../../media/threat-protection-status-report-content-malware-view.png" alt-text="Vista de malware de contenido en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-content-malware-view.png":::

En la vista **Ver datos por malware de contenido\>**, se muestra la siguiente información en el gráfico para Microsoft Defender para Office 365 organizaciones:

- **Motor antimalware**: archivos malintencionados detectados en SharePoint, OneDrive y Microsoft Teams por la [detección de virus integrada en Microsoft 365](virus-detection-in-spo.md).
- **Detonación de MDO**: archivos [malintencionados detectados por Caja fuerte Attachments para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).
- **Reputación de los archivos**

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Fecha (UTC)**
- **Nombres de archivos adjuntos**
- **Carga de trabajo**
- **Tecnología de detección**
- **Tamaño de archivos**
- **Última modificación del usuario**

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Detección**: **motor antimalware**, **detonación de MDO** y **detonación de archivos**
- **Carga de trabajo**: **Teams**, **SharePoint** y **OneDrive**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)**, ![icono solicitar informe.](../../media/m365-cc-sc-download-icon.png) **[Informe de solicitud](#request-report)** e ![icono exportar.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

### <a name="view-data-by-system-override-and-chart-breakdown-by-reason"></a>Visualización de datos por invalidación del sistema y desglose del gráfico por motivo

:::image type="content" source="../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png" alt-text="La invalidación de mensajes y el desglose del gráfico por motivo en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png":::

En la vista **Ver datos por invalidación del sistema** y **Desglose del gráfico por motivo** , se muestra la siguiente información de motivo de invalidación en el gráfico:

- **Omisión local**
- **IP allow**
- **Exchange regla de transporte** (regla de flujo de correo)
- **Remitentes permitidos por la organización**
- **Dominios permitidos de la organización**
- **ZAP no habilitado**
- **Remitente de Caja fuerte de usuario**
- **Dominio de Caja fuerte de usuario**
- **Simulación de suplantación** de identidad (phishing): para obtener más información, consulte [Configuración de la entrega de simulaciones de suplantación de identidad (phishing) de terceros a usuarios y mensajes sin filtrar a buzones de SecOps](configure-advanced-delivery.md).
- **Filtro de terceros**

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Subject**
- **Remitente**
- **Destinatarios**
- **Invalidación del sistema**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Motivo**: los mismos valores que el gráfico.
- **Ubicación de entrega**: **carpeta correo no deseado no habilitada** o **buzón de SecOps**.
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**: **Todo**
- **Nombre de directiva (solo vista de tabla de detalles):****Todos**
- **Destinatarios**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **[El botón Exportar](#export-report)** está disponible.

### <a name="view-data-by-system-override-and-chart-breakdown-by-delivery-location"></a>Visualización de datos por invalidación del sistema y desglose del gráfico por ubicación de entrega

:::image type="content" source="../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png" alt-text="La invalidación de mensajes y el desglose del gráfico por ubicación de entrega en el informe de estado de protección contra amenazas" lightbox="../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png":::

En la vista **Ver datos por invalidación del sistema** y **Desglose del gráfico por ubicación de entrega** , se muestra la siguiente información de motivo de invalidación en el gráfico:

- **Carpeta de correo no deseado no habilitada**
- **Buzón de SecOps**: para obtener más información, consulte [Configuración de la entrega de simulaciones de suplantación de identidad de terceros a los usuarios y mensajes sin filtrar a buzones de SecOps](configure-advanced-delivery.md).

En la tabla de detalles debajo del gráfico, está disponible la siguiente información:

- **Date**
- **Asunto**
- **Remitente**
- **Destinatarios**
- **Invalidación del sistema**
- **IP del remitente**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Si hace clic en **Filtrar**, están disponibles los siguientes filtros:

- **Fecha (UTC)** **Fecha de inicio** y **Fecha de finalización**
- **Motivo**
  - **Omisión local**
  - **IP allow**
  - **Exchange regla de transporte** (regla de flujo de correo)
  - **Remitentes permitidos por la organización**
  - **Dominios permitidos de la organización**
  - **ZAP no habilitado**
  - **Remitente de Caja fuerte de usuario**
  - **Dominio de Caja fuerte de usuario**
  - **Simulación de suplantación** de identidad (phishing): para obtener más información, consulte [Configuración de la entrega de simulaciones de suplantación de identidad (phishing) de terceros a usuarios y mensajes sin filtrar a buzones de SecOps](configure-advanced-delivery.md).
  - **Filtro de terceros**
- **Ubicación de entrega**: **carpeta correo no deseado no habilitada** o **buzón de SecOps**.
- **Dirección**:
  - **Todo**
  - **Entrantes**
  - **Salida**
- **Etiqueta**: **todas** o la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).
- **Dominio**: **todo** o un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- **Tipo de directiva**:
  - **Todo**
  - **Antimalware**
  - **datos adjuntos de Caja fuerte**<sup>\*</sup>
  - **Anti-phish**
  - **Antispam**
  - **Regla de flujo de correo** (regla de transporte)
  - **Otros**
- **Nombre de directiva (solo vista de tabla de detalles):****Todos**
- **Destinatarios**

<sup>\*</sup>solo Defender para Office 365

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Estado de protección contra amenazas** , el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **[El botón Exportar](#export-report)** está disponible.

## <a name="top-malware-report"></a>Informe de malware superior

El informe **de malware superior** muestra los diversos tipos de malware detectados por [la protección antimalware en EOP](anti-malware-protection.md).

Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración de & de correo electrónico** , busque **Malware superior** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/TopMalware>.

:::image type="content" source="../../media/top-malware-report-widget.png" alt-text="Widget de malware superior en la página Informes de colaboración de & por correo electrónico" lightbox="../../media/top-malware-report-widget.png":::

Al mantener el puntero sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y cuántos mensajes se detectaron como que tienen ese malware.

En la página **Informe de malware superior** , se muestra una versión más grande del gráfico circular. En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Malware principal**
- **Count**

Si hace clic en **Filtrar**, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

En la página **Malware superior** , el ![icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **[Crear programación](#schedule-report)** y ![exportar icono.](../../media/m365-cc-sc-download-icon.png) Los botones **[de exportación](#export-report)** están disponibles.

:::image type="content" source="../../media/top-malware-report-view.png" alt-text="Vista del informe de malware superior" lightbox="../../media/top-malware-report-view.png":::

## <a name="top-senders-and-recipients-report"></a>Informe de remitentes y destinatarios principales

El informe **de remitentes y destinatarios principales** está disponible tanto en EOP como en Defender para Office 365; sin embargo, los informes contienen datos diferentes. Por ejemplo, los clientes de EOP pueden ver información sobre los principales destinatarios de malware, correo no deseado y suplantación de identidad (suplantación de identidad), pero no información sobre el malware detectado por [Caja fuerte Datos adjuntos](safe-attachments.md) o suplantación de identidad detectado por [la protección de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

Los **principales remitentes y destinatarios** muestran los principales remitentes de mensajes de su organización, así como los destinatarios principales de los mensajes detectados por EOP y las características de protección de Defender para Office 365. De forma predeterminada, el informe muestra los datos de la última semana, pero los datos están disponibles para los últimos 90 días.

Para ver el informe en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración & por correo electrónico** , busque **El informe Principales remitentes y destinatarios** y, a continuación, haga clic en **Ver detalles**. Para ir directamente al informe, abra una de las siguientes direcciones URL:

- Defender para Office 365:<https://security.microsoft.com/reports/TopSenderRecipientsATP>
- EOP: <https://security.microsoft.com/reports/TopSenderRecipient>

:::image type="content" source="../../media/top-senders-and-recipients-widget.png" alt-text="Widget Remitentes y destinatarios principales en el panel Informes" lightbox="../../media/top-senders-and-recipients-widget.png":::

Al mantener el puntero sobre una cuña en el gráfico circular, puede ver el número de mensajes para el remitente o destinatario.

En la página **Principales remitentes y destinatarios** , se muestra una versión más grande del gráfico circular. Están disponibles los siguientes gráficos:

- **Mostrar datos para remitentes de correo superior** (esta es la vista predeterminada)
- **Mostrar datos para los principales destinatarios de correo**
- **Mostrar datos de los principales destinatarios de correo no deseado**
- **Mostrar datos para los principales destinatarios de malware** (EOP)
- **Mostrar datos para los principales destinatarios de suplantación de identidad (phishing)**
- **Mostrar datos para los principales destinatarios de malware (MDO)**
- **Mostrar datos para los principales destinatarios de phish (MDO)**

Los datos cambian en función de la selección.

Al mantener el puntero sobre una cuña en el gráfico circular, puede ver el recuento de mensajes para ese remitente o destinatario específico.

En la tabla de detalles debajo del gráfico se muestran los remitentes o destinatarios y los recuentos de mensajes en función de la vista seleccionada.

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione **Fecha de inicio** y **Fecha de finalización**.

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

En la página **Principales remitentes y destinatarios** , el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **El botón Exportar** está disponible.

:::image type="content" source="../../media/top-senders-and-recipients-report-view.png" alt-text="Vista Mostrar datos para remitentes de correo superior en el informe Remitentes y destinatarios principales" lightbox="../../media/top-senders-and-recipients-report-view.png":::

## <a name="url-protection-report"></a>Informe de protección de direcciones URL

El **informe de protección de direcciones URL** solo está disponible en Microsoft Defender para Office 365. Para obtener más información, vea [Informe de protección de direcciones URL](view-reports-for-mdo.md#url-protection-report).

## <a name="user-reported-messages-report"></a>Informe de mensajes notificados por el usuario

> [!IMPORTANT]
> Para que el informe **mensajes notificados** por el usuario funcione correctamente, **el registro de auditoría debe estar activado** para el entorno de Microsoft 365. Normalmente, lo hace alguien que tiene asignado el rol Registros de auditoría en Exchange Online. Para obtener más información, vea [Activar o desactivar Microsoft 365 búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

El informe **Mensajes notificados** por el usuario muestra información sobre los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad (phishing) o correo electrónico correcto mediante el [complemento Mensaje](enable-the-report-message-add-in.md) de informe o el [complemento De suplantación de identidad](enable-the-report-phish-add-in.md) de informe.

Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración & por correo electrónico** , busque **Mensajes notificados** por el usuario y haga clic en **Ver detalles**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/userSubmissionReport>. Para ir a [los envíos de administrador en el portal de Microsoft 365 Defender](admin-submission.md), haga clic en **Ir a envíos**.

:::image type="content" source="../../media/user-reported-messages-widget.png" alt-text="Widget de mensajes notificados por el usuario en la página Informes de colaboración & correo electrónico" lightbox="../../media/user-reported-messages-widget.png":::

Para filtrar el gráfico y la tabla de detalles, haga clic en **Filtrar** y seleccione uno o varios de los siguientes valores en el control flotante que aparece:

- **Fecha notificada**: **Hora de inicio** y **Hora de finalización**
- **Informe realizado por**
- **Asunto del correo electrónico**
- **Id. notificado de mensaje**
- **Identificador de mensaje de red**
- **Sender**
- **Motivo notificado**
  - **No basura**
  - **Suplantación de identidad**
  - **Correo no deseado**
- **Simulación de phish**: **Sí** o **No**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

Para agrupar las entradas, haga clic en **Agrupar** y seleccione uno de los siguientes valores en la lista desplegable:

- **Ninguna**
- **Motivo**
- **Sender**
- **Informe realizado por**
- **Resultado de reescanear**
- **Simulación de phish**

:::image type="content" source="../../media/user-reported-messages-report.png" alt-text="Informe de mensajes notificados por el usuario" lightbox="../../media/user-reported-messages-report.png":::

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Asunto del correo electrónico**
- **Informe realizado por**
- **Fecha notificada**
- **Sender**
- **Motivo notificado**
- **Resultado de reescanear**
- **Etiquetas**: para obtener más información sobre las etiquetas de usuario, consulte [Etiquetas de usuario](user-tags.md).

Para enviar un mensaje a Microsoft para su análisis, seleccione la entrada de mensaje de la tabla, haga clic en **Enviar a Microsoft para su análisis** y, a continuación, seleccione uno de los siguientes valores en la lista desplegable:

- **Informe limpio**
- **Informar de suplantación de identidad**
- **Informar de malware**
- **Notificar correo no deseado**'
- **Investigación del desencadenador** (Defender para Office 365)

En la página **Mensajes notificados** por el usuario, el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **[El botón Exportar](#export-report)** está disponible.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos se necesitan para ver estos informes?

Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el portal de Microsoft 365 Defender:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

**Nota**: Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características en Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en los informes, compruebe los filtros que usa y compruebe que las directivas están configuradas correctamente. Para obtener más información, consulte [Protección contra amenazas](protect-against-threats.md).

## <a name="schedule-report"></a>Programar informe

1. En la página principal del informe específico, haga clic en ![el icono Crear programación.](../../media/m365-cc-sc-create-icon.png) **Crear programación**.
2. Se abre **el Asistente para crear informes programados** . En la página **Nombre del informe programado** , revise o personalice el valor **Nombre** y, a continuación, haga clic en **Siguiente**.
3. En la página **Establecer preferencias** , configure los siguientes valores:
   - **Frecuencia**: seleccione uno de los valores siguientes:
     - **Semanal** (valor predeterminado)
     - **Mensualmente**
   - **Fecha de inicio**: cuándo comienza la generación del informe. El valor predeterminado es hoy.
   - **Fecha de expiración**: cuando finaliza la generación del informe. El valor predeterminado es un año a partir de hoy.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Destinatarios** , elija destinatarios para el informe. El valor predeterminado es su dirección de correo electrónico, pero puede agregar otros.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Revisar** , revise las selecciones. Puede hacer clic en el botón **Atrás** o en el vínculo **Editar** de las secciones correspondientes para realizar cambios.

   Cuando haya terminado, haga clic en **Enviar**.

### <a name="managed-existing-scheduled-reports"></a>Informes programados existentes administrados

Para administrar los informes programados que ya ha creado, siga estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> y expanda **Correo electrónico & colaboración**\>, seleccione **Administrar programaciones**.

   Para ir directamente a la página **Administrar programaciones** , use <https://security.microsoft.com/ManageSubscription>.

2. En la página **Administrar programaciones** , se muestra la siguiente información para cada informe programado:
   - **Programar fecha de inicio**
   - **Nombre de programación**
   - **Tipo de informe**
   - **Frequency**
   - **Último envío**

   Busque el informe programado existente que desea modificar.

3. Después de seleccionar el informe programado, realice cualquiera de las siguientes acciones en el control flotante de detalles que se abre:
   - **Editar nombre**: haga clic en este botón, cambie el nombre del informe en el control flotante que aparece y, a continuación, haga clic en **Guardar**.
   - **Eliminar programación**: haga clic en este botón, lea la advertencia que aparece (los informes anteriores ya no estarán disponibles para su descarga) y, a continuación, haga clic en **Guardar**.
   - **Sección Detalles de programación** : haga clic en **Editar preferencias** para cambiar la siguiente configuración:
     - **Frecuencia**: **semanal** o **mensual**
     - **Fecha de comienzo**
     - **Fecha de expiración**

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección Destinatarios** : haga clic en **Editar destinatarios** para agregar o quitar destinatarios para el informe programado. Cuando haya terminado, haga clic en **Guardar.**

   Cuando haya terminado, haga clic en **Cerrar**.

## <a name="request-report"></a>Informe de solicitud

1. En la página principal del informe específico, haga clic en ![el icono Solicitar informe.](../../media/m365-cc-sc-download-icon.png) **Informe de solicitud**.
2. Se abre el Asistente para **crear informes a petición** . En la página **Nombre del informe a petición** , revise o personalice el valor **Nombre** y, a continuación, haga clic en **Siguiente**.
3. En la página **Establecer preferencias** , revise o configure los siguientes valores:
   - **Fecha de inicio**: cuándo comienza la generación del informe. El valor predeterminado es hace un mes.
   - **Fecha de expiración**: cuando finaliza la generación del informe. El valor predeterminado es hoy.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Destinatarios** , elija destinatarios para el informe. El valor predeterminado es su dirección de correo electrónico, pero puede agregar otros.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Revisar** , revise las selecciones. Puede hacer clic en el botón **Atrás** o en el vínculo **Editar** de las secciones correspondientes para realizar cambios.

   Cuando haya terminado, haga clic en **Enviar**.

6. Una vez creado correctamente el informe, se le llevará a la página **Nuevo informe a petición creado** , donde puede hacer clic en **Crear otro informe** o **Listo**.

   El informe también está disponible en la página **Informes para descarga** , tal como se describe en la sección siguiente.

### <a name="download-reports"></a>Descargar informes

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Informes** \> y expanda **Correo electrónico & colaboración**\>, seleccione **Informes para descargar**.

   Para ir directamente a la página **Informes para descarga** , use <https://security.microsoft.com/ReportsForDownload>.

2. En la página **Informes para descarga** , se muestra la siguiente información para cada informe disponible:
   - **Fecha de comienzo**
   - **Nombre**
   - **Tipo de informe**
   - **Último envío**
   - **Dirección**

   Busque y seleccione el informe que desea descargar.

## <a name="export-report"></a>Exportar informe

En la página principal del informe específico, haga clic en ![el icono Exportar.](../../media/m365-cc-sc-download-icon.png) **Exportar** (si ese vínculo está disponible). Aparece un control flotante **Condiciones de exportación** en el que puede configurar los siguientes valores:

- **Seleccione una vista para exportar**: seleccione uno de los valores siguientes:
  - **Resumen**: los datos están disponibles durante los últimos 90 días.
  - **Detalles**: los datos están disponibles durante los últimos 30 días.
- **Fecha (UTC)**: **fecha de inicio** y **fecha de finalización**.

Cuando haya terminado de configurar los filtros, haga clic en **Exportar**. En el cuadro de diálogo que se abre, puede elegir abrir el archivo, guardar el archivo o recordar la selección.

Cada archivo .csv exportado está limitado a 150 000 filas. Si los datos contienen más de 150 000 filas, se crean varios archivos .csv.

## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado y antimalware en EOP](anti-spam-and-anti-malware-protection.md)

[Informes inteligentes e información en el portal de Microsoft 365 Defender](reports-and-insights-in-security-and-compliance.md)

[Visualización de informes de flujo de correo en el portal de Microsoft 365 Defender](view-mail-flow-reports.md)

[Ver informes para Defender para Office 365](view-reports-for-mdo.md)
