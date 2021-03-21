---
title: Habilitar buzones de archivo en el Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom: seo-marvel-apr2020
description: Aprenda a usar el centro de cumplimiento para habilitar los buzones de correo de archivo a fin de respaldar los requisitos de retención de mensajes, eDiscovery y retención de su organización.
ms.openlocfilehash: 2bc80d347d1324a317cc2cc2712d475781adc492
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926520"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>Habilitar los buzones de archivo en el centro de cumplimiento

El archivado en Microsoft 365 (también llamado *archivado local*) proporciona a los usuarios un espacio de almacenamiento adicional en el buzón. Después de habilitar los buzones de archivo, los usuarios pueden obtener acceso a los mensajes y almacenarlos en los buzones de archivo con Microsoft Outlook y Outlook en la Web (anteriormente denominada Outlook Web App). Los usuarios también pueden mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo. También pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados.

> [!NOTE]
> La función de archivado de expansión automática de Microsoft 365 proporciona almacenamiento adicional en los buzones de archivo. Cuando se activa el archivo de ampliación automática y se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Microsoft 365 agrega automáticamente espacio de almacenamiento adicional. Esto significa que los usuarios no se quedan sin espacio de almacenamiento en el buzón y que no tendrá que administrar nada después de habilitar el buzón de archivo por primera vez y activar el archivado de ampliación automática para su organización. Para obtener más información, consulte [Información general del archivado ilimitado](unlimited-archiving.md).

## <a name="get-the-necessary-permissions"></a>Obtener los permisos necesarios

Debe tener asignado el rol de Destinatarios de correo de Exchange Online para habilitar o deshabilitar los buzones de archivo. De manera predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Administración de destinatarios en la página **Permisos** del centro de administración de Exchange. Si no ve la página **Archivo** en el Centro de seguridad y cumplimiento, pida al administrador que le asigne los permisos necesarios.

## <a name="enable-an-archive-mailbox"></a>Habilitación de un buzón de archivo

1. Vaya a <https://protection.office.com>.

2. Inicie sesión con su cuenta profesional o educativa.

3. En el panel izquierdo del centro de cumplimiento de & de seguridad, haga clic en **control de la información** \> **archivo**.

   Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.

   > [!NOTE]
   > La página **Archivo** muestra un máximo de 500 usuarios.

4. En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.

   ![Haga clic en Activar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo.](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. En el panel de detalles para el usuario seleccionado, haga clic en **Habilitar**.

   Se muestra una advertencia que indica que, si habilita el buzón de archivo, los elementos en el buzón del usuario que sean más antiguos que la directiva de archivado asignada al buzón se moverán al nuevo buzón de archivo. La directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de Exchange Online mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario. Para más información, vea la sección **Más información** de este artículo.

6. Haga clic en **Sí** para habilitar el buzón de archivo.

   Puede tardar unos momentos para crear el buzón de archivo. Una vez creado, aparece **Buzón de archivo: habilitado** en el panel de detalles del usuario seleccionado. Es posible que deba hacer clic en **Actualizar** ![Icono de actualizar](../media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.

> [!TIP]
> También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles.

## <a name="disable-an-archive-mailbox"></a>Deshabilitar un buzón de archivo

También puede usar la página **Archivo** en el Centro de seguridad y cumplimiento para deshabilitar el buzón de archivo del usuario. Después de deshabilitar un buzón de archivo, puede volver a conectarlo al buzón de correo principal del usuario en un plazo de 30 días tras la deshabilitación. En este caso, se restaura el contenido original del buzón de archivo. Transcurridos los 30 días, el contenido del buzón de archivo original se elimina definitivamente y no se puede recuperar. Así, si vuelve a habilitar el archivo después de los 30 días posteriores a la deshabilitación, se crea un buzón de archivo nuevo.

La directiva de archivo de forma predeterminada asignada a los buzones de los usuarios mueve los elementos al buzón de archivo dos años después de la fecha de entrega del elemento. Si deshabilita un buzón de archivo de un usuario, no se realizará ninguna acción en los elementos del buzón y permanecerán en el buzón principal del usuario.

Para deshabilitar un buzón de archivo:

1. Vaya a <https://protection.office.com>.

2. Inicie sesión con su cuenta profesional o educativa.

3. En el panel izquierdo del centro de cumplimiento de & de seguridad, haga clic en **control de la información** \> **archivo**.

   Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.

   > [!NOTE]
   > La página **Archivo** muestra un máximo de 500 usuarios.

4. En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.

5. En el panel de detalles, haga clic en **Deshabilitar**.

   Aparece un mensaje de advertencia que indica que tendrá 30 días para volver a habilitar el buzón de archivo y que, transcurridos esos 30 días, toda la información del archivo se eliminará permanentemente.

6. Haga clic en **Sí** para deshabilitar el buzón de archivo.

   El buzón de archivo puede tardar un poco en deshabilitarse. Una vez deshabilitado, aparece **Buzón de archivo: deshabilitado** en el panel de detalles del usuario seleccionado. Es posible que deba hacer clic en **Actualizar** ![Icono de actualizar](../media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.

> [!TIP]
> También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Usar PowerShell de Exchange Online para habilitar o deshabilitar buzones de archivo.

También puede usar PowerShell de Exchange Online para habilitar buzones de archivo. La razón principal para usar PowerShell es que permite habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.

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

## <a name="more-information"></a>Más información

- Cuando un buzón de archivo está habilitado, los usuarios pueden almacenar mensajes en su buzón de archivo. Los usuarios pueden obtener acceso a los buzones de archivo mediante Microsoft Outlook y Outlook en la Web. Mediante cualquiera de estas aplicaciones cliente, los usuarios pueden visualizar mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo. Los usuarios también pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados.

  Para obtener una lista de las licencias de Outlook que son compatibles con el archivado local, vea [Requisitos de licencia de Outlook para las funciones de Exchange](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).

- Los buzones de archivo permiten que usted y sus usuarios cumplan con los requisitos de retención de mensajes de la organización, eDiscovery y conservación. Por ejemplo, puede usar la directiva de retención de Exchange de su organización para mover el contenido del buzón al buzón de archivo de los usuarios. Cuando se usa la herramienta de Búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar contenido específico en el buzón de un usuario, también se buscará en el buzón de archivo del usuario. Y, cuando se coloca una Retención por juicio o se aplica una directiva de retención en el buzón de un usuario, también se retienen los elementos del buzón de archivo.

- Cuando se habilitan los buzones de archivo, la organización puede beneficiarse de la directiva de retención de Exchange predeterminada (también llamada directiva de Administración de registros de mensajería o MRM) que se asigna automáticamente a todos los buzones. Cuando se habilita un buzón de archivo, la directiva de retención de Exchange predeterminada hace automáticamente lo siguiente:

  - Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo.

  - Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.

- Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, vea:

  - [Etiquetas de retención y directivas de retención en Exchange Online](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [Directiva de retención predeterminada de Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [Configurar una directiva de archivo y eliminación de buzones en la organización](set-up-an-archive-and-deletion-policy-for-mailboxes.md)