---
title: Administrar las directivas de Skype Empresarial Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Summary: Use PowerShell to manage your Skype Empresarial Online user account properties with policies.'
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916707"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="ef816-103">Administrar las directivas de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef816-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="ef816-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ef816-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ef816-105">Para administrar muchas propiedades de cuenta de usuario para Skype Empresarial Online, debe especificarlas como propiedades de directivas con PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef816-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ef816-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ef816-106">Before you begin</span></span>

<span data-ttu-id="ef816-107">Use estas instrucciones para configurarse para ejecutar los comandos (omita los pasos que ya ha completado):</span><span class="sxs-lookup"><span data-stu-id="ef816-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="ef816-108">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="ef816-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="ef816-109">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ef816-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="ef816-110">Instale el [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="ef816-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="ef816-111">Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="ef816-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="ef816-112">Cuando se le pida, escriba su Skype Empresarial nombre y contraseña de la cuenta de administrador en línea.</span><span class="sxs-lookup"><span data-stu-id="ef816-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="ef816-113">Administrar directivas de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ef816-113">Manage user account policies</span></span>

<span data-ttu-id="ef816-114">Muchas Skype Empresarial de cuentas de usuario en línea se configuran mediante directivas.</span><span class="sxs-lookup"><span data-stu-id="ef816-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="ef816-115">Las directivas son simplemente colecciones de configuraciones que se pueden aplicar a uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="ef816-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="ef816-116">Para echar un vistazo a cómo se ha configurado una directiva, puede ejecutar este comando de ejemplo para la directiva FederationAndPICDefault:</span><span class="sxs-lookup"><span data-stu-id="ef816-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="ef816-117">A su vez, debes recuperar algo similar a esto:</span><span class="sxs-lookup"><span data-stu-id="ef816-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="ef816-118">En este ejemplo, los valores de esta directiva determinan lo que un uso puede o no puede hacer cuando se trata de comunicarse con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="ef816-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="ef816-119">Por ejemplo, la propiedad EnableOutsideAccess debe establecerse en True para que un usuario pueda comunicarse con personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="ef816-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="ef816-120">Tenga en cuenta que esta propiedad no aparece en el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="ef816-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ef816-121">En su lugar, la propiedad se establece automáticamente en True o False en función de las demás selecciones que realice.</span><span class="sxs-lookup"><span data-stu-id="ef816-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="ef816-122">Las otras dos propiedades de interés son:</span><span class="sxs-lookup"><span data-stu-id="ef816-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="ef816-123">**EnableFederationAccess** indica si el usuario puede comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="ef816-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="ef816-124">**EnablePublicCloudAccess** indica si el usuario puede comunicarse con usuarios de Windows Live.</span><span class="sxs-lookup"><span data-stu-id="ef816-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="ef816-125">Por lo tanto, no cambia directamente las propiedades relacionadas con la federación en cuentas de usuario (por ejemplo, **Set-CsUser -EnableFederationAccess $True**).</span><span class="sxs-lookup"><span data-stu-id="ef816-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="ef816-126">En su lugar, asigne a una cuenta una directiva de acceso externo que tenga preconfigurados los valores de propiedad deseados.</span><span class="sxs-lookup"><span data-stu-id="ef816-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="ef816-127">Si queremos que un usuario pueda comunicarse con usuarios federados y con usuarios de Windows Live, esa cuenta de usuario debe tener asignada una directiva que permita esos tipos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="ef816-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="ef816-128">Si desea saber si alguien puede comunicarse o no con usuarios de fuera de la organización, debe:</span><span class="sxs-lookup"><span data-stu-id="ef816-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="ef816-129">Determinar qué directiva de acceso externo se ha asignado a dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="ef816-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="ef816-130">Determinar qué capacidades permite o no dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="ef816-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="ef816-131">Por ejemplo, puede hacerlo con este comando:</span><span class="sxs-lookup"><span data-stu-id="ef816-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="ef816-132">Este comando busca la directiva asignada al usuario y, a continuación, busca las capacidades habilitadas o deshabilitadas dentro de esa directiva.</span><span class="sxs-lookup"><span data-stu-id="ef816-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="ef816-133">Para administrar Skype Empresarial en línea con PowerShell, consulte los cmdlets para:</span><span class="sxs-lookup"><span data-stu-id="ef816-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="ef816-134">[Directiva de cliente](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="ef816-134">[Client policy](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="ef816-135">[Directiva de conferencia](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="ef816-135">[Conferencing policy](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="ef816-136">[Directiva móvil](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="ef816-136">[Mobile policy](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="ef816-137">[Directiva de correo de voz en línea](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="ef816-137">[Online Voicemail policy](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="ef816-138">[Directiva de enrutamiento de voz](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="ef816-138">[Voice Routing policy](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="ef816-139">Un Skype Empresarial de marcado en línea es una directiva en todos los aspectos excepto el nombre.</span><span class="sxs-lookup"><span data-stu-id="ef816-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="ef816-140">El nombre "plan de marcado" se eligió en lugar de, por ejemplo, "directiva de marcado" para proporcionar compatibilidad con versiones anteriores con Office Communications Server y con Exchange.</span><span class="sxs-lookup"><span data-stu-id="ef816-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="ef816-141">Por ejemplo, para ver todas las directivas de voz disponibles para su uso, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="ef816-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="ef816-142">Eso devuelve una lista de todas las directivas de voz disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="ef816-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="ef816-143">Sin embargo, tenga en cuenta que no todas las directivas se pueden asignar a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ef816-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="ef816-144">Esto se debe a varias restricciones relacionadas con las licencias y la ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="ef816-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="ef816-145">(La llamada "[ubicación de uso](/previous-versions/azure/dn194136(v=azure.100)).") Si desea conocer las directivas de acceso externo y las directivas de conferencia que se pueden asignar a un usuario determinado, use comandos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="ef816-145">(The so-called "[usage location](/previous-versions/azure/dn194136(v=azure.100)).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="ef816-p107">El parámetro ApplicableTo limita los datos devueltos a las directivas que se pueden asignar al usuario especificado (por ejemplo, Alex Darrow). Según las licencias y las restricciones de ubicación de uso, eso puede representar un subconjunto de todas las directivas disponibles.</span><span class="sxs-lookup"><span data-stu-id="ef816-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="ef816-148">En algunos casos, las propiedades de las directivas no se usan Microsoft 365, mientras que otras solo pueden administrarse por el personal de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef816-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="ef816-149">Con Skype Empresarial Online, los usuarios deben administrarse mediante una directiva de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="ef816-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="ef816-150">Si una propiedad válida relacionada con la directiva está en blanco, significa que el usuario en cuestión está administrado por una directiva global, que es una directiva que se aplica automáticamente a un usuario a menos que se le asigne específicamente una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="ef816-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="ef816-151">Dado que no vemos una directiva de cliente enumerada para una cuenta de usuario, se administra mediante la directiva global.</span><span class="sxs-lookup"><span data-stu-id="ef816-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="ef816-152">Puede determinar la directiva de cliente global con este comando:</span><span class="sxs-lookup"><span data-stu-id="ef816-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="ef816-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef816-153">See also</span></span>

[<span data-ttu-id="ef816-154">Administrar Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef816-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ef816-155">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef816-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ef816-156">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef816-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)