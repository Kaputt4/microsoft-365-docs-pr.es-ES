---
title: Habilitar el archivado de ampliación automática
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Para administradores: obtenga información sobre cómo habilitar el archivado de expansión automática, que proporciona a los usuarios almacenamiento adicional para sus buzones de Exchange Online. Puede habilitar el archivado de expansión automática para toda la organización o solo para usuarios específicos.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f1155eaf95a8cf814561650acee4784e8c469df
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012774"
---
# <a name="enable-auto-expanding-archiving"></a>Habilitar el archivado de ampliación automática

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede usar la característica de archivado de expansión automática Exchange Online para habilitar espacio de almacenamiento adicional para los buzones de archivo. Cuando se activa el archivado de expansión automática, el espacio de almacenamiento adicional se agrega automáticamente al buzón de archivo de un usuario hasta que alcanza el límite de almacenamiento de 1,5 TB. Puede activar el archivado de expansión automática para todos los usuarios de la organización o solo para usuarios específicos. Para obtener más información sobre el archivado de expansión automática, consulte [Información sobre el archivado de expansión automática](autoexpanding-archiving.md).

## <a name="before-you-enable-auto-expanding-archiving"></a>Antes de habilitar el archivado de expansión automática

- Después de activar el archivado de expansión automática para su organización o para un usuario específico, no se puede desactivar. Además, los administradores no pueden ajustar la cuota de almacenamiento para el archivado de expansión automática.

- Debe ser administrador global de su organización o miembro del grupo de roles Administración de la organización de su organización Exchange Online para habilitar el archivado de expansión automática. Como alternativa, debe ser miembro de un grupo de roles que tenga asignado el rol Destinatarios de correo para habilitar el archivado de expansión automática para usuarios específicos.

- El buzón de archivo de un usuario debe habilitarse para poder habilitar el archivado de expansión automática. A un usuario se le debe asignar una licencia Exchange Online plan 2 para habilitar el buzón de archivo. Si a un usuario se le asigna una licencia Exchange Online plan 1, tendría que asignarle una licencia de Archivado de Exchange Online independiente para habilitar su buzón de archivo. Consulte [Habilitación de buzones de archivo](enable-archive-mailboxes.md).

- Después de activar el archivado de expansión automática, un buzón de archivo se convierte en un archivo de expansión automática cuando el buzón de archivo (incluida la carpeta Elementos recuperables) alcanza los 90 GB. El espacio de almacenamiento adicional puede tardar hasta 30 días en aprovisionarse.

