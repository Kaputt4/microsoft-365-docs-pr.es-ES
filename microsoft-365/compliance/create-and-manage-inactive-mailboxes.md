---
title: Crear y administrar buzones inactivos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: Conserve el contenido de los buzones eliminados mediante la característica de buzones inactivos en Microsoft 365.
ms.openlocfilehash: acd00fedcf0949b7d0c9f85c17039105e9b34821
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100809"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Crear y administrar buzones inactivos

Microsoft 365 permite conservar el contenido de los buzones eliminados. Esta característica se denomina [buzones inactivos](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. Un buzón se vuelve inactivo cuando se aplica una retención por juicio o una directiva de retención (creada en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón antes de eliminar la cuenta de usuario correspondiente. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. Esto permite a los administradores, responsables de cumplimiento y administradores de registros usar la búsqueda de contenido para buscar y exportar el contenido de un buzón inactivo. Los buzones inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de su organización ni en otras listas.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo de diferentes maneras para conservar el contenido del buzón, estamos anunciando la retirada de las In-Place en el centro Exchange administración. Esto significa que debe usar las directivas de retención y retención por juicio para crear un buzón inactivo. A partir del 1 de julio de 2020 no podrá crear nuevas retenciones In-Place en Exchange Online. Pero aún podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo. Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de la retención. Solo podrá eliminar un buzón inactivo quitando la In-Place espera. Los buzones inactivos existentes que están en In-Place conservación se conservarán hasta que se quite la retención. Para obtener más información acerca de la retirada de In-Place, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>Preparativos antes de crear un buzón inactivo

- Para que un buzón esté inactivo, debe tener asignada una licencia del Plan 2 de Exchange Online para que se pueda aplicar una retención por juicio o una directiva de retención al buzón antes de eliminarla. Exchange Online Las licencias del plan 2 forman parte de una Office 365 Enterprise de E3 y E5. Si a un buzón se le asigna una licencia de plan 1 o Quiosco de Exchange Online de Exchange Online (que forman parte de una suscripción Office 365 E1 y F1 respectivamente), tendría que asignarle una licencia de Archivado de Exchange Online independiente para que se pueda aplicar una retención al buzón antes de eliminarla. Para obtener más información, vea [Archivado de Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).

- Las licencias asociadas con el buzón de Exchange Online eliminado estarán disponibles después de eliminar la cuenta de usuario correspondiente. A [continuación, puede asignar esas licencias a otro usuario](../admin/manage/assign-licenses-to-users.md).

- Si una retención por juicio o una directiva de retención (configurada para retener o eliminar contenido) no se aplica a un buzón antes de eliminarla, el contenido del buzón no se conservará ni se podrá detectar. Aun así, el buzón eliminado se puede recuperar en un plazo de 30 días a partir de su eliminación, pero el buzón junto con su contenido se eliminará permanentemente transcurrido dicho plazo, si no se recupera.

- Para obtener más información acerca de la retención por juicio, vea [Retención por juicio](/exchange/security-and-compliance/in-place-and-litigation-holds). Para obtener más información acerca de las directivas de retención, vea [Learn about retention policies and retention labels](retention.md).
  
## <a name="create-an-inactive-mailbox"></a>Crear un buzón inactivo

Hacer inactivo un buzón implica dos pasos: 1) colocar el buzón en retención por juicio o aplicar una directiva de retención y 2) eliminar el buzón o la cuenta de usuario correspondiente. Tras pasar el buzón a inactivo, su contenido se conservará hasta que se quite la retención o la directiva de retención.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Paso 1: Colocar un buzón en retención por juicio o aplicar una directiva de retención

Al colocar un buzón en retención por juicio o aplicar una directiva de retención (que está configurada para retener o conservar y, a continuación, eliminar contenido), se conserva el contenido del buzón antes de eliminarlo. Ambos tipos de retenciones conservarán todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de elementos modificados. Los elementos eliminados y modificados se conservan en el buzón inactivo durante un período de tiempo especificado o hasta que se elimine permanentemente el buzón inactivo mediante la eliminación de la retención o la directiva de retención aplicada a los buzones inactivos.
  
Si ya se ha colocado una retención en un buzón de correo o si ya se ha aplicado una directiva de retención a un buzón, lo único que tiene que hacer es eliminar la cuenta de usuario correspondiente, como se explica en el paso 2.
  
Para obtener procedimientos paso a paso para colocar un buzón en retención por juicio o aplicar una directiva de retención, vea:
  
- [Poner un buzón en retención por juicio](create-a-litigation-hold.md)

- [Más información sobre las directivas y las etiquetas de retención](retention.md)

> [!NOTE]
> Para las directivas de retención y retención por juicio, puede crear una retención indefinida o en una retención basada en tiempo. En una retención indefinida, el contenido del buzón inactivo se conservará siempre, hasta que se elimine la retención o hasta que se cambie la duración de la retención. Después de quitar la directiva de retención o retención (suponiendo que el buzón se eliminó hace más de 183 días), el buzón inactivo se marcará para su eliminación permanente y el contenido del buzón ya no se conservará ni se podrá detectar. En una directiva de retención o retención basada en tiempo, especifique la duración de la retención. Esta duración se establece para cada elemento, y se calcula a partir de la fecha en que un elemento de buzón se ha recibido o creado. Una vez que ha expirado la retención para un elemento de buzón, y ese elemento se ha movido a la carpeta Elementos recuperables del buzón inactivo o se encuentra en ella, el elemento se elimina permanentemente (purga) del buzón inactivo. 
  
