---
title: Ver informes de flujo de correo en el panel de informes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los informes de flujo de correo que están disponibles en el panel informes del centro de seguridad & cumplimiento.
ms.custom: ''
ms.openlocfilehash: 772aec3c18e3e6343bdfd4831252d03a46961735
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949625"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Ver informes de flujo de correo en el panel informes del centro de seguridad & cumplimiento

Además de los informes de flujo de correo que están disponibles en el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento, hay disponible una variedad de informes de flujo de correo adicionales en el panel de informes para ayudarle a supervisar su organización de 365 de Microsoft.

Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el [centro de seguridad & cumplimiento](https://office.protection.com) desde el panel de **informes** \> **Dashboard**. Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Informe de conector

El **Informe de conectores** muestra la actividad de flujo de correo en los [conectores entrantes y](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) salientes que están configurados para su organización.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de conector**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ConnectorReport> .

![Widget de informe de conectores en el panel de informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Vista informes para el informe de conector

Los siguientes gráficos están disponibles en la vista de informe:

- **Ver datos por: flujo del correo**: en este gráfico se muestra el número de mensajes entrantes y salientes organizados por:

  - **Total**
  - **De Internet sin conector**
  - **A Internet sin conector**
  - Un conector específico que haya configurado.

  Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de estas opciones o **todo el flujo de correo**.

  ![Ver los datos por flujo de correo en el informe de conectores](../../media/connector-report-view-data-by-mail-flow.png)

- **Ver datos por: uso de TLS**: en este gráfico se muestra el porcentaje de uso de la versión de seguridad de la capa de transporte (TLS) para el flujo de correo.

  Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de las siguientes opciones:

  - **Todo el flujo de correo**
  - **De Internet sin conector**
  - **A Internet sin conector**
  - Un conector específico que haya configurado.

  ![Ver datos por uso de TLS en el informe de conectores](../../media/connector-report-view-data-by-tls-usage.png)

Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

### <a name="details-table-view-for-the-connector-report"></a>Vista de tabla de detalles para el informe de conector

Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:

- **Date**
- **Dirección y nombre del conector**
- **Tipo de conector**
- **¿TLS forzado?**: el valor **true** o **false**.
- **Sin TLS** (porcentaje)
- **TLS 1,0** (porcentaje)
- **TLS 1,1** (porcentaje)
- **TLS 1,2** (porcentaje)
- **Volumen**: el número de mensajes.

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="exchange-transport-rule-report"></a>Informe de reglas de transporte de Exchange

El **Informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione regla de **transporte de Exchange**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Widget de regla de transporte de Exchange en el panel informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Vista informes para el informe de reglas de transporte de Exchange

Los siguientes gráficos están disponibles en la vista de informe:

- **Ver datos por: reglas** \> de transporte de Exchange **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte.

- **Ver datos por: reglas** \> de transporte de Exchange **Desglose por: gravedad: en**este gráfico se muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** . El nivel de gravedad se establece como una acción en la regla (**auditar esta regla con el nivel de gravedad** o _SetAuditSeverity_). Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Ver datos por: reglas de transporte de Exchange de DLP** \> **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP). Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:

  - **Mostrar datos para: todas las reglas de transporte de DLP**
  - **Mostrar datos para: usuarios comprometidos**
  - **Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**

- **Ver datos por: reglas de transporte de Exchange de DLP** \> **Dividir por: dirección**: esta vista muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** que se vieron afectados por las reglas de transporte de DLP. Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:

  - **Mostrar datos para: todas las reglas de transporte de DLP**
  - **Mostrar datos para: usuarios comprometidos**
  - **Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**

Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de gravedad

![Vista de informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Vista de tabla de detalles para el informe de regla de transporte de Exchange

Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: reglas de transporte de Exchange**:

  - **Date**
  - **Regla de transporte**
  - **Asunto**
  - **Dirección del remitente**
  - **Dirección del destinatario**
  - **Gravedad**
  - **Dirección**

- **Ver datos por: reglas de transporte de DLP de Exchange**:

  - **Date**
  - **Directiva DLP**
  - **Regla de transporte**
  - **Asunto**
  - **Dirección del remitente**
  - **Dirección del destinatario**
  - **Gravedad**
  - **Dirección**

Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de gravedad

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="forwarding-report"></a>Reenvío de informes

El **Informe de reenvío** muestra los mensajes reenviados automáticamente de la organización a dominios externos de los buzones de Exchange Online. Los mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar una cuenta en peligro.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **reenviar Informe**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Reenvío del widget de informe en el panel informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Vista informes para el informe de reenvío

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: métodos de reenvío**: se muestran los métodos siguientes:

  - **Regla de transporte**: también conocida como [reglas de flujo de correo](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
  - **Regla de buzón de correo**: también conocida como reglas de la [bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).

  ![Vista de métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- **Mostrar datos de: dominios de reenvío**: esta vista muestra los dominios de destinatario que son los destinos para el reenvío.

  ![Vista de dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- **Mostrar datos para: reenviadores**: se muestran los siguientes reenviadores:

  - **Regla de transporte**
  - El buzón de correo que contiene la regla de reenvío de la bandeja de entrada.

  ![Vista de reenvíos en el informe de reenvío](../../media/forwarding-report-forwarders.png)

Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

### <a name="details-table-view-for-the-forwarding-report"></a>Vista de tabla de detalles para el informe de reenvío

Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:

- **Reenviadores**: la **regla de transporte** de valor o el buzón que contiene la regla de reenvío de la bandeja de entrada.
- **Tipo de reenvío**: regla de **buzón de correo** de valor o regla de **transporte**.
- **Nombre de destinatario**
- **Dominio del destinatario**
- **Detalles**: este es el valor de GUID de la regla de flujo de correo o el valor RuleIdentity de la regla de bandeja de entrada.
- **Count**
- **Primera fecha de reenvío**

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="mailflow-status-report"></a>Informe de estado de flujo de notificación

El **Informe de estado de flujo** de correo es similar al [Informe de correo electrónico enviado y recibido](#sent-and-received-email-report), con información adicional sobre el correo electrónico permitido o bloqueado en el servidor perimetral. Este es el único informe que contiene información sobre la protección perimetral y muestra la cantidad de correo electrónico que se bloquea antes de que se permita el servicio para su evaluación por parte de Exchange Online Protection (EOP). Es importante comprender que si un mensaje se envía a cinco destinatarios, se cuenta como cinco mensajes diferentes y no un mensaje.
Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione informe de **Estado de flujo**de información. Para ir directamente al **Informe de estado del flujo de correo**, Abra <https://protection.office.com/mailflowStatusReport> .

![Widget de informe de estado de flujo de registros en el panel informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Tipo de vista para el informe de estado de flujo de información

Al abrir el informe, la ficha **tipo** se selecciona de forma predeterminada. De forma predeterminada, esta vista contiene un gráfico y una tabla de datos que se configura con los siguientes filtros:

- **Fecha**: los últimos 7 días.
- **Dirección**:

  - **Entrada**
  - **Saliente**
  - **Dentro de la organización**: este recuento es para los mensajes dentro de un espacio empresarial es decir el remitente abc@domain.com envía al destinatario xyz@domain.com (cuenta por separado de **entrada** y de **salida**)

- **Tipo**:

  - **Correo bueno**
  - **Malware**
  - **Correo no deseado**
  - **Protección perimetral**
  - **Mensajes de regla**
  - **Correo de suplantación de identidad**

El gráfico se organiza por los valores de **tipo** .

Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.

La tabla de datos contiene la siguiente información:

- **Dirección**
- **Tipo**
- **24 horas**
- **3 días**
- **7 días**
- **15 días**
- **30 días**

Si hace clic en **elegir una categoría para obtener más información**, puede seleccionar uno de los siguientes valores:

- **Correo electrónico de suplantación de identidad**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- **Malware en correo electrónico**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).
- **Detecciones de correo no deseado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).
- **Correo no deseado de Edge bloqueado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).

**Exportar**:

Para la vista de detalles, solo puede exportar datos de un día. Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.

Cada archivo. csv exportado está limitado a 150.000 filas. Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.

![Tipo ver en el informe de estado de flujo de información ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Vista de dirección para el informe de estado de flujo de información

Si hace clic en la ficha **Dirección** , se usarán los mismos filtros predeterminados de la vista de **tipos** .

El gráfico está organizado por valores de **Dirección** .

Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico. Se usan los mismos filtros de la vista **tipo** .

La tabla de datos contiene la misma información de la vista de **tipo** .

El comportamiento seleccionar **una categoría para obtener más información sobre** las selecciones disponibles y el comportamiento es el mismo que el de la vista **tipo** .

**Exportar**:

Para la vista de detalles, solo puede exportar datos de un día. Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.

Cada archivo. csv exportado está limitado a 150.000 filas. Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.

![Vista de dirección en el informe de estado de flujo de notificación ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Vista de embudo para el informe de estado de flujo de información

La vista de **embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo entrante y saliente de su organización. Proporciona detalles sobre el recuento de correo electrónico total y cómo las características de protección contra amenazas configuradas, incluida la protección perimetral, anti-malware, antiphishing, contra correo no deseado y contra la suplantación de identidad afectan a este recuento.

Si hace clic en la ficha **embudo** , de forma predeterminada, esta vista contendrá un gráfico y una tabla de datos configurada con los siguientes filtros:

- **Fecha**: los últimos 7 días.

- **Dirección**:

  - **Entrada**
  - **Saliente**
  - **Dentro de la organización**: este recuento es para los mensajes enviados en un espacio empresarial; es decir, el abc@domain.com del remitente envía al destinatario xyz@domain.com (contado por separado de entrante y saliente).

La vista agregada y la vista de tabla de datos permiten 90 días de filtrado.

Si hace clic en **filtrar**, puede filtrar tanto el gráfico como la tabla de datos.

Este gráfico muestra el número de correos electrónicos organizados por:

- **Correo electrónico total**
- **Correo electrónico tras la protección perimetral**
- **Correo electrónico después de anti-malware, reputación de archivo, bloque de tipo de archivo**
- **Correo electrónico después de antiphishing, reputación de dirección URL, suplantación de marca, anti-falseamiento**
- **Correo electrónico después de la protección contra correo no deseado, filtrado de correo masivo**
- **Correo electrónico después de suplantación de usuario y dominio**<sup>1</sup>
- **Correo electrónico después de detonación de archivo y URL**<sup>1</sup>
- **Correo electrónico detectado como benigno después de la protección tras la entrega (dirección URL, clic en protección del tiempo)**

<sup>1</sup> solo para ATP de Office 365

Para ver el correo electrónico filtrado por EOP o ATP por separado, haga clic en el valor de la leyenda del gráfico.

La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:

- **Date**
- **Correo electrónico total**
- **Protección perimetral**
- **Anti-malware, reputación de archivos, bloque de tipo de archivo**
- **Anti-phish, reputación de dirección URL, suplantación de marca, antifalsificación**
- **Contra correo electrónico no deseado, filtrado de correo masivo**
- **Suplantación de usuario y dominio (ATP)**
- **Detonación de archivo y dirección URL (ATP)**
- **Protección tras entrega y ZAP (ATP) o ZAP (EOP)**

Si selecciona una fila en la tabla de datos, se muestra un desglose de los recuentos de correo electrónico en el control flotante.

**Exportar**:

Después de hacer clic en **exportar** en **Opciones**, puede seleccionar uno de los siguientes valores:

- **Resumen (con datos para los últimos 90 días como máximo)**
- **Detalles (con datos de 30 últimos días como máximo)**

En **fecha**, elija un rango y, a continuación, haga clic en **aplicar**. Los datos de los filtros actuales se exportarán a un archivo. csv.

Cada archivo. csv exportado está limitado a 150.000 filas. Si los datos contienen más de 150.000 filas, se crearán varios archivos. csv.

 ![Vista de embudo en el informe de estado de flujo de notificación ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Vista técnica del informe de estado de flujo de información

La **vista técnica** es similar a la vista de **embudo** y proporciona detalles más granulares para las características de protección contra amenazas configuradas. Desde el gráfico, puede ver cómo se clasifican los mensajes en las diferentes etapas de la protección contra amenazas.

Si hace clic en la pestaña **vista técnica** , de forma predeterminada, esta vista contendrá un gráfico y una tabla de datos configurada con los siguientes filtros:

- **Fecha**: los últimos 7 días.

- **Dirección**:

  - **Entrada**
  - **Saliente**
  - **Dentro de la organización**: este recuento es para los mensajes dentro de un espacio empresarial es decir el remitente abc@domain.com envía al destinatario xyz@domain.com (cuenta por separado de entrada y de salida)

La vista agregada y la vista de tabla de datos permiten 90 días de filtrado.

Si hace clic en **filtrar**, puede filtrar tanto el gráfico como la tabla de datos.

Este gráfico muestra los mensajes organizados en las siguientes categorías:

- **Correo electrónico total**
- **Límite permitido, perimetral filtrado**
- **No es malware, detección de datos adjuntos seguros (ATP), detección del motor antimalware, bloqueo de reglas**
- **No phish, error de DMARC, detección de suplantación, detección de suplantación de identidad, detección de phish**
- **Sin detección con detonación de dirección URL, detección de detonación de dirección URL (ATP)**
- **No es correo no deseado, correo no deseado**
- **Correo electrónico no malintencionado, detección de vínculos seguros (ATP), ZAP**

Cuando desplaza el puntero sobre una categoría del gráfico, puede ver el número de mensajes que hay en esa categoría.

La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:

- **Date**
- **Correo electrónico total**
- **Borde filtrado**
- **Motor antimalware, datos adjuntos seguros, regla filtrado**
- **DMARC, suplantación, falsificación, phish filtrado**
- **Detección de detonación de dirección URL**
- **Filtrado contra correo electrónico no deseado**
- **ZAP quitado**
- **Detección por vínculos seguros**

Si selecciona una fila en la tabla de datos, se muestra un desglose de los recuentos de correo electrónico en el control flotante.

**Exportar**:

Al hacer clic en **exportar**, en **Opciones** , puede seleccionar uno de los siguientes valores:

- **Resumen (con datos para los últimos 90 días como máximo)**
- **Detalles (con datos de 30 últimos días como máximo)**

En **fecha**, elija un rango y, a continuación, haga clic en **aplicar**. Los datos de los filtros actuales se exportarán a un archivo. csv.

Cada archivo. csv exportado está limitado a 150.000 filas. Si los datos contienen más de 150.000 filas, se crearán varios archivos. csv.

 ![Vista de Tech en el informe de estado de flujo de información ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Informe de correo electrónico enviado y recibido

El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno". La diferencia entre este informe y el [Informe de estado de flujo](#mailflow-status-report) de correos es la siguiente: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral.

La vista agregada y la vista de detalles del informe permiten 90 días de filtrado.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **correo electrónico enviado y recibido**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Widget de correo electrónico enviado y recibido en el panel de informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Vista informes para el informe de correo electrónico enviado y recibido

Los siguientes gráficos están disponibles en la vista de informe:

- **Dividir por: escriba**: el gráfico muestra todas las categorías disponibles:

  - **Total**
  - **Correo bueno**
  - **Malware (anti-malware)** (EOP)
  - **Detecciones de correo no deseado**
  - **Mensajes de regla**
  - **Malware avanzado** (Office 365 ATP)

  Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.

  ![Tipo ver en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- **Desglose por: dirección**: el gráfico muestra los datos **totales**, **entrantes**y **salientes** . Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.

  ![Vista de dirección en el informe de correo electrónico enviados y recibidos](../../media/sent-and-received-email-report-direction-view.png)

- **Explorar en profundidad por** \> **Malware (anti-malware)**: esta selección le lleva a las [detecciones de malware en el informe de correo electrónico](view-email-security-reports.md#malware-detections-in-email-report).

- **Explorar en profundidad por** \> **Detecciones de correo no deseado)**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).

Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de tipo

Para volver a la vista de informe, haga clic en **Ver informe**.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Vista de tabla de detalles para el informe de correo electrónico enviado y recibido

Si hace clic en **ver tabla de detalles** en el cuadro **desglosar por: dirección** o **dividir por:** vista de dirección, se muestra la siguiente información:

- **Fecha (UTC)**
- **Tipo**
- **Dirección**
- **Número de mensajes**

Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de tipo

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="top-senders-and-recipients-report"></a>Informe de remitentes y destinatarios principales

El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **principales remitentes y destinatarios**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widgets principales remitentes y destinatarios en el panel informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Vista informes para los principales informes de remitentes y destinatarios

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para los \> remitentes de correo principales**
- **Mostrar datos para los \> principales destinatarios de correo**
- **Mostrar datos para los \> principales destinatarios de correo no deseado**
- **Mostrar datos para \> Destinatarios principales de malware** (EOP)
- **Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)

La composición del gráfico circular cambia en función de estas selecciones.

Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.

Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

![Gráfico circular en la vista de informe en el informe de remitentes y destinatarios principales](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Vista de tabla de detalles para el informe de remitentes y destinatarios principales

Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:

- **Mostrar datos para los \> remitentes de correo principales**

  - **Principales remitentes de correo**
  - **Count**

- **Mostrar datos para los \> principales destinatarios de correo**

  - **Destinatarios principales de correo**
  - **Count**

- **Mostrar datos para los \> principales destinatarios de correo no deseado**

  - **Principales destinatarios de correo no deseado**
  - **Count**

- **Mostrar datos para \> Destinatarios principales de malware** (EOP)

  - **Destinatarios principales de malware**
  - **Count**

- **Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)

  - **Destinatarios principales de malware (ATP)**
  - **Count**

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos se necesitan para ver estos informes?

Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.

- En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:

  -Organization Management-administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) -lector de seguridad

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:

  -Administración de la organización: administración de la organización de solo vista-destinatarios de solo vista-administración de cumplimiento

Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="related-topics"></a>Temas relacionados

[Informes inteligentes y reportes en el Centro de seguridad y cumplimiento](reports-and-insights-in-security-and-compliance.md)

[Reportes de flujo de Correo en el Centro de seguridad y cumplimiento](mail-flow-insights-v2.md)

[Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento](view-email-security-reports.md)

[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
