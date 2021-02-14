---
title: Migrar búsquedas y retenciones de exhibición de documentos electrónicos heredadas al Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 216ec3853f1b55c7fb34de3a236f50094202bca5
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352470"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="258e5-102">Migrar búsquedas y retenciones de exhibición de documentos electrónicos heredadas al Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="258e5-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="258e5-103">El Centro de cumplimiento de Microsoft 365 proporciona una experiencia mejorada para el uso de la exhibición de documentos electrónicos, incluidos: mayor confiabilidad, mejor rendimiento y muchas características adaptadas a flujos de trabajo de exhibición de documentos electrónicos, incluidos casos para organizar el contenido por asunto, conjuntos de revisión para revisar el contenido y análisis para ayudar a eliminar datos para su revisión, como agrupación casi duplicada, subprocesos de correo electrónico, análisis de temas y codificación predictiva.</span><span class="sxs-lookup"><span data-stu-id="258e5-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="258e5-104">Para ayudar a los clientes a aprovechar las nuevas y mejoradas funciones, en este artículo se proporcionan instrucciones básicas sobre cómo migrar las búsquedas y retenciones de exhibición de documentos electrónicos de In-Place desde el Centro de administración de Exchange al Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="258e5-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="258e5-105">Dado que hay muchos escenarios diferentes, en este artículo se proporcionan instrucciones generales para realizar búsquedas y retenciones de transición a un caso principal de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="258e5-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="258e5-106">El uso de casos de exhibición de documentos electrónicos no siempre es necesario, pero agregan un nivel adicional de seguridad al permitirle asignar permisos para controlar quién tiene acceso a los casos de exhibición de documentos electrónicos en su organización.</span><span class="sxs-lookup"><span data-stu-id="258e5-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="258e5-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="258e5-107">Before you begin</span></span>

- <span data-ttu-id="258e5-108">Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & para ejecutar los comandos de PowerShell que se describen en este artículo.</span><span class="sxs-lookup"><span data-stu-id="258e5-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="258e5-109">También debe ser miembro del grupo de roles Administración de la detección en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="258e5-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="258e5-110">En este artículo se proporcionan instrucciones sobre cómo crear una retención de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="258e5-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="258e5-111">La directiva de retención se aplicará a los buzones a través de un proceso asincrónico.</span><span class="sxs-lookup"><span data-stu-id="258e5-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="258e5-112">Al crear una retención de exhibición de documentos electrónicos, debe crear tanto CaseHoldPolicy como CaseHoldRule; de lo contrario, no se creará la retención y las ubicaciones de contenido no se colocarán en retención.</span><span class="sxs-lookup"><span data-stu-id="258e5-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="258e5-113">Paso 1: Conectarse a PowerShell de Exchange Online y PowerShell del Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="258e5-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="258e5-114">El primer paso es conectarse a PowerShell de Exchange Online y PowerShell del Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="258e5-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="258e5-115">Puede copiar el siguiente script, pegarlo en una ventana de PowerShell y, a continuación, ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="258e5-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="258e5-116">Se le pedirán las credenciales de la organización a la que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="258e5-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="258e5-117">Debe ejecutar los comandos en los siguientes pasos de esta sesión de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="258e5-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="258e5-118">Paso 2: Obtener una lista de In-Place búsquedas de exhibición de documentos electrónicos mediante Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="258e5-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="258e5-119">Después de autenticarse, puede obtener una lista de búsquedas de exhibición In-Place eDiscovery ejecutando el cmdlet **Get-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="258e5-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="258e5-120">Copie y pegue el siguiente comando en PowerShell y, a continuación, ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="258e5-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="258e5-121">Se mostrará una lista de búsquedas con sus nombres y el estado de cualquier In-Place retenciones.</span><span class="sxs-lookup"><span data-stu-id="258e5-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="258e5-122">El resultado del cmdlet será similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="258e5-122">The cmdlet output will be similar to the following:</span></span>

