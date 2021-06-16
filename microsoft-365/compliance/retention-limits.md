---
title: Límites de directivas de retención y directivas de etiqueta de retención.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Obtener información sobre el número máximo de directivas y elementos por directiva para directivas de retención y directivas de etiquetas de retención
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908106"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="a9fd4-103">Límites de directivas de retención y directivas de etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="a9fd4-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="a9fd4-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="a9fd4-105">Al usar [directivas de retención y directivas de etiqueta de retención](retention.md#retention-policies-and-retention-labels) para conservar o eliminar automáticamente datos de su organización, debe conocer ciertos límites.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="a9fd4-106">Número máximo de directivas por espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="a9fd4-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="a9fd4-107">Un solo espacio empresarial puede tener un máximo de 10 000 directivas (cualquier configuración).</span><span class="sxs-lookup"><span data-stu-id="a9fd4-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="a9fd4-108">Este número máximo incluye las diferentes directivas de retención y otras directivas de cumplimiento como directivas para DLP, barreras de información, retenciones de eDiscovery y etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="a9fd4-109">Dentro de este límite de 10 000 directivas, también hay algunos límites en el número máximo de directivas para la retención por carga de trabajo:</span><span class="sxs-lookup"><span data-stu-id="a9fd4-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="a9fd4-110">Exchange (cualquier configuración): 1800</span><span class="sxs-lookup"><span data-stu-id="a9fd4-110">Exchange (any configuration): 1,800</span></span>
- <span data-ttu-id="a9fd4-111">SharePoint o OneDrive (se incluyen automáticamente todos los sitios): 13</span><span class="sxs-lookup"><span data-stu-id="a9fd4-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="a9fd4-112">SharePoint o OneDrive (ubicaciones específicas incluidas o excluidas): 2600</span><span class="sxs-lookup"><span data-stu-id="a9fd4-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="a9fd4-113">Aunque las directivas de retención para Microsoft Teams y Yammer usan buzones para almacenar datos con fines de retención, el número máximo de directivas para Exchange Online excluye las directivas de retención para Teams y Yammer.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="a9fd4-114">Número máximo de elementos por directiva</span><span class="sxs-lookup"><span data-stu-id="a9fd4-114">Maximum number of items per policy</span></span>

<span data-ttu-id="a9fd4-115">Deben tenerse en cuenta ciertos límites por directiva si usa la configuración opcional para definir el ámbito de la configuración de retención para usuarios específicos, grupos específicos de Microsoft 365 o determinados sitios:</span><span class="sxs-lookup"><span data-stu-id="a9fd4-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="a9fd4-116">Número máximo de elementos por directiva para la retención:</span><span class="sxs-lookup"><span data-stu-id="a9fd4-116">Maximum numbers of items per policy for retention:</span></span>

- <span data-ttu-id="a9fd4-117">Buzones de Exchange: 1000</span><span class="sxs-lookup"><span data-stu-id="a9fd4-117">Exchange mailboxes: 1,000</span></span>
- <span data-ttu-id="a9fd4-118">Grupos de Microsoft 365: 1000</span><span class="sxs-lookup"><span data-stu-id="a9fd4-118">Microsoft 365 Groups: 1,000</span></span>
- <span data-ttu-id="a9fd4-119">Mensajes de canal de Teams: 1000</span><span class="sxs-lookup"><span data-stu-id="a9fd4-119">Teams channel messages: 1,000</span></span>
- <span data-ttu-id="a9fd4-120">Chats de Teams: 1000</span><span class="sxs-lookup"><span data-stu-id="a9fd4-120">Teams chats: 1,000</span></span>
- <span data-ttu-id="a9fd4-121">Mensajes de la comunidad de Yammer: 1000</span><span class="sxs-lookup"><span data-stu-id="a9fd4-121">Yammer community messages: 1,000</span></span>
- <span data-ttu-id="a9fd4-122">Mensajes del usuario de Yammer: 1000</span><span class="sxs-lookup"><span data-stu-id="a9fd4-122">Yammer user messages: 1,000</span></span>
- <span data-ttu-id="a9fd4-123">Sitios de SharePoint: 100</span><span class="sxs-lookup"><span data-stu-id="a9fd4-123">SharePoint sites: 100</span></span>
- <span data-ttu-id="a9fd4-124">Cuentas de OneDrive: 100</span><span class="sxs-lookup"><span data-stu-id="a9fd4-124">OneDrive accounts: 100</span></span>

<span data-ttu-id="a9fd4-125">Skype Empresarial debe limitarse a usuarios específicos y el número máximo admitido por directiva es 1000.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-125">Skype for Business has to be scoped to specific users and the maximum number supported per policy is 1,000.</span></span>

