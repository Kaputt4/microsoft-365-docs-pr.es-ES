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
# <a name="manage-customer-key"></a><span data-ttu-id="51bca-103">Administrar clave de cliente</span><span class="sxs-lookup"><span data-stu-id="51bca-103">Manage Customer Key</span></span>

<span data-ttu-id="51bca-104">Después de configurar la clave de cliente para Office 365, deberá crear y asignar una o más directivas de cifrado de datos (DEP).</span><span class="sxs-lookup"><span data-stu-id="51bca-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="51bca-105">Una vez que haya asignado los DEP, puede administrar las claves como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="51bca-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="51bca-106">Obtenga más información sobre la clave de cliente en los temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="51bca-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="51bca-107">Crear un DEP para su uso con varias cargas de trabajo para todos los usuarios del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="51bca-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="51bca-108">Antes de comenzar, asegúrese de que ha completado las tareas necesarias para configurar Cliente.</span><span class="sxs-lookup"><span data-stu-id="51bca-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="51bca-109">Para obtener información, vea [Configurar clave de cliente](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="51bca-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="51bca-110">Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="51bca-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="51bca-111">Para obtener información, vea [Obtener el URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="51bca-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="51bca-112">Para crear un DEP con varias cargas de trabajo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51bca-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="51bca-113">En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="51bca-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="51bca-114">Para crear un DEP, use el cmdlet New-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="51bca-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="51bca-115">Donde:</span><span class="sxs-lookup"><span data-stu-id="51bca-115">Where:</span></span>

   - <span data-ttu-id="51bca-116">*PolicyName* es el nombre que desea usar para la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="51bca-117">Los nombres no pueden contener espacios.</span><span class="sxs-lookup"><span data-stu-id="51bca-117">Names can't contain spaces.</span></span> <span data-ttu-id="51bca-118">Por ejemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="51bca-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="51bca-119">*KeyVaultURI1* es el URI de la primera clave de la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="51bca-120">Por ejemplo, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="51bca-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="51bca-121">*KeyVaultURI2* es el URI de la segunda clave de la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="51bca-122">Por ejemplo, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="51bca-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="51bca-123">Separe los dos URI por una coma y un espacio.</span><span class="sxs-lookup"><span data-stu-id="51bca-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="51bca-124">*Descripción de* la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué es la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="51bca-125">Puede incluir espacios en la descripción.</span><span class="sxs-lookup"><span data-stu-id="51bca-125">You can include spaces in the description.</span></span> <span data-ttu-id="51bca-126">Por ejemplo, "Directiva raíz para varias cargas de trabajo para todos los usuarios del espacio empresarial".</span><span class="sxs-lookup"><span data-stu-id="51bca-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="51bca-127">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="51bca-128">Asignar directiva de varias cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="51bca-128">Assign multi-workload policy</span></span>

