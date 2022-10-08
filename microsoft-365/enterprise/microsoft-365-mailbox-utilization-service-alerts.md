---
title: Alertas del servicio de uso de buzones
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
f1.keywords:
- NOCSH
description: Use avisos de servicio de uso de buzones para supervisar los buzones en espera que alcanzan su cuota de buzón.
ms.openlocfilehash: 35bff697727a77abc27555898e48106bc7070142
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185411"
---
# <a name="service-advisories-for-mailbox-utilization-in-exchange-online-monitoring"></a>Avisos de servicio para el uso del buzón de correo en la supervisión de Exchange Online

Hemos publicado un nuevo aviso de servicio de Exchange Online que le informa de los buzones que están en espera que están en riesgo de alcanzar o superar su cuota. Estos avisos de servicio proporcionan visibilidad del número de buzones de correo de la organización que pueden requerir la intervención del administrador.

Estos avisos de servicio se muestran en el Centro de administración de Microsoft 365. Para ver estos avisos de servicio, vaya a **Estado** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**Estado del servicio**</a> >  **Exchange Online** y, a continuación, haga clic en la pestaña **Problemas activos**. Este es un ejemplo de un aviso de servicio de uso de buzones de correo.

:::image type="content" alt-text="Alerta de servicio de uso del buzón de correo." source="../media/MailboxUtilizationServiceAlert.png" lightbox="../media/MailboxUtilizationServiceAlert.png":::

Para mostrar una lista de buzones que están cerca de su cuota de almacenamiento, seleccione el vínculo resaltado en la captura de pantalla siguiente para acceder al informe de uso del buzón. Este vínculo se muestra en el aviso de servicio.

:::image type="content" alt-text="Vínculo al informe de uso del buzón de correo." source="../media/LinkToMailboxUsageReport.png" lightbox="../media/LinkToMailboxUsageReport.png":::

Como alternativa, la dirección URL directa al informe de uso del buzón es <https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage/MailboxUsage>.

> [!NOTE]
> La información del informe de uso del buzón podría estar 24 horas detrás de la alerta de aviso del servicio de uso del buzón.

## <a name="what-do-these-service-advisories-indicate"></a>¿Qué indican estos avisos de servicio?

Los avisos de servicio para el uso del buzón de correo informan a los administradores sobre los buzones en espera que se acercan a la cuota de almacenamiento del buzón. El tipo de retenciones que se pueden colocar en los buzones incluye retenciones por litigio, suspensión de exhibición de documentos electrónicos y directivas de retención de Microsoft 365 (que están configuradas para conservar datos). Cuando un buzón está en espera, los usuarios (o los procesos automatizados) no pueden quitar permanentemente los datos de su buzón. En su lugar, los administradores deben configurar directivas de retención de MRM en Exchange Online (en línea con las directivas de cumplimiento de su organización relacionadas con la retención de datos) para mover datos del buzón principal de un usuario a su buzón de archivo. Si no es así y un buzón en suspensión alcanza un estado crítico o de advertencia, los administradores tienen que [habilitar los buzones de archivo](../compliance/enable-archive-mailboxes.md) y [habilitar el archivado de expansión automática](../compliance/enable-autoexpanding-archiving.md) y, a continuación, asegurarse de que el período de retención de la directiva de archivo asignada al buzón (que mueve el correo electrónico del buzón principal al buzón de archivo) es lo suficientemente corto. Si no se hace nada para resolver los problemas de cuota identificados por el aviso del servicio de uso del buzón de correo, es posible que los usuarios no puedan enviar o recibir mensajes de correo electrónico o invitaciones a reuniones.

Un aviso de servicio para el uso de buzones contiene tablas sobre el número de buzones que están cerca de su cuota. En las secciones siguientes se describe la información de estas tablas y las acciones que pueden realizar los administradores para ayudar a garantizar que estos buzones no superen su cuota.

> [!NOTE]
> Los avisos de servicio contienen descripciones de las propiedades de cuota de buzón que aparecen en las columnas de las tablas descritas en las secciones siguientes.

