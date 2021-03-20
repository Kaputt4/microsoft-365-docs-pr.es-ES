---
title: Administrar clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Después de configurar la clave de cliente, aprenda a administrarla restaurando claves AKV y administrando permisos y directivas de cifrado de datos.
ms.openlocfilehash: 8f55667254ce7f5cbd9d4de274623ca4a3c4aa9d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909952"
---
# <a name="manage-customer-key"></a>Administrar clave de cliente

Después de configurar la clave de cliente para Office 365, puede administrar las claves como se describe en este artículo. Obtenga más información sobre la clave de cliente en los temas relacionados.

## <a name="restore-azure-key-vault-keys"></a>Restaurar claves de Azure Key Vault

Antes de realizar una restauración, use las capacidades de recuperación proporcionadas por la eliminación suave. Todas las claves que se usan con la clave de cliente son necesarias para tener habilitada la eliminación suave. La eliminación suave actúa como una papelera de reciclaje y permite la recuperación durante un máximo de 90 días sin necesidad de restaurar. La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves. Si debe restaurar una clave para su uso con la clave de cliente, en Azure PowerShell, ejecute el cmdlet Restore-AzureKeyVaultKey de la siguiente manera:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Por ejemplo:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Si el almacén de claves ya contiene una clave con el mismo nombre, se produce un error en la operación de restauración. Restore-AzKeyVaultKey restaura todas las versiones de clave y todos los metadatos de la clave, incluido el nombre de la clave.
  
## <a name="manage-key-vault-permissions"></a>Administrar permisos del almacén de claves

Hay varios cmdlets disponibles que permiten ver y, si es necesario, quitar permisos del almacén de claves. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo. Para cada una de estas tareas, usará Azure PowerShell. Para obtener información sobre Azure Powershell, vea [Overview of Azure PowerShell](/powershell/azure/).

Para ver los permisos del almacén de claves, ejecute el cmdlet Get-AzKeyVault clave.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Por ejemplo:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Para quitar los permisos de un administrador, ejecute el cmdlet Remove-AzKeyVaultAccessPolicy:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Por ejemplo:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Administrar directivas de cifrado de datos (DEP) con clave de cliente

La clave de cliente controla los DEP de forma diferente entre los distintos servicios. Por ejemplo, puede crear un número diferente de DEP para los diferentes servicios.

