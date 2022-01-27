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
ms.openlocfilehash: 18bcc4c69fc15ea44253bbc4b0f5d5813cc23085
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241848"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Crear y administrar buzones inactivos

Los buzones inactivos le permiten conservar el correo electrónico de los [antiguos empleados](assign-ediscovery-permissions.md) después de salir de la organización y pueden acceder a ellos las personas autorizadas a las que se les han concedido permisos de exhibición de documentos electrónicos por motivos legales o de cumplimiento. Por ejemplo, administradores, responsables de cumplimiento y administradores de registros que pueden usar la búsqueda de contenido para buscar y exportar el contenido de un buzón inactivo. Los buzones inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de su organización ni en otras listas.

Para obtener más información acerca de los buzones inactivos, vea [Learn about inactive mailboxes](inactive-mailboxes-in-office-365.md).

## <a name="create-an-inactive-mailbox"></a>Crear un buzón inactivo

Hacer inactivo un buzón requiere una retención en el buzón y, a continuación, eliminar el buzón o la cuenta de usuario correspondiente.

Para que un buzón esté inactivo, se le debe asignar una licencia del Plan 2 de Exchange Online (o una licencia del Plan 1 de Exchange Online con una licencia de complemento de Archivado de Exchange Online) para que se pueda aplicar una retención al buzón antes de eliminarla. Después de eliminar la cuenta de usuario, cualquier licencia Exchange Online asociada a la cuenta de usuario estará disponible para asignarla a un nuevo usuario.

Se recomienda usar la retención Microsoft 365 para aplicar la retención en el buzón. Otros métodos se tratan [en Learn about inactive mailboxes](inactive-mailboxes-in-office-365.md).

La mejor manera de eliminar un buzón es eliminar la cuenta de usuario correspondiente en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Para obtener información sobre cómo eliminar cuentas de usuario, vea [Eliminar un usuario de la organización.](../admin/add-users/delete-a-user.md) Sin embargo, también puede eliminar el buzón mediante el cmdlet **Remove-Mailbox** en Exchange Online PowerShell. Para obtener más información, vea [Eliminar o restaurar buzones](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)de usuario en Exchange Online .

En la tabla siguiente se resume el proceso de creación de un buzón inactivo para distintos escenarios de retención.

<br/>

|Para...|Haga esto...|Resultado|
|---|---|---|
|Conservar el contenido del buzón de correo indefinidamente después de que un empleado abandone la organización|1. Aplicar la Microsoft 365 de retención con acciones de retención para el buzón (una directiva de retención) o elementos de correo electrónico específicos (una o más etiquetas de retención). <br /><br> 2. Espere a que se aplique la configuración de retención. <br /><br> 3. Quite la cuenta Microsoft 365 usuario.|Todo el contenido del buzón inactivo que tiene aplicada la configuración de retención, incluidos los elementos de la carpeta Elementos recuperables, se conserva indefinidamente.|
|Conservar todo el contenido del buzón durante un período específico después de que un empleado abandone la organización y, a continuación, elimine el buzón|1. Aplicar una directiva Microsoft 365 de retención al buzón de correo con la configuración de retención que retiene y, a continuación, elimina los elementos cuando expira el período de retención. <br /><br> 2. Espere a que se aplique la configuración de retención. <br /><br> 3. Quite la cuenta Microsoft 365 usuario.|Cuando expira el período de retención de un elemento de buzón de correo, el elemento se mueve a la carpeta Elementos recuperables y, a continuación, se elimina permanentemente (purga) del buzón inactivo cuando expira el período de retención de elementos eliminados (para buzones de correo Exchange). El período de retención de la Microsoft 365 de retención siempre se basa en la fecha original en que se recibió o creó un elemento de buzón.|


> [!NOTE]
> Si Microsoft 365 la configuración de retención configurada para conservar o conservar y eliminar contenido, ya se aplica al buzón o a los elementos de buzón de correo, o si ya se ha colocado una retención por juicio en un buzón o, a continuación, todo lo que tiene que hacer para crear un buzón inactivo es eliminar la cuenta de usuario correspondiente.


