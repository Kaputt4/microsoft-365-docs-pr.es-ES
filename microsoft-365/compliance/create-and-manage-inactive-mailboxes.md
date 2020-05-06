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
description: Puede crear un buzón inactivo en Microsoft 365 aplicando una directiva de retención o retención al buzón y, a continuación, eliminando la cuenta de usuario correspondiente. Los elementos de un buzón inactivo se conservan durante toda la Directiva de retención o retención que se le aplicó antes de que se desactivara. Para eliminar de forma permanente un buzón inactivo, solo tiene que quitar la Directiva de retención o retención.
ms.openlocfilehash: 6265504f12adeadbc51c36c1e97c999e30a0d141
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048019"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Crear y administrar buzones inactivos

Microsoft 365 permite conservar el contenido de los buzones de correo eliminados. Esta característica se denomina [buzones inactivos](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. Un buzón se vuelve inactivo cuando se aplica una directiva de retención por juicio o una directiva de retención (creada en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón antes de que se elimine la cuenta de usuario correspondiente. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. Esto permite que los administradores, los responsables de cumplimiento normativo y los administradores de registros usen la búsqueda de contenido para buscar y exportar el contenido de un buzón inactivo. Los buzones inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de su organización ni en otras listas.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido de los buzones, estamos anunciando la retirada de conservaciones locales en el centro de administración de Exchange. Esto significa que debe usar las retenciones por juicio y las directivas de retención para crear un buzón inactivo. A partir del 1 de julio de 2020, no podrá crear nuevas retenciones locales en Exchange Online. Pero todavía podrá cambiar la duración de retención de una conservación local colocada en un buzón inactivo. Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de retención. Solo se podrá eliminar un buzón inactivo si se quita la retención local. Los buzones inactivos existentes que se encuentran en conservación local se conservarán hasta que se quite la retención. Para obtener más información acerca de la retirada de suspensiones locales, consulte [jubilación de las herramientas de eDiscovery heredadas](legacy-ediscovery-retirement.md).
  
## <a name="before-you-begin"></a>Antes de empezar

- Para convertir un buzón en inactivo, se le debe asignar una licencia de plan 2 de Exchange online de modo que se pueda aplicar una directiva de retención por juicio o retención al buzón antes de eliminarlo. Las licencias del plan 2 de Exchange Online forman parte de una suscripción a Office 365 Enterprise E3 y E5. Si a un buzón se le asigna una licencia de quiosco de Exchange Online plan 1 o Exchange Online (que forman parte de una suscripción de Office 365 E1 y F1 respectivamente), deberá asignarle una licencia de archivado de Exchange Online independiente para que se pueda aplicar una retención al buzón antes de eliminarlo. Para obtener más información, vea [Archivado de Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).

- Las licencias asociadas al buzón de Exchange Online eliminado estarán disponibles después de que elimine la cuenta de usuario correspondiente. A continuación, puede [asignar esas licencias a otro usuario](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users). 

- Si la retención por juicio o una directiva de retención (que está configurada para conservar o conservar y, a continuación, eliminar contenido) no se aplica a un buzón de correo antes de su eliminación, el contenido del buzón no se conservará ni se podrá detectar. Aun así, el buzón eliminado se puede recuperar en un plazo de 30 días a partir de su eliminación, pero el buzón junto con su contenido se eliminará permanentemente transcurrido dicho plazo, si no se recupera.

- For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). Para obtener más información acerca de las directivas de retención, vea [información general sobre las directivas de retención en Microsoft 365](retention-policies.md).
  
## <a name="create-an-inactive-mailbox"></a>Crear un buzón inactivo

El hecho de que un buzón esté inactivo implica dos pasos: 1) colocar el buzón en retención por juicio o aplicarle una directiva de retención, y 2) eliminar el buzón o la cuenta de usuario correspondiente. Tras pasar el buzón a inactivo, su contenido se conservará hasta que se quite la retención o la directiva de retención.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Paso 1: poner un buzón en retención por juicio o aplicar una directiva de retención

Poner un buzón en retención por juicio o aplicar una directiva de retención (que está configurado para conservar o conservar y, a continuación, eliminar contenido) conserva el contenido en el buzón antes de eliminarlo. Ambos tipos de retenciones conservarán todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de elementos modificados. Los elementos eliminados y modificados se conservan en el buzón inactivo durante un período de tiempo especificado o hasta que se elimine permanentemente el buzón inactivo mediante la eliminación de la retención o la directiva de retención aplicada a los buzones inactivos.
  
Si ya se ha realizado una retención en un buzón o si ya se ha aplicado una directiva de retención a un buzón, todo lo que tiene que hacer es eliminar la cuenta de usuario correspondiente, tal como se explica en el paso 2.
  
Para conocer los procedimientos detallados para poner un buzón en retención por juicio o aplicar una directiva de retención, consulte:
  
- [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Introducción a las directivas de retención en Office 365](retention-policies.md)
    
