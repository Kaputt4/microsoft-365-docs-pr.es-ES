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
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización. Los informes de seguridad de correo electrónico están disponibles en el Centro de & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 568144c449d2f1a70082130cc847d48c3486d9da
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865109"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Hay varios informes disponibles en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) para ayudarle a ver cómo protegen su organización las características de seguridad de correo electrónico, como el correo no deseado, el antimalware y las características de cifrado de Microsoft 365. Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el Centro  de seguridad & Cumplimiento yendo al Panel \> **de informes.** Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .

![Panel informes en el Centro de & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Informe de usuarios comprometidos

> [!NOTE]
> Este informe está disponible en organizaciones de Microsoft 365 con buzones de Exchange Online. No está disponible en organizaciones independientes de Exchange Online Protection (EOP).

El **informe de usuarios comprometidos** muestra el número  de  cuentas de usuario que se marcaron como sospechosas o restringidas en los últimos 7 días. Las cuentas de cualquiera de estos estados son problemáticas o incluso están en peligro. Con el uso frecuente, puede usar el informe para detectar picos e incluso tendencias en cuentas sospechosas o restringidas. Para obtener más información acerca de los usuarios comprometidos, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)

![Widget Usuarios comprometidos en el panel informes](../../media/compromised-users-report-widget.png)

La vista de agregado muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.

Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione \>  **Usuarios comprometidos.** Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .

Puede filtrar el gráfico y la tabla de detalles haciendo clic en **Filtros** y seleccionando uno o varios de los siguientes valores:

- **Fecha de inicio** y **fecha de finalización**

- **Sospechoso:** la cuenta de usuario ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico.

- **Restringido:** se ha restringido el envío de correo electrónico a la cuenta de usuario debido a patrones altamente sospechosos.

![Vista de informe en el informe de usuarios comprometidos](../../media/compromised-users-report-activity-view.png)

Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:

- **Hora de creación**
- **Nombre de usuario**
- **Acción**

Para volver a la vista informe, haga clic **en Ver informe.**

## <a name="encryption-report"></a>Informe de cifrado

El **informe de cifrado** está disponible en EOP (suscripciones con buzones en Exchange Online o EOP independiente sin buzones de Exchange Online). El equipo de seguridad de su organización puede usar la información de este informe para identificar patrones y aplicar o ajustar directivas de forma proactiva para mensajes de correo electrónico confidenciales. Por ejemplo:

- Si ve un gran número de mensajes de correo electrónico cifrados por los usuarios, es posible que desee agregar una directiva de cifrado para automatizar el cifrado en determinados casos de uso. Para obtener más información, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

- Si tiene varias plantillas de cifrado disponibles, pero nadie las usa, puede explorar si los usuarios necesitan formación de características.

La vista de agregado permite el filtrado de los últimos 90 días, mientras que la vista de detalles permite el filtrado durante 10 días.

Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de \>  informes y seleccione Informe **de cifrado.** Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=EncryptionReport> .

