---
title: Editar o establecer la configuración de protección de aplicaciones para dispositivos Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Aprende a crear o editar directivas de administración de aplicaciones y a proteger los archivos de trabajo en los dispositivos personales de Windows 10 de los usuarios.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580022"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="9c63f-103">Establecer o editar la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="9c63f-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="9c63f-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="9c63f-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="9c63f-105">Editar una directiva de administración de aplicaciones para Windows 10</span><span class="sxs-lookup"><span data-stu-id="9c63f-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="9c63f-106">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="9c63f-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="9c63f-107">En el panel de navegación izquierdo, elija **Directivas de** \> **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="9c63f-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="9c63f-108">Elija una directiva de aplicación de Windows existente y, a **continuación, Edit**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="9c63f-109">Elija **Editar** junto a una configuración que desea cambiar y, a continuación, **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="9c63f-110">Crear una directiva de administración de aplicaciones para Windows 10</span><span class="sxs-lookup"><span data-stu-id="9c63f-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="9c63f-111">Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.</span><span class="sxs-lookup"><span data-stu-id="9c63f-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="9c63f-112">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="9c63f-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="9c63f-113">En la navegación izquierda, elija **Directivas** \> **de** \> **dispositivos Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="9c63f-114">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9c63f-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="9c63f-115">En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="9c63f-116">En **Tipo de dispositivo**, elija **Personal** o Propiedad de **la empresa**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="9c63f-117">La opción **Cifrar archivos de trabajo** se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9c63f-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="9c63f-118">Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9c63f-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="9c63f-119">Expande **Recuperar datos en dispositivos Windows**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="9c63f-120">Se recomienda **activarlo**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="9c63f-121">Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno.</span><span class="sxs-lookup"><span data-stu-id="9c63f-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="9c63f-122">Para obtener instrucciones, vea [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span><span class="sxs-lookup"><span data-stu-id="9c63f-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span></span>
    
    <span data-ttu-id="9c63f-123">De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="9c63f-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="9c63f-124">Solo el usuario puede abrir y descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="9c63f-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="9c63f-125">Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado.</span><span class="sxs-lookup"><span data-stu-id="9c63f-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="9c63f-126">Un administrador puede usar el certificado agente de recuperación de datos (DRA) para descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="9c63f-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="9c63f-128">Expanda **Proteger ubicaciones de red** y nube adicionales si desea agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones enumeradas están protegidos.</span><span class="sxs-lookup"><span data-stu-id="9c63f-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="9c63f-129">Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos.</span><span class="sxs-lookup"><span data-stu-id="9c63f-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="9c63f-p104">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="9c63f-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="9c63f-133">Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9c63f-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span>