![Ejemplo de PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="258e5-124">Paso 3: Obtener información sobre las In-Place de exhibición de documentos electrónicos y In-Place que desea migrar</span><span class="sxs-lookup"><span data-stu-id="258e5-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="258e5-125">De nuevo, usará el cmdlet **Get-MailboxSearch,** pero esta vez para obtener las propiedades de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="258e5-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="258e5-126">Puede almacenar estas propiedades en una variable para usarlas más adelante.</span><span class="sxs-lookup"><span data-stu-id="258e5-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="258e5-127">En el ejemplo siguiente se almacenan los resultados del cmdlet **Get-MailboxSearch** en una variable y, a continuación, se muestran las propiedades de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="258e5-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="258e5-128">El resultado de estos dos comandos será similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="258e5-128">The output of these two commands will be similar to the following:</span></span>

![Ejemplo de salida de PowerShell al usar Get-MailboxSearch para una búsqueda individual](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="258e5-130">La duración de la In-Place en este ejemplo es indefinida (*ItemHoldPeriod: Unlimited*).</span><span class="sxs-lookup"><span data-stu-id="258e5-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="258e5-131">Esto es típico para escenarios de exhibición de documentos electrónicos e investigación legal.</span><span class="sxs-lookup"><span data-stu-id="258e5-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="258e5-132">Si la duración de retención es diferente del valor indefinido, es probable que el motivo se deba a que la suspensión se usa para retener contenido en un escenario de retención.</span><span class="sxs-lookup"><span data-stu-id="258e5-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="258e5-133">En lugar de usar los cmdlets de exhibición de documentos electrónicos en PowerShell del Centro de seguridad y cumplimiento de & para escenarios de retención, se recomienda usar [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) y [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) para conservar el contenido.</span><span class="sxs-lookup"><span data-stu-id="258e5-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="258e5-134">El resultado de usar estos cmdlets será similar al uso de **New-CaseHoldPolicy** y **New-CaseHoldRule,** pero podrá especificar un período de retención y una acción de retención, como eliminar contenido después de que expire el período de retención.</span><span class="sxs-lookup"><span data-stu-id="258e5-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="258e5-135">Además, el uso de los cmdlets de retención no requiere que asocie las retenciones de retención con un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="258e5-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="258e5-136">Paso 4: Crear un caso en el Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="258e5-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="258e5-137">Para crear una retención de exhibición de documentos electrónicos, debe crear un caso de exhibición de documentos electrónicos con el que asociar la retención.</span><span class="sxs-lookup"><span data-stu-id="258e5-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="258e5-138">En el siguiente ejemplo se crea un caso de exhibición de documentos electrónicos con el nombre que prefiera.</span><span class="sxs-lookup"><span data-stu-id="258e5-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="258e5-139">Almacenaremos las propiedades del nuevo caso en una variable para su uso más adelante.</span><span class="sxs-lookup"><span data-stu-id="258e5-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="258e5-140">Puede ver esas propiedades ejecutando el `$case | FL` comando después de crear el caso.</span><span class="sxs-lookup"><span data-stu-id="258e5-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Ejemplo de ejecución del comando New-ComplianceCase](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="258e5-142">Paso 5: Crear la retención de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="258e5-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="258e5-143">Después de crear el caso, puede crear la retención y asociarla con el caso que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="258e5-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="258e5-144">Es importante recordar que debe crear una directiva de retención de casos y una regla de retención de casos.</span><span class="sxs-lookup"><span data-stu-id="258e5-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="258e5-145">Si la regla de retención de casos no se crea después de crear la directiva de retención de casos, no se creará la retención de eDiscovery y no se colocará ningún contenido en retención.</span><span class="sxs-lookup"><span data-stu-id="258e5-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="258e5-146">Ejecute los siguientes comandos para volver a crear la retención de exhibición de documentos electrónicos que desea migrar.</span><span class="sxs-lookup"><span data-stu-id="258e5-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="258e5-147">Estos ejemplos usan las propiedades del In-Place de retención del paso 3 que desea migrar.</span><span class="sxs-lookup"><span data-stu-id="258e5-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="258e5-148">El primer comando crea una nueva directiva de retención de casos y guarda las propiedades en una variable.</span><span class="sxs-lookup"><span data-stu-id="258e5-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="258e5-149">El segundo comando crea la regla de retención de mayúsculas y minúsculas correspondiente.</span><span class="sxs-lookup"><span data-stu-id="258e5-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Ejemplo de uso de cmdlets NewCaseHoldPolicy y NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="258e5-151">Paso 6: Comprobar la retención de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="258e5-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="258e5-152">Para asegurarse de que no haya problemas en la creación de la retención, es bueno comprobar que el estado de distribución de la retención es correcto.</span><span class="sxs-lookup"><span data-stu-id="258e5-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="258e5-153">La distribución significa que la retención se ha aplicado a todas las ubicaciones de contenido especificadas en el parámetro *ExchangeLocation* en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="258e5-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="258e5-154">Para ello, puede ejecutar el cmdlet **Get-CaseHoldPolicy.**</span><span class="sxs-lookup"><span data-stu-id="258e5-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="258e5-155">Dado que las propiedades guardadas en la variable $policy que creó en el paso anterior no se actualizan automáticamente en la variable, debe volver *a* ejecutar el cmdlet para comprobar que la distribución es correcta.</span><span class="sxs-lookup"><span data-stu-id="258e5-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="258e5-156">Las directivas de retención de casos pueden tardar entre 5 y 24 horas en distribuirse correctamente.</span><span class="sxs-lookup"><span data-stu-id="258e5-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="258e5-157">Ejecute el siguiente comando para comprobar que la retención de exhibición de documentos electrónicos se ha distribuido correctamente.</span><span class="sxs-lookup"><span data-stu-id="258e5-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="258e5-158">El valor success **de** la *propiedad DistributionStatus* indica que la retención se ha colocado correctamente en las ubicaciones de contenido.</span><span class="sxs-lookup"><span data-stu-id="258e5-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="258e5-159">Si la distribución aún no se ha completado, se muestra el valor **Pendiente.**</span><span class="sxs-lookup"><span data-stu-id="258e5-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![Ejemplo de Get-CaseHoldPolicy PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="258e5-161">Paso 7: Crear la búsqueda</span><span class="sxs-lookup"><span data-stu-id="258e5-161">Step 7: Create the search</span></span>

<span data-ttu-id="258e5-162">El último paso es volver a crear la búsqueda que identificó en el paso 3 y asociarla con el caso.</span><span class="sxs-lookup"><span data-stu-id="258e5-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="258e5-163">Después de crear la búsqueda, puede ejecutarla con el cmdlet **Start-ComplianceSearch** o ejecutarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="258e5-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Ejemplo de New-ComplianceSearch PowerShell](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="258e5-165">Paso 8: Comprobar el caso, la retención y la búsqueda en el Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="258e5-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="258e5-166">Para asegurarse de que todo está configurado correctamente, vaya al Centro de cumplimiento de Microsoft 365 en y haga clic en [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="258e5-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Exhibición de documentos electrónicos del Centro de cumplimiento de Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="258e5-168">El caso que creó en el paso 3 aparece en la **página de eDiscovery** principal.</span><span class="sxs-lookup"><span data-stu-id="258e5-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="258e5-169">Abra el caso y, a continuación, observe la retención que creó en el paso 4 en la lista de la **pestaña Retenciones.** Puede hacer clic en la retención para ver los detalles, incluido el número de buzones a los que se aplica la retención y el estado de distribución.</span><span class="sxs-lookup"><span data-stu-id="258e5-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Retenciones de eDiscovery en el Centro de cumplimiento de Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="258e5-171">La búsqueda que creó en el paso 7 aparece en la lista en la pestaña **Búsquedas** del caso de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="258e5-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Búsqueda de casos de eDiscovery en el Centro de cumplimiento de Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="258e5-173">Si migra una búsqueda de exhibición de documentos electrónicos de In-Place pero no la asocia a un caso de exhibición de documentos electrónicos, aparecerá en la página Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="258e5-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="258e5-174">Más información</span><span class="sxs-lookup"><span data-stu-id="258e5-174">More information</span></span>

- <span data-ttu-id="258e5-175">Para obtener más información acerca In-Place las retenciones & eDiscovery en el Centro de administración de Exchange, vea:</span><span class="sxs-lookup"><span data-stu-id="258e5-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="258e5-176">Exhibición de documentos electrónicos en contexto</span><span class="sxs-lookup"><span data-stu-id="258e5-176">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="258e5-177">Conservación local y retención por juicio</span><span class="sxs-lookup"><span data-stu-id="258e5-177">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="258e5-178">Para obtener más información acerca de los cmdlets de PowerShell usados en el artículo, vea:</span><span class="sxs-lookup"><span data-stu-id="258e5-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="258e5-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="258e5-179">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="258e5-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="258e5-180">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="258e5-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="258e5-181">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="258e5-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="258e5-182">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="258e5-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="258e5-183">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="258e5-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="258e5-184">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="258e5-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="258e5-185">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="258e5-186">Para obtener más información acerca del Centro de cumplimiento de Microsoft 365, vea Información general sobre el Centro de cumplimiento de [Microsoft 365.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="258e5-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
