---
title: Rotar o alternar una Clave de cliente o una clave de disponibilidad
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
description: Obtenga información sobre cómo deshacer las claves raíz del cliente almacenadas en Azure Key Vault que se usan con la clave de cliente. Los servicios incluyen Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345123"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="16e4e-104">Rotar o alternar una Clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="16e4e-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="16e4e-105">Solo enrolle una clave de cifrado que use con la clave de cliente cuando los requisitos de seguridad o cumplimiento dicten que debe rodar la clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="16e4e-106">Además, no elimine las claves que están o estaban asociadas con directivas.</span><span class="sxs-lookup"><span data-stu-id="16e4e-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="16e4e-107">Al rodar las claves, habrá contenido cifrado con las claves anteriores.</span><span class="sxs-lookup"><span data-stu-id="16e4e-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="16e4e-108">Por ejemplo, aunque los buzones activos se volverán a cifrar con frecuencia, los buzones inactivos, desconectados y deshabilitados aún pueden cifrarse con las claves anteriores.</span><span class="sxs-lookup"><span data-stu-id="16e4e-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="16e4e-109">SharePoint Online realiza una copia de seguridad del contenido con fines de restauración y recuperación, por lo que es posible que aún haya contenido archivado con claves anteriores.</span><span class="sxs-lookup"><span data-stu-id="16e4e-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="16e4e-110">Acerca de cómo implementar la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="16e4e-110">About rolling the availability key</span></span>

<span data-ttu-id="16e4e-111">Microsoft no expone el control directo de la clave de disponibilidad a los clientes.</span><span class="sxs-lookup"><span data-stu-id="16e4e-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="16e4e-112">Por ejemplo, solo puede girar (girar) las claves que posee en Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="16e4e-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="16e4e-113">Microsoft 365 las claves de disponibilidad en una programación definida internamente.</span><span class="sxs-lookup"><span data-stu-id="16e4e-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="16e4e-114">No hay ningún contrato de nivel de servicio (SLA) orientado al cliente para estos lanzamientos de claves.</span><span class="sxs-lookup"><span data-stu-id="16e4e-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="16e4e-115">Microsoft 365 gira la clave de disponibilidad mediante Microsoft 365 de servicio en un proceso automatizado y no manual.</span><span class="sxs-lookup"><span data-stu-id="16e4e-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="16e4e-116">Los administradores de Microsoft pueden iniciar el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="16e4e-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="16e4e-117">La clave se enrolla mediante mecanismos automatizados sin acceso directo al almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="16e4e-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="16e4e-118">El acceso al almacén secreto de clave de disponibilidad no se aprovisiona a los administradores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16e4e-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="16e4e-119">La implementación de la clave de disponibilidad aprovecha el mismo mecanismo usado para generar inicialmente la clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="16e4e-120">Para obtener más información acerca de la clave de disponibilidad, vea [Understand the availability key](customer-key-availability-key-understand.md).</span><span class="sxs-lookup"><span data-stu-id="16e4e-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16e4e-121">Exchange Online y Skype Empresarial claves de disponibilidad pueden ser efectivamente enrollados por los clientes que crean un nuevo DEP, ya que se genera una clave de disponibilidad única para cada DEP que cree.</span><span class="sxs-lookup"><span data-stu-id="16e4e-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="16e4e-122">Las claves de disponibilidad de los archivos SharePoint Online, OneDrive para la Empresa y Teams existen en el nivel del bosque y se comparten entre los dep y los clientes, lo que significa que la implementación solo se produce en una programación definida internamente por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16e4e-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="16e4e-123">Para mitigar el riesgo de no implementar la clave de disponibilidad cada vez que se crea un nuevo DEP, SharePoint, OneDrive y Teams revierten la clave intermedia de inquilino (TIK), la clave encapsulada por las claves raíz del cliente y la clave de disponibilidad, cada vez que se crea un nuevo DEP.</span><span class="sxs-lookup"><span data-stu-id="16e4e-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="16e4e-124">Solicitar una nueva versión de cada clave raíz existente que quieras roll</span><span class="sxs-lookup"><span data-stu-id="16e4e-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="16e4e-125">Cuando se rueda una clave, se solicita una nueva versión de una clave existente.</span><span class="sxs-lookup"><span data-stu-id="16e4e-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="16e4e-126">Para solicitar una nueva versión de una clave existente, use el mismo cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), con la misma sintaxis que usó para crear la clave en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="16e4e-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="16e4e-127">Una vez que haya terminado de implementar cualquier clave asociada con una directiva de cifrado de datos (DEP), ejecute otro cmdlet para asegurarse de que la clave de cliente comience a usar la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="16e4e-128">Realice este paso en cada Almacén de claves de Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="16e4e-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="16e4e-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16e4e-129">For example:</span></span>

