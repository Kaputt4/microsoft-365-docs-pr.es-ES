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
description: 'Resumen: use PowerShell para administrar las propiedades de la cuenta de usuario de Skype Empresarial Online con directivas.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477046"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="94b99-103">Administrar las directivas de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="94b99-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="94b99-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="94b99-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94b99-105">Para administrar muchas propiedades de cuenta de usuario para Skype Empresarial Online, debe especificarlas como propiedades de directivas con PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94b99-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="94b99-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="94b99-106">Before you begin</span></span>

<span data-ttu-id="94b99-107">Siga estas instrucciones para configurarse para ejecutar los comandos (omita los pasos que ya ha completado):</span><span class="sxs-lookup"><span data-stu-id="94b99-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="94b99-108">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="94b99-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="94b99-109">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="94b99-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="94b99-110">Instale el módulo [de PowerShell de Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="94b99-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="94b99-111">Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="94b99-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   <span data-ttu-id="94b99-112">Cuando se le solicite, escriba el nombre y la contraseña de su cuenta de administrador de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="94b99-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="94b99-113">Administrar directivas de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="94b99-113">Manage user account policies</span></span>

<span data-ttu-id="94b99-114">Muchas propiedades de cuenta de usuario de Skype Empresarial Online se configuran mediante directivas.</span><span class="sxs-lookup"><span data-stu-id="94b99-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="94b99-115">Las directivas son simplemente colecciones de configuraciones que se pueden aplicar a uno o más usuarios.</span><span class="sxs-lookup"><span data-stu-id="94b99-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="94b99-116">Para echar un vistazo a cómo se ha configurado una directiva, puede ejecutar este comando de ejemplo para la directiva FederationAndPICDefault:</span><span class="sxs-lookup"><span data-stu-id="94b99-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="94b99-117">A su vez, debería obtener algo similar a esto:</span><span class="sxs-lookup"><span data-stu-id="94b99-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="94b99-118">En este ejemplo, los valores de esta directiva determinan lo que un uso puede o no hacer cuando se trata de comunicarse con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="94b99-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="94b99-119">Por ejemplo, la propiedad EnableOutsideAccess debe establecerse en True para que un usuario pueda comunicarse con personas ajenas a la organización.</span><span class="sxs-lookup"><span data-stu-id="94b99-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="94b99-120">Tenga en cuenta que esta propiedad no aparece en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94b99-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="94b99-121">En su lugar, la propiedad se establece automáticamente en True o False en función de las demás selecciones que realice.</span><span class="sxs-lookup"><span data-stu-id="94b99-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="94b99-122">Las otras dos propiedades de interés son:</span><span class="sxs-lookup"><span data-stu-id="94b99-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="94b99-123">**EnableFederationAccess** indica si el usuario puede comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="94b99-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="94b99-124">**EnablePublicCloudAccess** indica si el usuario puede comunicarse con usuarios de Windows Live.</span><span class="sxs-lookup"><span data-stu-id="94b99-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="94b99-125">Por lo tanto, no se cambian directamente las propiedades relacionadas con la federación en las cuentas de usuario (por ejemplo, **Set-CsUser -EnableFederationAccess $True**).</span><span class="sxs-lookup"><span data-stu-id="94b99-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="94b99-126">En su lugar, asigne a una cuenta una directiva de acceso externo que tenga preconfigurados los valores de propiedad deseados.</span><span class="sxs-lookup"><span data-stu-id="94b99-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="94b99-127">Si queremos que un usuario pueda comunicarse con usuarios federados y con usuarios Windows Live, esa cuenta de usuario debe tener asignada una directiva que permita esos tipos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="94b99-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="94b99-128">Si desea saber si alguien puede comunicarse o no con usuarios externos a la organización, debe:</span><span class="sxs-lookup"><span data-stu-id="94b99-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="94b99-129">Determinar qué directiva de acceso externo se ha asignado a dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="94b99-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="94b99-130">Determinar qué capacidades permite o no dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="94b99-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="94b99-131">Por ejemplo, puede hacerlo con este comando:</span><span class="sxs-lookup"><span data-stu-id="94b99-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="94b99-132">Este comando busca la directiva asignada al usuario y, a continuación, busca las funcionalidades habilitadas o deshabilitadas en esa directiva.</span><span class="sxs-lookup"><span data-stu-id="94b99-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="94b99-133">Para administrar directivas de Skype Empresarial Online con PowerShell, consulte los cmdlets para:</span><span class="sxs-lookup"><span data-stu-id="94b99-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="94b99-134">[Directiva de cliente](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="94b99-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="94b99-135">[Directiva de conferencia](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="94b99-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="94b99-136">[Directiva móvil](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="94b99-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="94b99-137">[Directiva de correo de voz en línea](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="94b99-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="94b99-138">[Directiva de enrutamiento de voz](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="94b99-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="94b99-139">Un plan de marcado de Skype Empresarial Online es una directiva en todos los aspectos excepto el nombre.</span><span class="sxs-lookup"><span data-stu-id="94b99-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="94b99-140">Se eligió el nombre "plan de marcado" en lugar de, por ejemplo, "directiva de marcado" para proporcionar compatibilidad con versiones anteriores con Office Communications Server y con Exchange.</span><span class="sxs-lookup"><span data-stu-id="94b99-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="94b99-141">Por ejemplo, para ver todas las directivas de voz disponibles para su uso, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="94b99-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="94b99-142">Eso devuelve una lista de todas las directivas de voz disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="94b99-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="94b99-143">Sin embargo, tenga en cuenta que no todas las directivas se pueden asignar a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="94b99-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="94b99-144">Esto se debe a diversas restricciones relacionadas con las licencias y la ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="94b99-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="94b99-145">(La denominada "ubicación[de uso").](https://msdn.microsoft.com/library/azure/dn194136.aspx) Si desea conocer las directivas de acceso externo y las directivas de conferencia que se pueden asignar a un usuario determinado, use comandos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="94b99-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="94b99-p107">El parámetro ApplicableTo limita los datos devueltos a las directivas que se pueden asignar al usuario especificado (por ejemplo, Alex Darrow). Según las licencias y las restricciones de ubicación de uso, eso puede representar un subconjunto de todas las directivas disponibles.</span><span class="sxs-lookup"><span data-stu-id="94b99-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="94b99-148">En algunos casos, las propiedades de las directivas no se usan con Microsoft 365, mientras que otros solo pueden ser administrados por el personal de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94b99-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="94b99-149">Con Skype Empresarial Online, los usuarios deben ser administrados por una directiva de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="94b99-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="94b99-150">Si una propiedad válida relacionada con la directiva está en blanco, significa que el usuario en cuestión está siendo administrado por una directiva global, que es una directiva que se aplica automáticamente a un usuario a menos que se le asigne específicamente una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="94b99-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="94b99-151">Dado que no vemos una directiva de cliente para una cuenta de usuario, se administra mediante la directiva global.</span><span class="sxs-lookup"><span data-stu-id="94b99-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="94b99-152">Puede determinar la directiva de cliente global con este comando:</span><span class="sxs-lookup"><span data-stu-id="94b99-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="94b99-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="94b99-153">See also</span></span>

[<span data-ttu-id="94b99-154">Administrar Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="94b99-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="94b99-155">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="94b99-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="94b99-156">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94b99-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

