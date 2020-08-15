---
title: Elegir el dominio que se va a usar al crear grupos de 365 de Microsoft
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Obtenga información acerca de cómo elegir el dominio que se usará al crear grupos de Microsoft 365 mediante la configuración de directivas de direcciones de correo electrónico con PowerShell.
ms.openlocfilehash: 5ce0068f1b4562c37b2ccf2b1fb9a928b392a7ee
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686735"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="fa92e-103">Elegir el dominio que se va a usar al crear grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa92e-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="fa92e-104">Algunas organizaciones utilizan dominios de correo electrónico diferentes para segmentar diferentes partes de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fa92e-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="fa92e-105">Puede especificar el dominio que debe usarse cuando los usuarios creen grupos de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa92e-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="fa92e-106">Si su organización necesita que los usuarios creen sus grupos en dominios distintos del dominio aceptado predeterminado de su empresa, puede permitir esto mediante la configuración de directivas de direcciones de correo electrónico (EAPs) con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa92e-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="fa92e-107">Antes de poder ejecutar los cmdlets de PowerShell, descargue e instale un módulo que le permitirá hablar con su organización.</span><span class="sxs-lookup"><span data-stu-id="fa92e-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="fa92e-108">Consulte [conectarse a Exchange online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="fa92e-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="fa92e-109">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa92e-109">Example scenarios</span></span>

<span data-ttu-id="fa92e-110">Supongamos que el dominio principal de su empresa es Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa92e-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="fa92e-111">Pero el dominio aceptado predeterminado de su organización es service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa92e-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="fa92e-112">Esto significa que los grupos se crearán en service.contoso.com (por ejemplo, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fa92e-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="fa92e-113">Supongamos que también tiene subdominios configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="fa92e-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="fa92e-114">También desea que los grupos se creen en estos dominios:</span><span class="sxs-lookup"><span data-stu-id="fa92e-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="fa92e-115">students.contoso.com para estudiantes</span><span class="sxs-lookup"><span data-stu-id="fa92e-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="fa92e-116">faculty.contoso.com para miembros de profesores</span><span class="sxs-lookup"><span data-stu-id="fa92e-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="fa92e-117">En los dos escenarios siguientes, se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="fa92e-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="fa92e-118">Cuando hay varios EAPs, se evalúan en el orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="fa92e-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="fa92e-119">Un valor de 1 indica la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="fa92e-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="fa92e-120">Una vez que un EAP coincide, no se evalúan más EAP y las direcciones que se marcan en el grupo son las establecidas por el EAP coincidente.</span><span class="sxs-lookup"><span data-stu-id="fa92e-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="fa92e-121">> si ningún EAPs coincide con los criterios especificados, el grupo se aprovisiona en el dominio aceptado predeterminado de la organización.</span><span class="sxs-lookup"><span data-stu-id="fa92e-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="fa92e-122">Consulte [Manage accepted Domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obtener más información sobre cómo agregar un dominio aceptado.</span><span class="sxs-lookup"><span data-stu-id="fa92e-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="fa92e-123">Escenario 1</span><span class="sxs-lookup"><span data-stu-id="fa92e-123">Scenario 1</span></span>

<span data-ttu-id="fa92e-124">En el ejemplo siguiente se muestra cómo aprovisionar todos los grupos de Microsoft 365 de la organización en el dominio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa92e-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="fa92e-125">Escenario 2</span><span class="sxs-lookup"><span data-stu-id="fa92e-125">Scenario 2</span></span>

<span data-ttu-id="fa92e-126">Supongamos que desea controlar en qué subdominios se crean los grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa92e-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="fa92e-127">Quieres:</span><span class="sxs-lookup"><span data-stu-id="fa92e-127">You want:</span></span>
  
- <span data-ttu-id="fa92e-128">Grupos creados por los alumnos (usuarios que tienen el **Departamento** establecido en **alumnos**) en el dominio Students.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa92e-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="fa92e-129">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="fa92e-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="fa92e-130">Grupos creados por los miembros de los profesores (los usuarios que tienen el **Departamento** establecido en **profesora o dirección de correo electrónico contienen Faculty.contoso.com)**) en el dominio Faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa92e-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="fa92e-131">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="fa92e-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="fa92e-132">Los grupos creados por cualquier persona se crean en el dominio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa92e-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="fa92e-133">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="fa92e-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="fa92e-134">Cambiar las directivas de direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fa92e-134">Change email address policies</span></span>

<span data-ttu-id="fa92e-135">Para cambiar las plantillas de prioridad o dirección de correo electrónico de un EAP existente, use el cmdlet Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="fa92e-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="fa92e-136">El cambio de un EAP no afecta a los grupos que ya se han aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="fa92e-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="fa92e-137">Eliminar directivas de direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="fa92e-137">Delete email address policies</span></span>

<span data-ttu-id="fa92e-138">Para eliminar un EAP, use el cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="fa92e-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="fa92e-139">El cambio de un EAP no afecta a los grupos que ya se han aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="fa92e-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="fa92e-140">Requisitos de entornos híbridos</span><span class="sxs-lookup"><span data-stu-id="fa92e-140">Hybrid requirements</span></span>

<span data-ttu-id="fa92e-141">Si su organización está configurada en un escenario híbrido, consulte [Configure Microsoft 365 Groups with on-premises Exchange híbrida](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) para asegurarse de que su organización cumple los requisitos para la creación de grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa92e-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="fa92e-142">Información adicional acerca del uso de grupos de directivas de direcciones de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="fa92e-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="fa92e-143">Hay algunas cosas más que debe saber:</span><span class="sxs-lookup"><span data-stu-id="fa92e-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="fa92e-144">La creación de grupos rápidos depende del número de EAPs configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="fa92e-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="fa92e-145">Los administradores y los usuarios también pueden modificar los dominios cuando crean grupos.</span><span class="sxs-lookup"><span data-stu-id="fa92e-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="fa92e-146">El grupo de usuarios se determina mediante las consultas estándar (propiedades de usuario) que ya están disponibles.</span><span class="sxs-lookup"><span data-stu-id="fa92e-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="fa92e-147">Desproteger [propiedades filtrables para el parámetro-RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) para las propiedades filtrables admitidas.</span><span class="sxs-lookup"><span data-stu-id="fa92e-147">Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="fa92e-148">Si no configura ningún EAPs para grupos, se seleccionará el dominio aceptado predeterminado para la creación de grupos.</span><span class="sxs-lookup"><span data-stu-id="fa92e-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="fa92e-149">Si quita un dominio aceptado, debe actualizar el EAPs en primer lugar; de lo contrario, el aprovisionamiento de grupos se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="fa92e-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="fa92e-150">Se puede configurar un límite máximo de 100 directivas de direcciones de correo electrónico para una organización.</span><span class="sxs-lookup"><span data-stu-id="fa92e-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="fa92e-151">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="fa92e-151">Related articles</span></span>

[<span data-ttu-id="fa92e-152">Crear un grupo de 365 de Microsoft en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="fa92e-152">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