<span data-ttu-id="51bca-129">Asigne el DEP mediante el cmdlet Set-M365DataAtRestEncryptionPolicyAssignment.</span><span class="sxs-lookup"><span data-stu-id="51bca-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="51bca-130">Una vez que asigne la directiva, Microsoft 365 cifra los datos con la clave identificada en el DEP.</span><span class="sxs-lookup"><span data-stu-id="51bca-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="51bca-131">Donde *PolicyName* es el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="51bca-132">Por ejemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="51bca-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="51bca-133">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="51bca-134">Crear un DEP para su uso con Exchange Online buzones de correo</span><span class="sxs-lookup"><span data-stu-id="51bca-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="51bca-135">Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="51bca-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="51bca-136">Para obtener información, vea [Configurar clave de cliente](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="51bca-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="51bca-137">Para completar estos pasos, conéctese de forma remota a Exchange Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51bca-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="51bca-138">Un DEP está asociado con un conjunto de claves almacenadas en Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="51bca-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="51bca-139">Se asigna un DEP a un buzón en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51bca-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="51bca-140">Microsoft 365 usará las claves identificadas en la directiva para cifrar el buzón.</span><span class="sxs-lookup"><span data-stu-id="51bca-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="51bca-141">Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="51bca-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="51bca-142">Para obtener información, vea [Obtener el URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="51bca-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="51bca-143">¡Recuerda!</span><span class="sxs-lookup"><span data-stu-id="51bca-143">Remember!</span></span> <span data-ttu-id="51bca-144">Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes.</span><span class="sxs-lookup"><span data-stu-id="51bca-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="51bca-145">Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.</span><span class="sxs-lookup"><span data-stu-id="51bca-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="51bca-146">Para crear un DEP para usarlo con un buzón de correo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51bca-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="51bca-147">En el equipo local, con una cuenta de trabajo o educativa que tenga permisos de administrador global o de administrador Exchange Online en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="51bca-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="51bca-148">Para crear un DEP, use New-DataEncryptionPolicy cmdlet escribiendo el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="51bca-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="51bca-149">Donde:</span><span class="sxs-lookup"><span data-stu-id="51bca-149">Where:</span></span>

   - <span data-ttu-id="51bca-150">*PolicyName* es el nombre que desea usar para la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="51bca-151">Los nombres no pueden contener espacios.</span><span class="sxs-lookup"><span data-stu-id="51bca-151">Names can't contain spaces.</span></span> <span data-ttu-id="51bca-152">Por ejemplo, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="51bca-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="51bca-153">*Descripción de* la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué es la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="51bca-154">Puede incluir espacios en la descripción.</span><span class="sxs-lookup"><span data-stu-id="51bca-154">You can include spaces in the description.</span></span> <span data-ttu-id="51bca-155">Por ejemplo, "Clave raíz para buzones de correo en Estados Unidos y sus territorios".</span><span class="sxs-lookup"><span data-stu-id="51bca-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="51bca-156">*KeyVaultURI1* es el URI de la primera clave de la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="51bca-157">Por ejemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="51bca-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="51bca-158">*KeyVaultURI2* es el URI de la segunda clave de la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="51bca-159">Por ejemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="51bca-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="51bca-160">Separe los dos URI por una coma y un espacio.</span><span class="sxs-lookup"><span data-stu-id="51bca-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="51bca-161">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="51bca-162">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="51bca-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="51bca-163">Asignar un DEP a un buzón</span><span class="sxs-lookup"><span data-stu-id="51bca-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="51bca-164">Asigne el DEP a un buzón mediante el cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="51bca-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="51bca-165">Una vez que asigne la directiva, Microsoft 365 puede cifrar el buzón con la clave identificada en el DEP.</span><span class="sxs-lookup"><span data-stu-id="51bca-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="51bca-166">Donde *MailboxIdParameter* especifica un buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="51bca-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="51bca-167">Para obtener más información acerca del cmdlet Set-Mailbox, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="51bca-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="51bca-168">En entornos híbridos, puede asignar un DEP a los datos de buzones locales que se sincronizan con el Exchange Online inquilino.</span><span class="sxs-lookup"><span data-stu-id="51bca-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="51bca-169">Para asignar un DEP a estos datos de buzones sincronizados, usará el cmdlet Set-MailUser correo.</span><span class="sxs-lookup"><span data-stu-id="51bca-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="51bca-170">Para obtener más información acerca de los datos de buzones en el entorno híbrido, vea buzones locales con Outlook para iOS y Android con [autenticación moderna híbrida.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="51bca-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="51bca-171">Donde *MailUserIdParameter* especifica un usuario de correo (también conocido como usuario habilitado para correo).</span><span class="sxs-lookup"><span data-stu-id="51bca-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="51bca-172">Para obtener más información acerca del cmdlet Set-MailUser, vea [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="51bca-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="51bca-173">Crear un DEP para su uso con SharePoint Online, OneDrive para la Empresa y Teams archivos</span><span class="sxs-lookup"><span data-stu-id="51bca-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="51bca-174">Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="51bca-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="51bca-175">Para obtener información, vea [Configurar clave de cliente](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="51bca-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="51bca-176">Para configurar la clave de cliente para SharePoint Online, OneDrive para la Empresa y Teams, realice estos pasos conectándose de forma remota a SharePoint Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51bca-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="51bca-177">Asocie un DEP con un conjunto de claves almacenadas en Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="51bca-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="51bca-178">Se aplica un DEP a todos los datos en una ubicación geográfica, también denominada geo.</span><span class="sxs-lookup"><span data-stu-id="51bca-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="51bca-179">Si usa la característica multigeográfica de Office 365, puede crear un DEP por geo con la capacidad de usar diferentes claves por geo.</span><span class="sxs-lookup"><span data-stu-id="51bca-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="51bca-180">Si no usa multige geográficamente, puede crear un DEP en su organización para usarlo con SharePoint Online, OneDrive para la Empresa y Teams archivos.</span><span class="sxs-lookup"><span data-stu-id="51bca-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="51bca-181">Microsoft 365 las claves identificadas en el DEP para cifrar los datos en esa ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="51bca-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="51bca-182">Para crear el DEP, necesita los URI de Key Vault que obtuvo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="51bca-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="51bca-183">Para obtener información, vea [Obtener el URI de cada clave de Azure Key Vault](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="51bca-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="51bca-184">¡Recuerda!</span><span class="sxs-lookup"><span data-stu-id="51bca-184">Remember!</span></span> <span data-ttu-id="51bca-185">Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes.</span><span class="sxs-lookup"><span data-stu-id="51bca-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="51bca-186">Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.</span><span class="sxs-lookup"><span data-stu-id="51bca-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="51bca-187">Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51bca-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="51bca-188">En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, Conectar para SharePoint [PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="51bca-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="51bca-189">En el Shell Microsoft Office SharePoint Online administración, ejecute el cmdlet Register-SPODataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="51bca-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="51bca-190">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="51bca-191">Al registrar el DEP, el cifrado comienza en los datos de la geo.</span><span class="sxs-lookup"><span data-stu-id="51bca-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="51bca-192">El cifrado puede tardar algo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="51bca-192">Encryption can take some time.</span></span> <span data-ttu-id="51bca-193">Para obtener más información sobre el uso de este parámetro, [vea Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="51bca-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="51bca-194">Ver los DEP que ha creado para Exchange Online buzones de correo</span><span class="sxs-lookup"><span data-stu-id="51bca-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="51bca-195">Para ver una lista de todos los DEP que ha creado para buzones, use el cmdlet Get-DataEncryptionPolicy PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51bca-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="51bca-196">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51bca-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="51bca-197">Para devolver todos los DEP de la organización, ejecute el cmdlet Get-DataEncryptionPolicy sin ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="51bca-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="51bca-198">Para obtener más información acerca del cmdlet Get-DataEncryptionPolicy, [vea Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="51bca-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="51bca-199">Asignar un DEP antes de migrar un buzón a la nube</span><span class="sxs-lookup"><span data-stu-id="51bca-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="51bca-200">Al asignar el DEP, Microsoft 365 cifra el contenido del buzón mediante el DEP asignado durante la migración.</span><span class="sxs-lookup"><span data-stu-id="51bca-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="51bca-201">Este proceso es más eficaz que migrar el buzón, asignar el DEP y, a continuación, esperar a que se realice el cifrado, que puede tardar horas o, posiblemente, días.</span><span class="sxs-lookup"><span data-stu-id="51bca-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="51bca-202">Para asignar un DEP a un buzón antes de migrarlo a Office 365, ejecute el cmdlet Set-MailUser en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="51bca-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="51bca-203">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51bca-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="51bca-204">Ejecute el cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="51bca-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="51bca-205">Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y *DataEncryptionPolicyIdParameter* es el identificador del DEP.</span><span class="sxs-lookup"><span data-stu-id="51bca-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="51bca-206">Para obtener más información acerca del cmdlet Set-MailUser, vea [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="51bca-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="51bca-207">Determinar el DEP asignado a un buzón</span><span class="sxs-lookup"><span data-stu-id="51bca-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="51bca-208">Para determinar el DEP asignado a un buzón, use el cmdlet Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="51bca-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="51bca-209">El cmdlet devuelve un identificador único (GUID).</span><span class="sxs-lookup"><span data-stu-id="51bca-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="51bca-210">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51bca-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="51bca-211">Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón y DataEncryptionPolicyID devuelve el GUID del DEP.</span><span class="sxs-lookup"><span data-stu-id="51bca-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="51bca-212">Para obtener más información acerca del cmdlet Get-MailboxStatistics, vea [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="51bca-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="51bca-213">Ejecute el cmdlet Get-DataEncryptionPolicy para averiguar el nombre descriptivo del DEP al que está asignado el buzón.</span><span class="sxs-lookup"><span data-stu-id="51bca-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="51bca-214">Donde *GUID* es el GUID devuelto por el cmdlet Get-MailboxStatistics en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="51bca-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="51bca-215">Comprobar que la clave de cliente ha finalizado el cifrado</span><span class="sxs-lookup"><span data-stu-id="51bca-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="51bca-216">Tanto si ha enrollado una clave de cliente, ha asignado un nuevo DEP o migrado un buzón, siga los pasos descritos en esta sección para asegurarse de que el cifrado se completa.</span><span class="sxs-lookup"><span data-stu-id="51bca-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="51bca-217">Comprobar que el cifrado se completa para Exchange Online buzones de correo</span><span class="sxs-lookup"><span data-stu-id="51bca-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="51bca-218">Cifrar un buzón puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="51bca-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="51bca-219">Para el cifrado por primera vez, el buzón también debe moverse completamente de una base de datos a otra para que el servicio pueda cifrar el buzón.</span><span class="sxs-lookup"><span data-stu-id="51bca-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="51bca-220">Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.</span><span class="sxs-lookup"><span data-stu-id="51bca-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="51bca-221">La propiedad IsEncrypted devuelve un valor **de true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado.</span><span class="sxs-lookup"><span data-stu-id="51bca-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="51bca-222">El tiempo para completar los movimientos de buzones depende del número de buzones a los que asigne un DEP por primera vez y del tamaño de los buzones.</span><span class="sxs-lookup"><span data-stu-id="51bca-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="51bca-223">Si los buzones no se han cifrado después de una semana desde el momento en que asignó el DEP, póngase en contacto con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51bca-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="51bca-224">El cmdlet New-MoveRequest ya no está disponible para los movimientos de buzones locales.</span><span class="sxs-lookup"><span data-stu-id="51bca-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="51bca-225">Consulte este [anuncio para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obtener información adicional.</span><span class="sxs-lookup"><span data-stu-id="51bca-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="51bca-226">Comprobar que el cifrado se completa para SharePoint online, OneDrive para la Empresa y Teams archivos</span><span class="sxs-lookup"><span data-stu-id="51bca-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="51bca-227">Compruebe el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="51bca-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="51bca-228">El resultado de este cmdlet incluye:</span><span class="sxs-lookup"><span data-stu-id="51bca-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="51bca-229">Uri de la clave principal.</span><span class="sxs-lookup"><span data-stu-id="51bca-229">The URI of the primary key.</span></span>

