---
title: Ver informes de Defender para Office 365 en el panel informes
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
description: Busque y use informes para Microsoft Defender para Office 365 en el Centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b3e1ddf48ccd74b36c594d232c6761b921dee8c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599904"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Ver informes de Defender para Office 365 en el panel Informes del Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las organizaciones de Microsoft Defender para Office 365 (por ejemplo, suscripciones a Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 1 o complementos del Plan 2 de Microsoft Defender para Office 365) contienen una variedad de informes relacionados con la seguridad. Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)puede ver estos informes en el Centro de seguridad & cumplimiento yendo al **Panel de** \> **informes**. Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .

![El panel Informes del Centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Informe de tipos de archivo de Microsoft Defender para Office 365

El informe tipos de archivo de **Defender para Office 365** muestra el tipo de archivos detectados como malintencionados por [datos adjuntos seguros.](safe-attachments.md)

 La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite 10 días de filtrado.

Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Defender para tipos de archivo de \>  **Office 365**. Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget Tipos de archivo de Defender para Office 365 en el panel Informes](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> La información de este informe también está disponible en el informe de eliminación de mensajes de [Defender para Office 365](#defender-for-office-365-message-disposition-report).

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Vista de informe para el informe de tipos de archivo de Defender para Office 365

Las vistas siguientes están disponibles:

- **Ver datos por: Archivo:** El gráfico contiene la siguiente información:

  - **Datos adjuntos malintencionados de Excel**
  - **Datos adjuntos de Flash malintencionados**
  - **Datos adjuntos de PDF malintencionados**
  - **Datos adjuntos malintencionados de PowerPoint**
  - **Direcciones URL malintencionadas**
  - **Datos adjuntos de Word malintencionados**
  - **Datos adjuntos ejecutables malintencionados**
  - **Otros**

  Cuando mantiene el mouse sobre un día determinado (punto de datos), puede [](safe-attachments.md) ver el desglose de los tipos de archivos malintencionados detectados por datos adjuntos seguros y protección [contra malware en EOP](anti-malware-protection.md).

  ![Vista de archivos en el informe Tipos de archivo de Defender para Office 365](../../media/atp-file-types-report-file-view.png)

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

- **Ver datos por: Mensaje:** El gráfico contiene la siguiente información:

  - **Bloquear acceso**
  - **Mensajes reemplazados**
  - **Mensajes supervisados**
  - **Reemplazado por entrega dinámica de correo** electrónico: para obtener más información, vea Dynamic Delivery in Safe Attachments [policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Vista de mensajes en el informe tipos de archivo de Defender para Office 365](../../media/atp-file-types-report-message-view.png)

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor **de mensajes pasados** adicional.

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Vista de tabla de detalles para el informe de tipos de archivo de Defender para Office 365

Si hace clic **en Ver tabla de detalles,** el informe proporciona una vista casi en tiempo real de todos los clics que ocurren en la organización durante los últimos 10 días. La información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: Archivo**:

  - **Fecha**
  - **Dirección de destinatario**
  - **Dirección del remitente**
  - **Id. de** mensaje: disponible en el **campo de encabezado Id. de** mensaje en el encabezado del mensaje y debe ser único. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).
  - **Archivo**

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

- **Ver datos por: Mensaje**:

  - **Fecha**
  - **Dirección de destinatario**
  - **Dirección del remitente**
  - **Id. de mensaje**
  - **Archivo**
  - **Subject**

  Si hace clic **en Filtros,** puede modificar los resultados con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor **de mensajes pasados** adicional.

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="defender-for-office-365-message-disposition-report"></a>Informe de eliminación de mensajes de Microsoft Defender para Office 365

El **informe de eliminación de** mensajes atp muestra las acciones que se realizaron para los mensajes de correo electrónico que se detectaron como con contenido malintencionado.

Para ver el informe, abra el Centro de  [seguridad & cumplimiento](https://protection.office.com), vaya al Panel de informes y seleccione Defender para \>  Office **365 eliminación de mensajes**. Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Widget de disposición de mensajes de Defender para Office 365 en el panel informes](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> La información de este informe también está disponible en el informe Tipos de archivo de [Defender para Office 365](#defender-for-office-365-file-types-report).

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Vista Informe para el informe de eliminación de mensajes de Defender para Office 365

Las vistas siguientes están disponibles:

- **Ver datos por: Mensaje:** El gráfico contiene la siguiente información:

  - **Bloquear acceso**
  - **Mensajes reemplazados**
  - **Mensajes supervisados**
  - **Reemplazado por entrega dinámica de correo** electrónico: para obtener más información, vea Dynamic Delivery in Safe Attachments [policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Vista de mensajes en el informe tipos de archivo de Defender para Office 365](../../media/atp-file-types-report-message-view.png)

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor **de mensajes pasados** adicional.

- **Ver datos por: Archivo:** El gráfico contiene la siguiente información:

  - **Datos adjuntos malintencionados de Excel**
  - **Datos adjuntos de Flash malintencionados**
  - **Datos adjuntos de PDF malintencionados**
  - **Datos adjuntos malintencionados de PowerPoint**
  - **Direcciones URL malintencionadas**
  - **Datos adjuntos de Word malintencionados**
  - **Datos adjuntos ejecutables malintencionados**
  - **Otros**

  Cuando mantiene el mouse sobre un día determinado (punto de datos), puede [](safe-attachments.md) ver el desglose de los tipos de archivos malintencionados detectados por datos adjuntos seguros y protección [contra malware en EOP](anti-malware-protection.md).

  ![Vista de archivos en el informe Tipos de archivo de Defender para Office 365](../../media/atp-file-types-report-file-view.png)

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Vista de tabla detalles del informe de eliminación de mensajes de Defender para Office 365

Si hace clic **en Ver tabla de detalles,** el informe proporciona una vista casi en tiempo real de todos los clics que ocurren en la organización durante los últimos 10 días. La información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: Mensaje**:

  - **Fecha**
  - **Dirección de destinatario**
  - **Dirección del remitente**
  - **Id. de mensaje**
  - **Archivo**
  - **Subject**

  Si hace clic **en Filtros,** puede modificar los resultados con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor **de mensajes pasados** adicional.

- **Ver datos por: Archivo**:

  - **Fecha**
  - **Dirección de destinatario**
  - **Dirección del remitente**
  - **Id. de mensaje**
  - **Archivo**

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Los mismos valores de tipo de archivo que están visibles en el gráfico.

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="mail-latency-report"></a>Informe de latencia de correo

El **informe de latencia de** correo muestra una vista agregada de la latencia de entrega y detonación de correo experimentada en su organización. Los tiempos de entrega de correo en el servicio se ven afectados por una serie de factores y el tiempo de entrega absoluto en segundos a menudo no es un buen indicador de éxito o un problema. Un tiempo de entrega lento en un día puede considerarse un promedio de tiempo de entrega en otro día, o viceversa. El **informe de latencia de correo** intenta calificar la entrega de mensajes en función de datos estadísticos sobre los tiempos de entrega observados de otros mensajes:

- **Percentil 50:** este es el medio para los tiempos de entrega de mensajes. Puede considerar este valor como un tiempo medio de entrega.
- **Percentil 90:** esto indica una latencia alta para la entrega de mensajes. Solo el 10 % de los mensajes tardaron más de este valor en entregarse.
- **Percentil 99:** indica la latencia más alta para la entrega de mensajes.

La latencia de red y del lado cliente no se incluyen.

Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Informe de latencia \>  **de correo**. Para ir directamente al informe, abra <https://protection.office.com/mailLatencyReport?viewid=P50> .

![Widget de informe de latencia de correo en el panel Informes](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Vista Informe para el informe de latencia de correo

Al abrir el informe, la **pestaña Percentiles 50** está seleccionada de forma predeterminada.

De forma predeterminada, esta vista contiene un gráfico configurado con los filtros siguientes:

- **Fecha:** los últimos 7 días
- **Vista de mensaje**:
  - Mensajes detonados

En este gráfico se muestran los mensajes organizados en las siguientes categorías:

- **Latencia de entrega de correo**
- **Latencia de detonación**

Al pasar el mouse sobre una categoría del gráfico, puede ver un desglose de la latencia en cada categoría.

![Informe de latencia de correo](../../media/mail-latency-report.png)

Si hace clic **en Filtrar** en la vista informe, puede modificar los resultados con los filtros siguientes:

- Todos los mensajes
- Mensajes que contienen datos adjuntos o direcciones URL

Si hace clic en la **ficha Percentiles 90** o en la **ficha Percentiles 99,** se usan los mismos filtros predeterminados de la **vista Percentiles 50.**

### <a name="details-table-view-for-the-mail-latency-report"></a>Vista de tabla Detalles del informe de latencia de correo

La siguiente información se muestra en la vista de tabla de detalles:

- **Fecha**
- **Percentiles**
- **Recuento de mensajes**
- **Latencia general**

![Detalles del informe de latencia de correo](../../media/mail-latency-report-details.png)

Lo anterior muestra que el 14 de noviembre la latencia media experimentada para todos los mensajes entregados y detonados fue **de 108.033** segundos.

La tabla de detalles contiene la misma información en cada pestaña.

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El **informe de** estado de protección contra amenazas es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por Exchange Online [Protection](exchange-online-protection-overview.md) (EOP) y Microsoft Defender para Office 365. Para obtener más información, vea [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Informe de protección contra amenazas de url

El **informe de protección contra** amenazas url proporciona vistas de resumen y tendencias para las amenazas detectadas y las acciones realizadas en los clics de dirección URL como parte de [vínculos seguros.](safe-links.md) Este informe no tendrá los datos de clic de los usuarios en los que la directiva vínculos seguros aplicada tenga seleccionada la opción No realizar un seguimiento de los **clics del** usuario.

Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Informe de \>  protección de **direcciones URL**. Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget de informe de protección de direcciones URL en el panel Informes](../../media/url-protection-report-widget.png)

> [!NOTE]
> Se trata de un *informe de tendencias de protección,* lo que significa que los datos representan tendencias en un conjunto de datos más grande. Como resultado, los datos de la vista de agregado no están disponibles en tiempo real aquí, pero los datos de la vista de tabla de detalles lo son, por lo que es posible que vea una ligera discrepancia entre las dos vistas.

### <a name="report-view-for-the-url-threat-protection-report"></a>Vista Informe para el informe de protección contra amenazas de url

El **informe de protección contra** amenazas de dirección URL tiene dos vistas agregadas que se actualizan una vez cada cuatro horas y que muestran los datos de los últimos 90 días:

- **Acción de protección de clic de dirección URL:** muestra el número de clics de url de los usuarios de la organización y los resultados del clic:

  - **Bloqueado** (el usuario no ha navegado a la dirección URL)
  - **Bloqueado y hecho clic (el** usuario ha elegido continuar navegando a la dirección URL)
  - **Se ha hecho clic durante el examen** (el usuario ha hecho clic en el vínculo antes de completar el examen)

  Un clic indica que el usuario ha hecho clic en la página de bloqueo al sitio web malintencionado (los administradores pueden deshabilitar el clic en las directivas de vínculos seguros).

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Las acciones de protección de clics disponibles, además del valor **Permitido** (se permitió al usuario navegar a la dirección URL).

  ![Vista de acción de protección de clic de url en el informe de protección contra amenazas de url](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **Clic en dirección URL por aplicación:** muestra el número de clics de dirección URL de las aplicaciones que admiten vínculos seguros:

  - **Cliente de correo electrónico**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Otros**

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Las aplicaciones disponibles.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Vista de tabla de detalles para el informe de protección contra amenazas url

Si hace clic **en Ver** tabla de detalles, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren en la organización durante los últimos 7 días con los siguientes detalles:

- **Hora de hacer clic**
- **Usuario**
- **URL**
- **Action**
- **App**

Si hace clic **en Filtros** en la vista tabla de detalles, puede filtrar  por  los mismos criterios que en la vista de informe y también por dominios o destinatarios separados por comas.

> [!NOTE]
> El **filtro Dominios** hace referencia al dominio de dirección URL que aparece en los resultados del informe. 

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="additional-reports-to-view"></a>Informes adicionales para ver

Además de los informes descritos en este artículo, hay otros informes disponibles, como se describe en la tabla siguiente:

****

|Informe|Tema|
|---|---|
|**Explorer** (Microsoft Defender para Office 365 Plan 2) o detecciones en tiempo **real** (Microsoft Defender para Office 365 Plan 1)|[Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md)|
|**Informes de seguridad de** correo electrónico, como el informe de remitentes y destinatarios principales, el informe de correo suplantación de identidad y el informe de detecciones de correo no deseado.|[Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento](view-email-security-reports.md)|
|**Informes de flujo de** correo, como el informe de reenvío, el informe de estado de flujo de correo y el informe Principales remitentes y destinatarios.|[Ver informes de flujo de correo en el Centro de seguridad & cumplimiento](view-mail-flow-reports.md)|
|**Seguimiento de direcciones URL para vínculos seguros** (solo PowerShell). El resultado de este cmdlet muestra los resultados de las acciones vínculos seguros de los últimos siete días.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**Resultados de tráfico de correo para EOP y Microsoft Defender para Office 365** (solo PowerShell). El resultado de este cmdlet contiene información sobre Dominio, Fecha, Tipo de evento, Dirección, Acción y Recuento de mensajes.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**Informes de detalles de correo para detecciones de EOP y Defender para Office 365** (solo PowerShell). El resultado de este cmdlet contiene detalles sobre archivos o direcciones URL malintencionados, intentos de suplantación, suplantación y otras amenazas potenciales en el correo electrónico o los archivos.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>¿Qué permisos se necesitan para ver los informes de Defender para Office 365?

Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

**Nota:** Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & cumplimiento y permisos para otras características de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en los informes de Defender para Office 365, compruebe que las directivas están configuradas correctamente. Su organización debe tener [](set-up-safe-attachments-policies.md) [definidas directivas de vínculos](set-up-safe-links-policies.md) seguros y directivas de datos adjuntos seguros para que la protección de Defender para Office 365 esté en su lugar. Vea también Protección contra correo no deseado y [antimalware.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Temas relacionados

[Informes inteligentes y reportes en el Centro de seguridad y cumplimiento](reports-and-insights-in-security-and-compliance.md)

[Permisos de roles (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
