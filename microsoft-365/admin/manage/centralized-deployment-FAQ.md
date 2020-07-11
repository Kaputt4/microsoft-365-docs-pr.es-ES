---
title: Preguntas frecuentes sobre implementación centralizada
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise las respuestas a preguntas frecuentes sobre la implementación centralizada en el centro de administración de Microsoft 365.
ms.openlocfilehash: b1b5ccbb5373bf5d536208efdfe487bc0c872f25
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102889"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="01758-103">Preguntas frecuentes sobre implementación centralizada</span><span class="sxs-lookup"><span data-stu-id="01758-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="01758-104">La implementación centralizada es la forma recomendada para que un administrador de Office 365 implemente complementos de Office (Word, Excel, PowerPoint y Outlook) para usuarios y grupos de una organización, siempre que la organización cumpla todos los requisitos para usar la implementación centralizada, tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="01758-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="01758-105">¿Cómo sé si mi organización está configurada para la implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="01758-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="01758-106">La implementación centralizada de complementos requiere que los usuarios usen las aplicaciones de Microsoft 365 para empresas (y que hayan iniciado sesión en Office con sus credenciales de inicio de sesión en la organización) y tengan buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="01758-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="01758-107">El directorio de suscripción debe estar o estar federado a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="01758-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="01758-108">La implementación centralizada solo se admite para los buzones de correo en línea.</span><span class="sxs-lookup"><span data-stu-id="01758-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="01758-109">No admite la implementación en buzones de Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="01758-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="01758-110">Puede usar el [Comprobador de compatibilidad de implementación centralizada](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   para determinar si la suscripción es apta.</span><span class="sxs-lookup"><span data-stu-id="01758-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="01758-111">¿Cómo se dirigen las asignaciones de usuario de complementos con una implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="01758-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="01758-112">La implementación centralizada admite asignaciones a usuarios individuales, grupos y a todos los miembros del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="01758-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="01758-113">La implementación centralizada se puede usar para los usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no para los usuarios de grupos anidados o grupos que tienen grupos primarios.</span><span class="sxs-lookup"><span data-stu-id="01758-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="01758-114">La implementación centralizada también forma parte de la mayoría de los grupos de Azure Active Directory, incluidos los grupos de Office 365, las listas de distribución y los grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="01758-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="01758-115">Es mejor usar asignaciones de grupos en lugar de asignación de usuario individual para facilitar la administración.</span><span class="sxs-lookup"><span data-stu-id="01758-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="01758-116">Para obtener más información, vea [asignaciones de usuarios y grupos](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="01758-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="01758-117">¿Cuánto tiempo se tarda en mostrar los complementos para todos los usuarios?</span><span class="sxs-lookup"><span data-stu-id="01758-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="01758-118">Un complemento puede tardar hasta 24 horas en mostrarse para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="01758-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="01758-119">Puede tardar la misma cantidad de tiempo en las actualizaciones de los complementos, los cambios de desactivación o desactivación, o la eliminación de complementos.</span><span class="sxs-lookup"><span data-stu-id="01758-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="01758-120">Como administrador, ¿cómo se administra el acceso del usuario a los complementos de mi organización?</span><span class="sxs-lookup"><span data-stu-id="01758-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="01758-121">Para facilitar la implementación de complementos a usuarios, grupos o a toda la organización, se recomienda que los administradores usen la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="01758-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="01758-122">Para obtener más información acerca de la administración del acceso de usuarios, consulte:</span><span class="sxs-lookup"><span data-stu-id="01758-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="01758-123">Impedir las descargas del complemento desactivando la tienda Office en todos los clientes (excepto Outlook)</span><span class="sxs-lookup"><span data-stu-id="01758-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="01758-124">Especifique los administradores y los usuarios que pueden instalar y administrar complementos para Outlook</span><span class="sxs-lookup"><span data-stu-id="01758-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="01758-125">¿La implementación centralizada proporciona a los administradores la flexibilidad necesaria para elegir el método de implementación para complementos de Outlook?</span><span class="sxs-lookup"><span data-stu-id="01758-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="01758-126">Sí.</span><span class="sxs-lookup"><span data-stu-id="01758-126">Yes.</span></span> <span data-ttu-id="01758-127">La implementación centralizada proporciona a los administradores la flexibilidad de elegir uno de los tres métodos de implementación para los complementos de Outlook durante la implementación de complementos:</span><span class="sxs-lookup"><span data-stu-id="01758-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="01758-128">**Fijo (predeterminado)**   El complemento se implementa automáticamente en los usuarios asignados y no puede quitarlos.</span><span class="sxs-lookup"><span data-stu-id="01758-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="01758-129">**Disponible** Los usuarios pueden instalar el complemento en Outlook eligiendo **inicio > obtener más complementos > administración administrada por el administrador**.</span><span class="sxs-lookup"><span data-stu-id="01758-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="01758-130">**Opcional** El complemento se implementa automáticamente en los usuarios asignados, pero puede elegir quitarlos.</span><span class="sxs-lookup"><span data-stu-id="01758-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="01758-131">¿Los administradores pueden actualizar los complementos de línea de negocio (LOB)?</span><span class="sxs-lookup"><span data-stu-id="01758-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="01758-132">Sí.</span><span class="sxs-lookup"><span data-stu-id="01758-132">Yes.</span></span> <span data-ttu-id="01758-133">Los administradores pueden cargar un nuevo archivo de manifiesto para admitir los cambios de metadatos para los complementos LOB implementados por el administrador. El complemento se actualiza la próxima vez que se inicien las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="01758-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="01758-134">La aplicación web puede cambiar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="01758-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="01758-135">Para obtener más información, consulte [complemento de línea de negocio](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span><span class="sxs-lookup"><span data-stu-id="01758-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="01758-136">¿Pueden los administradores desactivar los complementos?</span><span class="sxs-lookup"><span data-stu-id="01758-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="01758-137">Sí.</span><span class="sxs-lookup"><span data-stu-id="01758-137">Yes.</span></span> <span data-ttu-id="01758-138">Los administradores pueden activar o desactivar los complementos que implementan para todos los usuarios desde el centro de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01758-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="01758-139">Para obtener más información, consulte [Estados de complementos](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="01758-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="01758-140">¿Los administradores pueden eliminar o quitar complementos?</span><span class="sxs-lookup"><span data-stu-id="01758-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="01758-141">Sí.</span><span class="sxs-lookup"><span data-stu-id="01758-141">Yes.</span></span> <span data-ttu-id="01758-142">Los administradores pueden eliminar complementos implementados para todos los usuarios desde el centro de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01758-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="01758-143">Para obtener más información, vea [eliminar un complemento](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="01758-143">For more information, see [Delete an add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="01758-144">¿Pueden los administradores implementar complementos de pago desde la tienda Office con una implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="01758-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="01758-145">No.</span><span class="sxs-lookup"><span data-stu-id="01758-145">No.</span></span> <span data-ttu-id="01758-146">No puede implementar complementos de pago desde la tienda Office con la implementación centralizada en este momento.</span><span class="sxs-lookup"><span data-stu-id="01758-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="01758-147">Le sugerimos que llegue al desarrollador de ISV para que el complemento de pago solicite un archivo de manifiesto o una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="01758-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="01758-148">A continuación, el administrador de inquilinos puede implementar el complemento como un complemento de LOB mediante una implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="01758-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="01758-149">¿Qué rol de administración necesito para administrar los complementos de mi organización?</span><span class="sxs-lookup"><span data-stu-id="01758-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="01758-150">Debe tener el rol de administrador global para administrar complementos. Si usted es la persona que compró su suscripción de Microsoft 365 para empresas, será el administrador global.</span><span class="sxs-lookup"><span data-stu-id="01758-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="01758-151">Su suscripción incluye un conjunto de roles de administrador que puede asignar a otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="01758-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="01758-152">Cada rol de administrador se asigna a funciones empresariales comunes y proporciona a los usuarios de su organización permisos para realizar tareas específicas en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01758-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="01758-153">Para obtener más información, vea [asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="01758-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  
