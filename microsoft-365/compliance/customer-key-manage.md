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
description: Después de configurar la clave de cliente, aprenda a administrarla mediante la restauración de claves AKV y la administración de permisos y las directivas de cifrado de datos.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547090"
---
# <a name="manage-customer-key"></a><span data-ttu-id="8e44d-103">Administrar clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8e44d-103">Manage Customer Key</span></span>

<span data-ttu-id="8e44d-104">Después de configurar la clave de cliente para Office 365, puede administrar las claves como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="8e44d-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="8e44d-105">Obtenga más información sobre la clave de cliente en los temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="8e44d-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="8e44d-106">Restaurar claves de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8e44d-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="8e44d-107">Antes de realizar una restauración, use las capacidades de recuperación proporcionadas por la eliminación de software.</span><span class="sxs-lookup"><span data-stu-id="8e44d-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="8e44d-108">Todas las claves que se usan con la clave de cliente deben tener habilitada la eliminación de forma automática.</span><span class="sxs-lookup"><span data-stu-id="8e44d-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="8e44d-109">La eliminación de software actúa como una papelera de reciclaje y permite la recuperación durante un máximo de 90 días sin necesidad de restaurarla.</span><span class="sxs-lookup"><span data-stu-id="8e44d-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="8e44d-110">La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="8e44d-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="8e44d-111">Si debe restaurar una clave para usarla con la clave de cliente, en Azure PowerShell, ejecute el cmdlet Restore-AzureKeyVaultKey como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="8e44d-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="8e44d-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e44d-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="8e44d-113">Si el almacén de claves ya contiene una clave con el mismo nombre, se produce un error en la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="8e44d-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="8e44d-114">Restore-AzKeyVaultKey restaura todas las versiones clave y todos los metadatos de la clave, incluido el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="8e44d-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="8e44d-115">Administrar permisos de almacén de claves</span><span class="sxs-lookup"><span data-stu-id="8e44d-115">Manage key vault permissions</span></span>

