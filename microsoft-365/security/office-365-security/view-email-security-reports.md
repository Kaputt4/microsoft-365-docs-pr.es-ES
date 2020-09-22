---
title: Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización. Los informes de seguridad de correo electrónico están disponibles en el centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 588c30ca07684636661c7946b2418b75574c8cbd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199222"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Hay disponibles varios informes en el centro de [seguridad & cumplimiento](https://protection.office.com) para ayudarle a ver cómo las características de seguridad del correo electrónico, como las características contra correo electrónico no deseado, antimalware y de cifrado de Microsoft 365 están protegiendo su organización. Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el centro de seguridad & cumplimiento desde el panel de **informes** \> **Dashboard**. Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Informe de usuarios comprometidos

> [!NOTE]
> Este informe está disponible en Microsoft 365 organizaciones con buzones de correo de Exchange Online. No está disponible en organizaciones independientes de Exchange Online Protection (EOP).

El informe de **usuarios comprometedos** muestra el número de cuentas de usuario que se marcaron como **sospechosas** o **restringidas** en los últimos 7 días. Las cuentas en cualquiera de estos Estados son problemáticas o incluso comprometidas. Con el uso frecuente, puede usar el informe para identificar picos e incluso tendencias, en cuentas sospechosas o restringidas. Para obtener más información acerca de los usuarios comprometidos, consulte [responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).

![Widget usuarios comprometidos en el panel informes](../../media/compromised-users-report-widget.png)

La vista agregada muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **usuarios comprometidos**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=CompromisedUsers> .

Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **filtros** y seleccionando uno o más de los siguientes valores:

- **Fecha de inicio** y **fecha de finalización**

- **Sospechoso**: la cuenta de usuario ha enviado un mensaje de correo electrónico sospechoso y corre el riesgo de que se restrinja el envío de correo electrónico.

- **Restringido**: se ha restringido el envío de correo electrónico a la cuenta de usuario debido a patrones muy sospechosos.

![Vista de informe en el informe de usuarios comprometedos](../../media/compromised-users-report-activity-view.png)

Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:

- **Hora de creación**
- **Nombre de usuario**
- **Acción**

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="encryption-report"></a>Informe de cifrado

El **Informe de cifrado** está disponible en EOP (suscripciones con buzones en Exchange online o EOP independiente sin buzones de Exchange Online). El equipo de seguridad de la organización puede usar la información de este informe para identificar patrones y aplicar de forma proactiva o ajustar las directivas de los mensajes de correo electrónico confidenciales. Por ejemplo:

- Si ve un gran número de mensajes de correo electrónico cifrados por los usuarios, es posible que desee agregar una directiva de cifrado para automatizar el cifrado para determinados casos de uso. Para obtener más información, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Si tiene varias plantillas de cifrado disponibles pero nadie las está usando, puede explorar si los usuarios necesitan formación de características.

La vista agregada permite filtrar los últimos 90 días, mientras que la vista de detalles permite el filtrado durante 10 días.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de cifrado**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=EncryptionReport> .

