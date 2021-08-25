---
title: Alertas de servicio de uso de buzones
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Use alertas de servicio de uso de buzones para supervisar los buzones en espera que están alcanzando su cuota de buzón.
ms.openlocfilehash: f6ce0ad5d7f4affd5d0f4a108be0f0fbebe54766
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508807"
---
# <a name="service-alerts-for-mailbox-utilization-in-exchange-online-monitoring"></a>Alertas de servicio para el uso de buzones en Exchange Online supervisión

Hemos publicado una nueva alerta de servicio Exchange Online que le informa de los buzones que están en espera y que están en riesgo de alcanzar o exceder su cuota. Estas alertas de servicio proporcionan visibilidad del número de buzones de la organización que pueden requerir intervención del administrador.

Estas alertas de servicio se muestran en el Centro de administración de Microsoft 365. Para ver estas alertas de servicio, vaya a **Health** Service health Exchange Online y, a  >    >  **continuación,** haga clic en la pestaña Problemas **activos.** Este es un ejemplo de una alerta de servicio de uso de buzones.

![Alerta del servicio de uso de buzones](../media/MailboxUtilizationServiceAlert.png)

Para mostrar una lista de buzones que se acercan a su cuota de almacenamiento (denominado informe de uso del *buzón),* haga clic en el vínculo resaltado en la siguiente captura de pantalla. Este vínculo se muestra en la alerta de servicio.

![Vínculo al informe de uso del buzón](../media/LinkToMailboxUsageReport.png)

Como alternativa, la dirección URL directa al informe de uso del buzón es <https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage/MailboxUsage> .

## <a name="what-do-these-service-alerts-indicate"></a>¿Qué indican estas alertas de servicio?

Las alertas de servicio para el uso del buzón informan a los administradores sobre los buzones en espera que se acercan a la cuota de almacenamiento del buzón. El tipo de retenciones que se pueden colocar en los buzones incluyen retenciones por juicio, retención de exhibición de documentos electrónicos y directivas de retención Microsoft 365 (que están configuradas para retener datos). Cuando un buzón está en espera, los usuarios (o procesos automatizados) no pueden quitar permanentemente los datos de su buzón. En su lugar, los administradores deben configurar directivas de retención de MRM en Exchange Online (en línea con las directivas de cumplimiento de su organización relacionadas con la retención de datos) para mover datos del buzón principal de un usuario a su buzón de archivo. Si no es así y un buzón de correo en una retención [](../compliance/enable-unlimited-archiving.md) alcanza un estado crítico o de advertencia, los [administradores](../compliance/enable-archive-mailboxes.md) tienen que habilitar buzones de archivo y habilitar el archivado de expansión automática y, a continuación, asegurarse de que el período de retención de la directiva de archivo asignada al buzón (que mueve el correo electrónico del buzón principal al buzón de archivo) sea lo suficientemente corto. Si no se hace nada para resolver los problemas de cuota identificados por las alertas del servicio de uso de buzones de correo, es posible que los usuarios no puedan enviar ni recibir mensajes de correo electrónico ni invitaciones a reuniones.

Una alerta de servicio para el uso de buzones contiene tablas sobre el número de buzones que se acercan a su cuota. En las secciones siguientes se describe la información de estas tablas y la acción que los administradores pueden realizar para ayudar a garantizar que estos buzones no superen su cuota.

> [!NOTE]
> Las alertas de servicio contienen descripciones de las propiedades de cuota de buzón que aparecen en las columnas de las tablas descritas en las secciones siguientes.

### <a name="mailboxes-on-hold-without-an-archive"></a>Buzones en espera sin archivo

En la tabla siguiente se muestra el número de buzones en espera que se acercan a su cuota pero que no tienen habilitado un buzón de archivo. Cada columna de la tabla identifica la cuota específica y el número de buzones que se acercan a esa cuota.

