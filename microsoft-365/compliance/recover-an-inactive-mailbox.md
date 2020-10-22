---
title: Recuperar un buzón inactivo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo recuperar el contenido de un buzón inactivo en Office 365 convirtiéndolo en un nuevo buzón de correo que contiene el contenido del buzón inactivo.
ms.openlocfilehash: 41096df9fe4c2ae78b07e06ebf8bd8384a83f4fa
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655751"
---
# <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. Si el empleado vuelve a su organización o si otro empleado lleva a cabo las responsabilidades laborales del antiguo empleado, hay dos formas de poner el contenido del buzón inactivo a disposición de un usuario:

- **Recuperar un buzón inactivo.** Si el antiguo empleado vuelve a su organización, o si se contrata a un nuevo empleado para que realice las responsabilidades laborales del antiguo empleado, puede recuperar el contenido del buzón inactivo. Este método convierte el buzón inactivo en un nuevo buzón activo que incluye el contenido del buzón inactivo. Una vez recuperado, el buzón inactivo deja de existir. Los procedimientos de este tema describen este método.

- **Restaurar un buzón inactivo.** Si otro empleado asume las responsabilidades laborales del antiguo empleado o si otro usuario necesita tener acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. También puede restaurar el archivo desde un buzón inactivo. Para conocer los procedimientos de este método, vea [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).

