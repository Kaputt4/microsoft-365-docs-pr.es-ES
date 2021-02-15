---
title: Preparar un dominio no enrutable para la sincronización de directorios
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Obtenga información sobre qué hacer si tiene un dominio no enrutable asociado a sus cuentas de usuario locales antes de sincronizarlas con su inquilino de Microsoft 365.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780337"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="c38f3-103">Preparar un dominio no enrutable para la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="c38f3-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="c38f3-104">Al sincronizar el directorio local con Microsoft 365, debe tener un dominio comprobado en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c38f3-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c38f3-105">Solo se sincronizan los nombres principales de usuario (UPN) asociados con el dominio local de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c38f3-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="c38f3-106">Sin embargo, cualquier UPN que contenga un dominio no enrutable, como ".local" (ejemplo: billa@contoso.local), se sincronizará con un dominio .onmicrosoft.com (ejemplo: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="c38f3-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="c38f3-107">Si actualmente usa un dominio ".local" para sus cuentas de usuario en AD DS, se recomienda cambiarlas para que usen un dominio comprobado, como billa@contoso.com, para sincronizarse correctamente con su dominio de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="c38f3-108">¿Qué ocurre si solo tengo un dominio local ".local"?</span><span class="sxs-lookup"><span data-stu-id="c38f3-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="c38f3-109">Usa Azure AD Connect para sincronizar su AD DS con el inquilino de Azure AD de su inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="c38f3-110">Para obtener más información, vea [Integración de las identidades locales con Azure AD.](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)</span><span class="sxs-lookup"><span data-stu-id="c38f3-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="c38f3-111">Azure AD Connect sincroniza el UPN y la contraseña de los usuarios para que los usuarios puedan iniciar sesión con las mismas credenciales que usan localmente.</span><span class="sxs-lookup"><span data-stu-id="c38f3-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="c38f3-112">Sin embargo, Azure AD Connect solo sincroniza usuarios con dominios comprobados por Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="c38f3-113">Esto significa que Azure AD también comprueba el dominio porque azure AD administra las identidades de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="c38f3-114">En otras palabras, el dominio debe ser un dominio de Internet válido (por ejemplo, .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="c38f3-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="c38f3-115">Si su AD DS interno solo usa un dominio no enrutable (por ejemplo, ".local"), es posible que esto no coincida con el dominio comprobado que tiene para su inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="c38f3-116">Puede solucionar este problema cambiando el dominio principal en su AD DS local o agregando uno o más sufijos UPN.</span><span class="sxs-lookup"><span data-stu-id="c38f3-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="c38f3-117">Cambiar el dominio principal</span><span class="sxs-lookup"><span data-stu-id="c38f3-117">Change your primary domain</span></span>

<span data-ttu-id="c38f3-118">Cambie su dominio principal a un dominio que haya comprobado en Microsoft 365, por ejemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c38f3-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="c38f3-119">A continuación, todos los usuarios que tienen el dominio contoso.local se actualizan para contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c38f3-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="c38f3-120">Sin embargo, este es un proceso muy implicado y se describe una solución más sencilla en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="c38f3-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="c38f3-121">Agregar sufijos UPN y actualizar los usuarios a ellos</span><span class="sxs-lookup"><span data-stu-id="c38f3-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="c38f3-122">Puede solucionar el problema ".local" registrando nuevos sufijos UPN en AD DS para que coincidan con el dominio (o dominios) que ha comprobado en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="c38f3-123">Después de registrar el nuevo sufijo, actualice los UPN de usuario para reemplazar ".local" por el nuevo nombre de dominio, por ejemplo, para que una cuenta de usuario se parezca a billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c38f3-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="c38f3-124">Después de actualizar los UPN para usar el dominio comprobado, está listo para sincronizar su AD DS local con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38f3-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="c38f3-125">Paso 1: Agregar el nuevo sufijo UPN\*\*</span><span class="sxs-lookup"><span data-stu-id="c38f3-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="c38f3-126">En el controlador de dominio de AD DS, en el Administrador de servidores, elija **Herramientas** dominios y \> **confianzas de Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="c38f3-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="c38f3-127">**O bien, si no tienes Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="c38f3-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="c38f3-128">Presione la tecla Windows  + **R** para abrir el cuadro de diálogo Ejecutar y, a continuación, escriba Domain.msc y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c38f3-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Elija Dominios y confianzas de Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="c38f3-130">En la **ventana Dominios y confianzas** de Active Directory, haga clic con el botón secundario en Dominios y **confianzas** de Active Directory y, a continuación, elija **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="c38f3-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Haga clic con el botón secundario en Dominios y confianzas de Active Directory y elija Propiedades](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="c38f3-132">En la pestaña Sufijos **UPN,** en el cuadro Sufijos **UPN** alternativos, escriba el nuevo sufijo o sufijos UPN y, a continuación, **elija** \> **Agregar aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c38f3-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Agregar un nuevo sufijo UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="c38f3-134">Elija **Aceptar** cuando haya terminado de agregar sufijos.</span><span class="sxs-lookup"><span data-stu-id="c38f3-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="c38f3-135">Paso 2: Cambiar el sufijo UPN para los usuarios existentes</span><span class="sxs-lookup"><span data-stu-id="c38f3-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="c38f3-136">En el controlador de dominio de AD DS, en el Administrador de servidores, elija **Herramientas** \> **usuarios y equipos de Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="c38f3-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="c38f3-137">**O bien, si no tienes Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="c38f3-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="c38f3-138">Presione la tecla Windows  + **R** para abrir el cuadro de diálogo Ejecutar y, a continuación, escriba Dsa.msc y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="c38f3-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="c38f3-139">Seleccione un usuario, haga clic con el botón secundario y, a continuación, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c38f3-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="c38f3-140">En la **pestaña** Cuenta, en la lista desplegable de sufijos UPN, elija el nuevo sufijo UPN y, a continuación, **elija Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c38f3-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Agregar nuevo sufijo UPN para un usuario](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="c38f3-142">Siga estos pasos para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="c38f3-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="c38f3-143">Usar PowerShell para cambiar el sufijo UPN de todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="c38f3-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="c38f3-144">Si tiene muchas cuentas de usuario que actualizar, es más fácil usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c38f3-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="c38f3-145">En el ejemplo siguiente se usan los cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) y [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) para cambiar todos los sufijos contoso.local a contoso.com en AD DS.</span><span class="sxs-lookup"><span data-stu-id="c38f3-145">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="c38f3-146">Por ejemplo, puede ejecutar los siguientes comandos de PowerShell para actualizar todos los sufijos contoso.local a contoso.com:</span><span class="sxs-lookup"><span data-stu-id="c38f3-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="c38f3-147">Consulta [el módulo de Windows PowerShell Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=624314) para obtener más información sobre el uso de Windows PowerShell en AD DS.</span><span class="sxs-lookup"><span data-stu-id="c38f3-147">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