Para obtener más información sobre el cifrado, consulte [cifrado de correo electrónico en Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Vista informes para el informe de cifrado

Puede usar los siguientes filtros en el gráfico:

- **Ver datos por: informe de cifrado de mensajes** y **desglose descendente por: método de cifrado**: están disponibles los siguientes métodos de cifrado:

  - **Cifrado por usuario**
  - **Cifrado por directiva**

  Si hace clic en **filtros**, puede modificar el gráfico con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Método de cifrado.
  - Plantilla de cifrado.

- **Ver datos por: informe de cifrado de mensajes** y **desglosar por: plantilla de cifrado**: están disponibles los siguientes métodos de cifrado:

  - **No reenviar**
  - **Cifrar solo**
  - **OME anterior**
  - **Personalizados**

  Si hace clic en **filtros**, puede modificar el gráfico con los siguientes filtros:

  - **Fecha de inicio** y **fecha de finalización**
  - Método de cifrado
  - Plantilla de cifrado

- **Ver datos por: los 5 dominios de destinatarios principales**: esta vista muestra un gráfico circular con recuentos de mensajes enviados para los 5 principales dominios de destinatarios.

  Si hace clic en **filtros**, puede seleccionar una **fecha de inicio** y una fecha de **finalización**.

### <a name="details-table-view-for-the-encryption-report"></a>Vista de tabla de detalles para el informe de cifrado

Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:

- **Dividir por: método de cifrado** o **desglosar por: plantilla de cifrado**: se muestra la siguiente información:

  - **Date**
  - **Dirección del remitente**
  - **Plantilla de cifrado**
  - **Método de cifrado**
  - **Dirección del destinatario**
  - **Asunto**

- **Ver datos por: los 5 dominios de destinatarios principales**:

  - **Date**
  - **Dominio del destinatario**
  - **Número de mensajes**
  
Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Método de cifrado
- Plantilla de cifrado

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="mailflow-status-report"></a>Informe de estado de flujo de notificación

El **Informe de estado de flujo** de correo contiene información sobre malware, correo no deseado, phishing y mensajes bloqueados del servidor perimetral. Para obtener más información, consulte [Informe de estado de flujo](view-mail-flow-reports.md#mailflow-status-report)de datos.

## <a name="malware-detections-in-email-report"></a>Informe de detecciones de malware en correo electrónico

El informe **de detecciones de malware en el informe de correo electrónico** muestra información sobre las detecciones de malware en los mensajes entrantes y salientes (malware detectado por Exchange Online Protection o EOP). Para obtener más información acerca de la protección contra malware en EOP, vea [Anti-Malware Protection in EOP](anti-malware-protection.md).

 El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles sólo permite 10 días.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **detecciones de malware en correo electrónico**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MalwareDetections> .

![Detecciones de malware en el widget de correo electrónico en el panel informes](../../media/malware-detections-widget.png)

Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **filtros** y seleccionando:

- **Fecha de inicio** y **fecha de finalización**
- **Entrada**
- **Saliente**

![Vista de informe en el informe de detección de malware en correo electrónico](../../media/malware-detections-report-view.png)

Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:

- **Date**
- **Dirección del remitente**
- **Dirección del destinatario**
- **Identificador del mensaje**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje y debe ser único. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).
- **Asunto**
- **Filename**
- **Nombre del malware**

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="sent-and-received-email-report"></a>Informe de correo electrónico enviado y recibido

El informe de **correo electrónico enviado y recibido** contiene información sobre malware, correo no deseado, reglas de flujo de correo (también conocidos como reglas de transporte) y detecciones de malware avanzadas una vez que el correo electrónico entra en el servicio. Para obtener más información, consulte [Informe de correo electrónico enviado y recibido](view-mail-flow-reports.md#sent-and-received-email-report).

## <a name="spam-detections-report"></a>Informe de detecciones de correo no deseado

El informe de **detecciones de correo no deseado** muestra mensajes de correo electrónico no deseado bloqueados por EOP. Los mensajes se cuentan de forma individual, no por destinatario. Por ejemplo, si se envió el mismo mensaje de correo no deseado a 100 destinatarios de la organización, se cuenta como un mensaje.

La vista agregada permite el filtrado de 90 días, mientras que la tabla de detalles permite el filtrado de 10 días.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **detecciones de correo no deseado**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget de detecciones de correo no deseado en el panel informes](../../media/spam-detections-report-widget.png)

Para obtener más información acerca de la protección contra correo no deseado, vea [protección contra correo no deseado en EOP](anti-spam-protection.md).

### <a name="report-view-for-the-spam-detections-report"></a>Vista informes para el informe de detecciones de correo no deseado

Los siguientes gráficos están disponibles en la vista de informe:

- **Dividir por: acción**: se muestran los siguientes tipos de eventos:

  - **Contenido de correo no deseado filtrado**
  - **Bloqueo de IP de correo no deseado**
  - **Bloque de sobre de correo no deseado**
  - **Filtro de DBEB de correo no deseado**: bloqueo perimetral basado en directorios (DBEB)

  Al pasar el mouse por encima de un día (punto de datos) en el gráfico, puede ver cuántos elementos se bloquearon ese día, así como la forma en que se clasifican dichos elementos.

  ![Vista de acción en el informe de detecciones de correo no deseado](../../media/spam-detections-report-action-view.png)

- **Desglose por: dirección**: se muestran las siguientes direcciones:

  - **Entrada**
  - **Saliente**

  ![Vista de dirección en en el informe de detecciones de correo no deseado](../../media/spam-detections-report-direction-view.png)

Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de tipo de evento

### <a name="details-table-view-for-the-spam-detections-report"></a>Vista de tabla de detalles para el informe de detecciones de correo no deseado

Si hace clic en **ver tabla de detalles** en cualquier vista de informe, se mostrará la siguiente información:

- **Date**
- **Dirección del remitente**
- **Dirección del destinatario**
- **Tipo de evento**
- **Acción**
- **Asunto**

Si hace clic en **filtros** en una tabla de detalles, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de tipo de evento

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="spoof-detections-report"></a>Informe de detecciones de suplantación de identidad

El informe de **detecciones de suplantación de identidad** muestra el número de mensajes de correo falsificados que se han detectado y de aquellos que se consideran "buenos" (correo falsificado realizado por razones empresariales legítimas). Para obtener más información sobre la suplantación de identidad, vea [anti-spoofing Protection in EOP](anti-spoofing-protection.md).

La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles sólo permite diez días de filtrado.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **detecciones de suplantación de identidad**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget detecciones de suplantación en el panel de informes](../../media/spoof-detections-widget.png)