### <a name="mailboxes-on-hold-without-an-archive"></a>Buzones en espera sin un archivo

En la tabla siguiente se muestra el número de buzones en espera que están cerca de su cuota pero no tienen habilitado un buzón de archivo. Cada columna de la tabla identifica la cuota específica y el número de buzones que se acercan a esa cuota.

| # Mailboxes ProhibitSendReceiveQuota (advertencia)| # Mailboxes ProhibitSendReceiveQuota (Critical)** |# Buzones RecoverableItemsQuota (advertencia)|# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 2             | 2             | 1                 | 0               |
||||

La acción que los administradores pueden realizar para estos buzones es habilitar el buzón de archivo y asegurarse de que se aplica una directiva de archivo MRM (que es una directiva de retención de MRM en Exchange Online que mueve elementos al buzón de archivo) al buzón de correo para que los elementos se muevan al buzón de archivo. Para obtener más información, vea [Configurar una directiva de archivo y eliminación para buzones de correo](../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).

Después de habilitar un buzón de archivo, se recomienda que considere la posibilidad de aumentar la cuota para la carpeta Elementos recuperables. Esto ayuda a evitar que se supere la cuota de la carpeta Elementos recuperables para los buzones que se colocan en espera. Para obtener más información, vea [Aumentar la cuota de elementos recuperables para buzones en espera](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md).

### <a name="mailboxes-on-hold-with-an-archive"></a>Buzones en espera con un archivo

En la tabla siguiente se muestra el número de buzones en espera que están cerca de su cuota y tienen habilitado un buzón de archivo.

|# Mailboxes ProhibitSendReceiveQuota (advertencia) |# Buzones ProhibitSendReceiveQuota (crítico) |# Buzones RecoverableItemsQuota (advertencia) |# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 1             | 1             | 6                 | 0               |
||||

La acción que los administradores pueden realizar para estos buzones es aumentar la cuota de la carpeta Elementos recuperables. Para obtener más información, vea [Aumentar la cuota de elementos recuperables para buzones en espera](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md).

Los administradores también deben asegurarse de que una directiva de archivo de MRM que mueve elementos al buzón de archivo también se aplica a los buzones de correo y que el período de retención de la directiva de archivo es lo suficientemente corto como para que los elementos no se conserven demasiado tiempo en el buzón principal antes de que se muevan al archivo.

> [!NOTE]
> Las directivas de archivo de MRM también mueven elementos de la carpeta Elementos recuperables del buzón principal a la carpeta Elementos recuperables del buzón de archivo correspondiente. Esta funcionalidad ayuda a evitar que el buzón supere la cuota de la cuota Elementos recuperables.

### <a name="mrm-retention-policies-in-your-organization"></a>Directivas de retención de MRM en su organización

Los avisos de servicio para el uso del buzón de correo también pueden contener una tabla con información sobre las directivas de retención de MRM en su organización y si los buzones que son una directiva de retención tienen o no un buzón de archivo. Para obtener más información sobre las [directivas de retención, consulte Etiquetas de retención y directivas de retención en Exchange Online](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies).

| RetentionPolicyGuid | MailboxType | HasMoveDumpsterToArchiveTag | HasMovePrimaryToArchiveTag | HasPersonalArchiveTag |  Buzones |
|:--------------|:--------------|:---------------|:---------------|:---------------|:--------------- |
| 6c041498-1611-5011-a058-1156ce60890c | PrimaryWithArchive | True | False | Verdadero | 398 |
| 6c041498-1611-5011-a058-1156ce60890c | Principal | True | False | Verdadero | 10 |
| 749ceecc-d49d-4000-a9d5-594dbaea1e56 | PrimaryWithArchive | Falso | True | False | 7  |
| 269f6a85-1234-4648-8cde-59bbc7bc67d0 | PrimaryWithArchive | True | True | True | 1 |
| 13fb778d-e1cb-4c44-5768-ad4282906c1f | PrimaryWithArchive | True | True  | False | 1 |
|||||||

En la lista siguiente se describe cada columna de la tabla anterior.

