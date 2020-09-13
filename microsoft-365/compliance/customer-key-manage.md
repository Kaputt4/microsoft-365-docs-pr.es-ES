---
title: Administrar la clave de cliente
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
description: Una vez configurada la clave de cliente, obtenga información sobre cómo administrarla mediante la restauración de claves de AKV y la administración de permisos y las directivas de cifrado de datos.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547090"
---
# <a name="manage-customer-key"></a>Administrar la clave de cliente

Una vez configurada la clave de cliente para Office 365, puede administrar las claves tal como se describe en este artículo. Obtenga más información acerca de la clave de cliente en los temas relacionados.

## <a name="restore-azure-key-vault-keys"></a>Restaurar claves de Azure Key Vault

Antes de realizar una restauración, use las capacidades de recuperación proporcionadas por la eliminación temporal. Todas las claves que se usan con la clave de cliente deben tener habilitada la eliminación temporal. La eliminación temporal actúa como una papelera de reciclaje y permite la recuperación de hasta 90 días sin necesidad de restaurarla. La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves. Si necesita restaurar una clave para usarla con la clave de cliente, en Azure PowerShell, ejecute el cmdlet restore-AzureKeyVaultKey de la siguiente manera:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Por ejemplo:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Si el almacén de claves ya contiene una clave con el mismo nombre, se producirá un error en la operación de restauración. Restore-AzKeyVaultKey restaura todas las versiones principales y todos los metadatos de la clave, incluido el nombre de la clave.
  
## <a name="manage-key-vault-permissions"></a>Administrar permisos de almacén de claves