Al pasar el mouse por encima de un día (punto de datos) en el gráfico, puede ver cuántos mensajes de correo electrónico de falsificación llegaron.

Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **filtros** y seleccionando uno o más de los siguientes valores:

- **Fecha de inicio** y **fecha de finalización**

- **Correo bueno**

- **Detectado como correo no deseado**

![Vista informes en el informe de detecciones de suplantación de identidad](../../media/spoof-detections-report-view.png)

Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:

- **Date**
- **Remitente falsificado**
- **Auténtico remitente**
- **IP del remitente**
- **Acción**
- **Número de mensajes**

Para volver a la vista de informe, haga clic en **Ver informe**.

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El informe de **Estado de protección contra amenazas** está disponible en EOP y en Office 365 ATP; sin embargo, los informes contienen datos diferentes. Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre [los archivos malintencionados detectados en SharePoint Online, OneDrive o Microsoft Teams](atp-for-spo-odb-and-teams.md).

El informe proporciona el número de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitios web (URL) bloqueados por el motor antimalware, [purgado automático de cero horas (ZAP)](zero-hour-auto-purge.md)y características de ATP como [vínculos seguros de ATP](atp-safe-links.md), [datos adjuntos seguros](atp-safe-attachments.md)de ATP y [protección contra el phishing](set-up-anti-phishing-policies.md)de ATP. Puede usar esta información para identificar tendencias o determinar si es necesario ajustar las directivas de la organización. Es importante comprender que si un mensaje se envía a cinco destinatarios, se cuenta como cinco mensajes diferentes y no un mensaje.

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione estado de **protección contra amenazas**. Para ir directamente al informe, abra una de las siguientes direcciones URL:

- Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .
- EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport>

![Widget de estado de protección contra amenazas en el panel de informes](../../media/threat-protection-status-report-widget.png)

De forma predeterminada, el gráfico muestra los datos de los últimos 7 días. Si hace clic en **filtros**, puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba pueden estar limitadas a 30 días). La vista de tabla de detalles permite filtrar durante 30 días.

### <a name="report-view-for-the-threat-protection-status-report"></a>Vista informes para el informe de estado de protección contra amenazas

Están disponibles las siguientes vistas:

- **Ver datos por: información general**: se muestra la siguiente información de detección:

  - **Malware de correo electrónico**
  - **Phishing de correo electrónico**
  - **Malware de contenido**

  ![Vista de información general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

- **Ver datos por: contenido \> Malware**<sup>1</sup>: se muestra la siguiente información para las organizaciones de ATP de Office 365:

  - **Motor antimalware**
  - **Detonación de archivos**

  ![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

- **Desglose por: tecnología de detección** y **ver datos por: \> phishing email**: se muestra la siguiente información:

  - **Reputación de dirección URL generada por ATP**<sup>1</sup>
  - **Filtro de phish avanzado**
  - **Anti-falseamiento: error de DMARC**
  - **Anti-suplantación de identidad: intra-org**
  - **Anti-falsear: dominio externo**
  - **Suplantación de marca**
  - **Suplantación de dominio**<sup>1</sup>
  - **Reputación de dirección URL de EOP**
  - **Filtro de phish general**
  - **Otros**
  - **Zap de phish**<sup>2</sup>
  - **Detonación de dirección URL**<sup>1</sup>
  - **Suplantación de usuario**<sup>1</sup>

  ![Vista de la tecnología de detección de correo phishing en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Desglose por: tecnología de detección** y **ver datos por: \> malware de correo electrónico**: se muestra la siguiente información:

  - **Reputación de archivo generada por ATP**<sup>1</sup>
  - **Motor antimalware**<sup>1</sup>
  - **Bloque de tipo de archivo de directiva antimalware**
  - **Detonación de archivo**<sup>1</sup>
  - **Reputación de archivos malintencionados**
  - **Zap de malware**<sup>2</sup>
  - **Otros**

  ![Vista de la tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Desglose por: tipo de directiva** y **ver datos por: \> phishing de correo electrónico** o **ver datos por: \> malware de correo electrónico**: se muestra la siguiente información:

  - **Anti-malware**
  - **Datos adjuntos seguros**<sup>1</sup>
  - **Anti-phish**
  - **Contra correo electrónico no deseado**
  - **Regla de flujo de correo** (también denominada regla de transporte)
  - **Otros**

  ![Vista de tipo de directiva de correo de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Desglose por: estado de entrega** y **ver datos por: \> phishing de correo electrónico** o **ver datos por: \> malware de correo electrónico**: se muestra la siguiente información:

  - **Error en la entrega**
  - **Sombra**
  - **Reenviado**
  - **Buzón de correo hospedado: carpeta personalizada**
  - **Buzón de correo hospedado: elementos eliminados**
  - **Buzón de correo hospedado: bandeja de entrada**
  - **Buzón hospedado: correo no deseado**
  - **Servidor local: entregado**
  - **Cuarentena**

  ![Vista de estado de entrega de correo de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> solo para ATP de Office 365

<sup>2</sup> la depuración automática de cero horas (ZAP) no está disponible en EOP independiente (solo funciona en buzones de Exchange Online).

Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

- **Fecha de inicio** y **fecha de finalización**
- Valor de detección
- **Protegido por** (solo para ATP de Office 365): **ATP** o **EOP**. Tenga en cuenta que esta propiedad filterable no está disponible en **ver datos por: \> malware de contenido**.

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Vista de tabla de detalles para el informe de estado de protección contra amenazas

Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: contenido \> Malware**:

  - **Date**
  - **Location**
  - **Dirigida por**
  - **Nombre del malware**

- **Ver datos por: información general**: no hay disponible ningún botón **tabla de detalles** de la vista.

- Todos los demás gráficos:

  - **Date**
  - **Asunto**
  - **Remitente**
  - **Destinatarios**
  - **Detectado por**
  - **Estado de entrega**
  - **Origen de la intromisión**

Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:

- **Fecha de inicio** y **fecha de finalización**
- Valor de detección
- **Protegido por** (solo para ATP de Office 365): **ATP** o **EOP**. Tenga en cuenta que esta propiedad filterable no está disponible en **ver datos por: \> malware de contenido**.

## <a name="top-malware-report"></a>Informe de malware principal

El informe de **malware más alto** muestra los distintos tipos de malware detectados por la [protección antimalware en EOP](anti-malware-protection.md).

Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **malware principal**. Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopMalware> .

![Widget de malware principal en el panel de informes](../../media/top-malware-report-widget.png)

Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes que se detectaron como si tuvieran ese malware.

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:

- **Malware principal**
- **Count**

Si hace clic en **filtros** en la vista de informe o en la vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

## <a name="url-threat-protection-report"></a>Informe de protección contra amenazas de URL

El **Informe de protección contra amenazas de direcciones URL** está disponible en la protección contra amenazas avanzada (ATP) de Office 365. Para obtener más información, consulte [Informe de protección contra amenazas de direcciones URL](view-reports-for-atp.md#url-threat-protection-report).

## <a name="user-reported-messages-report"></a>Informe de mensajes notificados por el usuario

El informe de **mensajes de** informes de usuario muestra información sobre los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad (phishing) o correo correcto mediante el [complemento de mensajes de informe](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).

Hay más detalles disponibles para cada mensaje, incluidos el motivo de la entrega, la excepción de la Directiva de correo no deseado o la regla de flujo de correo configurada para la organización. Para ver los detalles, seleccione un elemento de la lista de informes de usuarios y, a continuación, vea la información en las pestañas **Resumen** y **detalles** .

![El informe de mensajes de informes de usuario muestra los usuarios etiquetados como correo no deseado, no deseado o intentos de suplantación de identidad.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Para ver este informe, en el [centro de seguridad & cumplimiento](https://protection.office.com), realice una de las siguientes acciones:

- Vaya a **Threat management** \> **Dashboard** \> **mensajes de los que ha informado el usuario del panel de administración de**amenazas.

- Vaya a **Threat management** \> **Review** \> **los mensajes de revisión de administración de amenazas que ha informado el usuario**.

![En el centro de seguridad & cumplimiento, seleccione \> \> mensajes notificados por el usuario de revisión de administración de amenazas](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Para que el informe de mensajes notificados por el usuario funcione correctamente, el **registro de auditoría debe estar activado** para su entorno de Office 365. Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos se necesitan para ver estos informes?

Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.

- En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:

  -Organization Management-administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) -lector de seguridad

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:

  -Administración de la organización: administración de la organización de solo vista-destinatarios de solo vista-administración de cumplimiento

Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en los informes, compruebe que las directivas estén correctamente configuradas. Para obtener más información, consulte [proteger contra amenazas](protect-against-threats.md).

## <a name="related-topics"></a>Temas relacionados

[Protección contra correo electrónico no deseado y antimalware en EOP](anti-spam-and-anti-malware-protection.md)

[Informes inteligentes y reportes en el Centro de seguridad y cumplimiento](reports-and-insights-in-security-and-compliance.md)

[Ver informes de flujo de correo en el centro de seguridad & cumplimiento](view-mail-flow-reports.md)

[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
