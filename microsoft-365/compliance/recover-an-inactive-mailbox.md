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
description: Obtenga información sobre cómo recuperar el contenido de un buzón inactivo en Office 365 convertirlo en un nuevo buzón que contenga el contenido del buzón inactivo.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926178"
---
# <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se usa para conservar el correo electrónico de un empleado anterior después de que abandona la organización. Si ese empleado vuelve a la organización o si otro empleado asume las responsabilidades de trabajo del antiguo empleado, hay dos formas de que el contenido del buzón inactivo esté disponible para un usuario:

- **Recuperar un buzón inactivo.** Si el antiguo empleado vuelve a su organización o si se contrata a un nuevo empleado para asumir las responsabilidades laborales del antiguo empleado, puede recuperar el contenido del buzón inactivo. Este método convierte el buzón inactivo en un buzón nuevo y activo que contiene el contenido del buzón inactivo. Una vez recuperado, el buzón inactivo deja de existir. Los procedimientos de este tema describen este método.

- **Restaurar un buzón inactivo.** Si otro empleado asume las responsabilidades de trabajo del antiguo empleado o si otro usuario necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. También puede restaurar el archivo desde un buzón inactivo. Para obtener información sobre los procedimientos de este método, vea [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).

Consulte la sección [Más información](#more-information) para obtener más detalles sobre las diferencias entre la recuperación y restauración de un buzón inactivo, así como para obtener una descripción de lo que sucede cuando se recupera un buzón inactivo.

> [!NOTE]
> No puede recuperar ni restaurar un buzón inactivo configurado con un archivo de expansión automática. Si necesita recuperar datos de un buzón inactivo con un archivo de expansión automática, use la búsqueda de contenido para exportar los datos del buzón y luego importarlos a otro buzón. Para obtener instrucciones, consulte los temas siguientes:
>
> - [Búsqueda de contenido](content-search.md)
> - [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Requisitos para recuperar un buzón inactivo

- Debe usar powershell Exchange Online para recuperar un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Ejecute el siguiente comando para mostrar información de identidad para los buzones inactivos en la organización.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Use la información devuelta por este comando para recuperar un buzón inactivo específico.

## <a name="recover-inactive-mailboxes"></a>Recuperar buzones inactivos

Use el cmdlet **New-Mailbox** con el  *parámetro InactiveMailbox*  para recuperar un buzón inactivo.

1. Cree una variable que contenga las propiedades del buzón inactivo.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal.

2. En este ejemplo se usan las propiedades que se obtuvieron en el comando anterior y se recupera el buzón inactivo en un buzón activo para el usuario Ann Beebe. Asegúrese de que los valores especificados para los parámetros  *Name*  y  *MicrosoftOnlineServicesID*  sean únicos en su organización.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   La dirección SMTP principal del buzón inactivo recuperado tendrá el mismo valor que la especificada por el parámetro *MicrosoftOnlineServicesID.*

Después de recuperar un buzón inactivo, también se crea una nueva cuenta de usuario. Debe activar esta cuenta de usuario asignando una licencia. Para asignar una licencia en el centro Microsoft 365 administración, vea Agregar usuarios y [asignar licencias al mismo tiempo.](../admin/add-users/add-users.md)

## <a name="more-information"></a>Más información

- **¿Cuál es la diferencia principal entre recuperar y restaurar un buzón inactivo?** Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir y los cambios realizados en el contenido en el nuevo buzón afectarán el contenido que se encontraba originalmente en retención en el buzón inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia a otro buzón de correo. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Los cambios realizados en el contenido del buzón de destino no afectan el contenido original del buzón inactivo. El buzón inactivo se puede buscar todavía mediante el uso de la exhibición de documentos electrónicos local, su contenido se puede restaurar a otro buzón o se puede recuperar o eliminar en una fecha posterior.

- **¿Qué sucede cuando se recupera un buzón inactivo?** Cuando se recupera un buzón inactivo, sucede lo siguiente:

  - La retención que se aplicó a un buzón inactivo se cambia o quita en función del tipo de retención que se aplicó al buzón inactivo antes de recuperarlo.

    - **Retención por juicio.** Si la retención por juicio se ha habilitado para el buzón inactivo, se quita del buzón recuperado.

    - **Las retenciones** locales In-Place se quitan del buzón recuperado. Esto significa que el buzón recuperado se quita como buzón de origen de cualquier In-Place de retención o In-Place búsqueda de exhibición de documentos electrónicos.

    - **Microsoft 365 de retención con bloqueo de conservación.** Si el buzón inactivo se asignó a una directiva de retención con bloqueo de conservación (denominada directiva de retención *bloqueada),* el buzón recuperado se asigna a la misma directiva de retención bloqueada. Para obtener más información acerca de las directivas de retención bloqueadas, vea [[Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

    - **Microsoft 365 de retención sin bloqueo de conservación.** El buzón inactivo se quita de cualquier directiva de retención Microsoft 365 desbloqueada que se le aplicó. Sin embargo, la retención por juicio está habilitada en el buzón recuperado para evitar la eliminación del contenido del buzón en función de las directivas de retención de toda la organización que eliminen contenido con una antigüedad específica. Puede mantener la retención por juicio o quitarla. Para obtener más información, vea [Create a Litigation Hold](create-a-litigation-hold.md).

  - El período de recuperación de un solo elemento (definido por la propiedad de buzón **RetainDeletedItemsFor** ) se establece en 30 días. Normalmente, cuando se crea un nuevo buzón en Exchange Online, este período de retención se establece en 14 días. Si establece esto en el valor máximo de 30 días, tendrá más tiempo para recuperar los datos que se han eliminado (o depurado) de forma permanente del buzón inactivo. También puede deshabilitar la recuperación de un solo elemento o volver a establecer el período de recuperación de un solo elemento en el valor predeterminado de 14 días. Para obtener más información, consulte [Enable or disable single item recovery for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).

  - La suspensión de retención está habilitada y la duración de la suspensión de retención se establece en 30 días. Esto significa que la directiva de retención de Exchange predeterminada y las directivas de retención de Microsoft 365 de toda la organización o de Exchange que estén asignadas al nuevo buzón no se procesarán durante 30 días. Esto proporciona al empleado que vuelve o al nuevo propietario del buzón inactivo recuperado el tiempo suficiente para administrar los mensajes antiguos. De lo contrario, la directiva de retención de Exchange o Microsoft 365 podría eliminar elementos de buzones antiguos (o mover elementos al buzón de archivo, si está habilitado) que han expirado en función de la configuración configurada para las directivas de retención de Exchange o Microsoft 365. Transcurridos 30 días, expira la retención, la propiedad de buzón **RetentionHoldEnabled** se establece en **False** y el Asistente para carpetas administradas comienza a procesar las directivas asignadas al buzón. Si no necesita este tiempo adicional, solo puede quitar la suspensión de retención. Como alternativa, puede aumentar la duración de la suspensión de retención mediante el comando **Set-Mailbox -EndDateForRetentionHold**. Para obtener más información, consulte [Place a mailbox on retention hold](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Si necesita conservar el estado original del buzón inactivo, coloque una retención en el buzón recuperado.** Para evitar que el nuevo propietario del buzón o la directiva de retención eliminen permanentemente los mensajes del buzón inactivo recuperado, puede colocar el buzón en retención por juicio. Para obtener más información, vea [Create a Litigation Hold](./create-a-litigation-hold.md).

- **¿Qué identificador de usuario se puede usar cuando se recupera un buzón inactivo?** Al recuperar un buzón inactivo, el valor que especifique para el parámetro  *MicrosoftOnlineServicesID*  puede ser diferente del original asociado con el buzón inactivo. También se puede usar el identificador de usuario original. Pero, como se ha indicado anteriormente, asegúrese de que los valores usados para  *Name*  y  *MicrosoftOnlineServicesID*  son únicos en su organización al recuperar el buzón inactivo.

- **¿Qué sucede si no ha expirado el período de retención de buzón para el buzón inactivo?** Si un buzón inactivo se eliminó temporalmente hace menos de 30 días, no se puede usar el comando **New-Mailbox -InactiveMailbox** para recuperarlo. Debe recuperarla restaurando la cuenta de usuario correspondiente. Para obtener más información, [vea Delete a user from your organization](../admin/add-users/delete-a-user.md).

- **¿Cómo saber si ha expirado el período de retención del buzón eliminado temporalmente para un buzón inactivo?** Ejecute el siguiente comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Si no hay un valor para la propiedad **ExternalDirectoryObjectId**, el período de retención del buzón ha expirado y puede recuperar el buzón inactivo ejecutando el comando **New-Mailbox -InactiveMailbox**. Si hay un valor para la propiedad **ExternalDirectoryObjectId,** el período de retención del buzón eliminado temporalmente no ha expirado y debe recuperar el buzón restaurando la cuenta de usuario. Consulte [Elimine un usuario de su organización](../admin/add-users/delete-a-user.md).

- **Considere la posibilidad de habilitar el buzón de archivo después de recuperar un buzón inactivo.** Esto permite que el usuario que vuelve o el nuevo empleado muevan mensajes antiguos al buzón de archivo. Y cuando expire la retención, la directiva de archivo que forma parte de la directiva de retención de Exchange predeterminada asignada Exchange Online los buzones de correo moverá elementos que tienen dos años o más al buzón de archivo. Si no habilita el buzón de archivo, los elementos de más de dos años permanecerán en el buzón principal del usuario. Para obtener más información, vea [Enable archive mailboxes](enable-archive-mailboxes.md).