Consulte la sección [Más información](#more-information) para obtener más detalles sobre las diferencias entre la recuperación y restauración de un buzón inactivo, así como para obtener una descripción de lo que sucede cuando se recupera un buzón inactivo.

> [!NOTE]
> No puede recuperar o restaurar un buzón inactivo que está configurado con un archivo de expansión automática. Si necesita recuperar datos de un buzón inactivo con un archivo de expansión automática, use la búsqueda de contenido para exportar los datos del buzón y, a continuación, importe a otro buzón. Para obtener instrucciones, vea los siguientes temas:
>
> - [Búsqueda de contenido](content-search.md)
> - [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Requisitos para recuperar un buzón inactivo

- Debe usar Exchange Online PowerShell para recuperar un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Ejecute el siguiente comando para mostrar información de identidad para los buzones inactivos en la organización.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Use la información devuelta por este comando para recuperar un buzón inactivo específico.

## <a name="recover-inactive-mailboxes"></a>Recuperar buzones inactivos

Use el cmdlet **New-Mailbox** con el parámetro  *InactiveMailbox*  para recuperar un buzón inactivo.

1. Cree una variable que contenga las propiedades del buzón inactivo.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal.

2. En este ejemplo se usan las propiedades que se obtuvieron en el comando anterior y se recupera el buzón inactivo en un buzón activo para el usuario Ann Beebe. Asegúrese de que los valores especificados para los parámetros  *Name*  y  *MicrosoftOnlineServicesID*  son únicos en la organización.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   La dirección SMTP principal para el buzón inactivo recuperado tendrá el mismo valor que el especificado por el parámetro  *MicrosoftOnlineServicesID*  .

Después de recuperar un buzón inactivo, también se crea una nueva cuenta de usuario. Debe activar esta cuenta de usuario asignando una licencia. Para asignar una licencia en el centro de administración de Microsoft 365, consulte [Agregar usuarios y asignar licencias al mismo tiempo](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).

## <a name="more-information"></a>Más información

- **¿Cuál es la diferencia principal entre recuperar y restaurar un buzón inactivo?** Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir y los cambios realizados en el contenido en el nuevo buzón afectarán el contenido que se encontraba originalmente en retención en el buzón inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia a otro buzón de correo. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Los cambios realizados en el contenido del buzón de destino no afectan el contenido original del buzón inactivo. El buzón inactivo se puede buscar todavía mediante el uso de la exhibición de documentos electrónicos local, su contenido se puede restaurar a otro buzón o se puede recuperar o eliminar en una fecha posterior.

- **¿Qué sucede cuando se recupera un buzón inactivo?** Cuando se recupera un buzón inactivo, sucede lo siguiente:

  - La retención que se aplicó a un buzón inactivo se cambia o se quita en función del tipo de retención que se aplicó al buzón inactivo antes de que se recupere.

    - **Retención por juicio.** Si se habilitó la retención por juicio para el buzón inactivo, se quita del buzón de correo recuperado.

    - **Conservación local** In-Place suspensiones se quitan del buzón de correo recuperado. Esto significa que el buzón de correo recuperado se quita como un buzón de origen de cualquier In-Place retención o búsqueda de exhibición de documentos electrónicos In-Place.

    - **Directiva de retención de 365 de Microsoft con bloqueo de conservación.** Si el buzón inactivo se asignó a una directiva de retención con bloqueo de conservación (denominada *Directiva de retención bloqueada*), el buzón de correo recuperado se asignará a la misma directiva de retención bloqueada. Para obtener más información acerca de las directivas de retención bloqueadas, consulte [usar bloqueo de conservación para cumplir con los requisitos normativos](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).

    - **Directiva de retención de Microsoft 365 sin bloqueo de preservación.** El buzón inactivo se quita de cualquier directiva de retención de Microsoft 365 desbloqueada que se le haya aplicado. Sin embargo, la retención por juicio está habilitada en el buzón de correo recuperado para evitar la eliminación de contenido de buzón de correo en función de las directivas de retención de toda la organización que eliminan contenido anterior a una antigüedad específica. Puede mantener la retención por juicio o quitarla. Para obtener más información, vea [Create a Litigation Hold](create-a-litigation-hold.md).

  - El período de recuperación de un solo elemento (definido por la propiedad de buzón **RetainDeletedItemsFor** ) se establece en 30 días. Normalmente, cuando se crea un nuevo buzón en Exchange Online, este período de retención se establece en 14 días. Si establece esto en el valor máximo de 30 días, tendrá más tiempo para recuperar los datos que se han eliminado (o depurado) de forma permanente del buzón inactivo. También puede deshabilitar la recuperación de un solo elemento o volver a establecer el período de recuperación de un solo elemento en el valor predeterminado de 14 días. Para obtener más información, consulte [Enable or disable single item recovery for a mailbox](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).

  - La suspensión de retención está habilitada y la duración de la suspensión de retención se establece en 30 días. Esto significa que la Directiva de retención de Exchange predeterminada y todas las directivas de retención de Microsoft 365 de toda la organización o de todo el ámbito de Exchange que se asignan al nuevo buzón no se procesarán durante 30 días. Esto proporciona al empleado que vuelve o al nuevo propietario del buzón inactivo recuperado el tiempo suficiente para administrar los mensajes antiguos. De lo contrario, la Directiva de retención de Exchange o Microsoft 365 puede eliminar los elementos de buzón antiguos (o mover elementos al buzón de archivo, si está habilitado) que han expirado según la configuración de las directivas de retención de Exchange o Microsoft 365. Transcurrido el plazo de 30 días, la suspensión de **la retención** se establece en **false**y el Asistente para carpeta administrada comienza a procesar las directivas asignadas al buzón de correo. Si no necesita este tiempo adicional, solo puede quitar la suspensión de retención. Como alternativa, puede aumentar la duración de la suspensión de retención mediante el comando **Set-Mailbox -EndDateForRetentionHold**. Para obtener más información, consulte [Place a mailbox on retention hold](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Si necesita conservar el estado original del buzón inactivo, coloque una retención en el buzón recuperado.** Para evitar que el nuevo propietario del buzón o la Directiva de retención eliminen permanentemente los mensajes del buzón inactivo recuperado, puede poner el buzón en retención por juicio. Para obtener más información, vea [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

- **¿Qué identificador de usuario se puede usar cuando se recupera un buzón inactivo?** Al recuperar un buzón inactivo, el valor que especifique para el parámetro  *MicrosoftOnlineServicesID*  puede ser diferente del original que estaba asociado con el buzón inactivo. También se puede usar el identificador de usuario original. Pero, como se mencionó anteriormente, asegúrese de que los valores usados para  *nombre*  y  *MicrosoftOnlineServicesID*  son únicos dentro de la organización al recuperar el buzón inactivo.

- **¿Qué sucede si no ha expirado el período de retención de buzón para el buzón inactivo?** Si un buzón inactivo se eliminó temporalmente hace menos de 30 días, no se puede usar el comando **New-Mailbox -InactiveMailbox** para recuperarlo. Debe recuperarla mediante la restauración de la cuenta de usuario correspondiente. Para obtener más información, vea [eliminar un usuario de su organización](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

- **¿Cómo saber si ha expirado el período de retención del buzón eliminado temporalmente para un buzón inactivo?** Ejecute el siguiente comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Si no hay un valor para la propiedad **ExternalDirectoryObjectId**, el período de retención del buzón ha expirado y puede recuperar el buzón inactivo ejecutando el comando **New-Mailbox -InactiveMailbox**. Si hay un valor para la propiedad **ExternalDirectoryObjectId** , el período de retención de buzones eliminados temporalmente no ha expirado y tiene que recuperar el buzón mediante la restauración de la cuenta de usuario. Consulte [Elimine un usuario de su organización](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

- **Considere la posibilidad de habilitar el buzón de archivo después de recuperar un buzón inactivo.** Esto permite que el usuario que vuelve o el nuevo empleado muevan mensajes antiguos al buzón de archivo. Y cuando expire la suspensión de retención, la Directiva de archivo que forma parte de la Directiva de retención de Exchange predeterminada asignada a los buzones de correo de Exchange Online moverá los elementos que tengan dos años o más con el buzón de archivo. Si no habilita el buzón de archivo, los elementos de más de dos años permanecerán en el buzón principal del usuario. Para obtener más información, consulte [enable Archive mailboxes](enable-archive-mailboxes.md).