- También puede usar PowerShell para habilitar buzones de archivo. Consulte la sección [Más información](#more-information) para obtener un ejemplo del comando de PowerShell que puede usar para habilitar buzones de archivo para todos los usuarios de la organización.

- El archivado de expansión automática también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se requiere una licencia de ExchangeOnline (plan 2) o de ExchangeOnline (plan 1) con una licencia de Archivado de ExchangeOnline.

- El archivado de expansión automática impide recuperar o restaurar un [buzón inactivo](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes). Esto significa que si habilita el archivado de expansión automática para un buzón de correo y el buzón se deja inactivo en una fecha posterior, no podrá [recuperar el buzón inactivo](recover-an-inactive-mailbox.md) (convertirlo en un buzón activo) ni [restaurarlo](restore-an-inactive-mailbox.md) (combinando el contenido con un buzón existente). Si el archivado de expansión automática está habilitado en un buzón inactivo, la única manera de recuperar datos es mediante la herramienta de búsqueda de contenido del portal de cumplimiento de Microsoft Purview para exportar los datos del buzón e importarlos a otro buzón. Para obtener más información, vea la sección "Buzones inactivos y archivos de expansión automática" en [Información sobre los buzones inactivos](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives).

- No puede usar el centro de administración de Exchange ni el portal de cumplimiento de Microsoft Purview para habilitar el archivado de expansión automática. Tiene que usar Exchange Online PowerShell. Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Habilitación del archivado de expansión automática para toda la organización

Puede habilitar el archivado de expansión automática para toda la organización. Después de activarlo, el archivado de expansión automática se habilitará para los buzones de usuario existentes y para los nuevos buzones de usuario creados. Al crear buzones de usuario, asegúrese de habilitar el buzón de archivo principal del usuario para que la característica de archivado de expansión automática funcione para el nuevo buzón de usuario.
  
1. [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de expansión automática para toda la organización.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Habilitación del archivado de expansión automática para usuarios específicos

En lugar de habilitar el archivado de expansión automática para cada usuario de la organización, solo puede habilitarlo para usuarios específicos. Puede hacerlo porque solo algunos usuarios pueden necesitar una gran capacidad de almacenamiento de archivo.
  
Al habilitar el archivado de expansión automática para un usuario específico y el buzón de correo del usuario en espera o asignado a una directiva de retención, se realizan los dos cambios de configuración siguientes:
  
- La cuota de almacenamiento para el buzón de archivo principal del usuario se incrementa en 10 GB (de 100 GB a 110 GB). La cuota de advertencia de archivo también aumenta en 10 GB (de 90 GB a 100 GB).

- La cuota de almacenamiento de la carpeta Elementos recuperables del buzón principal del usuario se incrementa en 10 GB (también de 100 GB a 110 GB). La cuota de advertencia Elementos recuperables también aumenta en 10 GB (de 90 GB a 100 GB). Estos cambios solo son aplicables si el buzón está en espera o asignado a una directiva de retención.

Este espacio adicional se agrega para evitar cualquier problema de almacenamiento que pueda producirse antes de aprovisionar el archivo de expansión automática. *No se* agrega espacio de almacenamiento adicional al habilitar el archivado de expansión automática para toda la organización, como se describe en la sección anterior.
  
1. [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de expansión automática para un usuario específico. Como se explicó anteriormente, el buzón de archivo del usuario (archivo principal) debe estar habilitado para poder activar el archivado de expansión automática para ese usuario.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> En una implementación híbrida Exchange, no puede usar el comando **Enable-Mailbox -AutoExpandingArchive** para habilitar el archivado de expansión automática para un usuario específico cuyo buzón principal es local y cuyo buzón de archivo está basado en la nube. Para habilitar el archivado de expansión automática para buzones de archivo basados en la nube en una implementación híbrida Exchange, debe ejecutar el comando **Set-OrganizationConfig -AutoExpandingArchive** en Exchange Online PowerShell para habilitar el archivado de expansión automática para toda la organización. Si los buzones principal y de archivo de un usuario están basados en la nube, puede usar el comando **Enable-Mailbox -AutoExpandingArchive** para habilitar el archivado de expansión automática para ese usuario específico.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Comprobación de que el archivado de expansión automática está habilitado

Para comprobar que el archivado de expansión automática está habilitado para su organización, ejecute el siguiente comando en Exchange Online PowerShell.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Un valor de  `True` indica que el archivado de expansión automática está habilitado para la organización. 
  
Para comprobar que el archivado de expansión automática está habilitado para un usuario específico, ejecute el siguiente comando en Exchange Online PowerShell.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Un valor de  `True` indica que el archivado de expansión automática está habilitado para el usuario.
  
Para determinar si el archivado de expansión automática está habilitado para los buzones inactivos, ejecute el siguiente comando en Exchange Online PowerShell.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

Un valor de  `True` indica que el archivado de expansión automática está habilitado para el buzón inactivo. Un valor de `False` indica que el archivado de expansión automática no está habilitado.

Tenga en cuenta lo siguiente después de habilitar el archivado de expansión automática:
  
- Si ejecuta el comando **Set-OrganizationConfig -AutoExpandingArchive** para habilitar el archivado de expansión automática para su organización, no es necesario ejecutar **Enable-Mailbox -AutoExpandingArchive** en buzones individuales. La ejecución del cmdlet **Set-OrganizationConfig** para habilitar el archivado de expansión automática para su organización no cambia la propiedad  *AutoExpandingArchiveEnabled*  en los buzones de usuario a `True`.

- De forma similar, los valores de las propiedades de buzón  *ArchiveQuota*  y  *ArchiveWarningQuota*  no se cambian al habilitar el archivado de expansión automática. De hecho, al habilitar el archivado de expansión automática para un buzón de usuario y la propiedad  *AutoExpandingArchiveEnabled*  se establece en  `True`, se omiten las propiedades  *ArchiveQuota*  y  *ArchiveWarningQuota*  . Este es un ejemplo de estas propiedades de buzón después de habilitar el archivado de expansión automática para el buzón de un usuario. 

    ![Las propiedades ArchiveQuota y ArchiveWarningQuota se omiten después de habilitar el archivado de expansión automática.](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Más información

- También puede usar PowerShell para habilitar buzones de archivo. Por ejemplo, puede ejecutar el siguiente comando en Exchange Online PowerShell para habilitar buzones de archivo para todos los usuarios cuyo buzón de archivo aún no esté habilitado.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- El archivado de expansión automática se admite para los buzones de archivo basados en la nube en una implementación híbrida Exchange para los usuarios que tienen un buzón principal local. Sin embargo, después de habilitar el archivado de expansión automática para un buzón de archivo basado en la nube, no puede volver a colocar ese buzón de archivo en la organización Exchange local. El archivado de expansión automática no se admite para buzones locales en ninguna versión de Exchange Server.

- Para obtener una lista de Outlook clientes que los usuarios pueden usar para acceder a elementos del área de almacenamiento adicional en su buzón de archivo, consulte la sección "Requisitos de Outlook para acceder a elementos en un archivo expandido automáticamente" en [Información sobre el archivado de expansión automática](autoexpanding-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).

- Como se explicó anteriormente, se agregan 10 GB a la cuota de almacenamiento del buzón de archivo principal del usuario (y a la carpeta Elementos recuperables si el buzón está en espera) al ejecutar el comando **Enable-Mailbox -AutoExpandingArchive** . Esto proporciona almacenamiento adicional hasta que se aprovisiona el espacio de almacenamiento expandido automáticamente (lo que puede tardar hasta 30 días). Este espacio de almacenamiento adicional no se agrega al ejecutar **Set-OrganizationConfig -AutoExpandingArchive** para habilitar el archivado de expansión automática para todos los buzones de su organización. Si ha habilitado el archivado de expansión automática para toda la organización, pero necesita agregar los 10 GB adicionales de espacio de almacenamiento para un usuario específico, puede ejecutar el comando **Enable-Mailbox -AutoExpandingArchive** en ese buzón. Recibirá un error que indica que el archivado de expansión automática ya está habilitado, pero el espacio de almacenamiento adicional se agregará al buzón.

> [!IMPORTANT]
> El archivado de expansión automática solo se admite para buzones usados por usuarios individuales o para buzones compartidos con una tasa de crecimiento que no supera 1 GB al día. No se permite usar el registro en diario, las reglas de transporte o las reglas de reenvío automático para copiar mensajes en un buzón de archivo con fines de archivado. El buzón de archivo de un usuario está diseñado exclusivamente para dicho usuario. Microsoft se reserva el derecho de denegar el archivado adicional en los casos en los que se usa el buzón de archivo de un usuario para almacenar datos de archivo para otros usuarios o en otros casos de uso inadecuado.
