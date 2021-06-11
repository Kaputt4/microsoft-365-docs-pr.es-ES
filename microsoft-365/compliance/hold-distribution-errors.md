---
title: Solución de problemas de suspensión de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Solucionar errores relacionados con las retenciones legales aplicadas a custodios y orígenes de datos no custodiados en eDiscovery principal.
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538476"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="fad81-103">Solución de problemas de suspensión de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fad81-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="fad81-104">En este artículo se analizan los problemas comunes que pueden producirse con las retenciones de exhibición de documentos electrónicos y cómo resolverlos.</span><span class="sxs-lookup"><span data-stu-id="fad81-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="fad81-105">El artículo también incluye prácticas recomendadas para ayudarle a mitigar o evitar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="fad81-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="fad81-106">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="fad81-106">Recommended practices</span></span>

<span data-ttu-id="fad81-107">Para reducir el número de errores relacionados con las retenciones de exhibición de documentos electrónicos, se recomiendan los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="fad81-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="fad81-108">Si una distribución de retención aún está pendiente, con un estado de o , espere hasta que se complete la distribución de retención antes de `On (Pending)` `Off (Pending)` realizar más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="fad81-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="fad81-109">Compruebe si una directiva de retención está pendiente antes de realizar más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="fad81-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="fad81-110">Ejecute los siguientes comandos o guárdelos en un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fad81-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="fad81-111">Combina las actualizaciones en una retención de exhibición de documentos electrónicos en una única solicitud masiva en lugar de actualizar la directiva de retención repetidamente para cada transacción.</span><span class="sxs-lookup"><span data-stu-id="fad81-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="fad81-112">Por ejemplo, para agregar varios buzones de usuario a una directiva de retención existente mediante el cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) ejecute el comando (o agregue como un bloque de código a un script) para que se ejecute solo una vez para agregar varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="fad81-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="fad81-113">**Correcto:**</span><span class="sxs-lookup"><span data-stu-id="fad81-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="fad81-114">**Incorrecto:**</span><span class="sxs-lookup"><span data-stu-id="fad81-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="fad81-115">En el ejemplo incorrecto anterior, el cmdlet se ejecuta cinco veces distintas para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="fad81-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="fad81-116">Para obtener más información acerca de los procedimientos recomendados para agregar usuarios a una directiva de retención, vea la [sección Más](#more-information) información.</span><span class="sxs-lookup"><span data-stu-id="fad81-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="fad81-117">Antes de ponerse en contacto con el Soporte técnico de Microsoft sobre problemas de retención de exhibición de documentos electrónicos, siga los pasos de la sección [Error/problema:](#errorissue-holds-dont-sync) las retenciones no se sincronizan para reintentar la distribución de retención.</span><span class="sxs-lookup"><span data-stu-id="fad81-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="fad81-118">Este proceso suele resolver problemas temporales, incluidos los errores internos del servidor.</span><span class="sxs-lookup"><span data-stu-id="fad81-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="fad81-119">Error o problema: las retenciones no se sincronizan</span><span class="sxs-lookup"><span data-stu-id="fad81-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="fad81-120">Si ve uno de los siguientes mensajes de error al poner a los custodios y orígenes de datos en espera, siga los pasos de resolución para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="fad81-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="fad81-121">Recursos: tarda más de lo esperado en implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="fad81-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="fad81-122">Podría tardar 2 horas adicionales en actualizar el estado de implementación final, por lo que vuelve a comprobarlo en un par de horas.</span><span class="sxs-lookup"><span data-stu-id="fad81-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="fad81-123">La directiva no se puede implementar en el origen de contenido debido a un problema Office 365 centro de datos.</span><span class="sxs-lookup"><span data-stu-id="fad81-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="fad81-124">La directiva actual no se aplica a ningún contenido del origen, por lo que no hay ningún impacto de la implementación bloqueada.</span><span class="sxs-lookup"><span data-stu-id="fad81-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="fad81-125">Para solucionar este problema, intente volver a implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="fad81-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="fad81-126">Lo sentimos, no pudimos realizar los cambios solicitados en la directiva debido a un error transitorio del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="fad81-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="fad81-127">Vuelva a intentarlo en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="fad81-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="fad81-128">Solución</span><span class="sxs-lookup"><span data-stu-id="fad81-128">Resolution</span></span>

1. <span data-ttu-id="fad81-129">Conectar [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y cumplimiento y ejecute el siguiente comando para una retención de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="fad81-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="fad81-130">Examine el valor del parámetro *DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="fad81-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="fad81-131">Busque errores como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fad81-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="fad81-132">Error: Recursos: tarda más de lo esperado en implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="fad81-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="fad81-133">Podría tardar 2 horas adicionales en actualizar el estado de implementación final, por lo que vuelve a comprobarlo en un par de horas.</span><span class="sxs-lookup"><span data-stu-id="fad81-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="fad81-134">Intente ejecutar el **comando Set-CaseHoldPolicy -RetryDistribution** en la directiva de retención en cuestión; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fad81-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="fad81-135">Error: el sitio SharePoint es de solo lectura o no es accesible</span><span class="sxs-lookup"><span data-stu-id="fad81-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="fad81-136">Si ve el siguiente mensaje de error al poner en espera a los custodios y los orígenes de datos, significa que el administrador [global](/sharepoint/sharepoint-admin-role) de la organización o el administrador SharePoint ha bloqueado el sitio.</span><span class="sxs-lookup"><span data-stu-id="fad81-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="fad81-137">Un sitio bloqueado impide que la exhibición de documentos electrónicos coloque una retención en el sitio.</span><span class="sxs-lookup"><span data-stu-id="fad81-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="fad81-138">El SharePoint es de solo lectura o no es accesible.</span><span class="sxs-lookup"><span data-stu-id="fad81-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="fad81-139">Póngase en contacto con el administrador del sitio para que el sitio se grabe y, a continuación, vuelva a implementar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="fad81-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="fad81-140">Solución</span><span class="sxs-lookup"><span data-stu-id="fad81-140">Resolution</span></span>

<span data-ttu-id="fad81-141">Desbloquea el sitio (o pide a un administrador que lo desbloquee) para resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="fad81-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="fad81-142">Para obtener más información sobre cómo cambiar el estado de bloqueo de un sitio, vea [Bloquear y desbloquear sitios](/sharepoint/manage-lock-status).</span><span class="sxs-lookup"><span data-stu-id="fad81-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="fad81-143">Error: es posible que el buzón SharePoint sitio no exista</span><span class="sxs-lookup"><span data-stu-id="fad81-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="fad81-144">Si ve el siguiente mensaje de error al poner en espera a los custodios y orígenes de datos, siga los pasos de resolución para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="fad81-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="fad81-145">Es posible que el buzón SharePoint sitio no exista.</span><span class="sxs-lookup"><span data-stu-id="fad81-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="fad81-146">Si esto es incorrecto, póngase en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fad81-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="fad81-147">De lo contrario, quítela de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="fad81-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="fad81-148">Solución</span><span class="sxs-lookup"><span data-stu-id="fad81-148">Resolution</span></span>

- <span data-ttu-id="fad81-149">Ejecute [get-mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell para comprobar si el buzón de usuario existe en la organización.</span><span class="sxs-lookup"><span data-stu-id="fad81-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="fad81-150">Ejecute el cmdlet [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) en SharePoint PowerShell en línea para comprobar si el sitio existe en la organización.</span><span class="sxs-lookup"><span data-stu-id="fad81-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="fad81-151">Compruebe si la dirección URL del sitio ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="fad81-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="fad81-152">Más información</span><span class="sxs-lookup"><span data-stu-id="fad81-152">More information</span></span>

<span data-ttu-id="fad81-153">Las instrucciones sobre cómo actualizar directivas de retención para varios usuarios en la sección "Prácticas recomendadas" se deben al hecho de que el sistema bloquea las actualizaciones simultáneas de una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="fad81-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="fad81-154">Esto significa que cuando se aplica una directiva de retención actualizada a nuevas ubicaciones de contenido y la directiva de retención está en un estado pendiente, no se pueden agregar ubicaciones de contenido adicionales a la directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="fad81-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="fad81-155">Estas son algunas cosas que debe tener en cuenta para ayudarle a mitigar este problema:</span><span class="sxs-lookup"><span data-stu-id="fad81-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="fad81-156">Cada vez que se actualiza una retención, pasa inmediatamente a un estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="fad81-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="fad81-157">El estado pendiente significa que la retención se aplica a las ubicaciones de contenido.</span><span class="sxs-lookup"><span data-stu-id="fad81-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="fad81-158">Si tiene un script que ejecuta un bucle y agrega ubicaciones a la directiva uno a uno (similar al ejemplo incorrecto que se muestra en la sección "Prácticas recomendadas"), la primera ubicación de contenido (por ejemplo, un buzón de usuario) inicia el proceso de sincronización que desencadena el estado pendiente.</span><span class="sxs-lookup"><span data-stu-id="fad81-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="fad81-159">Esto significa que los demás usuarios que se agregan a la directiva en bucles posteriores producirán un error.</span><span class="sxs-lookup"><span data-stu-id="fad81-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="fad81-160">Si su organización usa un script que ejecuta un bucle para actualizar las ubicaciones de contenido de una directiva de retención, debe actualizar el script para que actualice las ubicaciones en una sola operación masiva (como se muestra en el ejemplo correcto en la sección "Prácticas recomendadas").</span><span class="sxs-lookup"><span data-stu-id="fad81-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
