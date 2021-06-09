---
title: 'Habilitar archivado ilimitado: Ayuda para administradores'
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Para administradores: obtenga información sobre cómo habilitar el archivado de expansión automática, que proporciona a los usuarios almacenamiento ilimitado para sus Exchange Online buzones de correo. Puede habilitar el archivado de expansión automática para toda la organización o solo para usuarios específicos.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac5661ac43ed9c0f35eba20007f0c4c4406ebf20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927830"
---
# <a name="enable-unlimited-archiving---admin-help"></a>Habilitar archivado ilimitado: Ayuda para administradores

Puede usar la característica de Exchange Online de archivado de expansión automática para habilitar el espacio de almacenamiento ilimitado para los buzones de archivo. Cuando se activa el archivado de expansión automática, se agrega espacio de almacenamiento adicional automáticamente al buzón de archivo de un usuario cuando se acerca al límite de almacenamiento. El resultado es una capacidad de almacenamiento de buzones ilimitada. Puede activar el archivado de expansión automática para todos los usuarios de la organización o solo para usuarios específicos. Para obtener más información sobre el archivado de expansión automática, vea [Overview of unlimited archiving in Office 365](unlimited-archiving.md).

## <a name="before-you-enable-auto-expanding-archiving"></a>Antes de habilitar el archivado de expansión automática

- Debe ser administrador global de su organización o miembro del grupo de roles Administración de la organización en su organización de Exchange Online para habilitar el archivado de expansión automática para toda la organización o para usuarios específicos. Como alternativa, debe ser miembro de un grupo de roles que tenga asignado el rol Destinatarios de correo para habilitar el archivado de expansión automática para usuarios específicos.

- El buzón de archivo de un usuario debe estar habilitado para poder habilitar el archivado de expansión automática. A un usuario se le debe asignar una Exchange Online del Plan 2 para habilitar el buzón de archivo. Si se asigna una licencia Exchange Online plan 1 a un usuario, tendrá que asignarle una licencia de Archivado de Exchange Online para habilitar su buzón de archivo. Consulte [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).

