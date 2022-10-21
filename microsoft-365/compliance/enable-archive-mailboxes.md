---
title: Habilitar buzones de archivo para Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier2
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
description: Obtenga información sobre cómo habilitar o deshabilitar buzones de archivo para que sean compatibles con los requisitos de retención de mensajes, eDiscovery y conservación de mensajes de su organización.
ms.openlocfilehash: 2dbece4e898ff4c01a6f224a1e7b69ab3a533448
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660211"
---
# <a name="enable-archive-mailboxes-for-microsoft-365"></a>Habilitar buzones de archivo para Microsoft 365

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

El archivado en Microsoft 365 (también llamado *Archivado local*) proporciona a los usuarios un espacio de almacenamiento adicional en el buzón. Para obtener más información, vea [Obtener información sobre los buzones de archivo](archive-mailboxes.md).

Use la información de este artículo para habilitar o deshabilitar un buzón de archivo mediante un portal de administración o mediante PowerShell. Obtenga también información sobre cómo ejecutar una comprobación de diagnóstico automatizada en el buzón de archivo de un usuario para identificar los problemas y las soluciones sugeridas.

La configuración para habilitar o deshabilitar los buzones de archivo se mueve de la [portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center.md) al [nuevo Centro de administración de Exchange (EAC).](/exchange/exchange-admin-center) Hasta que se complete este traslado para todos los inquilinos, esta página incluye instrucciones para ambas experiencias de administrador.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="get-the-necessary-permissions"></a>Obtener los permisos necesarios

Debe tener asignado el rol Destinatarios de correo en Exchange Online para habilitar o deshabilitar los buzones de archivo. De forma predeterminada, este rol se asigna a los grupos de roles Administración de destinatarios y Administración de la organización en la página **Permisos** del <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. 


## <a name="how-to-enable-an-archive-mailbox"></a>Habilitación de un buzón de archivo

La configuración para administrar buzones de archivo se mueve desde el portal de cumplimiento de Microsoft 365 Purview al nuevo Centro de administración de Exchange.

### <a name="use-the-new-exchange-admin-center-to-enable-an-archive-mailbox"></a>Uso del nuevo Centro de administración de Exchange para habilitar un buzón de archivo

> [!NOTE]
> Al habilitar el buzón de archivo, los elementos del buzón del usuario que sean anteriores a la directiva de archivado asignada al buzón se moverán al nuevo buzón de archivo. La directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de Exchange Online mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario. Para obtener más información, vea [Obtener información sobre los buzones de archivo](archive-mailboxes.md).

1. En el nuevo EAC, vaya a **Buzones de** **destinatarios**\>.

2. En la lista de buzones, seleccione el usuario para habilitar su buzón para el archivo.

3. En el panel flotante, seleccione **Otros** y, en **Archivo de buzón**, seleccione **Administrar archivo de buzón**: 
    
   ![Administrar el archivo de buzón de correo para un usuario seleccionado.](../media/manage-mailbox-archive-option.png)

4. En el panel **Administrar archivo de buzón de correo** , active Archivo **de buzón** y, a continuación, **Guardar**.

Puede tardar unos momentos para crear el buzón de archivo. Cuando se crea, **Activo** se muestra en la columna **Estado de archivo** del usuario seleccionado, aunque es posible que tenga que actualizar la página para ver el cambio de estado.

### <a name="use-the-purview-compliance-portal-to-enable-an-archive-mailbox"></a>Uso del portal de cumplimiento de Purview para habilitar un buzón de archivo

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento de Microsoft Purview</a> e inicie sesión.

2. En el panel izquierdo del portal de cumplimiento, seleccione **Administración** >  del ciclo de vida de datos **Archivo** de **Microsoft 365** > .

   En la página **Archivo**, la columna **Buzón de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.

   > [!NOTE]
   > La página **Archivo** muestra un máximo de 500 usuarios. Use el cuadro de búsqueda si no puede ver inmediatamente el nombre del usuario que desea.