- <span data-ttu-id="51bca-230">Uri de la clave secundaria.</span><span class="sxs-lookup"><span data-stu-id="51bca-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="51bca-231">El estado de cifrado de la geo.</span><span class="sxs-lookup"><span data-stu-id="51bca-231">The encryption status for the geo.</span></span> <span data-ttu-id="51bca-232">Los estados posibles incluyen:</span><span class="sxs-lookup"><span data-stu-id="51bca-232">Possible states include:</span></span>

  - <span data-ttu-id="51bca-233">**Sin registrar:** El cifrado de clave de cliente aún no se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="51bca-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="51bca-234">**Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos están en proceso de cifrado.</span><span class="sxs-lookup"><span data-stu-id="51bca-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="51bca-235">Si la clave de la geo se está registrando, también se mostrará información sobre qué porcentaje de sitios de la geo están completos para que pueda supervisar el progreso del cifrado.</span><span class="sxs-lookup"><span data-stu-id="51bca-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="51bca-236">**Registrado:** Se ha aplicado el cifrado de clave de cliente y se han cifrado todos los archivos de todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="51bca-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="51bca-237">**Rolling:** Hay un lanzamiento de teclas en curso.</span><span class="sxs-lookup"><span data-stu-id="51bca-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="51bca-238">Si la clave de la geo se está implementando, también se mostrará información sobre el porcentaje de sitios que han completado la operación de lanzamiento de teclas para poder supervisar el progreso.</span><span class="sxs-lookup"><span data-stu-id="51bca-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="51bca-239">Obtener detalles sobre los DEP que usa con varias cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="51bca-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="51bca-240">Para obtener detalles sobre todos los DEP que ha creado para usar con varias cargas de trabajo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51bca-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="51bca-241">En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="51bca-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="51bca-242">Para devolver la lista de todos los DEP de varias cargas de trabajo de la organización, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="51bca-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="51bca-243">Para devolver detalles sobre un DEP específico, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="51bca-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="51bca-244">En este ejemplo se devuelve información detallada para el DEP denominado "Contoso_Global".</span><span class="sxs-lookup"><span data-stu-id="51bca-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="51bca-245">Obtener información de asignación de DEP de varias cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="51bca-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="51bca-246">Para averiguar qué DEP está asignado actualmente a su inquilino, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="51bca-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="51bca-247">En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="51bca-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="51bca-248">Escriba este comando.</span><span class="sxs-lookup"><span data-stu-id="51bca-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="51bca-249">Deshabilitar un DEP de varias cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="51bca-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="51bca-250">Antes de deshabilitar un DEP de varias cargas de trabajo, desasigne el DEP de las cargas de trabajo del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="51bca-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="51bca-251">Para deshabilitar un DEP usado con varias cargas de trabajo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51bca-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="51bca-252">En el equipo local, con una cuenta de trabajo o escuela que tenga permisos de administrador global o administrador de cumplimiento en la organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.</span><span class="sxs-lookup"><span data-stu-id="51bca-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="51bca-253">Ejecute el cmdlet Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="51bca-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="51bca-254">Donde *PolicyName* es el nombre o identificador único de la directiva.</span><span class="sxs-lookup"><span data-stu-id="51bca-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="51bca-255">Por ejemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="51bca-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="51bca-256">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="51bca-257">Restaurar claves de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="51bca-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="51bca-258">Antes de realizar una restauración, use las capacidades de recuperación proporcionadas por la eliminación suave.</span><span class="sxs-lookup"><span data-stu-id="51bca-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="51bca-259">Todas las claves que se usan con la clave de cliente son necesarias para tener habilitada la eliminación suave.</span><span class="sxs-lookup"><span data-stu-id="51bca-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="51bca-260">La eliminación suave actúa como una papelera de reciclaje y permite la recuperación durante un máximo de 90 días sin necesidad de restaurar.</span><span class="sxs-lookup"><span data-stu-id="51bca-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="51bca-261">La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="51bca-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="51bca-262">Si debe restaurar una clave para su uso con la clave de cliente, en Azure PowerShell, ejecute el cmdlet Restore-AzureKeyVaultKey de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="51bca-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="51bca-263">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="51bca-264">Si el almacén de claves ya contiene una clave con el mismo nombre, se produce un error en la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="51bca-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="51bca-265">Restore-AzKeyVaultKey restaura todas las versiones de clave y todos los metadatos de la clave, incluido el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="51bca-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="51bca-266">Administrar permisos del almacén de claves</span><span class="sxs-lookup"><span data-stu-id="51bca-266">Manage key vault permissions</span></span>