- **RetentionPolicyGuid**: el GUID de la directiva de retención asignada a los buzones de su organización. En el ejemplo anterior, hay dos filas independientes para la misma directiva de retención. La primera fila indica el número de buzones con un archivo al que se asigna la directiva. La segunda fila indica el número de buzones sin un archivo al que se asigna la misma directiva.

   Para obtener más información sobre la directiva de retención que aparece en esta columna, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-RetentionPolicy <GUID> | FL
   ```

   El valor de la propiedad **Name** es el nombre de la directiva de retención que se muestra en la página **Directivas de retención** del <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

- **MailboxType**: especifica a qué tipo de buzones se asigna la directiva. Los valores incluyen *Principal* (buzones sin archivo) o *PrimaryWithArchive* (buzones con un archivo). Si el valor de esta columna es *Principal*, debe habilitar el archivo para los buzones (la columna **Buzón** indica el número de estos buzones) a los que se asigna la directiva. De lo contrario, una directiva de archivo o una etiqueta de archivo personal no funcionarán porque no hay un archivo al que mover elementos.

- **HasMoveDumpsterToArchiveTag**: indica que la directiva de retención incluye una etiqueta de retención que mueve elementos de la carpeta Elementos recuperables (también denominado *contenedor de memoria*) del buzón principal a la carpeta Elementos recuperables del archivo. Un administrador establece este tipo de etiqueta de retención. Si el período de retención de la etiqueta de elementos recuperables es demasiado largo, reducir el período de retención debe ayudar a evitar que los buzones de correo se acerquen a la cuota de la carpeta Elementos recuperables. Por ejemplo, si el período de retención se establece en 30 días, reducirlo a tres o cinco días puede ayudar.  Para obtener más información, vea [Aumentar la cuota de elementos recuperables para buzones en espera](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md).

- **HasMovePrimaryToArchiveTag**: indica si hay una etiqueta de retención predeterminada "mover al archivo" (también denominada *directiva de archivo*) incluida en la directiva de retención. En este caso, los mensajes se moverán de las carpetas normales del buzón principal al buzón de archivo. Un administrador establece este tipo de etiqueta de retención. De nuevo, si el período de retención de esta etiqueta es demasiado corto, los usuarios pueden tener problemas para alcanzar continuamente la cuota de su buzón principal. Reducir el período de retención de una directiva de archivo puede ayudar a resolver este problema.

- **HasPersonalArchiveTag**: indica si la directiva de retención incluye una etiqueta personal de "mover al archivo". Si la directiva de retención incluye una etiqueta personal de "mover al archivo", los usuarios pueden aplicar esta etiqueta a carpetas y mensajes de su buzón para mover elementos al archivo. Los usuarios también pueden configurar una regla de bandeja de entrada para mover mensajes a una carpeta con esta etiqueta aplicada. En ambos casos, esto puede ayudar a mover elementos al archivo para evitar alcanzar la cuota de su buzón principal.

- **Buzones**: indica el número de buzones (aquellos con o sin un archivo, que se indica en la columna **MailboxType** ) a los que se asigna la directiva de retención.

## <a name="how-often-will-i-see-these-service-advisories"></a>¿Con qué frecuencia veré estos avisos de servicio?

Si no toma medidas para resolver los problemas de cuota, puede esperar ver este tipo de aviso de servicio cada siete días. Los avisos de servicio posteriores pueden contener recuentos de buzones más altos para otros buzones que están cerca de su cuota. Si toma medidas para resolver problemas de cuota, este aviso de servicio solo se producirá cuando se identifique otro buzón con problemas de cuota.

## <a name="more-information"></a>Más información

- Para obtener información sobre la solución de problemas y la resolución de problemas de buzón de archivo, consulte [Solución de problemas de Microsoft Purview](/office365/troubleshoot/microsoft-365-compliance-welcome).

- Para obtener instrucciones sobre cómo identificar las retenciones colocadas en un buzón de correo, consulte [Cómo identificar el tipo de suspensión colocada en un buzón](../compliance/identify-a-hold-on-an-exchange-online-mailbox.md).
