---
title: 'Paso 7: Eliminar la cuenta de usuario de un antiguo empleado'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga estos pasos para eliminar la cuenta de usuario de un antiguo empleado.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244292"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="349b6-103">Paso 7: Eliminar la cuenta de usuario de un antiguo empleado</span><span class="sxs-lookup"><span data-stu-id="349b6-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="349b6-104">Después de haber guardado y accedido a todos los datos de usuario del antiguo empleado, puede suprimir su cuenta.</span><span class="sxs-lookup"><span data-stu-id="349b6-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="349b6-p101">No elimine la cuenta si ha configurado el reenvío de correo electrónico o la ha convertido en un buzón compartido. En ambos casos se necesita la cuenta para anclar el reenvío de correo o el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="349b6-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="349b6-107">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="349b6-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="349b6-108">Seleccione el nombre del empleado que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="349b6-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="349b6-109">En el nombre del usuario, seleccione **Eliminar usuario**.</span><span class="sxs-lookup"><span data-stu-id="349b6-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="349b6-110">Elija las opciones que desee para este usuario y, a continuación, **seleccione Eliminar usuario**.</span><span class="sxs-lookup"><span data-stu-id="349b6-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="349b6-111">Si ya ha concedido a otro usuario acceso al correo electrónico y al OneDrive, no tiene que volver a hacerlo aquí.</span><span class="sxs-lookup"><span data-stu-id="349b6-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="349b6-p103">Al eliminar un usuario, la cuenta se vuelve inactiva durante aproximadamente 30 días. Tiene tiempo hasta ese momento para restaurar la cuenta antes de que se elimine de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="349b6-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="349b6-114">¿Su organización utiliza Active Directory?</span><span class="sxs-lookup"><span data-stu-id="349b6-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="349b6-115">Si su organización sincroniza las cuentas de usuario Microsoft 365 desde un entorno local de Active Directory, debe eliminar y restaurar esas cuentas de usuario en el servicio de Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="349b6-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="349b6-116">No puede suprimirlas ni restaurarlas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="349b6-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="349b6-117">Para obtener información sobre cómo eliminar y restaurar una cuenta de usuario en Active Directory, vea [Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="349b6-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="349b6-118">Si usas Azure Active Directory, consulta el cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="349b6-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="349b6-119">Todo lo que debe saber sobre el cierre de la sesión de un empleado</span><span class="sxs-lookup"><span data-stu-id="349b6-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="349b6-120">Aquí tiene información sobre cómo quitar a un empleado del correo electrónico (Exchange).</span><span class="sxs-lookup"><span data-stu-id="349b6-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="349b6-121">**Qué puede hacer**</span><span class="sxs-lookup"><span data-stu-id="349b6-121">**What you can do**</span></span> <br/> |<span data-ttu-id="349b6-122">**Cómo debe hacerlo**</span><span class="sxs-lookup"><span data-stu-id="349b6-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="349b6-123">Cerrar una sesión (de Outlook en la Web, Outlook, Exchange Active Sync, etc.) y forzar el inicio de una sesión nueva</span><span class="sxs-lookup"><span data-stu-id="349b6-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="349b6-124">Restablecer la contraseña</span><span class="sxs-lookup"><span data-stu-id="349b6-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="349b6-125">Cerrar una sesión y bloquear el acceso a sesiones futuras (para todos los protocolos)</span><span class="sxs-lookup"><span data-stu-id="349b6-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="349b6-126">Deshabilite la cuenta.</span><span class="sxs-lookup"><span data-stu-id="349b6-126">Disable the account.</span></span> <span data-ttu-id="349b6-127">Por ejemplo, (en el centro Exchange administración o mediante PowerShell):</span><span class="sxs-lookup"><span data-stu-id="349b6-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="349b6-128">Cerrar la sesión de un protocolo en particular (como ActiveSync)</span><span class="sxs-lookup"><span data-stu-id="349b6-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="349b6-129">Deshabilite el protocolo.</span><span class="sxs-lookup"><span data-stu-id="349b6-129">Disable the protocol.</span></span> <span data-ttu-id="349b6-130">Por ejemplo, (en el centro Exchange administración o mediante PowerShell):</span><span class="sxs-lookup"><span data-stu-id="349b6-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="349b6-131">Las operaciones anteriores se pueden realizar en tres lugares:</span><span class="sxs-lookup"><span data-stu-id="349b6-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="349b6-132">**Si cierra la sesión aquí**</span><span class="sxs-lookup"><span data-stu-id="349b6-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="349b6-133">**Cuánto tiempo se tarda**</span><span class="sxs-lookup"><span data-stu-id="349b6-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="349b6-134">En el centro de administración de Exchange o usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="349b6-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="349b6-135">La duración estimada es de 30 minutos</span><span class="sxs-lookup"><span data-stu-id="349b6-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="349b6-136">En el centro de administración de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="349b6-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="349b6-137">La duración estimada es de 60 minutos</span><span class="sxs-lookup"><span data-stu-id="349b6-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="349b6-138">En un entorno local</span><span class="sxs-lookup"><span data-stu-id="349b6-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="349b6-139">La duración estimada es de 3 horas o más</span><span class="sxs-lookup"><span data-stu-id="349b6-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="349b6-140">Procedimiento para obtener una respuesta más rápida para la eliminación de la cuenta</span><span class="sxs-lookup"><span data-stu-id="349b6-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="349b6-p107">**Más rápida**: use el Centro de administración de Exchange (use PowerShell) o el Centro de administración de Azure Active Directory. En un entorno local, el cambio mediante DirSync puede tardar varias horas en sincronizarse.</span><span class="sxs-lookup"><span data-stu-id="349b6-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="349b6-p108">**Más rápida para un usuario con presencia local y en el centro de datos de Exchange**: finalice la sesión mediante el Centro de administración de Azure Active Directory o el Centro de administración de Exchange Y efectúe también el cambio en el entorno local. En caso contrario, DirSync sobrescribirá el cambio realizado en el Centro de administración de Exchange o el Centro de administración Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="349b6-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="349b6-145">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="349b6-145">Related articles</span></span>

[<span data-ttu-id="349b6-146">Restaurar un usuario</span><span class="sxs-lookup"><span data-stu-id="349b6-146">Restore a user</span></span>](restore-user.md)
