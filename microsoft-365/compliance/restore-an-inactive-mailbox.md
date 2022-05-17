---
title: Restaurar un buzón inactivo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Obtenga información sobre cómo restaurar (o combinar) el contenido de un buzón inactivo en un buzón existente.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 66f9e75a76b4fb1bda0f9ae0f70cfe12c816d2bb
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "65438233"
---
# <a name="restore-an-inactive-mailbox"></a>Restaurar un buzón inactivo

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Un buzón inactivo (que es un tipo de buzón eliminado temporalmente) se usa para conservar el correo electrónico de un antiguo empleado después de abandonar la organización. Si otro empleado asume las responsabilidades del empleado que se marchó o si dicho empleado vuelve a la organización, hay dos maneras en que puede hacer que el contenido del buzón inactivo esté disponible para un usuario:

- **Restaurar un buzón inactivo** Si otro empleado asume las responsabilidades del empleado que se marchó o si otro usuario necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. También puede restaurar el archivo desde un buzón inactivo. Una vez restaurado, el buzón inactivo se conserva y se mantiene como un buzón inactivo. En este artículo se describen los procedimientos para restaurar un buzón inactivo.

- **Recuperar un buzón inactivo** Si el empleado que se marchó vuelve a la organización o si se contrata a un nuevo empleado para que asuma las responsabilidades del empleado anterior, puede recuperar el contenido del buzón inactivo. Este método convierte el buzón inactivo en un buzón nuevo que contiene el contenido del buzón inactivo. Una vez recuperado, el buzón inactivo deja de existir. Para ver los procedimientos paso a paso, consulte [Recuperación de un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).