3. En la lista de buzones, seleccione el usuario para el que desea habilitar el buzón de archivo y seleccione la opción **Habilitar Archivo**:
    
   ![Habilitar la opción de archivo para un usuario seleccionado.](../media/enable-archive-option.png)
    
   Se muestra una advertencia que indica que, si habilita el buzón de archivo, los elementos en el buzón del usuario que sean más antiguos que la directiva de archivado asignada al buzón se moverán al nuevo buzón de archivo. La directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de Exchange Online mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario. Para obtener más información, vea [Obtener información sobre los buzones de archivo](archive-mailboxes.md).

5. Seleccione **Habilitar** para confirmar.

   Puede tardar unos momentos para crear el buzón de archivo. Cuando se ha creado, **Habilitado** se muestra en la columna **Buzón de archivo** del usuario seleccionado, aunque es posible que tenga que actualizar la página para ver el cambio de estado.

## <a name="how-to-disable-an-archive-mailbox"></a>Cómo deshabilitar un buzón de archivo

De forma similar a cómo habilitar un buzón de archivo, puede usar la misma configuración en el EAC o el portal de cumplimiento para deshabilitar el buzón de archivo de un usuario. Esta vez, desactive el **archivo de buzón** en el EAC o seleccione la opción **Deshabilitar archivo** después de seleccionar el usuario en el portal de cumplimiento.

After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.

The default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they'll remain in the user's primary mailbox.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Usar PowerShell de Exchange Online para habilitar o deshabilitar buzones de archivo.

You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.

El primer paso es conectar al PowerShell de Exchange Online. Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Una vez que esté conectado a Exchange Online, puede ejecutar los comandos de las secciones siguientes para habilitar o deshabilitar los buzones de archivo.

### <a name="enable-archive-mailboxes"></a>Habilitar buzones de archivo

Ejecute el comando siguiente para habilitar el buzón de archivo para un único usuario.

```powershell
Enable-Mailbox -Identity <username> -Archive
```

Ejecute el comando siguiente para habilitar el buzón de archivo para todos los usuarios de su organización (cuyo buzón de archivo no está habilitado en este momento).

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>Deshabilitar los buzones de archivo

Ejecute el siguiente comando para deshabilitar el buzón de archivo de un único usuario.

```powershell
Disable-Mailbox -Identity <username> -Archive
```

Ejecute el comando siguiente para deshabilitar el buzón de archivo para todos los usuarios de su organización (cuyo buzón de archivo está habilitado en este momento).

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="run-diagnostics-on-archive-mailboxes"></a>Ejecutar diagnósticos en buzones de correo de archivo

Puede ejecutar una comprobación de diagnóstico automatizada en el buzón de archivo de un usuario para identificar los problemas y las soluciones sugeridas.

Para ejecutar la comprobación de diagnóstico, haga clic en el siguiente botón. 

> [!div class="nextstepaction"]
> [Ejecutar pruebas: Buzón de archivo](https://aka.ms/PillarArchiveMailbox)

![Ejecutar diagnósticos en un buzón de archivo.](../media/ArchiveMailboxDiagnostics.png)

Se abre una página de control flotante en el Centro de administración de Microsoft 365. Escriba la dirección de correo electrónico del buzón que desea comprobar y haga clic en **Ejecutar las pruebas**.

> [!NOTE]
> Debe ser un administrador global de Microsoft 365 para usar la comprobación de diagnóstico del buzón de archivo. Además, esta característica no está disponible en las nubes de Microsoft 365 Government, Microsoft 365 operado por 21Vianet o Microsoft 365 Alemania.

## <a name="instructions-for-end-users"></a>Instrucciones para usuarios finales

Explicar a los usuarios cómo funciona su buzón de archivo y cómo pueden interactuar con él en Outlook en Windows, macOS y la Web. La documentación más eficaz se personalizará para su organización. Pero para obtener instrucciones básicas, consulte [Administrar el almacenamiento de correo electrónico con buzones de archivo en línea](https://prod.support.services.microsoft.com/en-us/office/manage-email-storage-with-online-archive-mailboxes-1cae7d17-7813-4fe8-8ca2-9a5494e9a721).

## <a name="next-steps"></a>Pasos siguientes

Considere la posibilidad de habilitar el [archivado de expansión automática](autoexpanding-archiving.md) para obtener espacio de almacenamiento adicional. Para obtener instrucciones, consulte [Habilitar el archivado de expansión automática](enable-autoexpanding-archiving.md).
