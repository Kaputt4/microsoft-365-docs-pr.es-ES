---
title: Preguntas frecuentes sobre la implementación centralizada
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
description: Revise las respuestas a preguntas frecuentes sobre la implementación centralizada desde el Centro de administración de Microsoft 365.
ms.openlocfilehash: 9f4841508701d4dd5878e99fcc51a436bc5824e2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915475"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="09010-103">Preguntas frecuentes sobre la implementación centralizada</span><span class="sxs-lookup"><span data-stu-id="09010-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="09010-104">La implementación centralizada es la forma recomendada para que un administrador de Office 365 implemente complementos de Office (Word, Excel, PowerPoint y Outlook) en usuarios y grupos de una organización, siempre que la organización cumpla todos los requisitos para usar la implementación centralizada, tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="09010-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="09010-105">¿Cómo sé si mi organización está configurada para la implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="09010-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="09010-106">La implementación centralizada de complementos requiere que los usuarios usen aplicaciones de Microsoft 365 para empresas (y que inicien sesión en Office con sus credenciales de inicio de sesión de la organización) y que tengan buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="09010-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="09010-107">El directorio de suscripción debe estar en Azure Active Directory o estar federado con él.</span><span class="sxs-lookup"><span data-stu-id="09010-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="09010-108">La implementación centralizada solo es compatible con buzones en línea.</span><span class="sxs-lookup"><span data-stu-id="09010-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="09010-109">No admite la implementación en buzones de Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="09010-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="09010-110">Puede usar el Control de compatibilidad [de](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)implementación centralizada   para determinar si la suscripción es apta.</span><span class="sxs-lookup"><span data-stu-id="09010-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="09010-111">¿Cómo se apuntan las asignaciones de usuario de complementos con implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="09010-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="09010-112">La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="09010-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="09010-113">La implementación centralizada se puede usar para usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no para usuarios de grupos anidados o grupos que tienen grupos primarios.</span><span class="sxs-lookup"><span data-stu-id="09010-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="09010-114">La implementación centralizada también forma parte de la mayoría de los grupos de Azure Active Directory, incluidos grupos de Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="09010-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="09010-115">Es mejor usar asignaciones de grupos en lugar de asignaciones de usuario individuales para facilitar la administración.</span><span class="sxs-lookup"><span data-stu-id="09010-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="09010-116">Para obtener más información, vea [Asignaciones de usuario y grupo.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="09010-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="09010-117">¿Cuánto tiempo se necesita para que los complementos se muestren para todos los usuarios?</span><span class="sxs-lookup"><span data-stu-id="09010-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="09010-118">Un complemento puede tardar hasta 24 horas en aparecer para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09010-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="09010-119">Puede tardar la misma cantidad de tiempo en actualizaciones de complementos, cambios desde activar o desactivar, o eliminaciones de complementos.</span><span class="sxs-lookup"><span data-stu-id="09010-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="09010-120">Como administrador, ¿cómo puedo administrar el acceso de usuario a los complementos de mi organización?</span><span class="sxs-lookup"><span data-stu-id="09010-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="09010-121">Para facilitar la implementación de complementos a usuarios, grupos o a toda la organización, se recomienda que los administradores usen la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="09010-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="09010-122">Para obtener más información acerca de cómo administrar el acceso de usuarios, vea:</span><span class="sxs-lookup"><span data-stu-id="09010-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="09010-123">Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)</span><span class="sxs-lookup"><span data-stu-id="09010-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="09010-124">Especifique los administradores y los usuarios que pueden instalar y administrar complementos para Outlook</span><span class="sxs-lookup"><span data-stu-id="09010-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="09010-125">¿La implementación centralizada proporcionará a los administradores la flexibilidad para elegir el método de implementación para los complementos de Outlook?</span><span class="sxs-lookup"><span data-stu-id="09010-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="09010-126">Sí.</span><span class="sxs-lookup"><span data-stu-id="09010-126">Yes.</span></span> <span data-ttu-id="09010-127">La implementación centralizada proporciona a los administradores la flexibilidad de elegir uno de los tres métodos de implementación para los complementos de Outlook durante la implementación de complementos:</span><span class="sxs-lookup"><span data-stu-id="09010-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="09010-128">**Fijo (predeterminado)**   El complemento se implementa automáticamente en los usuarios asignados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="09010-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="09010-129">**Disponible** Los usuarios pueden instalar el complemento en Outlook eligiendo Inicio > Obtener más complementos > **administrados por el administrador.**</span><span class="sxs-lookup"><span data-stu-id="09010-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="09010-130">**Opcional** El complemento se implementa automáticamente en los usuarios asignados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="09010-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="09010-131">¿Pueden los administradores actualizar los complementos de línea de negocio (LOB)</span><span class="sxs-lookup"><span data-stu-id="09010-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="09010-132">Sí.</span><span class="sxs-lookup"><span data-stu-id="09010-132">Yes.</span></span> <span data-ttu-id="09010-133">Los administradores pueden cargar un nuevo archivo de manifiesto para admitir los cambios de metadatos de los complementos de LOB implementados por el administrador. El complemento se actualiza la próxima vez que se inicien las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="09010-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="09010-134">La aplicación web puede cambiar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="09010-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="09010-135">Para obtener más información, [vea line-of-business add-in](./manage-addins-in-the-admin-center.md#more-about-office-add-ins-security).</span><span class="sxs-lookup"><span data-stu-id="09010-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="09010-136">¿Pueden los administradores desactivar los complementos?</span><span class="sxs-lookup"><span data-stu-id="09010-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="09010-137">Sí.</span><span class="sxs-lookup"><span data-stu-id="09010-137">Yes.</span></span> <span data-ttu-id="09010-138">Los administradores pueden activar o desactivar los complementos que implementan para todos los usuarios desde el Centro de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09010-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="09010-139">Para obtener más información, vea [Estados del complemento](./manage-addins-in-the-admin-center.md#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="09010-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="09010-140">¿Pueden los administradores eliminar o quitar complementos?</span><span class="sxs-lookup"><span data-stu-id="09010-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="09010-141">Sí.</span><span class="sxs-lookup"><span data-stu-id="09010-141">Yes.</span></span> <span data-ttu-id="09010-142">Los administradores pueden eliminar los complementos que implementaron para todos los usuarios del Centro de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09010-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="09010-143">Para obtener más información, [vea Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="09010-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="09010-144">¿Pueden los administradores implementar complementos de pago desde la Tienda Office mediante la implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="09010-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="09010-145">No.</span><span class="sxs-lookup"><span data-stu-id="09010-145">No.</span></span> <span data-ttu-id="09010-146">No puede implementar complementos de pago desde la Tienda Office con la implementación centralizada en este momento.</span><span class="sxs-lookup"><span data-stu-id="09010-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="09010-147">Te recomendamos que te llegues al desarrollador de ISV para que el complemento de pago solicite un archivo de manifiesto o una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="09010-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="09010-148">A continuación, el administrador del espacio empresarial puede implementar el complemento como complemento de LOB mediante la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="09010-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="09010-149">¿Qué rol de administrador necesito para administrar complementos para mi organización?</span><span class="sxs-lookup"><span data-stu-id="09010-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="09010-150">Administración global es el rol recomendado con acceso completo al ciclo de vida de administración de complementos.</span><span class="sxs-lookup"><span data-stu-id="09010-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="09010-151">Otros roles de administrador tienen un acceso limitado al ciclo de vida de implementación del complemento.</span><span class="sxs-lookup"><span data-stu-id="09010-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="09010-152">Si eres la persona que compró tu suscripción a Microsoft 365 para empresas, eres el administrador global.</span><span class="sxs-lookup"><span data-stu-id="09010-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="09010-153">La suscripción viene con un conjunto de roles de administrador que puede asignar a otros usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="09010-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="09010-154">Cada rol de administrador se asigna a funciones empresariales comunes y proporciona a los usuarios de la organización permisos para realizar tareas específicas en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09010-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="09010-155">Para obtener más información, vea [Asignar roles de administrador](../add-users/assign-admin-roles.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="09010-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 