| # Mailboxes ProhibitSendReceiveQuota (Advertencia)| # Mailboxes ProhibitSendReceiveQuota (Critical)** |# Mailboxes RecoverableItemsQuota (Advertencia)|# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 2             | 2             | 1                 | 0               |
||||

La acción que los administradores pueden realizar para estos buzones es habilitar el buzón de archivo y asegurarse de que una directiva de archivo de MRM (que es una directiva de retención de MRM en Exchange Online que mueve elementos al buzón de archivo) se aplica al buzón de correo para que los elementos se muevan al buzón de archivo. Para obtener más información, vea [Set up an archive and deletion policy for mailboxes](../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).

Después de habilitar un buzón de archivo, se recomienda aumentar la cuota de la carpeta Elementos recuperables. Esto ayuda a evitar que se supere la cuota de la carpeta Elementos recuperables para los buzones que están en espera. Para obtener más información, vea Aumentar la cuota de elementos [recuperables para buzones en espera.](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)

### <a name="mailboxes-on-hold-with-an-archive"></a>Buzones en espera con un archivo

En la tabla siguiente se muestra el número de buzones en espera que se acercan a su cuota y tienen habilitado un buzón de archivo.

|# Mailboxes ProhibitSendReceiveQuota (Advertencia) |# Mailboxes ProhibitSendReceiveQuota (Critical) |# Mailboxes RecoverableItemsQuota (Advertencia) |# Mailboxes RecoverableItemsQuota (Critical)** |
|:--------------|:--------------|:------------------|:--------------- |
| 1             | 1             | 6                  | 0               |
||||

La acción que los administradores pueden realizar para estos buzones es aumentar la cuota de la carpeta Elementos recuperables. Para obtener más información, vea Aumentar la cuota de elementos [recuperables para buzones en espera.](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)

Los administradores también deben asegurarse de que una directiva de archivo mrm que mueve elementos al buzón de archivo también se aplica a los buzones y que el período de retención de la directiva de archivo es lo suficientemente corto para que los elementos no se conserven demasiado tiempo en el buzón principal antes de que se muevan al archivo.

> [!NOTE]
> Las directivas de archivo de MRM también mueven elementos de la carpeta Elementos recuperables del buzón principal a la carpeta Elementos recuperables del buzón de archivo correspondiente. Esta funcionalidad ayuda a evitar que el buzón supere la cuota de la cuota elementos recuperables.

### <a name="mrm-retention-policies-in-your-organization"></a>Directivas de retención de MRM en la organización

Las alertas de servicio para el uso de buzones también pueden contener una tabla con información sobre las directivas de retención de MRM en su organización y si los buzones que son una directiva de retención tienen un buzón de archivo. Para obtener más información acerca de las directivas de retención, vea [Retention tags and retention policies in Exchange Online](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies).

| RetentionPolicyGuid | MailboxType | HasMoveDumpsterToArchiveTag | HasMovePrimaryToArchiveTag | HasPersonalArchiveTag |  Buzones |
|:--------------|:--------------|:---------------|:---------------|:---------------|:--------------- |
| 6c041498-1611-5011-a058-1156ce60890c | PrimaryWithArchive | Verdadero | False | True | 398 |
| 6c041498-1611-5011-a058-1156ce60890c | Principal | Verdadero | False | True | 10 |
| 749ceecc-d49d-4000-a9d5-594dbaea1e56 | PrimaryWithArchive | False | True | False | 7  |
| 269f6a85-1234-4648-8cde-59bbc7bc67d0 | PrimaryWithArchive | True | True | True | 1 |
| 13fb778d-e1cb-4c44-5768-ad4282906c1f | PrimaryWithArchive | True | True  | False | 1 |
|||||||

En la siguiente lista se describe cada columna de la tabla anterior.