**Exchange Online y Skype Empresarial:** Puede crear hasta 50 DEP. Para obtener instrucciones, vea [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**Archivos de SharePoint Online, OneDrive para la Empresa y Teams:** Un DEP se aplica a los datos de una ubicación geográfica, también denominada _geo_. Si usa la característica multige geográfica de Office 365, puede crear un DEP por geo. Si no está usando multige-geo, puede crear un DEP. Normalmente, se crea el DEP al configurar la clave de cliente. Para obtener instrucciones, vea [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Ver los DEP que ha creado para Exchange Online y Skype Empresarial

Para ver una lista de todos los DEP que ha creado para Exchange Online y Skype Empresarial mediante el cmdlet Get-DataEncryptionPolicy PowerShell, siga estos pasos.

1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Para devolver todos los DEP de la organización, ejecute el cmdlet Get-DataEncryptionPolicy sin ningún parámetro.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obtener más información acerca del cmdlet Get-DataEncryptionPolicy, [vea Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Asignar un DEP antes de migrar un buzón a la nube

Al asignar el DEP, Microsoft 365 cifra el contenido del buzón mediante el DEP asignado durante la migración. Este proceso es más eficaz que migrar el buzón, asignar el DEP y, a continuación, esperar a que se realice el cifrado, que puede tardar horas o, posiblemente, días.

Para asignar un DEP a un buzón antes de migrarlo a Office 365, ejecute el cmdlet Set-MailUser exchange Online PowerShell:

1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y *DataEncryptionPolicyIdParameter* es el identificador del DEP. Para obtener más información acerca del cmdlet Set-MailUser, vea [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar el DEP asignado a un buzón

Para determinar el DEP asignado a un buzón, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).
  
1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y DataEncryptionPolicyID devuelve el GUID del DEP. Para obtener más información acerca del cmdlet Get-MailboxStatistics, vea [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).
  
2. Ejecute el cmdlet Get-DataEncryptionPolicy para averiguar el nombre descriptivo del DEP al que está asignado el buzón.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Donde *GUID* es el GUID devuelto por el cmdlet Get-MailboxStatistics en el paso anterior.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Comprobar que la clave de cliente ha finalizado el cifrado

Tanto si acaba de implementar una clave de cliente, asignó un nuevo DEP o migró un buzón, siga los pasos descritos en esta sección para asegurarse de que el cifrado se completa.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Comprobar que el cifrado se completa para Exchange Online y Skype Empresarial

Cifrar un buzón puede tardar algún tiempo. Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar un DEP o la primera vez que asigne un DEP a un buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor **de true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado.

El tiempo para completar los movimientos del buzón depende del tamaño del buzón. Si la clave de cliente no ha cifrado completamente el buzón después de 72 horas desde el momento en que asigna un nuevo DEP, póngase en contacto con el soporte técnico de Microsoft para obtener ayuda. El cmdlet New-MoveRequest ya no está disponible para los movimientos de buzones locales. Consulte este [anuncio para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obtener información adicional.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Comprobar que el cifrado se completa para los archivos de SharePoint Online, OneDrive para la Empresa y Teams

Compruebe el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

El resultado de este cmdlet incluye:
  
- Uri de la clave principal.

- Uri de la clave secundaria.

- El estado de cifrado de la geo. Los estados posibles incluyen:

  - **Sin registrar:** El cifrado de clave de cliente aún no se ha aplicado.

  - **Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos están en proceso de cifrado. Si la clave de la geo se está registrando, también se mostrará información sobre qué porcentaje de sitios de la geo están completos para que pueda supervisar el progreso del cifrado.

  - **Registrado:** Se ha aplicado el cifrado de clave de cliente y se han cifrado todos los archivos de todos los sitios.

  - **Rolling:** Hay un lanzamiento de teclas en curso. Si la clave de la geo se está implementando, también se mostrará información sobre el porcentaje de sitios que han completado la operación de lanzamiento de teclas para poder supervisar el progreso.

## <a name="unassign-a-dep-from-a-mailbox"></a>Unassign a DEP from a mailbox

Se desasigna un DEP de un buzón mediante el cmdlet Set-mailbox PowerShell y se establece `DataEncryptionPolicy` el valor en `$NULL` . Al ejecutar este cmdlet, se desasigna el DEP asignado actualmente y se vuelve a cifrar el buzón con el DEP asociado con las claves administradas predeterminadas de Microsoft. No puede desasignar el DEP usado por las claves administradas de Microsoft. Si no desea usar claves administradas de Microsoft, puede asignar otro DEP al buzón.

Para desasignar el DEP de un buzón mediante el cmdlet Set-Mailbox PowerShell, siga estos pasos.

1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocar las claves e iniciar el proceso de ruta de depuración de datos

Controle la revocación de todas las claves raíz, incluida la clave de disponibilidad. La clave de cliente proporciona el control del aspecto de la planeación de salida de los requisitos normativos. Si decide revocar las claves para purgar los datos y salir del servicio, el servicio elimina la clave de disponibilidad una vez completado el proceso de depuración de datos.

Microsoft 365 audita y valida la ruta de depuración de datos. Para obtener más información, vea el informe SSAE 18 SOC 2 disponible en [el Portal de confianza de servicio](https://servicetrust.microsoft.com/). Además, Microsoft recomienda los siguientes documentos:

- [Guía de evaluación y cumplimiento de riesgos para instituciones financieras en Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Consideraciones sobre la planeación de salida de O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

La ruta de depuración de datos difiere ligeramente entre los diferentes servicios.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revocar las claves de cliente y la clave de disponibilidad para Exchange Online y Skype Empresarial

Al iniciar la ruta de depuración de datos para Exchange Online y Skype Empresarial, se establece una solicitud de purga de datos permanente en un DEP. Al hacerlo, se eliminan permanentemente los datos cifrados dentro de los buzones a los que está asignado ese DEP.

Dado que solo puede ejecutar el cmdlet de PowerShell en un DEP a la vez, considere la posibilidad de reasignar un solo DEP a todos los buzones antes de iniciar la ruta de depuración de datos.

> [!WARNING]
> No use la ruta de depuración de datos para eliminar un subconjunto de los buzones. Este proceso solo está pensado para los clientes que salen del servicio.

Para iniciar la ruta de depuración de datos, siga estos pasos:

1. Quite los permisos de ajuste y desenvuelto para "O365 Exchange Online" de Azure Key Vaults.

2. Con una cuenta profesional o educativa que tenga privilegios de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

3. Para cada DEP que contenga buzones que desee eliminar, ejecute el cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) de la siguiente manera.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Si se produce un error en el comando, asegúrese de que ha quitado los permisos de Exchange Online de ambas claves en Azure Key Vault, tal como se especificó anteriormente en esta tarea.Una vez que haya establecido el modificador PermanentDataPurgeRequested mediante el cmdlet Set-DataEncryptionPolicy, ya no podrá asignar este DEP a los buzones.

4. Póngase en contacto con el soporte técnico de Microsoft y solicite el eDocument de purga de datos.

    A su solicitud, Microsoft le envía un documento legal para confirmar y autorizar la eliminación de datos. La persona de la organización que se inscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento. Normalmente, se trata de una persona ejecutiva u otra persona designada en su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.

5. Una vez que el representante haya firmado el documento legal, descóyalo a Microsoft (normalmente a través de una firma de eDoc).

    Una vez que Microsoft recibe el documento legal, Microsoft ejecuta cmdlets para desencadenar la purga de datos que elimina primero la directiva, marca los buzones para su eliminación permanente y, a continuación, elimina la clave de disponibilidad. Una vez completado el proceso de purga de datos, los datos se han purgado, no se puede obtener acceso a Exchange Online y no se pueden recuperar.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Revocar las claves de cliente y la clave de disponibilidad de los archivos de SharePoint Online, OneDrive para la Empresa y Teams

Para iniciar la ruta de depuración de datos para archivos de SharePoint Online, OneDrive para la Empresa y Teams, siga estos pasos:

1. Revocar el acceso a Azure Key Vault. Todos los administradores del almacén de claves deben aceptar revocar el acceso.

   No se elimina Azure Key Vault para SharePoint Online. Los almacenes de claves pueden compartirse entre varios inquilinos y DEP de SharePoint Online.

2. Póngase en contacto con Microsoft para eliminar la clave de disponibilidad.

    Cuando se contacte con Microsoft para eliminar la clave de disponibilidad, le enviaremos un documento legal. La persona de la organización que se inscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento. Normalmente, se trata de una persona ejecutiva u otra persona designada en su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.

3. Una vez que el representante firme el documento legal, descóyalo a Microsoft (normalmente a través de una firma de eDoc).

   Una vez que Microsoft recibe el documento legal, ejecutamos cmdlets para desencadenar la purga de datos que realiza la eliminación de criptografía de la clave de inquilino, la clave de sitio y todas las claves individuales por documento, lo que rompe irrevocablemente la jerarquía de claves. Una vez completados los cmdlets de purga de datos, los datos se han purgado.

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Obtenga información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Configurar clave de cliente](customer-key-set-up.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Caja de seguridad del cliente](customer-lockbox-requests.md)

- [Cifrado de servicio](office-365-service-encryption.md)