<span data-ttu-id="51bca-267">Hay varios cmdlets disponibles que permiten ver y, si es necesario, quitar permisos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="51bca-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="51bca-268">Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo.</span><span class="sxs-lookup"><span data-stu-id="51bca-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="51bca-269">Para cada una de estas tareas, usará Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51bca-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="51bca-270">Para obtener información sobre Azure PowerShell, vea [Overview of Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="51bca-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="51bca-271">Para ver los permisos del almacén de claves, ejecute el cmdlet Get-AzKeyVault clave.</span><span class="sxs-lookup"><span data-stu-id="51bca-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="51bca-272">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="51bca-273">Para quitar los permisos de un administrador, ejecute el cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="51bca-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="51bca-274">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51bca-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="51bca-275">Revertir de clave de cliente a claves administradas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="51bca-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="51bca-276">Si necesita volver a las claves administradas por Microsoft, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="51bca-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="51bca-277">Cuando se desaborde, los datos se vuelve a cifrar con el cifrado predeterminado admitido por cada carga de trabajo individual.</span><span class="sxs-lookup"><span data-stu-id="51bca-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="51bca-278">Por ejemplo, Exchange Online cifrado predeterminado mediante claves administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51bca-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51bca-279">El offboarding no es lo mismo que una purga de datos.</span><span class="sxs-lookup"><span data-stu-id="51bca-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="51bca-280">Una purga de datos elimina de forma permanente los datos de la organización Microsoft 365, la eliminación de datos no se realiza.</span><span class="sxs-lookup"><span data-stu-id="51bca-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="51bca-281">No puede realizar una purga de datos para una directiva de varias cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51bca-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="51bca-282">If you decide not to use Customer Key for assigning multi-workload DEP anymore, you'll need to reach out to Microsoft support with a request to "offboard" from Customer Key.</span><span class="sxs-lookup"><span data-stu-id="51bca-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="51bca-283">Pida al equipo de soporte técnico que haga una solicitud de servicio Microsoft 365 equipo de clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="51bca-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="51bca-284">Llega a m365-ck@service.microsoft.com si tienes alguna pregunta.</span><span class="sxs-lookup"><span data-stu-id="51bca-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="51bca-285">Si ya no desea cifrar buzones individuales con DEP de nivel de buzón, puede desasignación de DEP de nivel de buzón de todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="51bca-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="51bca-286">Para desasignación de DEP de buzones de correo, use el Set-Mailbox cmdlet de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51bca-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="51bca-287">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51bca-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="51bca-288">Ejecute el cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="51bca-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="51bca-289">Al ejecutar este cmdlet, se desasoyó el DEP asignado actualmente y se vuelve a cifrar el buzón con el DEP asociado con las claves administradas por Microsoft predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="51bca-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="51bca-290">No puede desasignar el DEP usado por las claves administradas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51bca-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="51bca-291">Si no desea usar claves administradas por Microsoft, puede asignar otro DEP de clave de cliente al buzón.</span><span class="sxs-lookup"><span data-stu-id="51bca-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="51bca-292">Revocar las claves e iniciar el proceso de ruta de depuración de datos</span><span class="sxs-lookup"><span data-stu-id="51bca-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="51bca-293">Controle la revocación de todas las claves raíz, incluida la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="51bca-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="51bca-294">La clave de cliente proporciona el control del aspecto de la planeación de salida de los requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="51bca-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="51bca-295">Si decide revocar las claves para purgar los datos y salir del servicio, el servicio elimina la clave de disponibilidad una vez completado el proceso de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="51bca-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="51bca-296">Esto es compatible con los DEP de clave de cliente que están asignados a buzones individuales.</span><span class="sxs-lookup"><span data-stu-id="51bca-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="51bca-297">Microsoft 365 auditorías y valida la ruta de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="51bca-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="51bca-298">Para obtener más información, vea el informe SSAE 18 SOC 2 disponible en [el Portal de confianza de servicio](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="51bca-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="51bca-299">Además, Microsoft recomienda los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="51bca-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="51bca-300">Guía de evaluación y cumplimiento de riesgos para instituciones financieras en Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="51bca-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="51bca-301">Consideraciones sobre la planeación de salida de O365</span><span class="sxs-lookup"><span data-stu-id="51bca-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="51bca-302">La depuración de DEP de varias cargas de trabajo no se admite Microsoft 365 clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="51bca-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="51bca-303">El DEP de varias cargas de trabajo se usa para cifrar datos en varias cargas de trabajo en todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="51bca-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="51bca-304">La depuración de este DEP daría como resultado que los datos de varias cargas de trabajo se vuelvan inaccesibles.</span><span class="sxs-lookup"><span data-stu-id="51bca-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="51bca-305">Si decide salir de Microsoft 365 servicios, podría seguir la ruta de eliminación del espacio empresarial por el proceso documentado.</span><span class="sxs-lookup"><span data-stu-id="51bca-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="51bca-306">Vea [cómo eliminar un inquilino en Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="51bca-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="51bca-307">Revocar las claves de cliente y la clave de disponibilidad para Exchange Online y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="51bca-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="51bca-308">Al iniciar la ruta de depuración de datos para Exchange Online y Skype Empresarial, se establece una solicitud de purga de datos permanente en un DEP.</span><span class="sxs-lookup"><span data-stu-id="51bca-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="51bca-309">Al hacerlo, se eliminan permanentemente los datos cifrados dentro de los buzones a los que está asignado ese DEP.</span><span class="sxs-lookup"><span data-stu-id="51bca-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="51bca-310">Dado que solo puede ejecutar el cmdlet de PowerShell en un DEP a la vez, considere la posibilidad de reasignar un solo DEP a todos los buzones antes de iniciar la ruta de depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="51bca-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="51bca-311">No use la ruta de depuración de datos para eliminar un subconjunto de los buzones.</span><span class="sxs-lookup"><span data-stu-id="51bca-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="51bca-312">Este proceso solo está pensado para los clientes que salen del servicio.</span><span class="sxs-lookup"><span data-stu-id="51bca-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="51bca-313">Para iniciar la ruta de depuración de datos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51bca-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="51bca-314">Quite los permisos de ajuste y desenvolver para "O365 Exchange Online" de Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="51bca-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="51bca-315">Con una cuenta profesional o educativa que tenga privilegios de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51bca-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="51bca-316">Para cada DEP que contenga buzones que desee eliminar, ejecute el cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="51bca-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="51bca-317">Si se produce un error en el comando, asegúrese de que ha quitado los permisos de Exchange Online de ambas claves en Azure Key Vault, tal como se especificó anteriormente en esta tarea.</span><span class="sxs-lookup"><span data-stu-id="51bca-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="51bca-318">Una vez que haya establecido el modificador PermanentDataPurgeRequested mediante el cmdlet Set-DataEncryptionPolicy, ya no podrá asignar este DEP a los buzones.</span><span class="sxs-lookup"><span data-stu-id="51bca-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="51bca-319">Póngase en contacto con el soporte técnico de Microsoft y solicite el eDocument de purga de datos.</span><span class="sxs-lookup"><span data-stu-id="51bca-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="51bca-320">A su solicitud, Microsoft le envía un documento legal para confirmar y autorizar la eliminación de datos.</span><span class="sxs-lookup"><span data-stu-id="51bca-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="51bca-321">La persona de la organización que se inscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento.</span><span class="sxs-lookup"><span data-stu-id="51bca-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="51bca-322">Normalmente, se trata de una persona ejecutiva u otra persona designada en su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="51bca-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="51bca-323">Una vez que el representante haya firmado el documento legal, descóyalo a Microsoft (normalmente a través de una firma de eDoc).</span><span class="sxs-lookup"><span data-stu-id="51bca-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="51bca-324">Una vez que Microsoft recibe el documento legal, Microsoft ejecuta cmdlets para desencadenar la purga de datos que elimina primero la directiva, marca los buzones para su eliminación permanente y, a continuación, elimina la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="51bca-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="51bca-325">Una vez completado el proceso de purga de datos, los datos se han purgado, no se puede Exchange Online y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="51bca-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="51bca-326">Revocar las claves de cliente y la clave de disponibilidad para SharePoint Online, OneDrive para la Empresa y Teams archivos</span><span class="sxs-lookup"><span data-stu-id="51bca-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="51bca-327">Para iniciar la ruta de depuración de datos para SharePoint Online, OneDrive para la Empresa y Teams, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51bca-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="51bca-328">Revocar el acceso a Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="51bca-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="51bca-329">Todos los administradores del almacén de claves deben aceptar revocar el acceso.</span><span class="sxs-lookup"><span data-stu-id="51bca-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="51bca-330">No elimina Azure Key Vault para SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="51bca-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="51bca-331">Los almacenes de claves pueden compartirse entre varios SharePoint inquilinos y DEP en línea.</span><span class="sxs-lookup"><span data-stu-id="51bca-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="51bca-332">Póngase en contacto con Microsoft para eliminar la clave de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="51bca-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="51bca-333">Cuando se contacte con Microsoft para eliminar la clave de disponibilidad, le enviaremos un documento legal.</span><span class="sxs-lookup"><span data-stu-id="51bca-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="51bca-334">La persona de la organización que se inscribió como aprobador en la oferta de FastTrack durante la incorporación debe firmar este documento.</span><span class="sxs-lookup"><span data-stu-id="51bca-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="51bca-335">Normalmente, se trata de una persona ejecutiva u otra persona designada en su empresa que tiene autorización legal para firmar los documentos en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="51bca-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="51bca-336">Una vez que el representante firme el documento legal, descóyalo a Microsoft (normalmente a través de una firma de eDoc).</span><span class="sxs-lookup"><span data-stu-id="51bca-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="51bca-337">Una vez que Microsoft recibe el documento legal, ejecutamos cmdlets para desencadenar la purga de datos que realiza la eliminación de criptografía de la clave de inquilino, la clave de sitio y todas las claves individuales por documento, lo que rompe irrevocablemente la jerarquía de claves.</span><span class="sxs-lookup"><span data-stu-id="51bca-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="51bca-338">Una vez completados los cmdlets de purga de datos, los datos se han purgado.</span><span class="sxs-lookup"><span data-stu-id="51bca-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="51bca-339">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="51bca-339">Related articles</span></span>

- [<span data-ttu-id="51bca-340">Cifrado de servicio con clave de cliente</span><span class="sxs-lookup"><span data-stu-id="51bca-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="51bca-341">Obtenga información sobre la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="51bca-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="51bca-342">Configurar clave de cliente</span><span class="sxs-lookup"><span data-stu-id="51bca-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="51bca-343">Rotar o alternar una Clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="51bca-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="51bca-344">Caja de seguridad del cliente</span><span class="sxs-lookup"><span data-stu-id="51bca-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="51bca-345">Cifrado de servicio</span><span class="sxs-lookup"><span data-stu-id="51bca-345">Service Encryption</span></span>](office-365-service-encryption.md)