## <a name="view-a-list-of-inactive-mailboxes"></a>Ver una lista de buzones inactivos

Para ver una lista de los buzones inactivos de la organización:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> e inicie sesión con las credenciales de un administrador global o una cuenta de administrador de cumplimiento en su organización.

2. En el panel de navegación izquierdo, haga clic **en Mostrar todo** y, a continuación, haga clic en Retención de gobierno **de**  >  **información.**

   ![Haga clic en el botón Buzón inactivo de la página Retención.](../media/MCCInactiveMailboxes1.png)

3. En la **página Retención,** haga clic **en Buzón inactivo** para mostrar una lista de buzones inactivos.

4. Seleccione un buzón inactivo para mostrar una página desplegable con información sobre el buzón inactivo.

   ![La página desplegable muestra detalles sobre el buzón inactivo.](../media/MCCInactiveMailboxes2.png)  

Puede hacer clic en ![ Exportar icono de resultados de búsqueda.](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Exportar** para ver o descargar un archivo CSV que contiene información adicional sobre los buzones inactivos de la organización.

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

Puede obtener acceso al contenido del buzón inactivo mediante la herramienta búsqueda de contenido de la Centro de cumplimiento de Microsoft 365. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Búsqueda de contenido](content-search.md)

- [Exportar resultados de la búsqueda](export-search-results.md)

A continuación, se detallan algunos aspectos que se deben tener en cuenta al buscar buzones inactivos:
  
- Si una búsqueda de contenido incluye un buzón de usuario y ese buzón está inactivo, la búsqueda de contenido seguirá buscando en el buzón inactivo cuando vuelva a ejecutar la búsqueda después de que esté inactivo.

- En algunos casos, un usuario puede tener un buzón activo y un buzón inactivo que tenga la misma dirección SMTP. En este caso, solo se buscará el buzón específico que seleccione como ubicación para una búsqueda de contenido. En otras palabras, si agrega el buzón de un usuario a una búsqueda, no puede suponer que se buscarán sus buzones activos e inactivos; solo se buscará el buzón que agregue explícitamente a la búsqueda.

- Le recomendamos que no tenga un buzón activo y un buzón inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP que está asignada actualmente a un buzón inactivo, se recomienda recuperar el buzón inactivo o restaurar el contenido de un buzón inactivo en un buzón activo (o el archivo de un buzón activo) y, a continuación, eliminar el buzón inactivo.

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Después de que un buzón esté inactivo, es posible que pueda cambiar la duración de la retención aplicada al buzón inactivo.

Para ver los procedimientos paso a paso, vea Cambiar la [duración de retención de un buzón inactivo.](change-the-hold-duration-for-an-inactive-mailbox.md)
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Si un antiguo empleado vuelve a la organización o si se contrata a un nuevo empleado para que asuma las responsabilidades del empleado anterior, puede recuperar el contenido del buzón inactivo. 

Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. 

Para obtener procedimientos paso a paso y obtener más información acerca de cómo se recupera un buzón inactivo, vea [Recover an inactive mailbox](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar el contenido de un buzón inactivo en otro buzón de correo

Si otro empleado asume las responsabilidades de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. 

Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Todavía se pueden realizar búsquedas en el buzón inactivo mediante la exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón, o se puede recuperar o eliminar en una fecha posterior. 

Para ver los procedimientos paso a paso, vea [Restore an inactive mailbox](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

Si ya no necesita conservar el contenido de un buzón inactivo, puede eliminar permanentemente el buzón inactivo quitando la retención aplicada al buzón inactivo. El buzón se conservará durante 183 días después de quitar la directiva de retención o retención y se podrá recuperar durante ese tiempo. Después de 183 días, el buzón se marcará para su eliminación permanente y el buzón no se podrá recuperar. 

Para obtener procedimientos paso a paso para quitar una suspensión o una directiva de retención para eliminar permanentemente un buzón inactivo, vea [Delete an inactive mailbox](delete-an-inactive-mailbox.md).