- También puede usar PowerShell para habilitar buzones de archivo. Vea la [sección Más información](#more-information) para ver un ejemplo del comando de PowerShell que puede usar para habilitar buzones de archivo para todos los usuarios de la organización.

- El archivado de expansión automática también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se requiere una licencia Exchange Online plan 2 o una licencia Exchange Online plan 1 con una Archivado de Exchange Online de correo.

- El archivado de expansión automática le impide recuperar o restaurar un buzón [inactivo.](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes) Eso significa que si habilita el archivado de expansión automática para un buzón y el buzón se hace inactivo en una fecha posterior, no podrá recuperar el buzón inactivo [(al](recover-an-inactive-mailbox.md) convertirlo en un buzón activo) ni restaurarlo [(combinando](restore-an-inactive-mailbox.md) el contenido con un buzón existente). Si el archivado de expansión automática está habilitado en un buzón inactivo, la única forma de recuperar datos es mediante la herramienta de búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para exportar los datos del buzón e importarlos a otro buzón. Para obtener más información, vea la sección "Buzones inactivos y archivos de expansión automática" en [Overview of inactive mailboxes](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives).

- No puede usar el Centro de administración Exchange ni el Centro de seguridad & cumplimiento para habilitar el archivado de expansión automática. Debe usar Exchange Online PowerShell. Para conectarse a su Exchange Online con PowerShell remoto, vea [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Habilitar el archivado de expansión automática para toda la organización

Puede habilitar el archivado de expansión automática para toda la organización. Después de activarlo, el archivado de expansión automática se habilitará para los buzones de usuario existentes y para los nuevos buzones de usuario que se crean. Al crear buzones de usuario, asegúrese de habilitar el buzón de archivo principal del usuario para que la característica de archivado de expansión automática funcione para el nuevo buzón de usuario.
  
1. [Conectarse al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de expansión automática para toda la organización.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Habilitar el archivado de expansión automática para usuarios específicos

En lugar de habilitar el archivado de expansión automática para todos los usuarios de la organización, solo puede habilitarlo para usuarios específicos. Puede hacerlo porque es posible que solo algunos usuarios necesiten una gran capacidad de almacenamiento de archivos.
  
Al habilitar el archivado de expansión automática para un usuario específico y el buzón del usuario en espera o asignado a una directiva de retención, se realizan los dos cambios de configuración siguientes:
  
- La cuota de almacenamiento del buzón de archivo principal del usuario aumenta en 10 GB (de 100 GB a 110 GB). La cuota de advertencia de archivo también se incrementa en 10 GB (de 90 GB a 100 GB).

- La cuota de almacenamiento de la carpeta Elementos recuperables del buzón principal del usuario aumenta en 10 GB (también de 100 GB a 110 GB). La cuota de advertencia Elementos recuperables también aumenta en 10 GB (de 90 GB a 100 GB). Estos cambios solo se aplican si el buzón está en espera o se asigna a una directiva de retención.

Este espacio adicional se agrega para evitar problemas de almacenamiento que puedan producirse antes de aprovisionar el archivo de expansión automática. No se agrega  *espacio de almacenamiento*  adicional al habilitar el archivado de expansión automática para toda la organización, como se describe en la sección anterior.
  
1. [Conectarse al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. Ejecute el siguiente comando en Exchange Online PowerShell para habilitar el archivado de expansión automática para un usuario específico. Como se explicó anteriormente, el buzón de archivo del usuario (archivo principal) debe estar habilitado para poder activar el archivado de expansión automática para ese usuario.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> En una implementación híbrida de Exchange, no puede usar el comando **Enable-Mailbox -AutoExpandingArchive** para habilitar el archivado de expansión automática para un usuario específico cuyo buzón principal es local y cuyo buzón de archivo está basado en la nube. Para habilitar el archivado de expansión automática para buzones de archivo basados en la nube en una implementación híbrida de Exchange, debe ejecutar el comando **Set-OrganizationConfig -AutoExpandingArchive** en Exchange Online PowerShell para habilitar el archivado de expansión automática para toda la organización. Si los buzones principal y de archivo de un usuario están basados en la nube, puede usar el comando **Enable-Mailbox -AutoExpandingArchive** para habilitar el archivado de expansión automática para ese usuario específico.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Comprobar que el archivado de expansión automática está habilitado

Para comprobar que el archivado de expansión automática está habilitado para su organización, ejecute el siguiente comando en Exchange Online PowerShell.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Un valor de  `True` indica que el archivado de expansión automática está habilitado para la organización. 
  
Para comprobar que el archivado de expansión automática está habilitado para un usuario específico, ejecute el siguiente comando en Exchange Online PowerShell.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Un valor de indica que el archivado  `True` de expansión automática está habilitado para el usuario.
  
Para determinar si el archivado de expansión automática está habilitado para buzones inactivos, ejecute el siguiente comando en Exchange Online PowerShell.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

Un valor de  `True` indica que el archivado de expansión automática está habilitado para el buzón inactivo. Un valor de `False` indica que el archivado de expansión automática no está habilitado.

Tenga en cuenta lo siguiente después de habilitar el archivado de expansión automática:
  
- Si ejecuta el comando **Set-OrganizationConfig -AutoExpandingArchive** para habilitar el archivado de expansión automática para su organización, no tiene que ejecutar **enable-mailbox -AutoExpandingArchive** en buzones individuales. La ejecución del cmdlet **Set-OrganizationConfig** para habilitar el archivado de expansión automática para su organización no cambia la propiedad  *AutoExpandingArchiveEnabled*  en los buzones de usuario a `True` .

- Del mismo modo, los valores de las propiedades del buzón  *ArchiveQuota*  y  *ArchiveWarningQuota*  no se modifican al habilitar el archivado de expansión automática. De hecho, cuando habilita el archivado de expansión automática para un buzón de usuario y la propiedad *AutoExpandingArchiveEnabled* se establece en , se omiten las propiedades `True` *ArchiveQuota* y *ArchiveWarningQuota.* Este es un ejemplo de estas propiedades de buzón después de habilitar el archivado de expansión automática para el buzón de un usuario. 

    ![Las propiedades ArchiveQuota y ArchiveWarningQuota se omiten después de habilitar el archivado de expansión automática](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Más información

- También puede usar PowerShell para habilitar buzones de archivo. Por ejemplo, puede ejecutar el siguiente comando en Exchange Online PowerShell para habilitar buzones de archivo para todos los usuarios cuyo buzón de archivo aún no está habilitado.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Después de activar el archivado de expansión automática para su organización o para un usuario específico, un buzón de archivo se convierte en un archivo de expansión automática cuando el buzón de archivo (incluida la carpeta Elementos recuperables) alcanza los 90 GB. El espacio de almacenamiento adicional puede tardar hasta 30 días en aprovisionarse.

- Después de activar el archivado de expansión automática, no se puede desactivar. Además, los administradores no pueden ajustar la cuota de almacenamiento para el archivado de expansión automática.

- El archivado de expansión automática es compatible con buzones de archivo basados en la nube en una implementación híbrida Exchange para los usuarios que tienen un buzón principal local. Sin embargo, después de habilitar el archivado de expansión automática para un buzón de archivo basado en la nube, no podrá volver a agregar ese buzón de archivo a la organización Exchange local. El archivado de expansión automática no es compatible con buzones locales en ninguna versión de Exchange Server.

- Para obtener una lista de los clientes de Outlook que los usuarios pueden usar para obtener acceso a los elementos del área de almacenamiento adicional en su buzón de archivo, vea la sección "requisitos de Outlook para obtener acceso a elementos de un archivo expandido automáticamente" en [Overview of unlimited archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).

- Como se explicó anteriormente, se agregan 10 GB a la cuota de almacenamiento del buzón de archivo principal del usuario (y a la carpeta Elementos recuperables si el buzón está en espera) al ejecutar el comando **Enable-Mailbox -AutoExpandingArchive.** Esto proporciona almacenamiento adicional hasta que se aprovisiona el espacio de almacenamiento expandido automáticamente (que puede tardar hasta 30 días). Este espacio de almacenamiento adicional no se agrega al ejecutar **Set-OrganizationConfig -AutoExpandingArchive** para habilitar el archivado de expansión automática para todos los buzones de la organización. Si ha habilitado el archivado de expansión automática para toda la organización, pero necesita agregar los 10 GB adicionales de espacio de almacenamiento para un usuario específico, puede ejecutar el comando **Enable-Mailbox -AutoExpandingArchive** en ese buzón. Recibirá un error que dice que el archivado de expansión automática ya está habilitado, pero el espacio de almacenamiento adicional se agregará al buzón.

> [!IMPORTANT]
> El archivado de expansión automática solo se admite para buzones de correo usados para usuarios individuales o buzones compartidos con una tasa de crecimiento que no supere 1 GB al día. No se permite usar el registro en diario, las reglas de transporte o las reglas de reenvío automático para copiar mensajes en un buzón de archivo con el fin de archivarlos. El buzón de archivo de un usuario está diseñado exclusivamente para dicho usuario. Microsoft se reserva el derecho a denegar el archivado ilimitado en los casos en que el buzón de archivo de un usuario se utilice para almacenar datos de archivo para otros usuarios o en otros casos de uso inadecuado.