Para obtener más información sobre el cifrado, consulte [Cifrado de correo electrónico en Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Vista de informe para el informe de cifrado

Puede usar los siguientes filtros en el gráfico:

- **Ver datos por: Informe de cifrado de mensajes** y Dividir **por: Método de cifrado**: Están disponibles los siguientes métodos de cifrado:

  - **Cifrado por usuario**
  - **Cifrado por directiva**

  Si hace clic **en Filtros,** puede modificar el gráfico con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Método de cifrado.
  - Plantilla de cifrado.

- **Ver datos por: Informe de cifrado de mensajes** y Dividir **por: Plantilla de cifrado:** Están disponibles los siguientes métodos de cifrado:

  - **No reenviar**
  - **Cifrar solo**
  - **OME anterior**
  - **Personalizados**

  Si hace clic **en Filtros,** puede modificar el gráfico con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - Método de cifrado
  - Plantilla de cifrado

- **Ver datos por: principales 5** dominios de destinatarios: esta vista muestra un gráfico circular con recuentos de mensajes enviados para los 5 dominios de destinatarios principales.

  Si hace clic **en Filtros,** puede seleccionar una **fecha de inicio y** una fecha de **finalización.**

### <a name="details-table-view-for-the-encryption-report"></a>Vista de tabla de detalles para el informe de cifrado

Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:

- **Dividir por: Método de cifrado o** Dividir **por: Plantilla de cifrado:** se muestra la siguiente información:

  - **Fecha**
  - **Dirección del remitente**
  - **Plantilla de cifrado**
  - **Método de cifrado**
  - **Dirección del destinatario**
  - **Asunto**

- **Ver datos por: los 5 dominios de destinatarios principales:**

  - **Fecha**
  - **Dominio del destinatario**
  - **Recuento de mensajes**

Si hace clic **en Filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Método de cifrado
- Plantilla de cifrado

Para volver a la vista informe, haga clic **en Ver informe.**

## <a name="mailflow-status-report"></a>Informe de estado de flujo de correo

El **informe de estado de flujo de** correo contiene información sobre malware, correo no deseado, suplantación de identidad y mensajes bloqueados perimetrales. Para obtener más información, vea [el informe de estado de flujo de correo.](view-mail-flow-reports.md#mailflow-status-report)

## <a name="malware-detections-in-email-report"></a>Detecciones de malware en el informe de correo electrónico

Las detecciones de malware en el informe de correo electrónico muestran información sobre las detecciones de malware en los mensajes de correo electrónico entrantes y **salientes** (malware detectado por Exchange Online Protection o EOP). Para obtener más información acerca de la protección contra malware en EOP, vea [Protección antimalware en EOP.](anti-malware-protection.md)

 El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles solo permite 10 días.

Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione \>  Detecciones de malware en el correo **electrónico.** Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=MalwareDetections> .

![Detecciones de malware en el widget de correo electrónico en el panel informes](../../media/malware-detections-widget.png)

Puede filtrar el gráfico y la tabla de detalles haciendo clic **en Filtros** y seleccionando:

- **Fecha de inicio** y **fecha de finalización**
- **Entrada**
- **Saliente**

![Vista de informe en el informe de detección de malware en el correo electrónico](../../media/malware-detections-report-view.png)

Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:

- **Fecha**
- **Dirección del remitente**
- **Dirección del destinatario**
- **Id. de** mensaje: disponible en el **campo de encabezado Message-ID** en el encabezado del mensaje y debe ser único. Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).
- **Asunto**
- **Filename**
- **Nombre de malware**

Para volver a la vista informe, haga clic **en Ver informe.**

## <a name="mail-latency-report"></a>Informe de latencia de correo

El **informe de latencia de correo** contiene información sobre la latencia de entrega y detonación de correo experimentada en la organización. Para obtener más información, vea [El informe de latencia de correo](view-reports-for-atp.md#mail-latency-report).

## <a name="sent-and-received-email-report"></a>Informe de correo electrónico enviado y recibido

El **informe de correo electrónico enviado** y recibido contiene información sobre malware, correo no deseado, reglas de flujo de correo (también conocidas como reglas de transporte) y detecciones avanzadas de malware después de que el correo electrónico entre en el servicio. Para obtener más información, vea [El informe de correo electrónico enviado y recibido.](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>Informe de detecciones de correo no deseado

El **informe de detecciones de** correo no deseado muestra los mensajes de correo no deseado bloqueados por EOP. Los mensajes se cuentan individualmente, no por destinatario. Por ejemplo, si el mismo mensaje de correo no deseado se envió a 100 destinatarios de su organización, cuenta como un mensaje.

La vista de agregado permite el filtrado de 90 días, mientras que la tabla de detalles permite el filtrado de 10 días.

Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Detecciones \>  de correo **no deseado.** Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget Detecciones de correo no deseado en el panel Informes](../../media/spam-detections-report-widget.png)

Para obtener más información acerca de la protección contra correo no deseado, vea [Protección contra correo no deseado en EOP.](anti-spam-protection.md)

### <a name="report-view-for-the-spam-detections-report"></a>Vista de informe del informe de detecciones de correo no deseado

Los siguientes gráficos están disponibles en la vista de informe:

- **Dividir por: Acción:** se muestran los siguientes tipos de evento:

  - **Contenido de correo no deseado filtrado**
  - **Bloqueo de IP de correo no deseado**
  - **Bloqueo de sobre de correo no deseado**
  - **Filtro DBEB contra correo no deseado:** bloqueo perimetral basado en directorios (DBEB)

  Al mantener el puntero sobre un día (punto de datos) en el gráfico, puede ver cuántos elementos se bloquearon ese día, así como cómo se clasifican esos elementos.

  ![Vista de acción en el informe de detecciones de correo no deseado](../../media/spam-detections-report-action-view.png)

- **Dividir por: Dirección:** se muestran las siguientes direcciones:

  - **Entrada**
  - **Saliente**

  ![Vista de dirección en el informe de detecciones de correo no deseado](../../media/spam-detections-report-direction-view.png)

Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de tipo de evento

### <a name="details-table-view-for-the-spam-detections-report"></a>Vista de tabla de detalles del informe de detecciones de correo no deseado

Si hace clic **en Ver tabla de detalles en** cualquier vista de informe, se muestra la siguiente información:

- **Fecha**
- **Dirección del remitente**
- **Dirección del destinatario**
- **Tipo de evento**
- **Acción**
- **Asunto**

Si hace clic **en Filtros** en una tabla de detalles, puede modificar los resultados con los filtros siguientes:

- **Fecha de inicio** y **fecha de finalización**
- Valores de dirección
- Valores de tipo de evento

Para volver a la vista informe, haga clic **en Ver informe.**

## <a name="spoof-detections-report"></a>Informe de detecciones de suplantación de seguridad

El **informe de** detecciones de suplantación muestra cuántos mensajes de correo de suplantación de seguridad se detectaron y cuáles se consideraron "buenos" (correo de suplantación de seguridad realizado por motivos comerciales legítimos). Para obtener más información acerca de la suplantación de nombre, vea Protección contra la suplantación [en EOP.](anti-spoofing-protection.md)

La vista de agregado del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite diez días de filtrado.

Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Detecciones \>  **de suplantación de seguridad.** Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget Detecciones de suplantación de seguridad en el panel informes](../../media/spoof-detections-widget.png)

Al pasar el puntero sobre un día (punto de datos) en el gráfico, puede ver cuántos mensajes de correo de suplantación de voz se enviaron.

Puede filtrar el gráfico y la tabla de detalles haciendo clic en **Filtros** y seleccionando uno o varios de los siguientes valores:

- **Fecha de inicio** y **fecha de finalización**

- **Correo bueno**

- **Detectado como correo no deseado**

![Vista de informe en el informe de detecciones de suplantación de seguridad](../../media/spoof-detections-report-view.png)

Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:

- **Fecha**
- **Remitente suplantado**
- **Remitente verdadero**
- **IP del remitente**
- **Acción**
- **Recuento de mensajes**

Para volver a la vista informe, haga clic **en Ver informe.**

## <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El **informe de estado de** protección contra amenazas está disponible en EOP y Microsoft Defender para Office 365; sin embargo, los informes contienen datos diferentes. Por ejemplo, los clientes de EOP pueden ver información sobre el malware detectado en el correo electrónico, pero no información sobre archivos malintencionados detectados por ATP para [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)o Microsoft Teams.

El informe proporciona el recuento de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitio web (DIRECCIONES URL) bloqueadas por el [](atp-safe-attachments.md)motor antimalware, purga automática de cero horas [(ZAP)](zero-hour-auto-purge.md)y características de Defender para Office 365 como vínculos [seguros,](atp-safe-links.md)datos adjuntos seguros y [antiphishing.](set-up-anti-phishing-policies.md) Puede usar esta información para identificar tendencias o determinar si las directivas de la organización necesitan ajustes.

**Nota:** Es importante comprender que si se envía un mensaje a cinco destinatarios, lo contamos como cinco mensajes diferentes y no como un mensaje.

Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Estado de protección \>  contra **amenazas.** Para ir directamente al informe, abra una de las siguientes direcciones URL:

- Microsoft Defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget Estado de protección contra amenazas en el panel informes](../../media/threat-protection-status-report-widget.png)

