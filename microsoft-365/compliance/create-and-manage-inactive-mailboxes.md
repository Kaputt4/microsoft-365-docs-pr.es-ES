---
title: Crear y administrar buzones inactivos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
description: Cree y administre buzones inactivos que conserven el contenido de los buzones eliminados en Microsoft 365.
ms.openlocfilehash: b7a33101135b43357b095af6864b54c618abd84d
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417410"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Crear y administrar buzones inactivos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Los buzones inactivos le permiten conservar el correo electrónico de los antiguos empleados después de abandonar la organización y pueden acceder a ellos personas autorizadas a las que se les hayan concedido [permisos de exhibición](assign-ediscovery-permissions.md) de documentos electrónicos por motivos legales o de cumplimiento. Por ejemplo, los administradores, los responsables de cumplimiento y los administradores de registros que pueden usar búsqueda de contenido para buscar y exportar el contenido de un buzón inactivo. Los buzones inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de su organización ni en otras listas.

Para obtener más información acerca de los buzones inactivos, consulte [Más información sobre buzones inactivos](inactive-mailboxes-in-office-365.md).

## <a name="create-an-inactive-mailbox"></a>Creación de un buzón inactivo

Hacer que un buzón esté inactivo requiere una suspensión en el buzón y, a continuación, eliminar el buzón o la cuenta de usuario correspondiente.

Para que un buzón esté inactivo, se le debe asignar una licencia de Exchange Online Plan 2 (o una licencia de Exchange Online Plan 1 con una licencia de complemento de Archivado de Exchange Online) para que se pueda aplicar una suspensión al buzón antes de que se elimine. Una vez eliminada la cuenta de usuario, cualquier licencia de Exchange Online asociada a la cuenta de usuario estará disponible para asignarla a un nuevo usuario.

Se recomienda usar Microsoft 365 retención para aplicar la suspensión en el buzón. Otros métodos se tratan en [Información sobre los buzones inactivos](inactive-mailboxes-in-office-365.md).

La mejor manera de eliminar un buzón es eliminar la cuenta de usuario correspondiente en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Para obtener información sobre cómo eliminar cuentas de usuario, consulte [Eliminación de un usuario de su organización](../admin/add-users/delete-a-user.md). Sin embargo, también puede eliminar el buzón mediante el cmdlet **Remove-Mailbox** en Exchange Online PowerShell. Para obtener más información, vea [Eliminar o restaurar buzones de usuario en Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).

En la tabla siguiente se resume el proceso de creación de un buzón inactivo para diferentes escenarios de retención.

<br/>

|Para...|Haga esto...|Resultado|
|---|---|---|
|Conservar el contenido del buzón indefinidamente después de que un empleado deje la organización|1. Aplique Microsoft 365 configuración de retención con acciones de retención para el buzón (una directiva de retención) o elementos de correo electrónico específicos (una o varias etiquetas de retención). <br /><br> 2. Espere a que se aplique la configuración de retención. <br /><br> 3. Quite la cuenta de Microsoft 365 del usuario.|Todo el contenido del buzón inactivo que tiene aplicada la configuración de retención, incluidos los elementos de la carpeta Elementos recuperables, se conserva indefinidamente.|
|Conservar todo el contenido del buzón durante un período específico después de que un empleado deje la organización y, a continuación, eliminar el buzón|1. Aplique una directiva de retención de Microsoft 365 al buzón con la configuración de retención que retenga y elimine los elementos cuando expire el período de retención. <br /><br> 2. Espere a que se aplique la configuración de retención. <br /><br> 3. Quite la cuenta de Microsoft 365 del usuario.|Cuando expira el período de retención de un elemento de buzón de correo, el elemento se mueve a la carpeta Elementos recuperables y, a continuación, se elimina permanentemente (se purga) del buzón inactivo cuando expira el período de retención de elementos eliminados (para Exchange buzones). El período de retención de la directiva de retención de Microsoft 365 siempre se basa en la fecha original en que se recibió o creó un elemento de buzón.|


> [!NOTE]
> Si Microsoft 365 configuración de retención que está configurada para conservar o conservar y eliminar contenido, ya se aplica a los elementos de buzón o buzón, o una retención por juicio ya está colocada en un buzón de correo o, a continuación, todo lo que tiene que hacer para crear un buzón inactivo es eliminar la cuenta de usuario correspondiente.


## <a name="view-a-list-of-inactive-mailboxes"></a>Ver una lista de buzones inactivos

Para ver una lista de los buzones inactivos de la organización:

1. Vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> e inicie sesión con las credenciales de una Administrador global o una cuenta de administrador de cumplimiento de su organización.

