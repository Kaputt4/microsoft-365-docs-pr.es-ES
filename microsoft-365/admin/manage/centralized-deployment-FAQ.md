---
title: Preguntas frecuentes sobre la implementación centralizada
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise las respuestas a preguntas frecuentes acerca de la implementación centralizada desde el Centro de administración de Microsoft 365.
ms.openlocfilehash: 0da9ec9595fd433abe1e2e2ae3f2e3a0c6b3b9b5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228018"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="3ddbb-103">Preguntas frecuentes sobre la implementación centralizada</span><span class="sxs-lookup"><span data-stu-id="3ddbb-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="3ddbb-104">La implementación centralizada es la forma recomendada para que un administrador de Office 365 implemente complementos de Office (Word, Excel, PowerPoint y Outlook) en usuarios y grupos de una organización, siempre que la organización cumpla todos los requisitos para usar la implementación centralizada, tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="3ddbb-105">¿Cómo sé si mi organización está configurada para la implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="3ddbb-106">La implementación centralizada de complementos requiere que los usuarios estén usando Aplicaciones Microsoft 365 para empresas (y que inicien sesión en Office con sus credenciales de inicio de sesión de la organización) y tengan Exchange Online buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="3ddbb-107">El directorio de suscripción debe estar en, o federado para, Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="3ddbb-108">La implementación centralizada solo es compatible con buzones en línea.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="3ddbb-109">No admite la implementación en buzones de correo Exchange local.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="3ddbb-110">Puede usar el Control de compatibilidad [de](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)implementación centralizada   para determinar si la suscripción es apta.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="3ddbb-111">¿Cómo se apuntan las asignaciones de usuario de complementos con implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="3ddbb-112">La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="3ddbb-113">La implementación centralizada se puede usar para usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no para usuarios de grupos anidados o grupos que tienen grupos primarios.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="3ddbb-114">La implementación centralizada también forma parte de la mayoría de Azure Active Directory, incluidos Office 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="3ddbb-115">Es mejor usar asignaciones de grupos en lugar de asignaciones de usuario individuales para facilitar la administración.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="3ddbb-116">Para obtener más información, vea [Asignaciones de usuario y grupo.](./centralized-deployment-of-add-ins.md#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="3ddbb-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="3ddbb-117">¿Cuánto tiempo se necesita para que los complementos se muestren para todos los usuarios?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="3ddbb-118">Un complemento puede tardar hasta 24 horas en aparecer para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="3ddbb-119">Puede tardar la misma cantidad de tiempo en actualizaciones de complementos, cambios desde activar o desactivar, o eliminaciones de complementos.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="3ddbb-120">Como administrador, ¿cómo puedo administrar el acceso de usuario a los complementos de mi organización?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="3ddbb-121">Para facilitar la implementación de complementos a usuarios, grupos o a toda la organización, se recomienda que los administradores usen la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="3ddbb-122">Para obtener más información acerca de cómo administrar el acceso de usuarios, vea:</span><span class="sxs-lookup"><span data-stu-id="3ddbb-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="3ddbb-123">Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)</span><span class="sxs-lookup"><span data-stu-id="3ddbb-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="3ddbb-124">Especifique qué administradores y usuarios pueden instalar y administrar complementos para Outlook</span><span class="sxs-lookup"><span data-stu-id="3ddbb-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="3ddbb-125">¿La implementación centralizada proporcionará a los administradores la flexibilidad para elegir el método de implementación para Outlook complementos?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="3ddbb-126">Sí.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-126">Yes.</span></span> <span data-ttu-id="3ddbb-127">La implementación centralizada proporciona a los administradores la flexibilidad de elegir uno de los tres métodos de implementación para Outlook complementos durante la implementación del complemento:</span><span class="sxs-lookup"><span data-stu-id="3ddbb-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="3ddbb-128">**Fijo (predeterminado)**   El complemento se implementa automáticamente en los usuarios asignados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="3ddbb-129">**Disponible** Los usuarios pueden instalar el complemento en Outlook seleccionando Inicio > Obtener más complementos > **administrados por el administrador.**</span><span class="sxs-lookup"><span data-stu-id="3ddbb-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="3ddbb-130">**Opcional** El complemento se implementa automáticamente en los usuarios asignados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="3ddbb-131">¿Pueden los administradores actualizar los complementos de línea de negocio (LOB)</span><span class="sxs-lookup"><span data-stu-id="3ddbb-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="3ddbb-132">Sí.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-132">Yes.</span></span> <span data-ttu-id="3ddbb-133">Los administradores pueden cargar un nuevo archivo de manifiesto para admitir los cambios de metadatos de los complementos de LOB implementados por el administrador. El complemento se actualiza la próxima vez que se inicien Office aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="3ddbb-134">La aplicación web puede cambiar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="3ddbb-135">Para obtener más información, [vea line-of-business add-in](./manage-addins-in-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="3ddbb-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="3ddbb-136">¿Pueden los administradores desactivar los complementos?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="3ddbb-137">Sí.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-137">Yes.</span></span> <span data-ttu-id="3ddbb-138">Los administradores pueden activar o desactivar los complementos que implementan para todos los usuarios desde el Centro de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="3ddbb-139">Para obtener más información, vea [Estados del complemento](./manage-addins-in-the-admin-center.md#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="3ddbb-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="3ddbb-140">¿Pueden los administradores eliminar o quitar complementos?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="3ddbb-141">Sí.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-141">Yes.</span></span> <span data-ttu-id="3ddbb-142">Los administradores pueden eliminar los complementos que implementaron para todos los usuarios del Centro de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="3ddbb-143">Para obtener más información, [vea Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="3ddbb-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="3ddbb-144">¿Pueden los administradores implementar complementos de pago desde Office store mediante la implementación centralizada?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="3ddbb-145">No.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-145">No.</span></span> <span data-ttu-id="3ddbb-146">No puedes implementar complementos de pago desde la Tienda Office con la implementación centralizada en este momento.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="3ddbb-147">Te recomendamos que te llegues al desarrollador de ISV para que el complemento de pago solicite un archivo de manifiesto o una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="3ddbb-148">A continuación, el administrador del espacio empresarial puede implementar el complemento como complemento de LOB mediante la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="3ddbb-149">¿Qué rol de administrador necesito para administrar complementos para mi organización?</span><span class="sxs-lookup"><span data-stu-id="3ddbb-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="3ddbb-150">Administración global es el rol recomendado con acceso completo al ciclo de vida de administración de complementos.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="3ddbb-151">Si eres la persona que compró tu suscripción Microsoft 365 empresa, eres el administrador global.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-151">If you're the person who purchased your Microsoft 365 Business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="3ddbb-152">La suscripción viene con un conjunto de roles de administrador que puede asignar a otros usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-152">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="3ddbb-153">Cada rol de administrador se asigna a funciones empresariales comunes y proporciona a los usuarios de la organización permisos para realizar tareas específicas en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ddbb-153">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="3ddbb-154">Para obtener más información, vea [Asignar roles de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3ddbb-154">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md).</span></span> 
