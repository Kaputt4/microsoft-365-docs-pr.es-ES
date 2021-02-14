---
title: Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818869"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Colocar una conservación local en un buzón eliminado temporalmente en Exchange Online

Obtenga información sobre cómo crear una conservación local en un buzón eliminado temporalmente para que se convierta en inactivo y se conserve su contenido. Después, puede usar las herramientas de Microsoft eDiscovery para buscar el buzón inactivo.

> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de In-Place Holds en el Centro de administración de Exchange (EAC). A partir del 1 de julio de 2020 no podrá crear nuevas retenciones de In-Place en Exchange Online. Pero aún podrá administrar las retenciones de In-Place en el EAC o mediante el cmdlet **Set-MailboxSearch** en Exchange Online PowerShell. Sin embargo, a partir del 1 de octubre de 2020, no podrá administrar las In-Place locales. Solo los quitará en el EAC o con el cmdlet **Remove-MailboxSearch.** Para obtener más información acerca de la retirada de In-Place de documentos electrónicos, vea Retirada de herramientas de exhibición de [documentos electrónicos heredadas.](legacy-ediscovery-retirement.md)
  
You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. Después de que el buzón esté inactivo, puede buscar en el buzón mediante la exhibición de documentos electrónicos de In-Place en Exchange Online, la búsqueda de contenido en el Centro de seguridad & cumplimiento o el Centro de exhibición de documentos electrónicos en SharePoint Online. 
  
> [!NOTE]
> En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se puede recuperar en un período de retención específico. El período de retención de buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar (o convertirse en un buzón inactivo) en un plazo de 30 días después de eliminarse. Transcurrido este período, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse ni convertirse en inactivo. 
  
## <a name="requirements-for-in-place-holds"></a>Requisitos para In-Place retenciones locales

- Tiene que usar el cmdlet **New-MailboxSearch** en Windows PowerShell para colocar una conservación local en un buzón eliminado temporalmente. No puede usar el Centro de administración de Exchange (EAC) ni el Centro de eDiscovery en SharePoint Online. 

- Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Ejecute el siguiente comando para obtener información de identidad sobre los buzones eliminados temporalmente en la organización. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Para obtener más información acerca de los buzones inactivos, vea Información general sobre los buzones inactivos [en Office 365.](inactive-mailboxes-in-office-365.md)

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Colocar una conservación local en un buzón eliminado temporalmente para convertirlo en un buzón inactivo

Use el cmdlet **New-MailboxSearch** para convertir un buzón eliminado temporalmente en un buzón inactivo. Para obtener más información, vea [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Cree una variable que contenga las propiedades del buzón eliminado temporalmente.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGuid** para identificar el buzón eliminado temporalmente. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo y un buzón eliminado temporalmente tengan la misma dirección SMTP principal. 
  
2. Cree una conservación local y colóquela en el buzón eliminado temporalmente. En este ejemplo, no se especifica ninguna duración de la conservación. Esto significa que los elementos se conservarán de manera indefinida o hasta que la conservación se quite del buzón inactivo.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   También puede especificar una duración de la conservación cuando cree la conservación local. En este ejemplo se conservan elementos en el buzón inactivo durante aproximadamente 7 años.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Después de unos minutos, ejecute uno de los siguientes comandos para comprobar que el buzón eliminado temporalmente es un buzón inactivo.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    O bien
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Más información

Después de que convierta un buzón eliminado temporalmente en un buzón inactivo, existen varias maneras en las que puede administrar el buzón. Para obtener más información, vea:
  
- [Cambiar la duración de retención para un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Recuperar un buzón inactivo](recover-an-inactive-mailbox.md)

- [Restaurar un buzón inactivo](restore-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md) (quitando la retención)
