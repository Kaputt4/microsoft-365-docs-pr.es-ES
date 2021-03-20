---
title: Asignar directivas de Skype Empresarial Online por usuario con PowerShell para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Summary: Use PowerShell for Microsoft 365 to assign per-user communication settings with Skype for Business Online policies.'
ms.openlocfilehash: 2d3d953fe0beb74cc63f914137942f068ce90be7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905409"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="a3224-103">Asignar directivas de Skype Empresarial Online por usuario con PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3224-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="a3224-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a3224-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a3224-105">El uso de PowerShell para Microsoft 365 es una forma eficaz de asignar la configuración de comunicación por usuario con directivas de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a3224-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="a3224-106">Prepararse para ejecutar los comandos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3224-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="a3224-107">Use estas instrucciones para configurarse para ejecutar los comandos (omita los pasos que ya ha completado):</span><span class="sxs-lookup"><span data-stu-id="a3224-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="a3224-108">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="a3224-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="a3224-109">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a3224-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="a3224-110">Instale el [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="a3224-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="a3224-111">Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a3224-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="a3224-112">Cuando se le pida, escriba el nombre y la contraseña de la cuenta de administrador de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a3224-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="a3224-113">Actualización de la configuración de comunicación externa para una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="a3224-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="a3224-114">Supongamos que desea cambiar la configuración de comunicación externa en una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a3224-114">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="a3224-115">Por ejemplo, desea permitir que Alex se comunique con usuarios federados (EnableFederationAccess es igual a True), pero no con usuarios Windows Live (EnablePublicCloudAccess es igual a False).</span><span class="sxs-lookup"><span data-stu-id="a3224-115">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="a3224-116">Para ello, debe hacer dos cosas:</span><span class="sxs-lookup"><span data-stu-id="a3224-116">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="a3224-117">Buscar una directiva de acceso externo que cumpla nuestros criterios.</span><span class="sxs-lookup"><span data-stu-id="a3224-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="a3224-118">Asignar esa directiva de acceso externo a Alex.</span><span class="sxs-lookup"><span data-stu-id="a3224-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="a3224-119">¿Cómo se determina qué directiva de acceso externo asignar a Alex?</span><span class="sxs-lookup"><span data-stu-id="a3224-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="a3224-120">El siguiente comando devuelve todas las directivas de acceso externo donde EnableFederationAccess se establece en True y EnablePublicCloudAccess se establece en False:</span><span class="sxs-lookup"><span data-stu-id="a3224-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="a3224-121">A menos que haya creado instancias personalizadas de ExternalAccessPolicy, ese comando devuelve una directiva que cumple nuestros criterios (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="a3224-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="a3224-122">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a3224-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="a3224-123">Ahora que sabe qué directiva asignar a Alex, podemos asignar esa directiva mediante el cmdlet [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Get-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="a3224-123">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet.</span></span> <span data-ttu-id="a3224-124">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a3224-124">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="a3224-125">Asignar una directiva es bastante sencillo: simplemente especifique la identidad del usuario y el nombre de la directiva que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="a3224-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="a3224-126">Y cuando se trata de directivas y asignaciones de directivas, no se limita a trabajar con cuentas de usuario una vez.</span><span class="sxs-lookup"><span data-stu-id="a3224-126">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="a3224-127">Por ejemplo, supongamos que necesita una lista de todos los usuarios que tienen permiso para comunicarse con los socios federados y los usuarios de Windows Live.</span><span class="sxs-lookup"><span data-stu-id="a3224-127">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="a3224-128">Ya sabemos que a esos usuarios se les ha asignado la directiva de acceso de usuario externo FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="a3224-128">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="a3224-129">Dado que lo sabemos, puede mostrar una lista de todos esos usuarios ejecutando un comando simple.</span><span class="sxs-lookup"><span data-stu-id="a3224-129">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="a3224-130">Este es el comando:</span><span class="sxs-lookup"><span data-stu-id="a3224-130">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="a3224-131">En otras palabras, veremos a todos los usuarios donde la propiedad ExternalAccessPolicy se establece en FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="a3224-131">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="a3224-132">(Y, para limitar la cantidad de información que aparece en pantalla, use el cmdlet Select-Object para mostrarnos solo el nombre para mostrar de cada usuario).</span><span class="sxs-lookup"><span data-stu-id="a3224-132">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="a3224-133">Para configurar todas nuestras cuentas de usuario para que usen esa misma directiva, use este comando:</span><span class="sxs-lookup"><span data-stu-id="a3224-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="a3224-134">Este comando usa Get-CsOnlineUser para devolver una colección de todos los usuarios que se han habilitado para Lync y, a continuación, envía toda esa información a Grant-CsExternalAccessPolicy, que asigna la directiva FederationAndPICDefault a todos y cada uno de los usuarios de la colección.</span><span class="sxs-lookup"><span data-stu-id="a3224-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="a3224-135">Como ejemplo adicional, supongamos que ya asignó a Alex la directiva FederationAndPICDefault y ahora ha cambiado de opinión y le gustaría que la directiva de acceso externo global lo administrara.</span><span class="sxs-lookup"><span data-stu-id="a3224-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="a3224-136">No puede asignar explícitamente la directiva global a nadie.</span><span class="sxs-lookup"><span data-stu-id="a3224-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="a3224-137">En su lugar, la directiva global se usa para un usuario determinado si no se asigna ninguna directiva por usuario a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="a3224-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="a3224-138">Por lo tanto, si queremos que Alex esté administrado por la directiva global, debe  *desasignarlo*  cualquier directiva por usuario asignada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a3224-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="a3224-139">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a3224-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="a3224-140">Este comando establece el nombre de la directiva de acceso externo asignada a Alex en un valor nulo ($Null).</span><span class="sxs-lookup"><span data-stu-id="a3224-140">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="a3224-141">Null significa "nothing".</span><span class="sxs-lookup"><span data-stu-id="a3224-141">Null means "nothing".</span></span> <span data-ttu-id="a3224-142">En otras palabras, no se asigna ninguna directiva de acceso externo a Alex.</span><span class="sxs-lookup"><span data-stu-id="a3224-142">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="a3224-143">Cuando no se asigna ninguna directiva de acceso externo a un usuario, la directiva global administra ese usuario.</span><span class="sxs-lookup"><span data-stu-id="a3224-143">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="a3224-144">Administración de un gran número de usuarios</span><span class="sxs-lookup"><span data-stu-id="a3224-144">Managing large numbers of users</span></span>

<span data-ttu-id="a3224-145">Para administrar un gran número de usuarios (1000 o más), debe procesar por lotes los comandos a través de un bloque de script mediante el cmdlet [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="a3224-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="a3224-146">En ejemplos anteriores, cada vez que se ejecuta un cmdlet, debe configurar la llamada y, a continuación, esperar el resultado antes de enviarlo de vuelta.</span><span class="sxs-lookup"><span data-stu-id="a3224-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="a3224-147">Al usar un bloque de script, esto permite que los cmdlets se ejecuten de forma remota y, una vez completados, envíen los datos de vuelta.</span><span class="sxs-lookup"><span data-stu-id="a3224-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="a3224-148">Esto encontrará 500 usuarios a la vez que no tienen una directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="a3224-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="a3224-149">Se les concederá la directiva de cliente "ClientPolicyNoIMURL" y la directiva de acceso externo "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="a3224-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="a3224-150">Los resultados se agrupan por lotes en grupos de 50 y, a continuación, cada lote de 50 se envía al equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="a3224-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3224-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3224-151">See also</span></span>

[<span data-ttu-id="a3224-152">Administrar Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3224-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a3224-153">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3224-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a3224-154">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3224-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)