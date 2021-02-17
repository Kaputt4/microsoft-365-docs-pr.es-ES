---
title: Límites de directivas de retención y directivas de etiqueta de retención.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtener información sobre el número máximo de directivas y elementos por directiva para directivas de retención y directivas de etiquetas de retención
ms.openlocfilehash: 547c6396fa9bfcba6dbd271f09a7ea59f9acf170
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261595"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="a92b6-103">Límites de directivas de retención y directivas de etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="a92b6-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="a92b6-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a92b6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a92b6-105">Al usar [directivas de retención y directivas de etiqueta de retención](retention.md#retention-policies-and-retention-labels) para conservar o eliminar automáticamente datos de su organización, debe conocer ciertos límites.</span><span class="sxs-lookup"><span data-stu-id="a92b6-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="a92b6-106">Número máximo de directivas por espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="a92b6-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="a92b6-107">Un solo espacio empresarial puede tener un máximo de 10 000 directivas (cualquier configuración).</span><span class="sxs-lookup"><span data-stu-id="a92b6-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="a92b6-108">Este número máximo incluye las diferentes directivas de retención y otras directivas de cumplimiento, como las directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="a92b6-108">This maximum number includes the different policies for retention and other policies for compliance, such as DLP policies.</span></span>

<span data-ttu-id="a92b6-109">Número máximo de directivas para la retención por carga de trabajo:</span><span class="sxs-lookup"><span data-stu-id="a92b6-109">Maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="a92b6-110">Exchange Online (cualquier configuración): 1800</span><span class="sxs-lookup"><span data-stu-id="a92b6-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="a92b6-111">SharePoint o OneDrive (se incluyen automáticamente todos los sitios): 13</span><span class="sxs-lookup"><span data-stu-id="a92b6-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="a92b6-112">SharePoint o OneDrive (ubicaciones específicas incluidas o excluidas): 2600</span><span class="sxs-lookup"><span data-stu-id="a92b6-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="a92b6-113">Número máximo de elementos por directiva</span><span class="sxs-lookup"><span data-stu-id="a92b6-113">Maximum number of items per policy</span></span>

<span data-ttu-id="a92b6-114">Deben tenerse en cuenta ciertos límites por directiva si usa la configuración opcional para definir el ámbito de la configuración de retención para usuarios específicos, grupos específicos de Microsoft 365 o determinados sitios:</span><span class="sxs-lookup"><span data-stu-id="a92b6-114">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="a92b6-115">Número máximo de elementos por directiva para la retención:</span><span class="sxs-lookup"><span data-stu-id="a92b6-115">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="a92b6-116">1000 buzones de correo (buzones de usuario o de grupo)</span><span class="sxs-lookup"><span data-stu-id="a92b6-116">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="a92b6-117">Grupos de Microsoft 365 1 000.</span><span class="sxs-lookup"><span data-stu-id="a92b6-117">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="a92b6-118">1 000 usuarios para chats privados de Teams</span><span class="sxs-lookup"><span data-stu-id="a92b6-118">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="a92b6-119">100 sitios (OneDrive o SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a92b6-119">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="a92b6-120">Estas limitaciones son por directiva, por lo que si necesita usar inclusiones o exclusiones específicas por las que se superan estos números, puede crear otras directivas de retención con la misma configuración de retención.</span><span class="sxs-lookup"><span data-stu-id="a92b6-120">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="a92b6-121">Vea la siguiente sección con [algunos escenarios de ejemplo y soluciones](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usan varias directivas de retención por este motivo.</span><span class="sxs-lookup"><span data-stu-id="a92b6-121">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="a92b6-122">Sin embargo, tener varias directivas generan más sobrecargas administrativas, por lo que siempre debe confirmar si necesita realmente inclusiones y exclusiones.</span><span class="sxs-lookup"><span data-stu-id="a92b6-122">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="a92b6-123">Recuerde que la configuración predeterminada que se aplica a toda la ubicación no tiene ninguna limitación y esta opción de configuración puede ser una solución mejor que la creación y el mantenimiento de varias directivas.</span><span class="sxs-lookup"><span data-stu-id="a92b6-123">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="a92b6-124">Si necesita crear y mantener varias directivas para este escenario, plantéese usar [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para una configuración más eficaz.</span><span class="sxs-lookup"><span data-stu-id="a92b6-124">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="a92b6-125">Ejemplos de uso de varias directivas para evitar superar los límites máximos</span><span class="sxs-lookup"><span data-stu-id="a92b6-125">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="a92b6-126">Los ejemplos siguientes proporcionan algunas soluciones de diseño para cuando no pueda especificar solo la ubicación de una directiva de retención y debe tener en cuenta el máximo número de elementos documentados en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a92b6-126">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="a92b6-127">Ejemplo de Exchange:</span><span class="sxs-lookup"><span data-stu-id="a92b6-127">Exchange example:</span></span>

- <span data-ttu-id="a92b6-128">**Requisito**: en una organización con más de 40.000 buzones de usuario, la mayoría de los usuarios deben tener su correo electrónico retenido durante 7 años, pero un subconjunto de usuarios identificados (425) debe tener su correo electrónico retenido solo durante 5 años.</span><span class="sxs-lookup"><span data-stu-id="a92b6-128">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="a92b6-129">**Solución**: cree una directiva de retención para el correo electrónico de Exchange con un período de retención de 7 años y excluya el subconjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a92b6-129">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="a92b6-130">Luego, cree una segunda directiva de retención para el correo electrónico de Exchange con un período de retención de 5 años e incluya el subconjunto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a92b6-130">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="a92b6-131">En ambos casos, el número de inclusiones y exclusiones se encuentra por debajo del número máximo de buzones especificados para una sola directiva, y el subconjunto de usuarios tiene que excluirse explícitamente de la primera directiva, ya que tiene un período de retención [más largo](retention.md#the-principles-of-retention-or-what-takes-precedence) que la segunda directiva.</span><span class="sxs-lookup"><span data-stu-id="a92b6-131">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="a92b6-132">Si el subconjunto de usuarios necesita una directiva de retención más larga, no tendrá que excluirlos de la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="a92b6-132">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="a92b6-133">Con esta solución, si alguien nuevo se une a la organización, su buzón se incluirá automáticamente en la primera directiva durante 7 años y no hay ningún impacto en el número máximo de admitidos.</span><span class="sxs-lookup"><span data-stu-id="a92b6-133">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="a92b6-134">Pero los nuevos usuarios que requieran el período de retención de 5 años se agregarán a los números de inclusiones y exclusiones, cuyo límite es 1000.</span><span class="sxs-lookup"><span data-stu-id="a92b6-134">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="a92b6-135">Ejemplo de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a92b6-135">SharePoint example:</span></span>

- <span data-ttu-id="a92b6-136">**Requisito**: una organización tiene varios miles de sitios de SharePoint, pero solo 2000 sitios requieren un período de retención de 10 años y 8000 requieren un período de retención de 4 años.</span><span class="sxs-lookup"><span data-stu-id="a92b6-136">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="a92b6-137">**Solución**: cree 20 directivas de retención para SharePoint con un período de retención de 10 años que incluya 100 sitios específicos y cree 80 directivas de retención para SharePoint con un período de retención de 4 años que incluya 100 sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="a92b6-137">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="a92b6-138">Como es necesario retener todos los sitios de SharePoint, debe crear directivas de retención que especifiquen los sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="a92b6-138">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="a92b6-139">Como una directiva de retención no admite más de 100 sitios específicos, debe crear varias directivas para los dos períodos de retención.</span><span class="sxs-lookup"><span data-stu-id="a92b6-139">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="a92b6-140">Estas directivas de retención tienen el número máximo de sitios incluidos, por lo que el siguiente sitio nuevo que necesita retenerse requerirá una nueva directiva de retención, independientemente del periodo de retención.</span><span class="sxs-lookup"><span data-stu-id="a92b6-140">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

