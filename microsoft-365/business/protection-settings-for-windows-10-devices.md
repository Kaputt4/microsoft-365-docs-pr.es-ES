---
title: Establecer la configuración de protección de aplicaciones para dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Obtenga información sobre cómo crear una directiva de administración de aplicaciones y proteger los archivos de trabajo en dispositivos con Windows 10.
ms.openlocfilehash: ca6d789e0242975a0395e6cf5653d3f43f819801
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715260"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="41e28-103">Establecer la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="41e28-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="41e28-104">Crear una directiva de administración de aplicaciones para Windows 10</span><span class="sxs-lookup"><span data-stu-id="41e28-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="41e28-105">Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.</span><span class="sxs-lookup"><span data-stu-id="41e28-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="41e28-106">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="41e28-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="41e28-107">En el panel de navegación izquierdo, elija **Agregar** **directivas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="41e28-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="41e28-108">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="41e28-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="41e28-109">En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="41e28-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="41e28-110">En **tipo de dispositivo**, elija **personal** o **propiedad**de la empresa.</span><span class="sxs-lookup"><span data-stu-id="41e28-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="41e28-111">La opción **Cifrar archivos de trabajo** se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="41e28-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="41e28-112">Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo.</span><span class="sxs-lookup"><span data-stu-id="41e28-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="41e28-113">Expanda **recuperar datos en dispositivos Windows**.</span><span class="sxs-lookup"><span data-stu-id="41e28-113">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="41e28-114">Le recomendamos que la Active **.**</span><span class="sxs-lookup"><span data-stu-id="41e28-114">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="41e28-115">Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno.</span><span class="sxs-lookup"><span data-stu-id="41e28-115">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="41e28-116">Para obtener instrucciones, vea [crear y comprobar un certificado del agente de recuperación de datos (DRA) del sistema de archivos de cifrado (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="41e28-116">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="41e28-117">De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="41e28-117">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="41e28-118">Solo el usuario puede abrir y descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="41e28-118">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="41e28-119">Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado.</span><span class="sxs-lookup"><span data-stu-id="41e28-119">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="41e28-120">Un administrador puede usar el certificado del agente de recuperación de datos (DRA) para descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="41e28-120">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="41e28-122">Expanda **proteger la red y las ubicaciones de nube adicionales** si desea agregar más dominios o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones que se muestran están protegidos.</span><span class="sxs-lookup"><span data-stu-id="41e28-122">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="41e28-123">Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos.</span><span class="sxs-lookup"><span data-stu-id="41e28-123">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="41e28-p105">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="41e28-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="41e28-127">Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="41e28-127">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 