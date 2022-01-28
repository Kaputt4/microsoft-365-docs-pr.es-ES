---
title: Habilitar buzones de archivo para el cumplimiento de Microsoft 365
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
description: Obtenga información sobre cómo habilitar o deshabilitar buzones de archivo para que sean compatibles con los requisitos de retención de mensajes, eDiscovery y conservación de mensajes de su organización.
ms.openlocfilehash: be7939f11c6aea0161f76c3796ca2ff8bd515ba0
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241400"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>Habilitar los buzones de archivo en el centro de cumplimiento

El archivado en Microsoft 365 (también llamado *archivado local*) proporciona a los usuarios un espacio de almacenamiento adicional en el buzón. Para obtener más información, vea [Obtener información sobre los buzones de archivo](archive-mailboxes.md).

Use la información de este artículo para habilitar o deshabilitar un buzón de archivo en el Centro de cumplimiento de Microsoft 365 o mediante PowerShell. Obtenga también información sobre cómo ejecutar una comprobación de diagnóstico automatizada en el buzón de archivo de un usuario para identificar los problemas y las soluciones sugeridas.

## <a name="get-the-necessary-permissions"></a>Obtener los permisos necesarios

Debe tener asignado el rol Destinatarios de correo en Exchange Online para habilitar o deshabilitar los buzones de archivo. De forma predeterminada, este rol se asigna a los grupos de roles Administración de destinatarios y Administración de la organización en la página **Permisos** del <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. 

Si no ve la página **Archivo** en el Centro de cumplimiento de Microsoft 365, pida al administrador que le asigne los permisos necesarios.

## <a name="enable-an-archive-mailbox"></a>Habilitación de un buzón de archivo

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> e inicie sesión.

2. En el panel izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Control de la información** y luego en la pestaña **Archivo**.

   Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.

   > [!NOTE]
   > La página **Archivo** muestra un máximo de 500 usuarios.

3. En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.

   ![Haga clic en Activar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo.](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

4. En el panel de detalles para el usuario seleccionado, haga clic en **Habilitar**.

   Se muestra una advertencia que indica que, si habilita el buzón de archivo, los elementos en el buzón del usuario que sean más antiguos que la directiva de archivado asignada al buzón se moverán al nuevo buzón de archivo. Como se explicó anteriormente, la directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de ExchangeOnline mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario. Para más información consulte la sección: **Más información** de este artículo

5. Haga clic en **Sí** para habilitar el buzón de archivo.

   El buzón de archivo puede tardar un poco en crearse. Una vez creado, aparece **Buzón de archivo: habilitado** en el panel de detalles del usuario seleccionado. Es posible que tenga que hacer clic en **Actualizar** ![Icono de actualizar.](../media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información del panel de detalles.

> [!TIP]
> También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles.

## <a name="disable-an-archive-mailbox"></a>Deshabilitar un buzón de archivo

También puede usar la página **Archivar** en el centro de cumplimiento de Microsoft 365 para deshabilitar el buzón de archivo de un usuario. Después de deshabilitar un buzón de archivo, puede volver a conectarlo al buzón de correo principal del usuario en un plazo de 30 días tras la deshabilitación. En este caso se restaura el contenido original del buzón de archivo. Transcurridos los 30 días, el contenido del buzón de archivo original se elimina definitivamente y no se puede recuperar. Así pues, si vuelve a habilitar el archivo después de los 30 días posteriores a la deshabilitación, se crea un buzón de archivo nuevo.

La directiva de archivo predeterminada asignada a los buzones de usuarios mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó. Si deshabilita el buzón de archivo de un usuario, no se realizará ninguna acción en los elementos del buzón y permanecerán en el buzón principal del usuario.

Para deshabilitar un buzón de archivo:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> e inicie sesión.

2. En el panel izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Control de la información** y luego en la pestaña **Archivo**.

   Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.

   > [!NOTE]
   > La página **Archivo** muestra un máximo de 500 usuarios.

3. En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.

4. En el panel de detalles, haga clic en **Deshabilitar**.

   Aparece un mensaje de advertencia que indica que tendrá 30 días para volver a habilitar el buzón de archivo y que, transcurridos esos 30 días, toda la información del archivo se eliminará permanentemente.

5. Haga clic en **Sí** para deshabilitar el buzón de archivo.

   El buzón de archivo puede tardar un poco en deshabilitarse. Una vez deshabilitado, aparece **Buzón de archivo: deshabilitado** está desplegado el panel de detalles del usuario seleccionado. Es posible que deba hacer clic en **Actualizar** ![icono Actualizar](../media/O365-MDM-Policy-RefreshIcon.gif). para actualizar la información en el panel de detalles.

> [!TIP]
> También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Usar PowerShell de Exchange Online para habilitar o deshabilitar buzones de archivo.

También puede usar PowerShell de Exchange Online para habilitar los buzones de archivo. La razón principal para usar PowerShell es que permite habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.

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

## <a name="next-steps"></a>Pasos siguientes

Considere la posibilidad de habilitar el [archivado de expansión automática](autoexpanding-archiving.md) para obtener espacio de almacenamiento adicional. Para obtener instrucciones, consulte [Habilitar el archivado de expansión automática](enable-autoexpanding-archiving.md).