Hay disponibles varios cmdlets que permiten ver y, si es necesario, quitar permisos de almacén de clave. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo. Para cada una de estas tareas, usará Azure PowerShell. Para obtener información sobre Azure PowerShell, vea [información general sobre Azure PowerShell](https://docs.microsoft.com/powershell/azure/).

Para ver los permisos de almacén de clave, ejecute el cmdlet Get-AzKeyVault.

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

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Administración de directivas de cifrado de datos (DEPs) con clave de cliente

La clave de cliente administra DEPs de forma diferente entre los distintos servicios. Por ejemplo, puede crear un número diferente de DEPs para los distintos servicios.

**Exchange Online y Skype empresarial:** Puede crear hasta 50 DEPs. Para obtener instrucciones, consulte [crear una directiva de cifrado de datos (DEP) para usarla con Exchange Online y Skype empresarial](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**Archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams:** Un DEP se aplica a los datos en una ubicación geográfica, también denominada _geo_. Si usa la característica multigeográfica de Office 365, puede crear un DEP por geo. Si no usa la función multigeográfica, puede crear un DEP. Normalmente, el DEP se crea al configurar la clave de cliente. Para obtener instrucciones, vea [crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Ver el DEPs que ha creado para Exchange Online y Skype empresarial

Para ver una lista de todos los DEPs que ha creado para Exchange Online y Skype empresarial mediante el cmdlet Get-DataEncryptionPolicy de PowerShell, siga estos pasos.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Para devolver todos los DEPs de la organización, ejecute el cmdlet Get-DataEncryptionPolicy sin ningún parámetro.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obtener más información sobre el cmdlet Get-DataEncryptionPolicy, consulte [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Asignar un DEP antes de migrar un buzón a la nube

Cuando se asigna la DEP, Microsoft 365 cifra el contenido del buzón con la DEP asignada durante la migración. Este proceso es más eficaz que migrar el buzón, asignar el DEP y, a continuación, esperar a que se produzca el cifrado, lo que puede tardar horas o posiblemente días.

Para asignar una DEP a un buzón antes de migrarla a Office 365, ejecute el cmdlet Set-MailUser en Exchange Online PowerShell:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y *DATAENCRYPTIONPOLICYIDPARAMETER* es el identificador de la DEP. Para obtener más información sobre el cmdlet Set-MailUser, consulte [set-mailuser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinación de la DEP asignada a un buzón

Para determinar la DEP asignada a un buzón, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón de correo y DataEncryptionPolicyID devuelve el GUID de la DEP. Para obtener más información acerca del cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).
  
2. Ejecute el cmdlet Get-DataEncryptionPolicy para averiguar el nombre descriptivo de la DEP a la que está asignado el buzón.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Donde *GUID* es el GUID que devuelve el cmdlet Get-MailboxStatistics en el paso anterior.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Comprobar que la clave de cliente ha finalizado el cifrado

Tanto si acaba de realizar una clave de cliente, se le ha asignado una nueva DEP o ha migrado un buzón de correo, siga los pasos de esta sección para asegurarse de que se complete el cifrado.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Comprobar que el cifrado se complete para Exchange Online y Skype empresarial

El cifrado de un buzón puede tardar algún tiempo. Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar una DEP o la primera vez que asigna un DEP a un buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor **true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado.

El tiempo para completar los movimientos de buzones depende del tamaño del buzón. Si la clave de cliente no ha cifrado completamente el buzón de correo después de 72 horas desde el momento en que asigna un nuevo DEP, póngase en contacto con el soporte técnico de Microsoft para obtener ayuda. El cmdlet New-MoveRequest ya no está disponible para los movimientos de buzones locales. Consulte [este anuncio](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) para obtener información adicional.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Comprobar que se ha completado el cifrado para los archivos de SharePoint Online, OneDrive para la empresa y Teams

Compruebe el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

El resultado de este cmdlet incluye:
  
- URI de la clave principal.

- URI de la clave secundaria.

- El estado de cifrado de la geografía. Los Estados posibles son:

  - No **registrado:** Aún no se ha aplicado el cifrado de clave de cliente.

  - **Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos se encuentran en proceso de cifrado. Si se está registrando la clave de la geografía, también se mostrará la información sobre el porcentaje de sitios de la geografía que se completa para que pueda supervisar el progreso del cifrado.

  - **Registrado:** Se ha aplicado el cifrado de clave de cliente y todos los archivos de todos los sitios se han cifrado.

  - **Desplazamiento:** Hay un lanzamiento de clave en curso. Si la clave de la geo está girando, también se mostrará información sobre el porcentaje de sitios que han completado la operación de desplazamiento de claves para que pueda supervisar el progreso.

## <a name="unassign-a-dep-from-a-mailbox"></a>Cancelar la asignación de un DEP de un buzón

Puede quitar la asignación de un DEP de un buzón mediante el cmdlet Set-Mailbox PowerShell y establecer el `DataEncryptionPolicy` en `$NULL` . Al ejecutar este cmdlet, se anula la asignación del DEP asignado actualmente y se vuelve a cifrar el buzón con el DEP asociado a las claves administradas predeterminadas de Microsoft. No puede cancelar la asignación de la DEP usada por las claves administradas de Microsoft. Si no desea usar las claves administradas de Microsoft, puede asignar otro DEP al buzón.

Para cancelar la asignación de DEP de un buzón mediante el cmdlet Set-Mailbox PowerShell, siga estos pasos.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocar las claves e iniciar el proceso de la ruta de depuración de datos

Puede controlar la revocación de todas las claves raíz, incluida la clave de disponibilidad. La clave de cliente proporciona el control del aspecto de la planeación de salida de los requisitos normativos. Si decide revocar las claves para purgar los datos y salir del servicio, el servicio elimina la clave de disponibilidad una vez que finaliza el proceso de depuración de datos.

Microsoft 365 audita y valida la ruta de acceso de depuración de datos. Para obtener más información, vea el informe de SOC 2 de SSAE 18 disponible en el [portal de confianza del servicio](https://servicetrust.microsoft.com/). Además, Microsoft recomienda los siguientes documentos:

- [Guía de cumplimiento y evaluación de riesgos para instituciones financieras en la nube de Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Consideraciones de planeación de salida de O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

La ruta de acceso de la depuración de datos difiere ligeramente entre los diferentes servicios.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revocar las claves de cliente y la clave de disponibilidad para Exchange Online y Skype empresarial

Cuando se inicia la ruta de acceso de depuración de datos para Exchange Online y Skype empresarial, se establece una solicitud de depuración de datos permanente en un DEP. Al hacerlo, se eliminan de forma permanente los datos cifrados de los buzones a los que está asignada DEP.

Como solo puede ejecutar el cmdlet de PowerShell con un DEP a la vez, considere la posibilidad de reasignar un único DEP a todos los buzones antes de iniciar la ruta de acceso de depuración de datos.

> [!WARNING]
> No use la ruta de acceso de purga de datos para eliminar un subconjunto de los buzones. Este proceso solo está destinado a los clientes que están saliendo del servicio.

Para iniciar la ruta de acceso de depuración de datos, siga estos pasos:

1. Quite los permisos de ajuste y desajuste para "O365 Exchange Online" de Azure Key Vaults.

2. Con una cuenta profesional o educativa con privilegios de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

3. Para cada DEP que contiene buzones de correo que desea eliminar, ejecute el cmdlet [set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) de la siguiente manera.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Si se produce un error en el comando, asegúrese de que ha quitado los permisos de Exchange online de las dos claves en Azure Key Vault como se especificó anteriormente en esta tarea.Una vez que haya establecido el conmutador PermanentDataPurgeRequested con el cmdlet Set-DataEncryptionPolicy, ya no podrá asignar este DEP a los buzones.

4. Póngase en contacto con el soporte técnico de Microsoft y solicite la depuración de datos eDocument.

    En su solicitud, Microsoft le envía un documento legal para confirmar y autorizar la eliminación de datos. La persona de la organización que se registró como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento. Normalmente, se trata de un ejecutivo u otra persona designada en su empresa, legalmente autorizada para firmar el papeleo en nombre de su organización.

5. Una vez que el representante haya firmado el documento legal, devuelvalo a Microsoft (normalmente a través de una firma de eDoc).

    Una vez que Microsoft recibe el documento legal, ejecuta cmdlets para desencadenar la depuración de datos que primero elimina la Directiva, marca los buzones de correo para su eliminación permanente y, a continuación, elimina la clave de disponibilidad. Una vez que finaliza el proceso de depuración de datos, los datos se han purgado, son inaccesibles para Exchange Online y no se pueden recuperar.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Revocar las claves de cliente y la clave de disponibilidad para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams

Para iniciar la ruta de acceso de depuración de datos para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, siga estos pasos:

1. Revocar el acceso a la bóveda de claves de Azure. Todos los administradores de la bóveda clave deben aceptar el acceso para revocar el acceso.

   No se elimina el almacén de claves de Azure para SharePoint Online. Los almacenes clave se pueden compartir entre varios inquilinos de SharePoint Online y DEPs.

2. Póngase en contacto con Microsoft para eliminar la clave de disponibilidad.

    Cuando se ponga en contacto con Microsoft para eliminar la clave Availability, le enviaremos un documento legal. La persona de la organización que se registró como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento. Normalmente, se trata de un ejecutivo u otra persona designada en su empresa, legalmente autorizada para firmar el papeleo en nombre de su organización.

3. Una vez que el representante firme el documento legal, devuelva el documento a Microsoft (normalmente a través de una firma de eDoc).

   Una vez que Microsoft recibe el documento legal, ejecutamos cmdlets para desencadenar la depuración de datos que realiza la eliminación de cifrado de la clave de inquilino, la clave de sitio y todas las claves individuales por documento, rompiendo de una jerarquía de claves de una vez irrevocable. Una vez que se completen los cmdlets de depuración de datos, se purgarán los datos.

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Obtener información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Configurar la clave de cliente](customer-key-set-up.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Caja de seguridad del cliente](customer-lockbox-requests.md)

- [Cifrado de servicio](office-365-service-encryption.md)
