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
ms.openlocfilehash: 0e1221e533418166b80afd94431414016774f247
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575786"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="460bb-103">Establecer la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="460bb-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="460bb-104">Crear una directiva de administración de aplicaciones para Windows 10</span><span class="sxs-lookup"><span data-stu-id="460bb-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="460bb-105">Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.</span><span class="sxs-lookup"><span data-stu-id="460bb-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="460bb-106">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="460bb-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="460bb-107">En el panel de navegación izquierdo, elija **Agregar** **directivas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="460bb-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="460bb-108">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="460bb-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="460bb-109">En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="460bb-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="460bb-110">En **tipo de dispositivo**, elija **personal** o **propiedad**de la empresa.</span><span class="sxs-lookup"><span data-stu-id="460bb-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="460bb-111">La opción **Cifrar archivos de trabajo** se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="460bb-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="460bb-112">Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo.</span><span class="sxs-lookup"><span data-stu-id="460bb-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="460bb-113">Expanda la opción **Recuperar datos en dispositivos Windows** y se recomienda que la **active**.</span><span class="sxs-lookup"><span data-stu-id="460bb-113">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="460bb-p101">Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, vea [Crear y comprobar un certificado del Agente de recuperación de datos (DRA) del Sistema de cifrado de archivos (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="460bb-p101">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="460bb-p102">De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado. El certificado del agente de recuperación de datos (ARD) puede ser utilizado por un administrador para descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="460bb-p102">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="460bb-p103">Expanda la opción **Proteger otras ubicaciones de red y nube** si quiere agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones de la lista están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos.</span><span class="sxs-lookup"><span data-stu-id="460bb-p103">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="460bb-p104">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="460bb-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="460bb-126">Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="460bb-126">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 