Consulte la sección [Más información](#more-information) de este artículo para obtener más información sobre las diferencias entre restaurar y recuperar un buzón inactivo.

> [!NOTE]
> No se puede recuperar ni restaurar un buzón inactivo configurado con un archivo de expansión automática. Si necesita recuperar datos de un buzón inactivo con un archivo de expansión automática, use la búsqueda de contenido para exportar los datos del buzón y, a continuación, importarlos a otro buzón. Para obtener instrucciones, consulte los artículos siguientes:
>
> - [Búsqueda de contenido](content-search.md)
> - [Exportar resultados de búsqueda de contenido](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>Requisitos para restaurar un buzón inactivo

- Debe usar Exchange Online PowerShell para restaurar un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC) ni el portal de cumplimiento Microsoft Purview para este procedimiento. Para obtener instrucciones paso a paso para usar Exchange Online PowerShell, consulte [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Ejecute el siguiente comando en Exchange Online PowerShell para obtener información de identidad de los buzones inactivos de la organización.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Use la información devuelta por este comando para identificar y restaurar un buzón inactivo específico.

- Para obtener más información sobre los buzones inactivos, vea [Buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-inactive-mailboxes"></a>Restauración de buzones inactivos

Use el cmdlet **New-MailboxRestoreRequest** con los parámetros  _SourceMailbox_ y  _TargetMailbox_ para restaurar el contenido de un buzón inactivo en un buzón existente. Para obtener más información sobre el uso de este cmdlet, vea [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).

Para poder restaurar un buzón inactivo, debe agregar legacyExchangeDN del buzón inactivo al buzón de destino, como una dirección de proxy X500 del buzón de destino. Esto tiene que hacerse porque el cmdlet **New-MailboxRestoreRequest** comprueba si el valor de la propiedad **LegacyExchangeDN** en los buzones de origen y de destino es el mismo. Después de restaurar el buzón inactivo, opcionalmente puede quitar legacyExchangeDN del buzón inactivo del buzón de origen. Asegúrese de esperar hasta que se complete la solicitud de restauración del buzón antes de quitar LegacyExchangeDN.

Siga estos pasos para restaurar un buzón inactivo en un buzón existente:

1. Cree una variable que contenga las propiedades del buzón inactivo.

   ```powershell
   $inactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal.

2. Muestre legacyExchangeDN del buzón inactivo para que pueda agregarlo como una dirección de proxy al buzón de destino en el paso siguiente.

   ```powershell
   $inactiveMailbox.LegacyExchangeDN
   ```

3. Agregue LegacyExchangeDN del buzón inactivo como una dirección de proxy X500 al buzón de destino.

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Add="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

4. Restaurar el contenido del buzón inactivo en un buzón existente. El contenido del buzón inactivo (buzón de origen) se combinará en las carpetas correspondientes en el buzón existente (buzón de destino).

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $inactiveMailbox.DistinguishedName -TargetMailbox <identity of target mailbox> 
   ```

   Como alternativa, puede especificar una carpeta de nivel superior en el buzón de destino en el que se va a restaurar el contenido del buzón inactivo. Si la carpeta de destino especificada o la estructura de carpetas de destino no existe en el buzón de destino, se crea durante el proceso de restauración.

   En este ejemplo se copian los elementos del buzón y las subcarpetas de un buzón inactivo a una carpeta denominada "Buzón inactivo" en la estructura de carpetas de nivel superior del buzón de destino.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox <identity of target mailbox> -TargetRootFolder "Inactive Mailbox"
   ```

5. Una vez completada la solicitud de restauración, puede quitar opcionalmente legacyExchangeDN del buzón inactivo del buzón de destino. Salir de LegacyExchangeDN desde el buzón inactivo no afectará al buzón de destino.

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Remove="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Restaurar el archivo a partir de un buzón inactivo

Si un buzón inactivo tiene un buzón de archivo, también puede restaurarlo en el buzón de archivo de un buzón existente. Para restaurar el archivo desde un buzón inactivo, debe agregar los modificadores _SourceIsArchive_ y _TargetIsArchive_ al comando usado para restaurar un buzón inactivo.

1. Cree una variable que contenga las propiedades del buzón inactivo.

   ```powershell
   $inactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > En el comando anterior, use el valor de la propiedad **DistinguishedName** o **ExchangeGUID** para identificar el buzón inactivo. Estas propiedades son únicas para cada buzón en su organización, mientras que es posible que un buzón activo e inactivo puedan tener la misma dirección SMTP principal.

2. Muestre legacyExchangeDN del buzón inactivo para que pueda agregarlo como una dirección de proxy al buzón de destino en el paso siguiente.

   ```powershell
   $inactiveMailbox.LegacyExchangeDN
   ```

3. Agregue LegacyExchangeDN del buzón inactivo como una dirección de proxy X500 al buzón de destino.

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Add="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

4. Restaure el contenido del archivo a partir del buzón inactivo (archivo de origen) en el archivo de un buzón existente (archivo de destino). En este ejemplo, el contenido del archivo de origen se copia a una carpeta denominada "Archivo de buzón inactivo" en el archivo del buzón de destino.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox <identity of target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive"
   ```

5. Una vez completada la solicitud de restauración, puede quitar opcionalmente legacyExchangeDN del buzón inactivo del buzón de destino. Salir de LegacyExchangeDN desde el buzón inactivo no afectará al buzón de destino.

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Remove="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

## <a name="more-information"></a>Más información

- **¿Cuál es la diferencia principal entre recuperar y restaurar un buzón inactivo?** Cuando se recupera un buzón inactivo, el buzón se convierte en un nuevo buzón. El contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón está vinculado a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir y los cambios realizados en el contenido en el nuevo buzón afectarán el contenido que se encontraba originalmente en retención en el buzón inactivo. Por el contrario, cuando se restaura un buzón inactivo, el contenido simplemente se copia a otro buzón de correo. El buzón inactivo se conserva y sigue siendo un buzón inactivo. Los cambios realizados en el contenido del buzón de destino no afectan el contenido original del buzón inactivo. El buzón inactivo todavía se puede buscar mediante la [herramienta Búsqueda de contenido](content-search.md), su contenido se puede restaurar en otro buzón o se puede recuperar o eliminar en una fecha posterior.

- **¿Cómo se encuentran los buzones inactivos?** Para obtener una lista de los buzones inactivos en la organización y mostrar información útil para restaurar un buzón inactivo, puede ejecutar este comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Use una directiva de retención de Microsoft 365 o una suspensión por juicio o para conservar el contenido del buzón inactivo.** Si desea conservar el estado de un buzón inactivo después de restaurarlo, puede aplicar una [directiva de retención de Microsoft 365](retention.md) al buzón de destino o colocar el buzón de destino en [suspensión por juicio](create-a-litigation-hold.md) antes de restaurar el buzón inactivo. Esto evitará la eliminación permanente de los elementos del buzón inactivo después de que se restauran en el buzón de destino.

- **Habilitar la suspensión de retención en el buzón de destino antes de restaurar un buzón inactivo.** Como los elementos del buzón de un buzón inactivo podrían ser antiguos, considere la posibilidad de habilitar la suspensión de retención en el buzón de destino antes de restaurar un buzón inactivo. Al colocar un buzón en suspensión de retención, no se procesará la directiva de retención que se le asigna hasta que se elimine la suspensión de retención o hasta que expire el período de suspensión de retención. De este modo, el propietario del buzón de destino tiene tiempo para administrar los mensajes antiguos del buzón inactivo. De lo contrario, la directiva de retención puede eliminar los elementos antiguos (o mover elementos al buzón de archivo, si está habilitado) que han expirado en función de las opciones de retención configuradas para el buzón de destino. Para obtener más información, vea [Colocar un buzón en retención en Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Puede usar otros parámetros con el cmdlet New-MailboxRestoreRequest para implementar escenarios de restauración diferentes para los buzones inactivos.**. Por ejemplo, puede ejecutar este comando para restaurar el archivo desde el buzón inactivo en el buzón principal del buzón de destino.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive"
  ```

  Al ejecutar este comando también puede restaurar el buzón principal inactivo en el archivo del buzón de destino.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox"
  ```

- **¿Qué hace el parámetro TargetRootFolder?** Como se explicó anteriormente, puede usar el parámetro **TargetRootFolder** para especificar una carpeta en la parte superior de la estructura de carpetas (también denominada la raíz) en el buzón de destino en el que se va a restaurar el contenido del buzón inactivo. Si no usa este parámetro, se combinan los elementos de buzón del buzón inactivo en las carpetas predeterminadas correspondientes del buzón de destino, y se vuelven a crear las carpetas personalizadas en la raíz del buzón de destino. Las siguientes ilustraciones resaltan las diferencias entre no usar y usar el parámetro **TargetRootFolder**.

  **Jerarquía de carpetas en el buzón de destino cuando no se usa el parámetro TargetRootFolder**

  ![Captura de pantalla cuando no se usa el parámetro TargetRootFolder.](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **Jerarquía de carpetas en el buzón de destino cuando se usa el parámetro TargetRootFolder**

  ![Captura de pantalla cuando se usa el parámetro TargetRootFolder.](../media/300da592-7323-48db-b8a4-07012259d113.png)
