---
title: Administrar clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Después de configurar la clave de cliente, obtenga información sobre cómo administrarla mediante la restauración de claves akv y la administración de permisos y la creación y asignación de directivas de cifrado de datos.
ms.openlocfilehash: 0ca6aa1e2cf725359d74477b486a4763a35ba681
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465918"
---
# <a name="manage-customer-key"></a>Administrar clave de cliente

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Después de configurar la clave de cliente, deberá crear y asignar una o varias directivas de cifrado de datos (DEP). Una vez que haya asignado los DEP, puede administrar las claves como se describe en este artículo. Obtenga más información sobre la clave de cliente en los temas relacionados.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Creación de un DEP para su uso con varias cargas de trabajo para todos los usuarios del inquilino

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar la clave de cliente. Para obtener información, consulte [Configuración de la clave de cliente](customer-key-set-up.md). Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación. Para obtener información, consulte [Obtención del URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

Para crear un DEP de varias cargas de trabajo, siga estos pasos:
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global o administrador de cumplimiento en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana de Windows PowerShell.

2. Para crear un DEP, use el cmdlet New-M365DataAtRestEncryptionPolicy.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Donde:

   - *PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, Contoso_Global.

   - *KeyVaultURI1* es el URI de la primera clave de la directiva. Por ejemplo, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* es el URI de la segunda clave de la directiva. Por ejemplo, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Separe los dos URI por una coma y un espacio.

   - *Descripción* de la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué sirve la directiva. Puede incluir espacios en la descripción. Por ejemplo, "Directiva raíz para varias cargas de trabajo para todos los usuarios del inquilino".

Ejemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Asignación de directivas de varias cargas de trabajo

Asigne el DEP mediante el cmdlet Set-M365DataAtRestEncryptionPolicyAssignment. Una vez que asigne la directiva, Microsoft 365 cifra los datos con la clave identificada en el DEP.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Donde *PolicyName* es el nombre de la directiva. Por ejemplo, Contoso_Global.

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Creación de un DEP para su uso con buzones de Exchange Online

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault. Para obtener información, consulte [Configuración de la clave de cliente](customer-key-set-up.md). Para completar estos pasos, conéctese de forma remota a Exchange Online con Windows PowerShell.

Un DEP está asociado a un conjunto de claves almacenadas en Azure Key Vault. Asigne un DEP a un buzón de Microsoft 365. Microsoft 365 usará las claves identificadas en la directiva para cifrar el buzón. Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación. Para obtener información, consulte [Obtención del URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

¡Recordar! Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes. Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.

Para crear un DEP que se usará con un buzón de correo, siga estos pasos:
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global o de administrador Exchange Online en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana de Windows PowerShell.

2. Para crear un DEP, escriba el siguiente comando para usar el cmdlet New-DataEncryptionPolicy.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Donde:

   - *PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes.

   - *Descripción* de la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué sirve la directiva. Puede incluir espacios en la descripción. Por ejemplo, "Clave raíz para buzones en EE. UU. y sus territorios".

   - *KeyVaultURI1* es el URI de la primera clave de la directiva. Por ejemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* es el URI de la segunda clave de la directiva. Por ejemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separe los dos URI por una coma y un espacio.

   Ejemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Asignación de un DEP a un buzón

Asigne el DEP a un buzón mediante el cmdlet Set-Mailbox. Una vez que asigne la directiva, Microsoft 365 puede cifrar el buzón con la clave identificada en el DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailboxIdParameter* especifica un buzón de usuario. Para obtener más información sobre el cmdlet Set-Mailbox, consulte [Set-Mailbox](/powershell/module/exchange/set-mailbox).

En entornos híbridos, puede asignar un DEP a los datos de buzón de correo local que se sincronizan en el inquilino de Exchange Online. Para asignar un DEP a estos datos de buzón sincronizados, usará el cmdlet Set-MailUser. Para obtener más información sobre los datos de buzón en el entorno híbrido, consulte [Buzones locales que usan Outlook para iOS y Android con autenticación moderna híbrida](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailUserIdParameter* especifica un usuario de correo (también conocido como usuario habilitado para correo). Para obtener más información sobre el cmdlet Set-MailUser, consulte [Set-MailUser](/powershell/module/exchange/set-mailuser).

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Creación de un DEP para su uso con archivos SharePoint Online, OneDrive para la Empresa y Teams

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault. Para obtener información, consulte [Configuración de la clave de cliente](customer-key-set-up.md).
  
Para configurar la clave de cliente para SharePoint archivos en línea, OneDrive para la Empresa y Teams, complete estos pasos mediante la conexión remota a SharePoint Online con Windows PowerShell.
  
Un DEP se asocia a un conjunto de claves almacenadas en Azure Key Vault. Se aplica un DEP a todos los datos de una ubicación geográfica, también denominada geoárea. Si usa la característica multigeográfica de Office 365, puede crear un DEP por geo con la capacidad de usar claves diferentes por geo. Si no usa multigeográfica, puede crear un DEP en su organización para usarlo con archivos de SharePoint Online, OneDrive para la Empresa y Teams. Microsoft 365 usa las claves identificadas en el DEP para cifrar los datos de esa ubicación geográfica. Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación. Para obtener información, consulte [Obtención del URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).
  
¡Recordar! Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes. Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conectar para SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).

2. En el shell de administración de Microsoft Office SharePoint Online, ejecute el cmdlet Register-SPODataEncryptionPolicy de la siguiente manera:

   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Ejemplo:
  
   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a'
   ```

   Al registrar el DEP, el cifrado comienza en los datos de la ubicación geográfica. El cifrado puede tardar algún tiempo. Para obtener más información sobre el uso de este parámetro, vea [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Ver los DEP que ha creado para los buzones de Exchange Online

Para ver una lista de todos los DEP que ha creado para los buzones de correo, use el cmdlet de PowerShell Get-DataEncryptionPolicy.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Para devolver todos los DEP de la organización, ejecute el cmdlet Get-DataEncryptionPolicy sin ningún parámetro.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Para obtener más información sobre el cmdlet Get-DataEncryptionPolicy, consulte [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Asignar un DEP antes de migrar un buzón a la nube

Al asignar el DEP, Microsoft 365 cifra el contenido del buzón mediante el DEP asignado durante la migración. Este proceso es más eficaz que migrar el buzón de correo, asignar el DEP y, a continuación, esperar a que se produzca el cifrado, lo que puede tardar horas o posiblemente días.

Para asignar un DEP a un buzón antes de migrarlo a Office 365, ejecute el cmdlet Set-MailUser en Exchange Online PowerShell:

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-MailUser.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y *DataEncryptionPolicyIdParameter* es el identificador del DEP. Para obtener más información sobre el cmdlet Set-MailUser, consulte [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinación del DEP asignado a un buzón

Para determinar el DEP asignado a un buzón de correo, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y DataEncryptionPolicyID devuelve el GUID del DEP. Para obtener más información sobre el cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).
  
2. Ejecute el cmdlet Get-DataEncryptionPolicy para averiguar el nombre descriptivo del DEP al que está asignado el buzón.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Donde *GUID* es el GUID devuelto por el cmdlet Get-MailboxStatistics en el paso anterior.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Comprobación de que la clave de cliente ha finalizado el cifrado

Tanto si ha inscrito una clave de cliente, ha asignado un nuevo DEP como si ha migrado un buzón de correo, siga los pasos de esta sección para asegurarse de que se completa el cifrado.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Comprobación de que el cifrado se completa para los buzones de Exchange Online

El cifrado de un buzón de correo puede tardar algún tiempo. Para el cifrado por primera vez, el buzón también debe moverse completamente de una base de datos a otra para que el servicio pueda cifrar el buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si se cifra un buzón de correo.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor de **true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado. El tiempo para completar los movimientos de buzón depende del número de buzones a los que se asigna un DEP por primera vez y del tamaño de los buzones. Si los buzones no se han cifrado después de una semana desde el momento en que asignó el DEP, póngase en contacto con Microsoft.

El cmdlet New-MoveRequest ya no está disponible para los movimientos de buzón local. Consulte [este anuncio](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) para obtener información adicional.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Comprobación de que el cifrado se completa para SharePoint archivos en línea, OneDrive para la Empresa y Teams

Compruebe el estado del cifrado mediante la ejecución del cmdlet Get-SPODataEncryptionPolicy como se indica a continuación:

```PowerShell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
```

La salida de este cmdlet incluye:
  
- URI de la clave principal.

- Uri de la clave secundaria.

- Estado de cifrado de la ubicación geográfica. Los posibles estados incluyen:

  - **No registrado:** Todavía no se ha aplicado el cifrado de clave de cliente.

  - **Registrar:** Se ha aplicado el cifrado de clave de cliente y los archivos están en proceso de cifrado. Si la clave de la geoárea se está registrando, también se mostrará información sobre qué porcentaje de sitios de la ubicación geográfica se completa para que pueda supervisar el progreso del cifrado.

  - **Registrado:** Se ha aplicado el cifrado de clave de cliente y se han cifrado todos los archivos de todos los sitios.

  - **Balanceo:** Hay una lista de claves en curso. Si la clave de la geoárea está gradual, también se mostrará información sobre el porcentaje de sitios que han completado la operación de puesta en marcha de claves para que pueda supervisar el progreso.

- También generará el porcentaje de sitios incorporados.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Obtenga detalles sobre los DEP que usa con varias cargas de trabajo.

Para obtener detalles sobre todos los DEP que ha creado para usarlos con varias cargas de trabajo, complete estos pasos:

1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global o administrador de cumplimiento en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana de Windows PowerShell.

   - Para devolver la lista de todos los DEP de varias cargas de trabajo de la organización, ejecute este comando.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Para devolver detalles sobre un DEP específico, ejecute este comando. En este ejemplo se devuelve información detallada del DEP denominado "Contoso_Global".

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Obtención de información de asignación de DEP de varias cargas de trabajo

Para averiguar qué DEP está asignado actualmente al inquilino, siga estos pasos. 

1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global o administrador de cumplimiento en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana de Windows PowerShell.

2. Escriba este comando.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Deshabilitación de un DEP de varias cargas de trabajo

Antes de deshabilitar un DEP de varias cargas de trabajo, quite la asignación del DEP de las cargas de trabajo del inquilino. Para deshabilitar un DEP usado con varias cargas de trabajo, complete estos pasos:

1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global o administrador de cumplimiento en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana de Windows PowerShell.

2. Ejecute el cmdlet Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Donde *PolicyName* es el nombre o identificador único de la directiva. Por ejemplo, Contoso_Global.

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Restauración de claves de Azure Key Vault

Antes de realizar una restauración, use las funcionalidades de recuperación proporcionadas por la eliminación temporal. Todas las claves que se usan con clave de cliente son necesarias para tener habilitada la eliminación temporal. La eliminación temporal actúa como una papelera de reciclaje y permite la recuperación durante un máximo de 90 días sin necesidad de restaurar. La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves. Si debe restaurar una clave para usarla con la clave de cliente, en Azure PowerShell, ejecute el cmdlet Restore-AzureKeyVaultKey como se indica a continuación:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Por ejemplo:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Si el almacén de claves ya contiene una clave con el mismo nombre, se produce un error en la operación de restauración. Restore-AzKeyVaultKey restaura todas las versiones de clave y todos los metadatos de la clave, incluido el nombre de la clave.
  
## <a name="manage-key-vault-permissions"></a>Administración de permisos del almacén de claves

Hay varios cmdlets disponibles que permiten ver y, si es necesario, quitar permisos del almacén de claves. Es posible que tenga que quitar permisos, por ejemplo, cuando un empleado deja el equipo. Para cada una de estas tareas, usará Azure PowerShell. Para obtener información sobre Azure PowerShell, consulte [Información general de Azure PowerShell](/powershell/azure/).

Para ver los permisos del almacén de claves, ejecute el cmdlet Get-AzKeyVault.

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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Reversión de la clave de cliente a las claves administradas por Microsoft

Si necesita volver a las claves administradas por Microsoft, puede hacerlo. Al desconectarse, los datos se vuelven a cifrar mediante el cifrado predeterminado compatible con cada carga de trabajo individual. Por ejemplo, Exchange Online admite el cifrado predeterminado mediante claves administradas por Microsoft.

> [!IMPORTANT]
> La eliminación no es lo mismo que una purga de datos. Una purga de datos elimina permanentemente los datos de la organización de Microsoft 365, pero la eliminación no lo hace. No se puede realizar una purga de datos para una directiva de varias cargas de trabajo.

Si decide no usar la clave de cliente para asignar dep de cargas de trabajo múltiples, tendrá que ponerse en contacto con el soporte técnico de Microsoft con una solicitud para "offboard" desde la clave de cliente. Pida al equipo de soporte técnico que abra una solicitud de servicio en el equipo de clave de cliente de Microsoft Purview. Póngase en contacto con m365-ck@service.microsoft.com si tiene alguna pregunta.

Si ya no desea cifrar buzones individuales mediante DEP de nivel de buzón, puede anular la asignación de desasignaciones de nivel de buzón de correo de todos los buzones de correo.

Para anular la asignación de los DEP de buzón de correo, use el cmdlet de PowerShell de Set-Mailbox.

1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-Mailbox.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

Al ejecutar este cmdlet, se anula la asignación del DEP asignado actualmente y se vuelve a cifrar el buzón mediante el DEP asociado a las claves administradas por Microsoft predeterminadas. No se puede anular la asignación del DEP usado por las claves administradas por Microsoft. Si no desea usar claves administradas por Microsoft, puede asignar otro DEP de clave de cliente al buzón.

> [!IMPORTANT]
> No se admite la reversión de la clave de cliente a las claves administradas por Microsoft para SharePoint archivos en línea, OneDrive para la Empresa y Teams. 

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Revocar las claves e iniciar el proceso de ruta de acceso de purga de datos

Puede controlar la revocación de todas las claves raíz, incluida la clave de disponibilidad. Clave de cliente proporciona control del aspecto de planeamiento de salida de los requisitos normativos para usted. Si decide revocar las claves para purgar los datos y salir del servicio, el servicio elimina la clave de disponibilidad una vez que se completa el proceso de purga de datos. Esto es compatible con los DEP de clave de cliente que se asignan a buzones individuales.

Microsoft 365 audita y valida la ruta de acceso de purga de datos. Para obtener más información, consulte el informe SSAE 18 SOC 2 disponible en el [Portal de confianza](https://servicetrust.microsoft.com/) de servicios. Además, Microsoft recomienda los siguientes documentos:

- [Guía de evaluación y cumplimiento de riesgos para instituciones financieras en la nube de Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Consideraciones sobre el planeamiento de salida de O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

No se admite la purga de DEP de varias cargas de trabajo para la clave de cliente. El DEP de varias cargas de trabajo se usa para cifrar los datos en varias cargas de trabajo entre todos los usuarios del inquilino. La purga de este tipo de DEP daría lugar a que los datos de varias cargas de trabajo fueran inaccesibles. Si decide salir de Microsoft 365 servicios por completo, podría seguir la ruta de acceso de eliminación de inquilinos según el proceso documentado. Vea [cómo eliminar un inquilino en Azure Active Directory](/azure/active-directory/enterprise-users/directory-delete-howto).

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Revoque las claves de cliente y la clave de disponibilidad para Exchange Online y Skype Empresarial

Al iniciar la ruta de acceso de purga de datos para Exchange Online y Skype Empresarial, se establece una solicitud de purga de datos permanente en un DEP. Al hacerlo, se eliminan permanentemente los datos cifrados dentro de los buzones a los que se asigna ese DEP.

Dado que solo puede ejecutar el cmdlet de PowerShell en un DEP a la vez, considere la posibilidad de reasignar un único DEP a todos los buzones antes de iniciar la ruta de acceso de purga de datos.

> [!WARNING]
> No use la ruta de acceso de purga de datos para eliminar un subconjunto de los buzones de correo. Este proceso solo está pensado para los clientes que salen del servicio.

Para iniciar la ruta de acceso de purga de datos, complete estos pasos:

1. Quite los permisos de encapsulado y desencapsulado para "O365 Exchange Online" de Azure Key Vault.

2. Con una cuenta profesional o educativa que tenga privilegios de administrador global en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

3. Para cada DEP que contenga buzones que quiera eliminar, ejecute el cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) como se indica a continuación.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Si se produce un error en el comando, asegúrese de que ha quitado los permisos de Exchange Online de ambas claves en Azure Key Vault como se especificó anteriormente en esta tarea. Una vez que haya establecido el modificador PermanentDataPurgeRequested mediante el cmdlet Set-DataEncryptionPolicy, ya no podrá asignar este DEP a buzones.

4. Póngase en contacto con el soporte técnico de Microsoft y solicite el documento electrónico de purga de datos.

    A petición suya, Microsoft le envía un documento legal para confirmar y autorizar la eliminación de datos. La persona de su organización que se registró como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento. Normalmente, se trata de una persona ejecutiva u otra persona designada en su empresa que tiene autorización legal para firmar la documentación en nombre de su organización.

5. Una vez que su representante haya firmado el documento legal, devuévalo a Microsoft (normalmente a través de una firma de eDoc).

    Una vez que Microsoft recibe el documento legal, Microsoft ejecuta cmdlets para desencadenar la purga de datos que primero elimina la directiva, marca los buzones para su eliminación permanente y, a continuación, elimina la clave de disponibilidad. Una vez completado el proceso de purga de datos, los datos se han purgado, no se puede acceder a Exchange Online y no se pueden recuperar.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Revocar las claves de cliente y la clave de disponibilidad para SharePoint archivos en línea, OneDrive para la Empresa y Teams

No se admite la purga de SharePoint, OneDrive para el trabajo o la escuela, y los ARCHIVOS DEP de Teams no se admiten en clave de cliente. Estos DEP de varias cargas de trabajo se usan para cifrar datos en varias cargas de trabajo en todos los usuarios del inquilino. La purga de este tipo de DEP daría lugar a que los datos de varias cargas de trabajo se hicieran inaccesibles. Si decide salir de Microsoft 365 servicios por completo, podría seguir la ruta de acceso de eliminación de inquilinos según el proceso documentado. Vea cómo [eliminar un inquilino en Azure Active Directory](/azure/active-directory/enterprise-users/directory-delete-howto).  

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente de Microsoft Purview](customer-key-overview.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Configuración de la clave de cliente](customer-key-set-up.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Caja de seguridad del cliente](customer-lockbox-requests.md)

- [Cifrado de servicio](office-365-service-encryption.md)