1. <span data-ttu-id="16e4e-130">Inicie sesión en su suscripción de Azure con Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16e4e-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="16e4e-131">Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="16e4e-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="16e4e-132">Ejecute el cmdlet Add-AzKeyVaultKey como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16e4e-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="16e4e-133">En este ejemplo, dado que existe una clave denominada **Contoso-CK-EX-NA-VaultA1-Key001** en el almacén **contoso-CK-EX-NA-VaultA1,** el cmdlet crea una nueva versión de la clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="16e4e-134">Esta operación conserva las versiones clave anteriores en el historial de versiones de la clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="16e4e-135">Necesita la versión de clave anterior para descifrar los datos que aún cifra.</span><span class="sxs-lookup"><span data-stu-id="16e4e-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="16e4e-136">Una vez que haya terminado de implementar cualquier clave asociada a un DEP, ejecute un cmdlet adicional para asegurarse de que la clave de cliente comience a usar la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="16e4e-137">En las secciones siguientes se describen los cmdlets con más detalle.</span><span class="sxs-lookup"><span data-stu-id="16e4e-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="16e4e-138">Actualizar las claves de los DEP de varias cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="16e4e-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="16e4e-139">Al implementar cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con varias cargas de trabajo, debe actualizar el DEP para que apunte a la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="16e4e-140">Este proceso no gira la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="16e4e-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="16e4e-141">Para indicar a clave de cliente que use la nueva clave para cifrar varias cargas de trabajo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="16e4e-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="16e4e-142">En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="16e4e-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="16e4e-143">Ejecute el cmdlet Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="16e4e-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="16e4e-144">Donde *PolicyName* es el nombre o identificador único de la directiva.</span><span class="sxs-lookup"><span data-stu-id="16e4e-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="16e4e-145">Por ejemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="16e4e-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="16e4e-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16e4e-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="16e4e-147">Actualizar las claves para Exchange Online DEP</span><span class="sxs-lookup"><span data-stu-id="16e4e-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="16e4e-148">Al implementar cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con Exchange Online y Skype Empresarial, debe actualizar el DEP para que apunte a la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="16e4e-149">Esto no gira la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="16e4e-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="16e4e-150">Para indicar a clave de cliente que use la nueva clave para cifrar buzones, ejecute el cmdlet Set-DataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="16e4e-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="16e4e-151">Ejecute el cmdlet Set-DataEncryptionPolicy en Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="16e4e-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="16e4e-152">Para comprobar el valor de la propiedad DataEncryptionPolicyID para el buzón de correo, siga los pasos descritos en [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="16e4e-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="16e4e-153">El valor de esta propiedad cambia una vez que el servicio aplica la clave actualizada.</span><span class="sxs-lookup"><span data-stu-id="16e4e-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="16e4e-154">Actualizar las claves de SharePoint Online, OneDrive para la Empresa y Teams archivos</span><span class="sxs-lookup"><span data-stu-id="16e4e-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="16e4e-155">SharePoint Online solo te permite rodar una tecla a la vez.</span><span class="sxs-lookup"><span data-stu-id="16e4e-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="16e4e-156">Si desea rodar ambas claves en un almacén de claves, espere a que se complete la primera operación.</span><span class="sxs-lookup"><span data-stu-id="16e4e-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="16e4e-157">Microsoft recomienda escalonar las operaciones para evitar este problema.</span><span class="sxs-lookup"><span data-stu-id="16e4e-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="16e4e-158">Al implementar cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con SharePoint Online y OneDrive para la Empresa, debe actualizar el DEP para que apunte a la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="16e4e-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="16e4e-159">Esto no gira la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="16e4e-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="16e4e-160">Ejecute el cmdlet Update-SPODataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="16e4e-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="16e4e-161">Mientras este cmdlet inicia la operación de lanzamiento de claves para SharePoint Online y OneDrive para la Empresa, la acción no se completa inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="16e4e-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="16e4e-162">Para ver el progreso de la operación de lanzamiento de claves, ejecute el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="16e4e-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="16e4e-163">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="16e4e-163">Related articles</span></span>

- [<span data-ttu-id="16e4e-164">Cifrado de servicio con clave de cliente para Office 365</span><span class="sxs-lookup"><span data-stu-id="16e4e-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="16e4e-165">Configurar clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="16e4e-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="16e4e-166">Administrar Clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="16e4e-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="16e4e-167">Obtenga información sobre la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="16e4e-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)