### <a name="step-2-delete-the-mailbox"></a>Paso 2: Eliminar el buzón.

Después de colocar el buzón en espera o de aplicar una directiva de retención, el siguiente paso es eliminar el buzón. La mejor manera de eliminar un buzón es eliminar la cuenta de usuario correspondiente en el centro de administración Microsoft 365 usuario. Para obtener información sobre cómo eliminar cuentas de usuario, vea [Eliminar un usuario de la organización.](../admin/add-users/delete-a-user.md)
  
> [!NOTE]
> También puede eliminar el buzón mediante el cmdlet **Remove-Mailbox** en Exchange Online PowerShell. Para obtener más información, vea [Eliminar o restaurar buzones](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)de usuario en Exchange Online . 
  
## <a name="view-a-list-of-inactive-mailboxes"></a>Ver una lista de buzones inactivos

Para ver una lista de los buzones inactivos de la organización:

1. Vaya a <https://compliance.microsoft.com> e inicie sesión con las credenciales de una cuenta de administrador de su organización.

2. En el panel de navegación izquierdo del centro de Microsoft 365 cumplimiento, haga clic en Mostrar todo y, a continuación, haga clic en Gobierno de **> retención.**

   ![Haga clic en el botón Buzón inactivo de la página Retención](../media/MCCInactiveMailboxes1.png)

3. En la **página Retención,** haga clic **en Buzón inactivo** para mostrar una lista de buzones inactivos.

4. Seleccione un buzón inactivo para mostrar una página desplegable con información sobre el buzón inactivo.

   ![La página desplegable muestra detalles sobre el buzón inactivo](../media/MCCInactiveMailboxes2.png)  

Puede hacer clic en Exportar icono de resultados de búsqueda Exportar para ver o descargar un archivo CSV que contenga información adicional sobre los buzones inactivos ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)  de la organización.

Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar la lista de buzones inactivos.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

También puede ejecutar el siguiente comando para exportar la lista de buzones inactivos y otra información a un archivo CSV. En este ejemplo, el archivo CSV se crea en el directorio actual.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> Es posible que un buzón inactivo tenga la misma dirección SMTP que un buzón de usuario activo. En este caso, el valor de la **propiedad DistinguishedName** o **ExchangeGuid** se puede usar para identificar de forma única un buzón inactivo.
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Buscar y exportar el contenido de un buzón inactivo

Puede tener acceso al contenido del buzón inactivo mediante la herramienta búsqueda de contenido en el Centro de seguridad & cumplimiento. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de la búsqueda](export-search-results.md)

A continuación, se detallan algunos aspectos que se deben tener en cuenta al buscar buzones inactivos:
  
- Si una búsqueda de contenido incluye un buzón de usuario y ese buzón está inactivo, la búsqueda de contenido seguirá buscando en el buzón inactivo cuando vuelva a ejecutar la búsqueda después de que esté inactivo.

- En algunos casos, un usuario puede tener un buzón activo y un buzón inactivo que tenga la misma dirección SMTP. En este caso, solo se buscará el buzón específico que seleccione como ubicación para una búsqueda de contenido. En otras palabras, si agrega el buzón de un usuario a una búsqueda, no puede suponer que se buscarán sus buzones activos e inactivos; solo se buscará el buzón que agregue explícitamente a la búsqueda.

- Le recomendamos que no tenga un buzón activo y un buzón inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP que está asignada actualmente a un buzón inactivo, se recomienda recuperar el buzón inactivo o restaurar el contenido de un buzón inactivo en un buzón activo (o el archivo de un buzón activo) y, a continuación, eliminar el buzón inactivo.

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Después de que un buzón esté inactivo, puede cambiar la duración de la retención o la directiva de retención aplicada al buzón inactivo. Para ver los procedimientos paso a paso, vea [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Si un antiguo empleado vuelve a la organización o si se contrata a un nuevo empleado para que asuma las responsabilidades del empleado anterior, puede recuperar el contenido del buzón inactivo. Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. Para obtener procedimientos paso a paso y obtener más información acerca de cómo recuperar un buzón inactivo, vea Recuperar un buzón inactivo [en Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar el contenido de un buzón inactivo en otro buzón de correo

Si otro empleado asume las responsabilidades de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Todavía se pueden realizar búsquedas en el buzón inactivo mediante la exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón, o se puede recuperar o eliminar en una fecha posterior. Para ver los procedimientos paso a paso, vea [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

Si ya no necesita conservar el contenido de un buzón inactivo, puede eliminar permanentemente el buzón inactivo quitando la retención o quitando la directiva de retención aplicada al buzón inactivo. El buzón se conservará durante 183 días después de quitar la directiva de retención o retención. Después de 183 días, el buzón se marcará para su eliminación permanente y el buzón no se podrá recuperar. Si el buzón inactivo se eliminó en los últimos 183 días, aún puede recuperarlo. Para obtener procedimientos paso a paso para quitar una suspensión o una directiva de retención para eliminar permanentemente un buzón inactivo, vea [Delete an inactive mailbox](delete-an-inactive-mailbox.md).