> [!NOTE]
> Para las retenciones por juicio y las directivas de retención, puede crear una retención indefinida o en una retención basada en tiempo. En una retención indefinida, el contenido del buzón inactivo se conservará siempre, hasta que se elimine la retención o hasta que se cambie la duración de la retención. Una vez quitada la retención o la directiva de retención (y siempre y cuando hayan pasado más de 30 días desde que el buzón se eliminara), el buzón inactivo se marcará para su eliminación permanente y su contenido se dejará de conservar o detectar. En una directiva de retención o retención basada en tiempo, se especifica la duración de la retención. Esta duración se establece para cada elemento, y se calcula a partir de la fecha en que un elemento de buzón se ha recibido o creado. Una vez que ha expirado la retención para un elemento de buzón, y ese elemento se ha movido a la carpeta Elementos recuperables del buzón inactivo o se encuentra en ella, el elemento se elimina permanentemente (purga) del buzón inactivo. 
  
### <a name="step-2-delete-the-mailbox"></a>Paso 2: Eliminar el buzón.

Una vez que el buzón se coloca en retención o se le aplica una directiva de retención, el siguiente paso consiste en eliminar el buzón. La mejor forma de eliminar un buzón es eliminar la cuenta de usuario correspondiente en el centro de administración de Microsoft 365. Para obtener información sobre cómo eliminar cuentas de usuario, vea [eliminar un usuario de su organización](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
  
> [!NOTE]
> También puede eliminar el buzón mediante el cmdlet **Remove-Mailbox** en Exchange Online PowerShell. Para obtener más información, vea [eliminar o restaurar buzones de usuario en Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Ver una lista de buzones inactivos

Para ver una lista de los buzones inactivos en su organización:
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización. 
    
2. Haga clic en**retención**del **gobierno** > de información.
    
3. En la página **retención** , haga clic en **más**![elipses](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)de la barra de navegación y, a continuación, en **buzones inactivos**.
    
    ![En la página retención, haga clic en más y, a continuación, haga clic en buzones inactivos para mostrar una lista de buzones inactivos](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Se muestra la página **buzones inactivos** . Nota se muestra el número total de buzones inactivos en la organización. 
    
    ![Se muestra una lista de todos los buzones inactivos en la organización](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar la lista de buzones inactivos.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

Puede hacer clic ![en exportar resultados](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) de la búsqueda para **exportar** para ver o descargar un archivo CSV que contenga información adicional acerca de los buzones inactivos en su organización. 
  
También puede ejecutar el siguiente comando para exportar la lista de buzones inactivos y otra información a un archivo CSV. En este ejemplo, el archivo CSV se crea en el directorio actual.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> Es posible que un buzón inactivo pueda tener la misma dirección SMTP que un buzón de usuario activo. En este caso, el valor de la propiedad **DistinguishedName** o **ExchangeGuid** puede usarse para identificar de forma exclusiva un buzón inactivo. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Buscar y exportar el contenido de un buzón inactivo

Puede tener acceso al contenido del buzón inactivo mediante la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Búsqueda de contenido de Office 365](content-search.md)
    
- [Exportar resultados de la búsqueda de contenido](export-search-results.md)
    
A continuación, se detallan algunos aspectos que se deben tener en cuenta al buscar buzones inactivos:
  
- Si una búsqueda de contenido incluye un buzón de usuario y, a continuación, dicho buzón se convierte en inactivo, la búsqueda de contenido continuará buscando en el buzón inactivo cuando vuelva a ejecutar la búsqueda después de que quede inactiva.
    
- En algunos casos, es posible que un usuario tenga un buzón activo y un buzón inactivo con la misma dirección SMTP. En este caso, solo se buscará en el buzón específico que seleccione como ubicación para una búsqueda de contenido. Es decir, si agrega el buzón de un usuario a una búsqueda, no puede suponer que se buscará en los buzones activos e inactivos; solo se buscará en el buzón que agregue explícitamente a la búsqueda.
    
- Le recomendamos que no tenga un buzón activo y un buzón inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP actualmente asignada a un buzón inactivo, se recomienda recuperar el buzón inactivo o restaurar el contenido de un buzón inactivo en un buzón activo (o el archivo de un buzón activo) y, a continuación, eliminar el buzón inactivo.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Una vez que un buzón se convierte en inactivo, puede cambiar la duración de la retención o la Directiva de retención que se aplica al buzón inactivo. Para conocer los procedimientos paso a paso, vea [cambiar la duración de retención para un buzón inactivo en Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Si un antiguo empleado vuelve a la organización o si se contrata a un nuevo empleado para que asuma las responsabilidades del empleado anterior, puede recuperar el contenido del buzón inactivo. Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. Para conocer los procedimientos paso a paso y obtener más información acerca de Cuándo recuperar un buzón inactivo, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar el contenido de un buzón inactivo en otro buzón de correo

Si otro empleado asume las responsabilidades de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Todavía se pueden realizar búsquedas en el buzón inactivo mediante la exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón, o se puede recuperar o eliminar en una fecha posterior. Para conocer los procedimientos paso a paso, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

Si ya no necesita conservar el contenido de un buzón inactivo, puede eliminar de forma permanente el buzón inactivo quitando la retención o quitando la Directiva de retención aplicada al buzón inactivo. En caso de que el buzón se eliminara hace más de 30 días, se marcará para su eliminación permanente después de quitar la retención y el buzón no podrá recuperarse. Si el buzón se eliminó durante los últimos 30 días, podrá seguir recuperando el buzón una vez quitada la retención o la directiva de retención. Para obtener instrucciones paso a paso para quitar una suspensión o una directiva de retención para eliminar de forma permanente un buzón inactivo, consulte [eliminar un buzón inactivo](delete-an-inactive-mailbox.md).
