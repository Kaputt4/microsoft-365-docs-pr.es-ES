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
description: 'Resumen: Use PowerShell para administrar las propiedades de la cuenta de usuario de Skype empresarial online con directivas.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477046"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="90787-103">Administrar las directivas de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="90787-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="90787-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="90787-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="90787-105">Para administrar muchas propiedades de la cuenta de usuario de Skype empresarial online, debe especificarlas como propiedades de directivas con PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90787-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="90787-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="90787-106">Before you begin</span></span>

<span data-ttu-id="90787-107">Siga estas instrucciones para preparar la ejecución de los comandos (omita los pasos que ya ha completado):</span><span class="sxs-lookup"><span data-stu-id="90787-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="90787-108">En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90787-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="90787-109">Si usa la versión pública de Microsoft Teams más reciente, no es necesario que instale el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="90787-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="90787-110">Instale el [módulo de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="90787-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="90787-111">Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="90787-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   <span data-ttu-id="90787-112">Cuando se le solicite, escriba el nombre y la contraseña de la cuenta de administrador en línea de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="90787-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="90787-113">Administrar directivas de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="90787-113">Manage user account policies</span></span>

<span data-ttu-id="90787-114">Muchas de las propiedades de las cuentas de usuario de Skype empresarial online se configuran mediante directivas.</span><span class="sxs-lookup"><span data-stu-id="90787-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="90787-115">Las directivas son simplemente colecciones de opciones de configuración que se pueden aplicar a uno o más usuarios.</span><span class="sxs-lookup"><span data-stu-id="90787-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="90787-116">Para echar un vistazo al modo en que se ha configurado la Directiva, puede ejecutar este comando de ejemplo para la Directiva FederationAndPICDefault:</span><span class="sxs-lookup"><span data-stu-id="90787-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="90787-117">Por su parte, debería obtener algo similar a esto:</span><span class="sxs-lookup"><span data-stu-id="90787-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="90787-118">En este ejemplo, los valores de esta directiva determinan lo que un uso puede o no hacer cuando se trata de comunicarse con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="90787-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="90787-119">Por ejemplo, la propiedad EnableOutsideAccess debe establecerse en true para que un usuario pueda comunicarse con personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="90787-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="90787-120">Tenga en cuenta que esta propiedad no aparece en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90787-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="90787-121">En su lugar, la propiedad se establece automáticamente en true o false en función de las otras selecciones que realice.</span><span class="sxs-lookup"><span data-stu-id="90787-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="90787-122">Las otras dos propiedades de interés son:</span><span class="sxs-lookup"><span data-stu-id="90787-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="90787-123">**EnableFederationAccess** indica si el usuario puede comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="90787-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="90787-124">**EnablePublicCloudAccess** indica si el usuario puede comunicarse con usuarios de Windows Live.</span><span class="sxs-lookup"><span data-stu-id="90787-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="90787-125">Por lo tanto, no cambie directamente las propiedades relacionadas con la Federación de las cuentas de usuario (por ejemplo, **set-CsUser-EnableFederationAccess $true**).</span><span class="sxs-lookup"><span data-stu-id="90787-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="90787-126">En su lugar, asigna a una cuenta una directiva de acceso externo que tiene los valores de propiedad deseados preconfigurados.</span><span class="sxs-lookup"><span data-stu-id="90787-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="90787-127">Si queremos que un usuario pueda comunicarse con usuarios federados y con usuarios de Windows Live, la cuenta de usuario debe tener asignada una directiva que permita estos tipos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="90787-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="90787-128">Si desea saber si alguien puede comunicarse con usuarios externos a la organización, debe:</span><span class="sxs-lookup"><span data-stu-id="90787-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="90787-129">Determinar qué directiva de acceso externo se ha asignado a dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="90787-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="90787-130">Determinar qué capacidades permite o no dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="90787-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="90787-131">Por ejemplo, puede hacerlo con este comando:</span><span class="sxs-lookup"><span data-stu-id="90787-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="90787-132">Este comando busca la directiva asignada al usuario y, a continuación, busca las funciones habilitadas o deshabilitadas en esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="90787-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="90787-133">Para administrar las directivas de Skype empresarial online con PowerShell, consulte los cmdlets de:</span><span class="sxs-lookup"><span data-stu-id="90787-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="90787-134">[Directiva de cliente](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="90787-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="90787-135">[Directiva de conferencia](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="90787-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="90787-136">[Directiva móvil](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="90787-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="90787-137">[Directiva de correo de voz en línea](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="90787-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="90787-138">[Directiva de enrutamiento de voz](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="90787-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="90787-139">Un plan de marcado de Skype empresarial online es una directiva en todos los aspectos excepto en el nombre.</span><span class="sxs-lookup"><span data-stu-id="90787-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="90787-140">Se ha elegido el nombre "plan de marcado" en lugar de, por ejemplo, "Directiva de marcado" para proporcionar compatibilidad con versiones anteriores de Office Communications Server y con Exchange.</span><span class="sxs-lookup"><span data-stu-id="90787-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="90787-141">Por ejemplo, para ver todas las directivas de voz disponibles para su uso, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="90787-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="90787-142">Eso devuelve una lista de todas las directivas de voz disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="90787-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="90787-143">No obstante, tenga en cuenta que no todas las directivas se pueden asignar a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="90787-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="90787-144">Esto se debe a varias restricciones relacionadas con la concesión de licencias y la ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="90787-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="90787-145">(El denominado "ubicación de[uso](https://msdn.microsoft.com/library/azure/dn194136.aspx)"). Si desea conocer las directivas de acceso externo y las directivas de conferencia que se pueden asignar a un usuario en particular, use comandos similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="90787-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="90787-p107">El parámetro ApplicableTo limita los datos devueltos a las directivas que se pueden asignar al usuario especificado (por ejemplo, Alex Darrow). Según las licencias y las restricciones de ubicación de uso, eso puede representar un subconjunto de todas las directivas disponibles.</span><span class="sxs-lookup"><span data-stu-id="90787-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="90787-148">En algunos casos, las propiedades de las directivas no se usan con Microsoft 365, mientras que otras solo pueden ser administradas por el personal de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90787-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="90787-149">Con Skype empresarial online, los usuarios deben ser administrados por una directiva de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="90787-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="90787-150">Si una propiedad relacionada con directivas válida está en blanco, significa que el usuario en cuestión se administra mediante una directiva global, que es una directiva que se aplica automáticamente a un usuario a menos que se le asigne específicamente una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="90787-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="90787-151">Como no vemos una directiva de cliente listada para una cuenta de usuario, ésta se administra mediante la directiva global.</span><span class="sxs-lookup"><span data-stu-id="90787-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="90787-152">Puede determinar la Directiva de cliente global con este comando:</span><span class="sxs-lookup"><span data-stu-id="90787-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="90787-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="90787-153">See also</span></span>

[<span data-ttu-id="90787-154">Administrar Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="90787-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="90787-155">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="90787-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="90787-156">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90787-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