De forma predeterminada, el gráfico muestra los datos de los últimos 7 días. Si hace clic **en Filtros,** puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba podrían estar limitadas a 30 días). La vista de tabla de detalles permite filtrar durante 30 días.

### <a name="report-view-for-the-threat-protection-status-report"></a>Vista de informe del informe de estado de protección contra amenazas

Están disponibles las siguientes vistas:

- **Ver datos por: Información general:** se muestra la siguiente información de detección:

  - **Malware de correo electrónico**
  - **Suplantación de identidad de correo electrónico**
  - **Malware de contenido**

  ![Vista general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

- **Ver datos por: Contenido \> Malware**<sup>1:</sup>se muestra la siguiente información para organizaciones de Microsoft Defender para Office 365:

  - **Motor de antimalware:** archivos malintencionados detectados en SharePoint, OneDrive y Microsoft Teams mediante la detección de virus integrada [en Microsoft 365](virus-detection-in-spo.md).
  - **Detonación de archivos:** archivos malintencionados detectados por [ATP para Sharepoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).

  ![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

- **Ver datos por: Invalidación de** mensaje: se muestra la siguiente información de motivo de invalidación:

  - **Skip local**
  - **Ip permitido**
  - **Regla de flujo de correo**
  - **Remitente permitido**
  - **Dominios permitidos**
  - **ZAP no habilitado**
  - **Carpeta de correo no deseado no habilitada**
  - **Remitente seguro de usuario**
  - **Dominio seguro de usuario**

  ![Vista de invalidación de mensajes en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-message-override-view.png)

- **Dividir por: Tecnología de detección** y **Ver datos por: Correo \> electrónico suplantación** de identidad : se muestra la siguiente información:

  - **Reputación** de la dirección URL generada por ATP <sup>1:</sup>reputación de url malintencionada generada desde Defender para detonaciones de Office 365 en otros clientes de Microsoft 365.
  - **Filtro de suplantación de** identidad avanzado: señales de suplantación de identidad basadas en el aprendizaje automático.
  - **Anti-spoof - Error de DMARC:** error de autenticación de DMARC en mensajes.
  - **Anti-spoof - dentro de la organización:** el remitente está intentando suplantación de identidad del dominio del destinatario.
  - **Anti-spoof - external domain**: Sender is trying to spoof some other domain.
  - **Suplantación de marca:** suplantación de marcas conocidas basada en remitentes.
  - **Suplantación de dominio**<sup>1:</sup>suplantación de dominios que el cliente posee o define.
  - **Reputación de la dirección URL de EOP:** reputación de la dirección URL malintencionada.
  - **Filtro de suplantación de** identidad general: señales de suplantación de identidad basadas en reglas de analista.
  - **Otros**
  - **Phish ZAP**<sup>2</sup>: Purga automática de cero horas de mensajes de suplantación de identidad.
  - **Detonación de dirección URL**<sup>1</sup>
  - **Suplantación de usuario**<sup>1:</sup>suplantación de usuarios definida por el administrador o aprendida a través de la inteligencia de buzones.

  ![Vista de tecnología de detección para correo electrónico de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Dividir por: Tecnología de detección** y **Ver datos por: Malware de \> correo** electrónico: se muestra la siguiente información:

  - **Reputación de archivo generada por ATP**<sup>1:</sup>toda la reputación de archivos malintencionados generada por Defender para detonaciones de Office 365.
  - **Motor antimalware**<sup>1:</sup>Detección de motores antimalware.
  - Bloque de tipo de archivo de directiva **antimalware:** se trata de mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.
  - **Detonación de archivos**<sup>1:</sup>Detección por datos adjuntos seguros.
  - **Reputación de archivos malintencionados**
  - **Malware ZAP**<sup>2</sup>
  - **Otros**

  ![Vista de tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Dividir por: Tipo de directiva** y Ver datos por: Correo electrónico **\> Phish** o Ver datos **por: \> Malware** de correo electrónico: Se muestra la siguiente información:

  - **Antimalware**
  - **Datos adjuntos**<sup>seguros 1</sup>
  - **Anti-phish**
  - **Contra correo no deseado**
  - **Regla de flujo de** correo (también conocida como regla de transporte)
  - **Otros**

  ![Vista de tipo de directiva para correo electrónico de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Dividir por: Estado de** entrega y Ver datos por: Correo electrónico **\> phish** o ver datos **por: \> Malware** de correo electrónico : Se muestra la siguiente información:

  - **Error en la entrega**
  - **Dropped**
  - **Reenviado**
  - **Buzón hospedado: carpeta personalizada**
  - **Buzón hospedado: elementos eliminados**
  - **Buzón hospedado: Bandeja de entrada**
  - **Buzón hospedado: correo no deseado**
  - **Servidor local: entregado**
  - **Cuarentena**

  ![Vista de estado de entrega para correo electrónico de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1 Defender</sup> solo para Office 365

<sup>2</sup> Purga automática de cero horas (ZAP) no está disponible en EOP independiente (solo funciona en buzones de Exchange Online).

Si hace clic **en Filtros,** los filtros disponibles dependen del gráfico que estuviera viendo:

- Para **ver datos por: Malware de \>** contenido, puede modificar el informe por fecha de inicio **y** **fecha** de finalización, y el valor **de** detección.

- Para **ver datos mediante: Invalidación de** mensaje, puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - **Motivo de invalidación**
  - **Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)
  - **Dominio**

- Para todas las demás vistas, puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - **Detección**
  - **Protegido por:** **ATP** o **EOP**
  - **Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)
  - **Dominio**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Vista de tabla de detalles del informe de estado de protección contra amenazas

Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: Información general:** no hay ningún botón **de tabla de detalles** de vista disponible.

- **Ver datos por: Contenido \> Malware:**

  - **Fecha**
  - **Location**
  - **Dirigida por**
  - **Nombre de malware**

  Si hace clic **en Filtros** en esta vista, puede modificar el informe por fecha de inicio **y** **fecha** de finalización, y el valor **de** detección.

- **Ver datos por: Invalidación de mensaje:**

  - **Fecha**
  - **Asunto**
  - **Remitente**
  - **Destinatarios**
  - **Detectado por**
  - **Motivo de invalidación**
  - **Origen de peligro**
  - **Tags**

  Si hace clic **en Filtros** en esta vista, puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - **Motivo de invalidación**
  - **Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)
  - **Dominio**
  - **Destinatarios** (Tenga en cuenta que esta propiedad que se puede filtrar solo está disponible en la vista de tabla de detalles)

- Todos los demás gráficos:

  - **Fecha**
  - **Asunto**
  - **Remitente**
  - **Destinatarios**
  - **Detectado por**
  - **Estado de entrega**
  - **Origen de peligro**
  - **Tags**

  Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:

  - **Fecha de inicio** y **fecha de finalización**
  - **Detección**
  - **Protegido por**: **Defender para Office 365** o **EOP**
  - **Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad). Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)
  - **Dominio**
  - **Destinatarios** (Tenga en cuenta que esta propiedad que se puede filtrar solo está disponible en la vista de tabla de detalles)

## <a name="top-malware-report"></a>Informe de malware principal

El **informe de malware** superior muestra los distintos tipos de malware detectados por la protección [antimalware en EOP.](anti-malware-protection.md)

Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de \>  informes y seleccione **Malware superior.** Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=TopMalware> .

![Widget De malware superior en el panel informes](../../media/top-malware-report-widget.png)

Al pasar el puntero sobre una plataforma en el gráfico circular, puede ver el nombre de un tipo de malware y cuántos mensajes se detectaron como que tienen ese malware.

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:

- **Malware principal**
- **Count**

Si hace clic **en Filtros en** la vista informe o en la vista Tabla de detalles, puede especificar un intervalo de fechas con fecha **de** inicio y fecha **de finalización.**

## <a name="url-threat-protection-report"></a>Informe de protección contra amenazas de URL

El **informe de protección contra amenazas de** url está disponible en Microsoft Defender para Office 365. Para obtener más información, vea el [informe de protección contra amenazas de url.](view-reports-for-atp.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Informe de mensajes notificados por el usuario

El  informe de mensajes notificados por el usuario muestra información sobre los mensajes de [](enable-the-report-message-add-in.md) correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad o correo electrónico bueno mediante el complemento Informar de mensaje o el complemento Detección de suplantación de identidad de [informes.](enable-the-report-phish-add-in.md)

Los detalles están disponibles para cada mensaje, incluido el motivo de la entrega, como una excepción de directiva de correo no deseado o una regla de flujo de correo configurada para su organización. Para ver detalles, seleccione un elemento en la lista de  informes de usuario y, a continuación, vea la información en las pestañas **Resumen** y Detalles.

![El User-Reported mensajes de correo electrónico muestra los mensajes que los usuarios etiquetan como correo no deseado, no como correo no deseado o intentos de suplantación de identidad.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Para ver este informe, en el Centro de & [cumplimiento,](https://protection.office.com)realice una de las siguientes acciones:

- Vaya a Mensajes **del panel de administración** \> **de** \> **amenazas notificados por el usuario.**

- Vaya a **Administración de amenazas** \> **Revisar** \> **mensajes notificados por el usuario.**

![En el Centro de seguridad & cumplimiento, elija Administración de amenazas \> Revisar \> mensajes notificados por el usuario](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Para que el informe de mensajes notificados  por el usuario funcione correctamente, el registro de auditoría debe estar activado para su entorno de Office 365. Esto lo suele hacer alguien que tiene el rol Registros de auditoría asignado en Exchange Online. Para obtener más información, vea Activar o desactivar la búsqueda del registro de auditoría [de Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos se necesitan para ver estos informes?

Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

**Nota:** agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & Cumplimiento y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="what-if-the-reports-arent-showing-data"></a>¿Qué ocurre si los informes no muestran datos?

Si no ve datos en los informes, compruebe que las directivas están configuradas correctamente. Para obtener más información, vea [Proteger contra amenazas.](protect-against-threats.md)

## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado y antimalware en EOP](anti-spam-and-anti-malware-protection.md)

[Informes inteligentes y reportes en el Centro de seguridad y cumplimiento](reports-and-insights-in-security-and-compliance.md)

[Ver informes de flujo de correo en el Centro de & cumplimiento](view-mail-flow-reports.md)

[Ver informes de Defender para Office 365](view-reports-for-atp.md)
