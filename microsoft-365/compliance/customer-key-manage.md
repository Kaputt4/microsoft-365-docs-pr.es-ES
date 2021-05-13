---
title: Administrar clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Después de configurar la clave de cliente, aprenda a administrarla restaurando claves AKV y administrando permisos y creando y asignando directivas de cifrado de datos.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345063"
---
# <a name="manage-customer-key"></a>Administrar clave de cliente

Después de configurar la clave de cliente para Office 365, deberá crear y asignar una o más directivas de cifrado de datos (DEP). Una vez que haya asignado los DEP, puede administrar las claves como se describe en este artículo. Obtenga más información sobre la clave de cliente en los temas relacionados.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Crear un DEP para su uso con varias cargas de trabajo para todos los usuarios del espacio empresarial

Antes de comenzar, asegúrese de que ha completado las tareas necesarias para configurar Cliente. Para obtener información, vea [Configurar clave de cliente](customer-key-set-up.md). Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación. Para obtener información, vea [Obtener el URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

Para crear un DEP con varias cargas de trabajo, siga estos pasos:
  
1. En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

2. Para crear un DEP, use el cmdlet New-M365DataAtRestEncryptionPolicy.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Donde:

   - *PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, Contoso_Global.

   - *KeyVaultURI1* es el URI de la primera clave de la directiva. Por ejemplo, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* es el URI de la segunda clave de la directiva. Por ejemplo, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Separe los dos URI por una coma y un espacio.

   - *Descripción de* la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué es la directiva. Puede incluir espacios en la descripción. Por ejemplo, "Directiva raíz para varias cargas de trabajo para todos los usuarios del espacio empresarial".

Ejemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Asignar directiva de varias cargas de trabajo

Asigne el DEP mediante el cmdlet Set-M365DataAtRestEncryptionPolicyAssignment. Una vez que asigne la directiva, Microsoft 365 cifra los datos con la clave identificada en el DEP.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Donde *PolicyName* es el nombre de la directiva. Por ejemplo, Contoso_Global.

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Crear un DEP para su uso con Exchange Online buzones de correo

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault. Para obtener información, vea [Configurar clave de cliente](customer-key-set-up.md). Para completar estos pasos, conéctese de forma remota a Exchange Online con Windows PowerShell.

Un DEP está asociado con un conjunto de claves almacenadas en Azure Key Vault. Se asigna un DEP a un buzón en Microsoft 365. Microsoft 365 usará las claves identificadas en la directiva para cifrar el buzón. Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación. Para obtener información, vea [Obtener el URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

¡Recuerda! Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes. Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.

Para crear un DEP para usarlo con un buzón de correo, siga estos pasos:
  
1. En el equipo local, con una cuenta de trabajo o educativa que tenga permisos de administrador global o de administrador Exchange Online en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

2. Para crear un DEP, use New-DataEncryptionPolicy cmdlet escribiendo el siguiente comando.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Donde:

   - *PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes.

   - *Descripción de* la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué es la directiva. Puede incluir espacios en la descripción. Por ejemplo, "Clave raíz para buzones de correo en Estados Unidos y sus territorios".

   - *KeyVaultURI1* es el URI de la primera clave de la directiva. Por ejemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* es el URI de la segunda clave de la directiva. Por ejemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separe los dos URI por una coma y un espacio.

   Ejemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Asignar un DEP a un buzón

Asigne el DEP a un buzón mediante el cmdlet Set-Mailbox. Una vez que asigne la directiva, Microsoft 365 puede cifrar el buzón con la clave identificada en el DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailboxIdParameter* especifica un buzón de usuario. Para obtener más información acerca del cmdlet Set-Mailbox, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).

En entornos híbridos, puede asignar un DEP a los datos de buzones locales que se sincronizan con el Exchange Online inquilino. Para asignar un DEP a estos datos de buzones sincronizados, usará el cmdlet Set-MailUser correo. Para obtener más información acerca de los datos de buzones en el entorno híbrido, vea buzones locales con Outlook para iOS y Android con [autenticación moderna híbrida.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailUserIdParameter* especifica un usuario de correo (también conocido como usuario habilitado para correo). Para obtener más información acerca del cmdlet Set-MailUser, vea [Set-MailUser](/powershell/module/exchange/set-mailuser).

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Crear un DEP para su uso con SharePoint Online, OneDrive para la Empresa y Teams archivos

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault. Para obtener información, vea [Configurar clave de cliente](customer-key-set-up.md).
  
Para configurar la clave de cliente para SharePoint Online, OneDrive para la Empresa y Teams, realice estos pasos conectándose de forma remota a SharePoint Online con Windows PowerShell.
  
Asocie un DEP con un conjunto de claves almacenadas en Azure Key Vault. Se aplica un DEP a todos los datos en una ubicación geográfica, también denominada geo. Si usa la característica multigeográfica de Office 365, puede crear un DEP por geo con la capacidad de usar diferentes claves por geo. Si no usa multige geográficamente, puede crear un DEP en su organización para usarlo con SharePoint Online, OneDrive para la Empresa y Teams archivos. Microsoft 365 las claves identificadas en el DEP para cifrar los datos en esa ubicación geográfica. Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación. Para obtener información, vea [Obtener el URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).
  
¡Recuerda! Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes. Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.
  
1. En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, Conectar para SharePoint [PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).

2. En el Shell Microsoft Office SharePoint Online administración, ejecute el cmdlet Register-SPODataEncryptionPolicy de la siguiente manera:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Ejemplo:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Al registrar el DEP, el cifrado comienza en los datos de la geo. El cifrado puede tardar algo de tiempo. Para obtener más información sobre el uso de este parámetro, [vea Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Ver los DEP que ha creado para Exchange Online buzones de correo

Para ver una lista de todos los DEP que ha creado para buzones, use el cmdlet Get-DataEncryptionPolicy PowerShell.

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Para devolver todos los DEP de la organización, ejecute el cmdlet Get-DataEncryptionPolicy sin ningún parámetro.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obtener más información acerca del cmdlet Get-DataEncryptionPolicy, [vea Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Asignar un DEP antes de migrar un buzón a la nube

Al asignar el DEP, Microsoft 365 cifra el contenido del buzón mediante el DEP asignado durante la migración. Este proceso es más eficaz que migrar el buzón, asignar el DEP y, a continuación, esperar a que se realice el cifrado, que puede tardar horas o, posiblemente, días.

Para asignar un DEP a un buzón antes de migrarlo a Office 365, ejecute el cmdlet Set-MailUser en Exchange Online PowerShell:

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y *DataEncryptionPolicyIdParameter* es el identificador del DEP. Para obtener más información acerca del cmdlet Set-MailUser, vea [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar el DEP asignado a un buzón

Para determinar el DEP asignado a un buzón, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).
  
1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

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

Tanto si ha enrollado una clave de cliente, ha asignado un nuevo DEP o migrado un buzón, siga los pasos descritos en esta sección para asegurarse de que el cifrado se completa.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Comprobar que el cifrado se completa para Exchange Online buzones de correo

Cifrar un buzón puede tardar algún tiempo. Para el cifrado por primera vez, el buzón también debe moverse completamente de una base de datos a otra para que el servicio pueda cifrar el buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor **de true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado. El tiempo para completar los movimientos de buzones depende del número de buzones a los que asigne un DEP por primera vez y del tamaño de los buzones. Si los buzones no se han cifrado después de una semana desde el momento en que asignó el DEP, póngase en contacto con Microsoft.

El cmdlet New-MoveRequest ya no está disponible para los movimientos de buzones locales. Consulte este [anuncio para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obtener información adicional.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Comprobar que el cifrado se completa para SharePoint online, OneDrive para la Empresa y Teams archivos

Compruebe el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:

```PowerShell
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

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Obtener detalles sobre los DEP que usa con varias cargas de trabajo

Para obtener detalles sobre todos los DEP que ha creado para usar con varias cargas de trabajo, siga estos pasos:

1. En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

   - Para devolver la lista de todos los DEP de varias cargas de trabajo de la organización, ejecute este comando.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Para devolver detalles sobre un DEP específico, ejecute este comando. En este ejemplo se devuelve información detallada para el DEP denominado "Contoso_Global".

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Obtener información de asignación de DEP de varias cargas de trabajo

Para averiguar qué DEP está asignado actualmente a su inquilino, siga estos pasos. 

1. En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

2. Escriba este comando.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Deshabilitar un DEP de varias cargas de trabajo

Antes de deshabilitar un DEP de varias cargas de trabajo, desasigne el DEP de las cargas de trabajo del espacio empresarial. Para deshabilitar un DEP usado con varias cargas de trabajo, siga estos pasos:

1. En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

2. Ejecute el cmdlet Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Donde *PolicyName* es el nombre o identificador único de la directiva. Por ejemplo, Contoso_Global.

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

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

Hay varios cmdlets disponibles que permiten ver y, si es necesario, quitar permisos del almacén de claves. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo. Para cada una de estas tareas, usará Azure PowerShell. Para obtener información sobre Azure PowerShell, vea [Overview of Azure PowerShell](/powershell/azure/).

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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Revertir de clave de cliente a claves administradas de Microsoft

Si necesita volver a las claves administradas por Microsoft, puede hacerlo. Cuando se desaborde, los datos se vuelve a cifrar con el cifrado predeterminado admitido por cada carga de trabajo individual. Por ejemplo, Exchange Online cifrado predeterminado mediante claves administradas por Microsoft.

> [!IMPORTANT]
> El offboarding no es lo mismo que una purga de datos. Una purga de datos elimina de forma permanente los datos de la organización Microsoft 365, la eliminación de datos no se realiza. No puede realizar una purga de datos para una directiva de varias cargas de trabajo.

If you decide not to use Customer Key for assigning multi-workload DEP anymore, you'll need to reach out to Microsoft support with a request to "offboard" from Customer Key. Pida al equipo de soporte técnico que haga una solicitud de servicio Microsoft 365 equipo de clave de cliente. Llega a m365-ck@service.microsoft.com si tienes alguna pregunta.

Si ya no desea cifrar buzones individuales con DEP de nivel de buzón, puede desasignación de DEP de nivel de buzón de todos los buzones.

Para desasignación de DEP de buzones de correo, use el Set-Mailbox cmdlet de PowerShell.

1. Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

Al ejecutar este cmdlet, se desasoyó el DEP asignado actualmente y se vuelve a cifrar el buzón con el DEP asociado con las claves administradas por Microsoft predeterminadas. No puede desasignar el DEP usado por las claves administradas de Microsoft. Si no desea usar claves administradas por Microsoft, puede asignar otro DEP de clave de cliente al buzón.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocar las claves e iniciar el proceso de ruta de depuración de datos

Controle la revocación de todas las claves raíz, incluida la clave de disponibilidad. La clave de cliente proporciona el control del aspecto de la planeación de salida de los requisitos normativos. Si decide revocar las claves para purgar los datos y salir del servicio, el servicio elimina la clave de disponibilidad una vez completado el proceso de depuración de datos. Esto es compatible con los DEP de clave de cliente que están asignados a buzones individuales.

Microsoft 365 auditorías y valida la ruta de depuración de datos. Para obtener más información, vea el informe SSAE 18 SOC 2 disponible en [el Portal de confianza de servicio](https://servicetrust.microsoft.com/). Además, Microsoft recomienda los siguientes documentos:

- [Guía de evaluación y cumplimiento de riesgos para instituciones financieras en Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Consideraciones sobre la planeación de salida de O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

La depuración de DEP de varias cargas de trabajo no se admite Microsoft 365 clave de cliente. El DEP de varias cargas de trabajo se usa para cifrar datos en varias cargas de trabajo en todos los usuarios del espacio empresarial. La depuración de este DEP daría como resultado que los datos de varias cargas de trabajo se vuelvan inaccesibles. Si decide salir de Microsoft 365 servicios, podría seguir la ruta de eliminación del espacio empresarial por el proceso documentado. Vea [cómo eliminar un inquilino en Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revocar las claves de cliente y la clave de disponibilidad para Exchange Online y Skype Empresarial

Al iniciar la ruta de depuración de datos para Exchange Online y Skype Empresarial, se establece una solicitud de purga de datos permanente en un DEP. Al hacerlo, se eliminan permanentemente los datos cifrados dentro de los buzones a los que está asignado ese DEP.

Dado que solo puede ejecutar el cmdlet de PowerShell en un DEP a la vez, considere la posibilidad de reasignar un solo DEP a todos los buzones antes de iniciar la ruta de depuración de datos.

> [!WARNING]
> No use la ruta de depuración de datos para eliminar un subconjunto de los buzones. Este proceso solo está pensado para los clientes que salen del servicio.

Para iniciar la ruta de depuración de datos, siga estos pasos:

1. Quite los permisos de ajuste y desenvolver para "O365 Exchange Online" de Azure Key Vaults.

2. Con una cuenta profesional o educativa que tenga privilegios de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

3. Para cada DEP que contenga buzones que desee eliminar, ejecute el cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) de la siguiente manera.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Si se produce un error en el comando, asegúrese de que ha quitado los permisos de Exchange Online de ambas claves en Azure Key Vault, tal como se especificó anteriormente en esta tarea.Una vez que haya establecido el modificador PermanentDataPurgeRequested mediante el cmdlet Set-DataEncryptionPolicy, ya no podrá asignar este DEP a los buzones.

4. Póngase en contacto con el soporte técnico de Microsoft y solicite el eDocument de purga de datos.

    A su solicitud, Microsoft le envía un documento legal para confirmar y autorizar la eliminación de datos. La persona de la organización que se inscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento. Normalmente, se trata de una persona ejecutiva u otra persona designada en su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.

5. Una vez que el representante haya firmado el documento legal, descóyalo a Microsoft (normalmente a través de una firma de eDoc).

    Una vez que Microsoft recibe el documento legal, Microsoft ejecuta cmdlets para desencadenar la purga de datos que elimina primero la directiva, marca los buzones para su eliminación permanente y, a continuación, elimina la clave de disponibilidad. Una vez completado el proceso de purga de datos, los datos se han purgado, no se puede Exchange Online y no se pueden recuperar.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Revocar las claves de cliente y la clave de disponibilidad para SharePoint Online, OneDrive para la Empresa y Teams archivos

Para iniciar la ruta de depuración de datos para SharePoint Online, OneDrive para la Empresa y Teams, siga estos pasos:

1. Revocar el acceso a Azure Key Vault. Todos los administradores del almacén de claves deben aceptar revocar el acceso.

   No elimina Azure Key Vault para SharePoint Online. Los almacenes de claves pueden compartirse entre varios SharePoint inquilinos y DEP en línea.

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