- **RetentionPolicyGuid:** EL GUID de la directiva de retención asignada a los buzones de la organización. En el ejemplo anterior, hay dos filas independientes para la misma directiva de retención. La primera fila indica el número de buzones con un archivo asignado a la directiva. La segunda fila indica el número de buzones sin un archivo al que se asigna la misma directiva.

   Para obtener más información acerca de la directiva de retención que se muestra en esta columna, ejecute el siguiente comando [en Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-RetentionPolicy <GUID> | FL
   ```

   El valor de la **propiedad Name** es el nombre de la directiva de retención que se muestra en la página **Directivas** de retención en el centro Exchange administración.

- **MailboxType:** especifica el tipo de buzones a los que está asignada la directiva. Los valores *incluyen Primary* (buzones sin archivo) o *PrimaryWithArchive* (buzones con un archivo). Si el valor de esta columna es *Primario*, debe habilitar  el archivo para los buzones (la columna Buzón indica el número de estos buzones) a los que se asigna la directiva. De lo contrario, una directiva de archivo o una etiqueta de archivo personal no funcionarán porque no hay un archivo al que mover elementos.

- **HasMoveDumpsterToArchiveTag:** indica que la directiva de retención incluye una etiqueta de retención que mueve elementos de la carpeta Elementos recuperables (también denominado contenedor *de* volcado de datos) en el buzón principal a la carpeta Elementos recuperables del archivo. Este tipo de etiqueta de retención la establece un administrador. Si el período de retención de la etiqueta elementos recuperables es demasiado largo, reducir el período de retención debería ayudar a evitar que los buzones se acerquen a la cuota de la carpeta Elementos recuperables. Por ejemplo, si el período de retención se establece en 30 días, reducirlo a tres o cinco días puede resultar de ayuda.  Para obtener más información, vea Aumentar la cuota de elementos [recuperables para buzones en espera.](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)

- **HasMovePrimaryToArchiveTag:** indica si hay una etiqueta de retención predeterminada de "mover a archivo" (también denominada directiva de *archivo)* incluida en la directiva de retención. En este caso, los mensajes se mueven de las carpetas regulares del buzón principal al buzón de archivo. Este tipo de etiqueta de retención la establece un administrador. De nuevo, si el período de retención de esta etiqueta es demasiado corto, es posible que los usuarios tengan problemas para alcanzar continuamente la cuota de su buzón principal. Reducir el período de retención de una directiva de archivo puede ayudar a solucionar este problema.

- **HasPersonalArchiveTag:** indica si la directiva de retención incluye una etiqueta personal "mover al archivo". Si la directiva de retención incluye una etiqueta personal de "mover al archivo", los usuarios pueden aplicar esta etiqueta a las carpetas y mensajes de su buzón para mover elementos al archivo. Los usuarios también pueden configurar una regla de bandeja de entrada para mover mensajes a una carpeta con esta etiqueta aplicada. En ambos casos, esto puede ayudar a mover elementos al archivo para evitar alcanzar la cuota de su buzón principal.

- **Buzones:** indica el número de buzones (aquellos con o sin un archivo, que se indica en la columna **MailboxType)** a los que se asigna la directiva de retención.

## <a name="how-often-will-i-see-these-service-alerts"></a>¿Con qué frecuencia voy a ver estas alertas de servicio?

Si no toma medidas para resolver los problemas de cuota, puede esperar ver este tipo de alerta de servicio cada cuatro días. Las alertas de servicio posteriores pueden contener recuentos de buzones más altos para otros buzones que se acercan a su cuota. Si toma medidas para resolver problemas de cuota, esta alerta de servicio solo se producirá cuando se identifique otro buzón con problemas de cuota.

## <a name="more-information"></a>Más información

- Para obtener información sobre cómo solucionar y solucionar problemas de buzones de archivo, [vea Microsoft 365 solución de problemas de cumplimiento.](/office365/troubleshoot/microsoft-365-compliance-welcome)

- Para obtener instrucciones sobre cómo identificar las retenciones colocadas en un buzón, vea [How to identify the type of hold placed on a mailbox](../compliance/identify-a-hold-on-an-exchange-online-mailbox.md).
