---
title: Ver los informes de defender para Office 365 en el panel de informes
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Busque y use informes de Microsoft defender para Office 365 en el centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a237049c9ebbccf1c01feeb21129496e16d437b2
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572494"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Ver los informes de defender para Office 365 en el panel de informes del centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft defender para Office 365 organizaciones (por ejemplo, suscripciones a Microsoft 365 E5 o Microsoft defender para Office 365 plan 1 o Microsoft defender para Office 365 plan 2 complementos) contienen una variedad de informes relacionados con la seguridad. Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), puede ver estos informes en el centro de seguridad & cumplimiento desde el panel de **informes** \> **Dashboard**. Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .

![Panel informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Informe de tipos de archivo de defender para Office 365

El informe **de la defender para Office 365 del informe de tipos de archivo** muestra el tipo de archivos detectados como malintencionados por [datos adjuntos seguros](atp-safe-attachments.md).

 La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite 10 días de filtrado.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **defender para Office 365 tipos de archivo**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ATPFileReport> .

![Defender para Office 365 widget tipos de archivo en el panel de informes](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> La información de este informe también está disponible en el [Informe de disposición del mensaje de defender para Office 365](#defender-for-office-365-message-disposition-report).

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Vista informes para el informe de tipos de archivo de defender para Office 365

Están disponibles las siguientes vistas:

- **Ver datos por: archivo**: el gráfico contiene la siguiente información:

  - **Datos adjuntos de Excel malintencionados**
  - **Datos adjuntos de Flash malintencionados**
  - **Datos adjuntos de PDF malintencionados**
  - **Datos adjuntos de PowerPoint malintencionados**
  - **Direcciones URL malintencionadas**
  - **Datos adjuntos de Word malintencionado**
  - **Datos adjuntos ejecutables malintencionados**
  - **Otros**

  Cuando desplaza el puntero sobre un día concreto (punto de datos), puede ver el desglose de los tipos de archivos malintencionados que se detectaron con [datos adjuntos seguros](atp-safe-attachments.md) y la [protección antimalware en EOP](anti-malware-protection.md).

  ![Vista de archivo en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-file-view.png)

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

- **Ver datos por: mensaje**: el gráfico contiene la siguiente información:

  - **Bloquear acceso**
  - **Mensajes reemplazados**
  - **Mensajes supervisados**
  - **Reemplazado por la entrega de correo electrónico dinámica**: para obtener más información, consulte [entrega dinámica en las directivas de datos adjuntos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Vista de mensaje en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-message-view.png)

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Vista de tabla de detalles del informe de tipos de archivo de defender para Office 365

Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización durante los últimos 10 días. La información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: archivo**:

  - **Date**
  - **Dirección del destinatario**
  - **Dirección del remitente**
  - **Identificador del mensaje**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje y debe ser único. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).
  - **Archivo**

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

- **Ver datos por: mensaje**:

  - **Date**
  - **Dirección del destinatario**
  - **Dirección del remitente**
  - **Id. de mensaje**
  - **Archivo**
  - **Subject**

  Si hace clic en **filtros**, puede modificar los resultados con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="defender-for-office-365-message-disposition-report"></a>Informe de disposición de mensajes de defender para Office 365

El informe de **disposición de mensajes de ATP** muestra las acciones que se tomaron para los mensajes de correo electrónico que se detectaron con contenido malintencionado.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **defender para Office 365 disposición de mensajes**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Widget de disposición del mensaje de defender para Office 365 en el panel de informes](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> La información de este informe también está disponible en el [Informe de tipos de archivo de defender para Office 365](#defender-for-office-365-file-types-report).

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Vista informes del informe de disposición de los mensajes de defender para Office 365

Están disponibles las siguientes vistas:

- **Ver datos por: mensaje**: el gráfico contiene la siguiente información:

  - **Bloquear acceso**
  - **Mensajes reemplazados**
  - **Mensajes supervisados**
  - **Reemplazado por la entrega de correo electrónico dinámica**: para obtener más información, consulte [entrega dinámica en las directivas de datos adjuntos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Vista de mensaje en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-message-view.png)

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .

- **Ver datos por: archivo**: el gráfico contiene la siguiente información:

  - **Datos adjuntos de Excel malintencionados**
  - **Datos adjuntos de Flash malintencionados**
  - **Datos adjuntos de PDF malintencionados**
  - **Datos adjuntos de PowerPoint malintencionados**
  - **Direcciones URL malintencionadas**
  - **Datos adjuntos de Word malintencionado**
  - **Datos adjuntos ejecutables malintencionados**
  - **Otros**

  Cuando desplaza el puntero sobre un día concreto (punto de datos), puede ver el desglose de los tipos de archivos malintencionados que se detectaron con [datos adjuntos seguros](atp-safe-attachments.md) y la [protección antimalware en EOP](anti-malware-protection.md).

  ![Vista de archivo en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-file-view.png)

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Vista de tabla de detalles del informe de disposición de los mensajes de defender para Office 365

Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización durante los últimos 10 días. La información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: mensaje**:

  - **Date**
  - **Dirección del destinatario**
  - **Dirección del remitente**
  - **Id. de mensaje**
  - **Archivo**
  - **Subject**

  Si hace clic en **filtros**, puede modificar los resultados con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .

- **Ver datos por: archivo**:

  - **Date**
  - **Dirección del destinatario**
  - **Dirección del remitente**
  - **Id. de mensaje**
  - **Archivo**

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="mail-latency-report"></a>Informe de latencia de correo

El **Informe de latencia de correo** muestra una vista agregada de la entrega de correo y la latencia de detonación experimentada en la organización. Los tiempos de entrega de correo en el servicio se ven afectados por una serie de factores, y el tiempo de entrega absoluto en segundos no suele ser un buen indicador de éxito o problema. Una hora de entrega lenta en un día puede considerarse un promedio de tiempo de entrega en otro día o viceversa. El **Informe de latencia de correo** intenta calificar la entrega de mensajes en función de los datos estadísticos sobre los tiempos de entrega observados de otros mensajes:

- **percentil 50**: es la mitad de los tiempos de entrega de mensajes. Este valor se puede considerar como tiempo medio de entrega.
- **nonagésimo percentil**: Esto indica una latencia alta para la entrega de mensajes. Solo el 10% de los mensajes tardó más que este valor para entregar.
- **percentil 99th**: indica la latencia más alta para la entrega de mensajes.

No se incluye la latencia de la red y del cliente.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione informe de **latencia de correo**. Para ir directamente al informe, Abra <https://protection.office.com/mailLatencyReport?viewid=P50> .

![Widget de informe de latencia de correo en el panel informes](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Vista informes para el informe de latencia de correo

Al abrir el informe, la ficha **percentiles 50** está seleccionada de forma predeterminada.

De forma predeterminada, esta vista contiene un gráfico que está configurado con los siguientes filtros:

- **Fecha**: los últimos 7 días
- **Vista de mensajes**:
  - Mensajes detonados

Este gráfico muestra los mensajes organizados en las siguientes categorías:

- **Latencia de entrega de correo**
- **Latencia de detonación**

Cuando desplaza el puntero sobre una categoría del gráfico, puede ver un desglose de la latencia en cada categoría.

![Informe de latencia de correo](../../media/mail-latency-report.png)

Si hace clic en **filtrar** en la vista de informe, puede modificar los resultados con los siguientes filtros:

- Todos los mensajes
- Mensajes que contienen datos adjuntos o direcciones URL

Si hace clic en la pestaña **90 percentiles** o la ficha **percentiles de 99th** , se usan los mismos filtros predeterminados de la vista **percentil 50** .

### <a name="details-table-view-for-the-mail-latency-report"></a>Vista de tabla de detalles para el informe de latencia de correo

La siguiente información se muestra en la vista de tabla de detalles:

- **Date**
- **Percentiles**
- **Número de mensajes**
- **Latencia general**

![Detalles del informe de latencia de correo](../../media/mail-latency-report-details.png)

El anterior muestra que el 14 de noviembre la latencia media experimentada para todos los mensajes entregados y detonaciones fue de **108,033** segundos.

La tabla de detalles contiene la misma información en cada pestaña.

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El informe de **Estado de protección contra amenazas** es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y Microsoft defender para Office 365. Para obtener más información, consulte [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Informe de protección contra amenazas de URL

El **Informe de protección contra amenazas de direcciones URL** proporciona vistas de Resumen y tendencias para las amenazas detectadas y las acciones tomadas en los clics de direcciones URL como parte de los [vínculos seguros](atp-safe-links.md). Este informe no tendrá hacer clic en datos de usuarios en los que la Directiva de vínculos seguros aplicada tiene seleccionada la opción no hacer **un seguimiento de los clics del usuario** .

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a **informes** de \> **Panel** y seleccione **Informe de protección de URL**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget de informe de protección de URL en el panel informes](../../media/url-protection-report-widget.png)

> [!NOTE]
> Se trata de un *Informe de tendencias de protección*, lo que significa que los datos representan tendencias en un conjunto de datos más grande. Como resultado, los datos de la vista de agregado no están disponibles en tiempo real aquí, pero los datos de la vista de tabla de detalles son, por lo que es posible que vea una ligera diferencia entre las dos vistas.

### <a name="report-view-for-the-url-threat-protection-report"></a>Vista informes para el informe de protección contra amenazas de direcciones URL

El informe de **protección contra amenazas de direcciones URL** tiene dos vistas agregadas que se actualizan una vez cada cuatro horas que muestra datos para los últimos 90 días:

- **Hacer clic en dirección URL acción de protección**: muestra el número de clics de direcciones URL por parte de los usuarios de la organización y los resultados del clic:

  - **Bloqueado** (se ha bloqueado al usuario para que navegue a la dirección URL)
  - **Bloqueado y clic en**
  - **Clic durante el examen**

  Un clic indica que el usuario ha acpulsado a través de la página de bloque al sitio Web malintencionado (los administradores pueden deshabilitar el clic en las directivas de vínculos a prueba de errores).

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Las acciones de clic en protección disponibles, más el valor **permitido** (el usuario tuvo permiso para navegar a la dirección URL).

  ![Vista de dirección URL haga clic en acción de protección en el informe de protección contra amenazas URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **Dirección URL haga clic en por aplicación**: muestra el número de clics de direcciones URL por aplicaciones que admiten vínculos seguros:

  - **Cliente de correo electrónico**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Otros**

  Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Las aplicaciones disponibles.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Vista de tabla de detalles para el informe de protección contra amenazas de direcciones URL

Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización en los últimos 7 días con los siguientes detalles:

- **Haga clic en hora**
- **Usuario**
- **URL**
- **Acción**
- **App**

Si hace clic en **filtros** en la vista de tabla de detalles, puede filtrar por los mismos criterios que en la vista de informe y también por **dominios** o **destinatarios** separados por comas.

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="additional-reports-to-view"></a>Informes adicionales para ver

Además de los informes descritos en este tema, hay varios otros informes disponibles, tal como se describe en la tabla siguiente:

****

|Informe|Tema|
|---|---|
|**Explorer** (Microsoft defender para Office 365 plan 2) o **detecciones en tiempo real** (microsoft defender para Office 365 plan 1)|[Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md)|
|**Informes de seguridad de correo electrónico**, como el informe de remitentes y destinatarios principales, el informe de correo falsificado y el informe de detecciones de correo no deseado.|[Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento](view-email-security-reports.md)|
|**Informes de flujo de correo**, como el informe de reenvío, el informe de estado de flujo de correo y el informe de remitentes y destinatarios principales.|[Ver informes de flujo de correo en el centro de seguridad & cumplimiento](view-mail-flow-reports.md)|
|**Seguimiento de dirección URL para vínculos seguros** (solo PowerShell). El resultado de este cmdlet muestra los resultados de las acciones de vínculos a prueba de errores en los últimos siete días.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Resultados del tráfico de correo para EOP y Microsoft defender para Office 365** (solo PowerShell). El resultado de este cmdlet contiene información sobre el dominio, la fecha, el tipo de evento, la dirección, la acción y el recuento de mensajes.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**Informes de detalles de correo para EOP y defender para Office 365 DETECTIONS** (solo PowerShell). El resultado de este cmdlet contiene detalles sobre archivos malintencionados o direcciones URL, intentos de suplantación de identidad (phishing), suplantación y otras amenazas potenciales en el correo electrónico o los archivos.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>¿Qué permisos se necesitan para ver los informes de defender para Office 365?

Para poder ver y usar los informes descritos en este tema, debe pertenecer a uno de los siguientes grupos de roles en el centro de seguridad & cumplimiento:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

**Nota**: agregar usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en sus informes de defender para Office 365, compruebe que las directivas están configuradas correctamente. La organización debe tener directivas de [vínculos seguros](set-up-atp-safe-links-policies.md) y [las directivas de datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) definidas para que defender para Office 365 esté en su lugar. Consulte también [protección contra correo no deseado y antimalware](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Temas relacionados

[Informes inteligentes y reportes en el Centro de seguridad y cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Permisos de funciones (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