<span data-ttu-id="8e44d-116">Hay disponibles varios cmdlets que le permiten ver y, si es necesario, quitar permisos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="8e44d-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="8e44d-117">Es posible que deba quitar permisos, por ejemplo, cuando un empleado abandona el equipo.</span><span class="sxs-lookup"><span data-stu-id="8e44d-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="8e44d-118">Para cada una de estas tareas, usará Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e44d-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="8e44d-119">Para obtener información sobre Azure Powershell, vea [Información general de Azure PowerShell.](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="8e44d-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="8e44d-120">Para ver los permisos del almacén de claves, ejecute el cmdlet Get-AzKeyVault clave.</span><span class="sxs-lookup"><span data-stu-id="8e44d-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="8e44d-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e44d-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="8e44d-122">Para quitar los permisos de un administrador, ejecute el cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="8e44d-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="8e44d-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e44d-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="8e44d-124">Administrar directivas de cifrado de datos (DEP) con clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8e44d-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="8e44d-125">La clave de cliente controla las DEP de forma diferente entre los distintos servicios.</span><span class="sxs-lookup"><span data-stu-id="8e44d-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="8e44d-126">Por ejemplo, puede crear un número diferente de DEP para los diferentes servicios.</span><span class="sxs-lookup"><span data-stu-id="8e44d-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="8e44d-127">**Exchange Online y Skype Empresarial:** Puede crear hasta 50 DEP.</span><span class="sxs-lookup"><span data-stu-id="8e44d-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="8e44d-128">Para obtener instrucciones, consulte Crear una directiva de cifrado de [datos (DEP)](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)para su uso con Exchange Online y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8e44d-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="8e44d-129">**Archivos de SharePoint Online, OneDrive para la Empresa y Teams:** Un DEP se aplica a los datos en una ubicación geográfica, también denominada _geo_.</span><span class="sxs-lookup"><span data-stu-id="8e44d-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="8e44d-130">Si usa la característica multige geográfica de Office 365, puede crear un DEP por geo.</span><span class="sxs-lookup"><span data-stu-id="8e44d-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="8e44d-131">Si no usa multige geográfica, puede crear un DEP.</span><span class="sxs-lookup"><span data-stu-id="8e44d-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="8e44d-132">Normalmente, se crea el DEP al configurar la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="8e44d-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="8e44d-133">Para obtener instrucciones, vea Crear una directiva de cifrado de datos (DEP) para cada ubicación geográfica de [SharePoint Online y OneDrive para la Empresa.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)</span><span class="sxs-lookup"><span data-stu-id="8e44d-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8e44d-134">Ver los DEP que ha creado para Exchange Online y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8e44d-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="8e44d-135">Para ver una lista de todos los DEP que ha creado para Exchange Online y Skype Empresarial con el cmdlet Get-DataEncryptionPolicy PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="8e44d-136">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e44d-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8e44d-137">Para devolver todos los DEP de la organización, ejecute el cmdlet Get-DataEncryptionPolicy sin ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="8e44d-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="8e44d-138">Para obtener más información acerca Get-DataEncryptionPolicy cmdlet, [vea Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="8e44d-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="8e44d-139">Asignar un DEP antes de migrar un buzón a la nube</span><span class="sxs-lookup"><span data-stu-id="8e44d-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="8e44d-140">Al asignar el DEP, Microsoft 365 cifra el contenido del buzón mediante el DEP asignado durante la migración.</span><span class="sxs-lookup"><span data-stu-id="8e44d-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="8e44d-141">Este proceso es más eficaz que migrar el buzón, asignar el DEP y, a continuación, esperar a que se realice el cifrado, que puede tardar horas o, posiblemente, días.</span><span class="sxs-lookup"><span data-stu-id="8e44d-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="8e44d-142">Para asignar un DEP a un buzón antes de migrarlo a Office 365, ejecute el cmdlet Set-MailUser en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8e44d-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="8e44d-143">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e44d-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8e44d-144">Ejecute el cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="8e44d-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="8e44d-145">Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y *DataEncryptionPolicyIdParameter* es el identificador del DEP.</span><span class="sxs-lookup"><span data-stu-id="8e44d-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="8e44d-146">Para obtener más información acerca del cmdlet Set-MailUser, [vea Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="8e44d-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="8e44d-147">Determinar el DEP asignado a un buzón</span><span class="sxs-lookup"><span data-stu-id="8e44d-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="8e44d-148">Para determinar el DEP asignado a un buzón de correo, use Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e44d-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="8e44d-149">El cmdlet devuelve un identificador único (GUID).</span><span class="sxs-lookup"><span data-stu-id="8e44d-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="8e44d-150">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e44d-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="8e44d-151">Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y DataEncryptionPolicyID devuelve el GUID del DEP.</span><span class="sxs-lookup"><span data-stu-id="8e44d-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="8e44d-152">Para obtener más información acerca del cmdlet Get-MailboxStatistics, [consulte Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="8e44d-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="8e44d-153">Ejecute el cmdlet Get-DataEncryptionPolicy para averiguar el nombre descriptivo del DEP al que está asignado el buzón.</span><span class="sxs-lookup"><span data-stu-id="8e44d-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="8e44d-154">Donde *GUID* es el GUID devuelto por el cmdlet Get-MailboxStatistics en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8e44d-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="8e44d-155">Comprobar que la clave de cliente ha finalizado el cifrado</span><span class="sxs-lookup"><span data-stu-id="8e44d-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="8e44d-156">Tanto si acaba de implementar una clave de cliente, asignar un nuevo DEP o migrar un buzón, siga los pasos de esta sección para asegurarse de que el cifrado se complete.</span><span class="sxs-lookup"><span data-stu-id="8e44d-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8e44d-157">Comprobar que el cifrado se completa para Exchange Online y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8e44d-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="8e44d-158">Cifrar un buzón puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="8e44d-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="8e44d-159">Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar un DEP o la primera vez que asigne un DEP a un buzón.</span><span class="sxs-lookup"><span data-stu-id="8e44d-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="8e44d-160">Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.</span><span class="sxs-lookup"><span data-stu-id="8e44d-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="8e44d-161">La propiedad IsEncrypted devuelve un valor **true** si el buzón está cifrado y un valor **false** si el buzón no está cifrado.</span><span class="sxs-lookup"><span data-stu-id="8e44d-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="8e44d-162">El tiempo para completar los movimientos de buzones depende del tamaño del buzón.</span><span class="sxs-lookup"><span data-stu-id="8e44d-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="8e44d-163">Si la clave de cliente no ha cifrado completamente el buzón después de 72 horas desde el momento en que asigna un nuevo DEP, póngase en contacto con el soporte técnico de Microsoft para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="8e44d-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="8e44d-164">El New-MoveRequest cmdlet ya no está disponible para los movimientos de buzones locales.</span><span class="sxs-lookup"><span data-stu-id="8e44d-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="8e44d-165">Consulte este [anuncio para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obtener información adicional.</span><span class="sxs-lookup"><span data-stu-id="8e44d-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="8e44d-166">Comprobar que el cifrado se completa para los archivos de SharePoint Online, OneDrive para la Empresa y Teams</span><span class="sxs-lookup"><span data-stu-id="8e44d-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="8e44d-167">Compruebe el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e44d-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="8e44d-168">El resultado de este cmdlet incluye:</span><span class="sxs-lookup"><span data-stu-id="8e44d-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="8e44d-169">El URI de la clave principal.</span><span class="sxs-lookup"><span data-stu-id="8e44d-169">The URI of the primary key.</span></span>

- <span data-ttu-id="8e44d-170">El URI de la clave secundaria.</span><span class="sxs-lookup"><span data-stu-id="8e44d-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="8e44d-171">El estado de cifrado de la geo.</span><span class="sxs-lookup"><span data-stu-id="8e44d-171">The encryption status for the geo.</span></span> <span data-ttu-id="8e44d-172">Entre los estados posibles se incluyen:</span><span class="sxs-lookup"><span data-stu-id="8e44d-172">Possible states include:</span></span>

  - <span data-ttu-id="8e44d-173">**Sin registrar:** Aún no se ha aplicado el cifrado de clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="8e44d-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="8e44d-174">**Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos están en proceso de cifrado.</span><span class="sxs-lookup"><span data-stu-id="8e44d-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="8e44d-175">Si la clave de la ubicación geográfica se está registrando, también se mostrará información sobre qué porcentaje de sitios de la geo se han completado para que pueda supervisar el progreso del cifrado.</span><span class="sxs-lookup"><span data-stu-id="8e44d-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="8e44d-176">**Registrado:** Se ha aplicado el cifrado de clave de cliente y se han cifrado todos los archivos de todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="8e44d-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="8e44d-177">**Rolling:** Hay un lanzamiento de teclas en curso.</span><span class="sxs-lookup"><span data-stu-id="8e44d-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="8e44d-178">Si la clave de la geo se está implementando, también se mostrará información sobre el porcentaje de sitios que han completado la operación de succión de claves para poder supervisar el progreso.</span><span class="sxs-lookup"><span data-stu-id="8e44d-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="8e44d-179">Desasignar un DEP de un buzón</span><span class="sxs-lookup"><span data-stu-id="8e44d-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="8e44d-180">Puede desasignar un DEP de un buzón mediante el cmdlet set-mailbox de PowerShell y establecer `DataEncryptionPolicy` el valor en `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="8e44d-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="8e44d-181">Al ejecutar este cmdlet, se desasigna el DEP asignado actualmente y se vuelve a cifrar el buzón mediante el DEP asociado con las claves administradas de Microsoft predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="8e44d-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="8e44d-182">No puede desasignar el DEP usado por las claves administradas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e44d-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="8e44d-183">Si no desea usar claves administradas de Microsoft, puede asignar otro DEP al buzón.</span><span class="sxs-lookup"><span data-stu-id="8e44d-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="8e44d-184">Para desasignar el DEP de un buzón con Set-Mailbox cmdlet de PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="8e44d-185">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e44d-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8e44d-186">Ejecute el cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="8e44d-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="8e44d-187">Revocar las claves e iniciar el proceso de ruta de depuración de datos</span><span class="sxs-lookup"><span data-stu-id="8e44d-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="8e44d-188">Controle la revocación de todas las claves raíz, incluida la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8e44d-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="8e44d-189">La clave de cliente proporciona control sobre el aspecto de la planeación de salida de los requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="8e44d-190">Si decide revocar las claves para purgar los datos y salir del servicio, el servicio elimina la clave de disponibilidad una vez completado el proceso de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="8e44d-191">Microsoft 365 audita y valida la ruta de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="8e44d-192">Para obtener más información, vea el informe SSAE 18 SOC 2 disponible en el [Portal de confianza de servicios.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="8e44d-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="8e44d-193">Además, Microsoft recomienda los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="8e44d-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="8e44d-194">Guía de evaluación de riesgos y cumplimiento para instituciones financieras en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8e44d-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="8e44d-195">Consideraciones sobre la planeación de salida de O365</span><span class="sxs-lookup"><span data-stu-id="8e44d-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="8e44d-196">La ruta de depuración de datos difiere ligeramente entre los distintos servicios.</span><span class="sxs-lookup"><span data-stu-id="8e44d-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8e44d-197">Revocar las claves de cliente y la clave de disponibilidad para Exchange Online y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8e44d-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="8e44d-198">Cuando inicia la ruta de depuración de datos para Exchange Online y Skype Empresarial, establece una solicitud de depuración de datos permanente en un DEP.</span><span class="sxs-lookup"><span data-stu-id="8e44d-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="8e44d-199">Al hacerlo, se eliminan de forma permanente los datos cifrados dentro de los buzones a los que está asignado ese DEP.</span><span class="sxs-lookup"><span data-stu-id="8e44d-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="8e44d-200">Dado que solo puede ejecutar el cmdlet de PowerShell en un DEP a la vez, considere la posibilidad de reasignar un solo DEP a todos los buzones antes de iniciar la ruta de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="8e44d-201">No use la ruta de depuración de datos para eliminar un subconjunto de sus buzones.</span><span class="sxs-lookup"><span data-stu-id="8e44d-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="8e44d-202">Este proceso solo está destinado a los clientes que salen del servicio.</span><span class="sxs-lookup"><span data-stu-id="8e44d-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="8e44d-203">Para iniciar la ruta de depuración de datos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8e44d-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="8e44d-204">Quite los permisos de ajuste y desencapsulación para "O365 Exchange Online" de Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="8e44d-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="8e44d-205">Con una cuenta profesional o educativa que tenga privilegios de administrador global en su organización, conéctese a [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e44d-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="8e44d-206">Para cada DEP que contenga buzones que desee eliminar, ejecute el cmdlet [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="8e44d-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="8e44d-207">Si se produce un error en el comando, asegúrese de que ha quitado los permisos de Exchange Online de ambas claves en Azure Key Vault, como se especificó anteriormente en esta tarea.</span><span class="sxs-lookup"><span data-stu-id="8e44d-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="8e44d-208">Una vez que haya establecido el modificador PermanentDataPurgeRequested con el cmdlet Set-DataEncryptionPolicy, ya no podrá asignar este DEP a los buzones.</span><span class="sxs-lookup"><span data-stu-id="8e44d-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="8e44d-209">Póngase en contacto con el soporte técnico de Microsoft y solicite el eDocument de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="8e44d-210">A petición de usted, Microsoft le envía un documento legal para confirmar y autorizar la eliminación de datos.</span><span class="sxs-lookup"><span data-stu-id="8e44d-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="8e44d-211">La persona de su organización que se suscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento.</span><span class="sxs-lookup"><span data-stu-id="8e44d-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="8e44d-212">Normalmente, se trata de una persona ejecutiva u otra persona designada de su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="8e44d-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="8e44d-213">Una vez que su representante haya firmado el documento legal, vuelva a Microsoft (normalmente a través de una firma de eDoc).</span><span class="sxs-lookup"><span data-stu-id="8e44d-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="8e44d-214">Una vez que Microsoft recibe el documento legal, Microsoft ejecuta cmdlets para desencadenar la purga de datos que elimina primero la directiva, marca los buzones para su eliminación permanente y, a continuación, elimina la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8e44d-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="8e44d-215">Una vez completado el proceso de depuración de datos, los datos se han purgado, no se puede obtener acceso a Exchange Online y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="8e44d-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="8e44d-216">Revocar las claves de cliente y la clave de disponibilidad para los archivos de SharePoint Online, OneDrive para la Empresa y Teams</span><span class="sxs-lookup"><span data-stu-id="8e44d-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="8e44d-217">Para iniciar la ruta de depuración de datos para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8e44d-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="8e44d-218">Revocar el acceso al Almacén de claves de Azure.</span><span class="sxs-lookup"><span data-stu-id="8e44d-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="8e44d-219">Todos los administradores del almacén de claves deben aceptar revocar el acceso.</span><span class="sxs-lookup"><span data-stu-id="8e44d-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="8e44d-220">No se elimina el Almacén de claves de Azure para SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8e44d-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="8e44d-221">Los almacenes de claves se pueden compartir entre varios inquilinos y DEP de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8e44d-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="8e44d-222">Póngase en contacto con Microsoft para eliminar la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8e44d-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="8e44d-223">Cuando se contacte con Microsoft para eliminar la clave de disponibilidad, le enviaremos un documento legal.</span><span class="sxs-lookup"><span data-stu-id="8e44d-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="8e44d-224">La persona de su organización que se suscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento.</span><span class="sxs-lookup"><span data-stu-id="8e44d-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="8e44d-225">Normalmente, se trata de una persona ejecutiva u otra persona designada de su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="8e44d-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="8e44d-226">Una vez que su representante firme el documento legal, vuelva a Microsoft (normalmente a través de una firma de eDoc).</span><span class="sxs-lookup"><span data-stu-id="8e44d-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="8e44d-227">Una vez que Microsoft recibe el documento legal, ejecutamos cmdlets para desencadenar la purga de datos que realiza la eliminación criptográfica de la clave de inquilino, la clave de sitio y todas las claves individuales por documento, lo que rompe irrevocablemente la jerarquía de claves.</span><span class="sxs-lookup"><span data-stu-id="8e44d-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="8e44d-228">Una vez completados los cmdlets de depuración de datos, los datos se han purgado.</span><span class="sxs-lookup"><span data-stu-id="8e44d-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8e44d-229">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8e44d-229">Related articles</span></span>

- [<span data-ttu-id="8e44d-230">Cifrado de servicio con clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8e44d-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="8e44d-231">Más información sobre la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="8e44d-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="8e44d-232">Configurar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8e44d-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="8e44d-233">Rotar o alternar una Clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="8e44d-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="8e44d-234">Caja de seguridad del cliente</span><span class="sxs-lookup"><span data-stu-id="8e44d-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="8e44d-235">Cifrado de servicio</span><span class="sxs-lookup"><span data-stu-id="8e44d-235">Service Encryption</span></span>](office-365-service-encryption.md)