<span data-ttu-id="a9fd4-126">Estas limitaciones son por directiva, por lo que si necesita usar inclusiones o exclusiones específicas por las que se superan estos números, puede crear otras directivas de retención con la misma configuración de retención.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-126">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="a9fd4-127">Vea la siguiente sección con [algunos escenarios de ejemplo y soluciones](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usan varias directivas de retención por este motivo.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-127">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="a9fd4-128">Sin embargo, tener varias directivas generan más sobrecargas administrativas, por lo que siempre debe confirmar si necesita realmente inclusiones y exclusiones.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-128">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="a9fd4-129">Recuerde que la configuración predeterminada que se aplica a toda la ubicación no tiene ninguna limitación y esta opción de configuración puede ser una solución mejor que la creación y el mantenimiento de varias directivas.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-129">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="a9fd4-130">Si necesita crear y mantener varias directivas para este escenario, plantéese usar [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para una configuración más eficaz.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-130">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="a9fd4-131">Ejemplos de uso de varias directivas para evitar superar los límites máximos</span><span class="sxs-lookup"><span data-stu-id="a9fd4-131">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="a9fd4-132">Los ejemplos siguientes proporcionan algunas soluciones de diseño para cuando no pueda especificar solo la ubicación de una directiva de retención y debe tener en cuenta el máximo número de elementos documentados en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-132">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="a9fd4-133">Ejemplo de Exchange:</span><span class="sxs-lookup"><span data-stu-id="a9fd4-133">Exchange example:</span></span>

- <span data-ttu-id="a9fd4-134">**Requisito**: en una organización con más de 40.000 buzones de usuario, la mayoría de los usuarios deben tener su correo electrónico retenido durante 7 años, pero un subconjunto de usuarios identificados (425) debe tener su correo electrónico retenido solo durante 5 años.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-134">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="a9fd4-135">**Solución**: cree una directiva de retención para el correo electrónico de Exchange con un período de retención de 7 años y excluya el subconjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-135">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="a9fd4-136">Luego, cree una segunda directiva de retención para el correo electrónico de Exchange con un período de retención de 5 años e incluya el subconjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-136">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="a9fd4-137">En ambos casos, el número de inclusiones y exclusiones se encuentra por debajo del número máximo de buzones especificados para una sola directiva, y el subconjunto de usuarios tiene que excluirse explícitamente de la primera directiva, ya que tiene un período de retención [más largo](retention.md#the-principles-of-retention-or-what-takes-precedence) que la segunda directiva.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-137">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="a9fd4-138">Si el subconjunto de usuarios necesita una directiva de retención más larga, no tendrá que excluirlos de la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-138">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="a9fd4-139">Con esta solución, si alguien nuevo se une a la organización, su buzón se incluirá automáticamente en la primera directiva durante 7 años y no hay ningún impacto en el número máximo de admitidos.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-139">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="a9fd4-140">Pero los nuevos usuarios que requieran el período de retención de 5 años se agregarán a los números de inclusiones y exclusiones, cuyo límite es 1000.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-140">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="a9fd4-141">Ejemplo de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a9fd4-141">SharePoint example:</span></span>

- <span data-ttu-id="a9fd4-142">**Requisito**: una organización tiene varios miles de sitios de SharePoint, pero solo 2000 sitios requieren un período de retención de 10 años y 8000 requieren un período de retención de 4 años.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-142">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="a9fd4-143">**Solución**: cree 20 directivas de retención para SharePoint con un período de retención de 10 años que incluya 100 sitios específicos y cree 80 directivas de retención para SharePoint con un período de retención de 4 años que incluya 100 sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-143">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="a9fd4-144">Como es necesario retener todos los sitios de SharePoint, debe crear directivas de retención que especifiquen los sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-144">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="a9fd4-145">Como una directiva de retención no admite más de 100 sitios específicos, debe crear varias directivas para los dos períodos de retención.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-145">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="a9fd4-146">Estas directivas de retención tienen el número máximo de sitios incluidos, por lo que el siguiente sitio nuevo que necesita retenerse requerirá una nueva directiva de retención, independientemente del periodo de retención.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-146">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="a9fd4-147">Número máximo de elementos para eliminar</span><span class="sxs-lookup"><span data-stu-id="a9fd4-147">Maximum number of items for disposition</span></span>

<span data-ttu-id="a9fd4-148">Para la [eliminación del contenido](disposition.md), hay algunos límites que deben tenerse en cuenta:</span><span class="sxs-lookup"><span data-stu-id="a9fd4-148">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="a9fd4-149">1 000 000 elementos pendientes de eliminación por fase para cada etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="a9fd4-149">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="a9fd4-150">Prueba de eliminación hasta siete años después de eliminar el elemento, con un límite de 1 000 000 de elementos por etiqueta de retención para ese período.</span><span class="sxs-lookup"><span data-stu-id="a9fd4-150">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
<span data-ttu-id="a9fd4-151">Si necesita una prueba de eliminación superior a ese límite de 1 000 000 para los elementos que se marcan como registros, póngase en contacto con el [Soporte técnico de Microsoft](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="a9fd4-151">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>
