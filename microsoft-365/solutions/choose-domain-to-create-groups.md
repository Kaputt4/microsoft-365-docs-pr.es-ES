---
title: Elegir el dominio que se usará al crear Microsoft 365 grupos
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: Aprenda a elegir el dominio que se va a usar al crear Microsoft 365 mediante la configuración de directivas de direcciones de correo electrónico mediante PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583153"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="9abc8-103">Elegir el dominio que se usará al crear Microsoft 365 grupos</span><span class="sxs-lookup"><span data-stu-id="9abc8-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="9abc8-104">Algunas organizaciones utilizan dominios de correo electrónico diferentes para segmentar diferentes partes de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9abc8-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="9abc8-105">Puede especificar qué dominio debe usarse cuando los usuarios creen Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="9abc8-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="9abc8-106">Si su organización necesita que los usuarios creen sus grupos en dominios distintos del dominio aceptado predeterminado de su empresa, puede permitirlo configurando directivas de direcciones de correo electrónico (APE) con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9abc8-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="9abc8-107">Antes de poder ejecutar los cmdlets de PowerShell, descargue e instale un módulo que le permitirá hablar con su organización.</span><span class="sxs-lookup"><span data-stu-id="9abc8-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="9abc8-108">Consulte Conectar [para Exchange Online con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9abc8-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="9abc8-109">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9abc8-109">Example scenarios</span></span>

<span data-ttu-id="9abc8-110">Supongamos que el dominio principal de su empresa es Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9abc8-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="9abc8-111">Pero el dominio aceptado predeterminado de la organización es service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9abc8-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="9abc8-112">Esto significa que los grupos se crearán en service.contoso.com (por ejemplo, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9abc8-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="9abc8-113">Supongamos que también tiene subdominios configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="9abc8-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="9abc8-114">También desea que los grupos se creen en estos dominios:</span><span class="sxs-lookup"><span data-stu-id="9abc8-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="9abc8-115">students.contoso.com para estudiantes</span><span class="sxs-lookup"><span data-stu-id="9abc8-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="9abc8-116">faculty.contoso.com para profesores</span><span class="sxs-lookup"><span data-stu-id="9abc8-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="9abc8-117">Los dos escenarios siguientes explican cómo lograr esto.</span><span class="sxs-lookup"><span data-stu-id="9abc8-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="9abc8-118">Cuando se tienen EAP de mulitple, se evalúan en el orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="9abc8-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="9abc8-119">Un valor de 1 significa la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="9abc8-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="9abc8-120">Una vez que un EAP coincide, no se evalúa ningún EAP más y las direcciones que se marcan en el grupo son según el EAP coincidente.</span><span class="sxs-lookup"><span data-stu-id="9abc8-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="9abc8-121">> Si ningún AED coincide con los criterios especificados, el grupo se aprovisiona en el dominio aceptado predeterminado de la organización.</span><span class="sxs-lookup"><span data-stu-id="9abc8-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="9abc8-122">Consulte [Administrar dominios aceptados en Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) para obtener más información sobre cómo agregar un dominio aceptado.</span><span class="sxs-lookup"><span data-stu-id="9abc8-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="9abc8-123">Escenario 1</span><span class="sxs-lookup"><span data-stu-id="9abc8-123">Scenario 1</span></span>

<span data-ttu-id="9abc8-124">En el ejemplo siguiente se muestra cómo aprovisionar todos los Microsoft 365 de la organización en el dominio groups.contoso.com usuario.</span><span class="sxs-lookup"><span data-stu-id="9abc8-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="9abc8-125">Escenario 2</span><span class="sxs-lookup"><span data-stu-id="9abc8-125">Scenario 2</span></span>

<span data-ttu-id="9abc8-126">Supongamos que desea controlar en qué subdominios Microsoft 365 se crean los grupos.</span><span class="sxs-lookup"><span data-stu-id="9abc8-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="9abc8-127">Quieres:</span><span class="sxs-lookup"><span data-stu-id="9abc8-127">You want:</span></span>
  
- <span data-ttu-id="9abc8-128">Grupos creados por alumnos (usuarios que tienen **Departamento** establecido en **Estudiantes)** en el students.groups.contoso.com de correo.</span><span class="sxs-lookup"><span data-stu-id="9abc8-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="9abc8-129">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="9abc8-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="9abc8-130">Grupos creados por miembros del  profesorado (usuarios que tienen departamento establecido en Profesor o dirección de correo electrónico contiene **faculty.contoso.com)**) en el faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9abc8-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="9abc8-131">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="9abc8-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="9abc8-132">Los grupos creados por cualquier otra persona se crean en el groups.contoso.com usuario.</span><span class="sxs-lookup"><span data-stu-id="9abc8-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="9abc8-133">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="9abc8-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="9abc8-134">Cambiar directivas de direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="9abc8-134">Change email address policies</span></span>

<span data-ttu-id="9abc8-135">Para cambiar las plantillas de prioridad o dirección de correo electrónico para un EAP existente, use el cmdlet Set-EmailAddressPolicy correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9abc8-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="9abc8-136">Cambiar un EAP no tiene ningún impacto en los grupos que ya se han aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="9abc8-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="9abc8-137">Eliminar directivas de direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="9abc8-137">Delete email address policies</span></span>

<span data-ttu-id="9abc8-138">Para eliminar un EAP, use el cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="9abc8-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="9abc8-139">Cambiar un EAP no tiene ningún impacto en los grupos que ya se han aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="9abc8-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="9abc8-140">Requisitos híbridos</span><span class="sxs-lookup"><span data-stu-id="9abc8-140">Hybrid requirements</span></span>

<span data-ttu-id="9abc8-141">Si la organización está configurada en un escenario híbrido, consulte [Configure Microsoft 365 groups with on-premises Exchange hybrid para](/exchange/hybrid-deployment/set-up-microsoft-365-groups) asegurarse de que la organización cumple los requisitos para crear Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="9abc8-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="9abc8-142">Información adicional sobre cómo usar grupos de directivas de direcciones de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="9abc8-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="9abc8-143">Hay que saber algunas cosas más:</span><span class="sxs-lookup"><span data-stu-id="9abc8-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="9abc8-144">La forma en que se crean los grupos rápidos depende del número de EPE configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="9abc8-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="9abc8-145">Los administradores y los usuarios también pueden modificar dominios al crear grupos.</span><span class="sxs-lookup"><span data-stu-id="9abc8-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="9abc8-146">El grupo de usuarios se determina mediante las consultas estándar (propiedades de usuario) que ya están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9abc8-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="9abc8-147">Consulte [Propiedades filtrables para el parámetro -RecipientFilter](/powershell/exchange/recipientfilter-properties) para las propiedades filtrables admitidas.</span><span class="sxs-lookup"><span data-stu-id="9abc8-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="9abc8-148">Si no configura ningún EAP para grupos, se selecciona el dominio aceptado predeterminado para la creación de grupos.</span><span class="sxs-lookup"><span data-stu-id="9abc8-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="9abc8-149">Si quita un dominio aceptado, primero debe actualizar los EPE, de lo contrario, el aprovisionamiento de grupos se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="9abc8-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="9abc8-150">Se puede configurar un límite máximo de 100 directivas de direcciones de correo electrónico para una organización.</span><span class="sxs-lookup"><span data-stu-id="9abc8-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-content"></a><span data-ttu-id="9abc8-151">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9abc8-151">Related content</span></span>

<span data-ttu-id="9abc8-152">[Planeación de gobierno de colaboración paso a paso](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9abc8-152">[Collaboration governance planning step-by-step](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (article)</span></span>

<span data-ttu-id="9abc8-153">[Crear el plan de gobierno de colaboración](collaboration-governance-first.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9abc8-153">[Create your collaboration governance plan](collaboration-governance-first.md) (article)</span></span>

<span data-ttu-id="9abc8-154">[Crear un grupo Microsoft 365 en el Centro de administración](../admin/create-groups/create-groups.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9abc8-154">[Create an Microsoft 365 group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>