---
title: Configurar una lista de direcciones URL bloqueadas personalizadas mediante vínculos seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar una lista de direcciones URL bloqueadas para su organización mediante la protección contra amenazas avanzada de Office 365.
ms.openlocfilehash: 9e0c6e75358c97a21ab0765edf5a15bafe53d75e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035377"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="c086d-103">Configurar una lista de direcciones URL bloqueadas personalizadas mediante vínculos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="c086d-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c086d-104">Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c086d-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="c086d-105">Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="c086d-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c086d-106">Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), su organización puede tener una lista personalizada de direcciones de sitios web (URL) que están bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="c086d-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="c086d-107">Cuando se bloquea una dirección URL, los usuarios que hacen clic en los vínculos a la dirección URL bloqueada se toman en una [Página de advertencia](atp-safe-links-warning-pages.md) similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c086d-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Este sitio está bloqueado](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="c086d-109">La lista de URL bloqueadas se define en el equipo de seguridad de Microsoft 365 para empresas de la organización, y esa lista se aplica a todos los usuarios de la organización que están cubiertos por las directivas de vínculos seguros de ATP de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c086d-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="c086d-110">Lea este artículo para obtener información sobre cómo configurar la lista de direcciones URL bloqueadas personalizadas de la organización para [vínculos seguros de ATP en Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c086d-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="c086d-111">Ver o editar una lista personalizada de direcciones URL bloqueadas</span><span class="sxs-lookup"><span data-stu-id="c086d-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="c086d-112">[Vínculos seguros de ATP en Office 365](atp-safe-links.md) usa varias listas, incluida la lista de direcciones URL bloqueadas personalizadas de la organización.</span><span class="sxs-lookup"><span data-stu-id="c086d-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="c086d-113">Si tiene los permisos necesarios, puede configurar la lista personalizada de su organización.</span><span class="sxs-lookup"><span data-stu-id="c086d-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="c086d-114">Para ello, edite la Directiva de vínculos a prueba de errores predeterminada de su organización.</span><span class="sxs-lookup"><span data-stu-id="c086d-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="c086d-115">Para editar (o definir) las directivas de ATP, debe tener asignado uno de los roles descritos en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="c086d-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="c086d-116">Role</span><span class="sxs-lookup"><span data-stu-id="c086d-116">Role</span></span>  |<span data-ttu-id="c086d-117">Dónde y cómo se asigna</span><span class="sxs-lookup"><span data-stu-id="c086d-117">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="c086d-118">administrador global</span><span class="sxs-lookup"><span data-stu-id="c086d-118">global administrator</span></span> |<span data-ttu-id="c086d-119">La persona que se registra para comprar Microsoft 365 es un administrador global de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c086d-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="c086d-120">(Para obtener más información, consulte [acerca de los roles de administrador de Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="c086d-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="c086d-121">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="c086d-121">Security Administrator</span></span> |<span data-ttu-id="c086d-122">Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()</span><span class="sxs-lookup"><span data-stu-id="c086d-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="c086d-123">Administración de la organización en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c086d-123">Exchange Online Organization Management</span></span> |<span data-ttu-id="c086d-124">Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange ()</span><span class="sxs-lookup"><span data-stu-id="c086d-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="c086d-125">o bien</span><span class="sxs-lookup"><span data-stu-id="c086d-125">or</span></span> <br>  <span data-ttu-id="c086d-126">Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="c086d-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="c086d-127">Para obtener más información acerca de los roles y los permisos, consulte [permisos en el centro de seguridad &amp; y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c086d-127">To learn more about roles and permissions, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="c086d-128">Para ver o editar una lista de direcciones URL bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="c086d-128">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="c086d-129">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c086d-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="c086d-130">En el panel de navegación izquierdo, en **Administración de amenazas**, elija **vínculos seguros**de **Directiva** \> .</span><span class="sxs-lookup"><span data-stu-id="c086d-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="c086d-131">En la sección **directivas que se aplican a toda la organización** , seleccione predeterminado y, a continuación, elija **Editar** (el botón Editar **es**similar a un lápiz).</span><span class="sxs-lookup"><span data-stu-id="c086d-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="c086d-132">![Haga clic en Editar para editar la directiva predeterminada para protección de vínculos seguros](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="c086d-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="c086d-133">Esto le permite ver la lista de direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="c086d-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="c086d-134">En primer lugar, es posible que no tenga ninguna dirección URL mencionada aquí.</span><span class="sxs-lookup"><span data-stu-id="c086d-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="c086d-135">![Lista de direcciones URL bloqueadas en la Directiva de vínculos seguros predeterminada](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="c086d-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="c086d-136">Seleccione el cuadro **Escriba una dirección URL válida** , escriba una dirección URL y, a continuación, elija**+** el signo más ().</span><span class="sxs-lookup"><span data-stu-id="c086d-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="c086d-137">Cuando termine de agregar direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c086d-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="c086d-138">Algunas cosas que debe tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="c086d-138">A few things to keep in mind</span></span>

<span data-ttu-id="c086d-139">Mientras agrega direcciones URL a la lista, tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="c086d-139">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="c086d-140">No incluya una barra diagonal ( **/**) al final de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c086d-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="c086d-141">Por ejemplo, en lugar de escribir `https://www.contoso.com/`, escriba `https://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="c086d-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>
    
- <span data-ttu-id="c086d-142">Puede especificar una dirección URL de solo dominio (like `contoso.com` o `tailspintoys.com`).</span><span class="sxs-lookup"><span data-stu-id="c086d-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="c086d-143">Esto impedirá que se haga clic en cualquier dirección URL que contenga el dominio.</span><span class="sxs-lookup"><span data-stu-id="c086d-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="c086d-144">Puede especificar un subdominio (como `toys.contoso.com*`) sin bloquear un dominio completo (como `contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="c086d-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="c086d-145">Este bloque hará clic en cualquier dirección URL que contenga el subdominio, pero no bloqueará los clics en una dirección URL que contenga el dominio completo.</span><span class="sxs-lookup"><span data-stu-id="c086d-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="c086d-146">Puede incluir hasta tres asteriscos comodín (\*) por dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c086d-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="c086d-147">En la tabla siguiente se enumeran algunos ejemplos de lo que se puede especificar y el efecto que tienen dichas entradas.</span><span class="sxs-lookup"><span data-stu-id="c086d-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="c086d-148">**Entrada de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c086d-148">**Example Entry**</span></span>|<span data-ttu-id="c086d-149">**Qué hace**</span><span class="sxs-lookup"><span data-stu-id="c086d-149">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c086d-150">`contoso.com` o `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="c086d-150">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="c086d-151">Bloquea el dominio, los subdominios y las rutas de los `https://www.contoso.com`, `https://sub.contoso.com`como, y`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="c086d-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>  <br/> |
|`https://contoso.com/a`  <br/> |<span data-ttu-id="c086d-152">Bloquea un sitio `https://contoso.com/a` , pero no otros subtrazados adicionales como`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c086d-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://contoso.com/a*`  <br/> |<span data-ttu-id="c086d-153">Bloquea un sitio `https://contoso.com/a` y subrutas adicionales como`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c086d-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://toys.contoso.com*`  <br/> |<span data-ttu-id="c086d-154">Bloquea un subdominio ("juguetes" en este caso), pero permite hacer clic en otras direcciones URL de `https://contoso.com` dominio `https://home.contoso.com`(como o).</span><span class="sxs-lookup"><span data-stu-id="c086d-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="c086d-155">Cómo definir excepciones para determinados usuarios de una organización</span><span class="sxs-lookup"><span data-stu-id="c086d-155">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="c086d-156">Si desea que determinados grupos puedan ver direcciones URL que puedan estar bloqueadas para otros usuarios, puede especificar una directiva de vínculos seguros ATP que se aplique a destinatarios específicos.</span><span class="sxs-lookup"><span data-stu-id="c086d-156">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="c086d-157">Consulte [configurar una lista de direcciones URL personalizadas "no reescribir" mediante vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c086d-157">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