2. En el panel de navegación izquierdo, seleccione **Mostrar todo** y, a continuación, seleccione Administración  > **del ciclo de vida** de **datosDirectivas de** mantenimiento.

3. Seleccione la opción **Buzón inactivo** :

   ![Opción Buzón inactivo en la página Directivas de retención de la administración del ciclo de vida de datos.](../media/inactive-mailbox-option.png)

4. La página **Buzones inactivos** muestra una lista de buzones inactivos. Seleccione uno para ver detalles sobre ese buzón inactivo. Los detalles incluyen el identificador de Exchange del buzón de correo y si está en [suspensión por juicio](create-a-litigation-hold.md).
    
    No verá otros tipos de retenciones en el panel de detalles, por ejemplo, una directiva de retención de Microsoft 365 o una suspensión de eDiscovery. Para encontrar esta información, consulte [Cómo identificar el tipo de retención colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Si tiene muchos buzones inactivos, es posible que le resulte más fácil buscar y ordenar un archivo CSV para obtener los detalles que ve en la lista: en la página **Buzones inactivos** , seleccione :::image type="icon" source="../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png"::: **Exportar**.

Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar la lista de buzones inactivos:

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

También puede ejecutar el siguiente comando para exportar la lista de buzones inactivos y otra información a un archivo CSV. En este ejemplo, el archivo CSV se crea en el directorio actual.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> Es posible que un buzón inactivo tenga la misma dirección SMTP que un buzón de usuario activo. En este caso, el valor de la propiedad **DistinguishedName** o **ExchangeGuid** se puede usar para identificar de forma única un buzón inactivo.
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Buscar y exportar el contenido de un buzón inactivo

Puede acceder al contenido del buzón inactivo mediante la herramienta Búsqueda de contenido de la portal de cumplimiento Microsoft Purview. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de la búsqueda](export-search-results.md)

A continuación, se detallan algunos aspectos que se deben tener en cuenta al buscar buzones inactivos:
  
- Si una búsqueda de contenido incluye un buzón de usuario y ese buzón se convierte en inactivo, la búsqueda de contenido seguirá buscando en el buzón inactivo cuando vuelva a ejecutar la búsqueda después de que se vuelva a poner inactiva.

- En algunos casos, un usuario puede tener un buzón activo y un buzón inactivo que tengan la misma dirección SMTP. En este caso, solo se buscará el buzón específico que seleccione como ubicación para una búsqueda de contenido. En otras palabras, si agrega el buzón de un usuario a una búsqueda, no puede suponer que se buscarán sus buzones activos e inactivos; solo se buscará el buzón que agregue explícitamente a la búsqueda.

- Le recomendamos que no tenga un buzón activo y un buzón inactivo con la misma dirección SMTP. Si necesita reutilizar la dirección SMTP que está asignada actualmente a un buzón inactivo, se recomienda recuperar el buzón inactivo o restaurar el contenido de un buzón inactivo en un buzón activo (o el archivo de un buzón activo) y, a continuación, eliminar el buzón inactivo.

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Una vez que un buzón de correo está inactivo, es posible que pueda cambiar la duración de la suspensión aplicada al buzón inactivo.

Para ver los procedimientos paso a paso, consulte [Cambio de la duración de retención de un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Si un antiguo empleado vuelve a la organización o si se contrata a un nuevo empleado para que asuma las responsabilidades del empleado anterior, puede recuperar el contenido del buzón inactivo. 

Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. 

Para obtener procedimientos paso a paso y más información sobre cómo se produce al recuperar un buzón inactivo, consulte [Recuperación de un buzón inactivo](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar el contenido de un buzón inactivo en otro buzón de correo

Si otro empleado asume las responsabilidades de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. 

Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Todavía se pueden realizar búsquedas en el buzón inactivo mediante la exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón, o se puede recuperar o eliminar en una fecha posterior. 

Para ver los procedimientos paso a paso, consulte [Restauración de un buzón inactivo](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

Si ya no necesita conservar el contenido de un buzón inactivo, puede eliminar permanentemente el buzón inactivo quitando la suspensión aplicada al buzón inactivo. El buzón se conservará durante 183 días después de quitar la directiva de retención o suspensión y se podrá recuperar durante ese tiempo. Después de 183 días, el buzón se marcará para su eliminación permanente y el buzón no se podrá recuperar. 

Para ver los procedimientos paso a paso para quitar una suspensión o una directiva de retención para eliminar permanentemente un buzón inactivo, consulte [Eliminación de un buzón inactivo](delete-an-inactive-mailbox.md).
