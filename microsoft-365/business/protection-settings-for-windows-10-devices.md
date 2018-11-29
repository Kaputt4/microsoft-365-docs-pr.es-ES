---
title: Establecer la configuración de protección de aplicaciones para dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Obtenga información sobre cómo crear una directiva de administración de aplicaciones y protección de archivos de trabajo en los dispositivos de Windows 10.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871361"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="278b6-103">Establecer la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="278b6-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="278b6-104">Crear una directiva de administración de aplicaciones para Windows 10</span><span class="sxs-lookup"><span data-stu-id="278b6-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="278b6-105">Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.</span><span class="sxs-lookup"><span data-stu-id="278b6-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="278b6-p101">Inicie sesión en [Microsoft 365 Business](https://portal.office.com) con credenciales de administrador global. Elija el icono **Administrador** para ir al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="278b6-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="278b6-108">En la tarjeta **Directivas de dispositivos** del portal de administración, elija **Agregar directiva**.</span><span class="sxs-lookup"><span data-stu-id="278b6-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="278b6-110">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="278b6-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="278b6-111">En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="278b6-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="278b6-112">Bajo \*\* tipo de dispositivo \*\*, elija **Personal** o **Propietaria de la empresa**.</span><span class="sxs-lookup"><span data-stu-id="278b6-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="278b6-113">La opción **Cifrar archivos de trabajo** se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="278b6-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="278b6-114">Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo.</span><span class="sxs-lookup"><span data-stu-id="278b6-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="278b6-p102">Expanda **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos** \> configure las opciones como quiera. La opción **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** está **desactivada** de forma predeterminada, pero se recomienda que la **active** y acepte los valores predeterminados. Vea [Configuración disponible](protection-settings-for-windows-10-devices.md#bkmk_settings) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="278b6-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="278b6-118">Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="278b6-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="278b6-119">Expanda la opción **Recuperar datos en dispositivos Windows** y se recomienda que la **active**.</span><span class="sxs-lookup"><span data-stu-id="278b6-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="278b6-p103">Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, vea [Crear y comprobar un certificado del Agente de recuperación de datos (DRA) del Sistema de cifrado de archivos (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="278b6-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="278b6-p104">De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado. El certificado del agente de recuperación de datos (ARD) puede ser utilizado por un administrador para descifrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="278b6-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="278b6-p105">Expanda la opción **Proteger otras ubicaciones de red y nube** si quiere agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones de la lista están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos.</span><span class="sxs-lookup"><span data-stu-id="278b6-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="278b6-p106">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="278b6-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="278b6-132">Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="278b6-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="278b6-133">Configuración disponible</span><span class="sxs-lookup"><span data-stu-id="278b6-133">Available settings</span></span>

<span data-ttu-id="278b6-134">La siguiente configuración está disponible para administrar la forma de obtener acceso a archivos de trabajo de Office.</span><span class="sxs-lookup"><span data-stu-id="278b6-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="278b6-135">Para obtener más información, consulte [Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="278b6-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="278b6-136">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="278b6-136">**Setting**</span></span>|<span data-ttu-id="278b6-137">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="278b6-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="278b6-138">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="278b6-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="278b6-139">Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="278b6-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="278b6-140">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="278b6-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="278b6-141">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="278b6-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="278b6-142">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="278b6-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="278b6-143">Esta configuración determina el tiempo que un usuario puede estar inactivo antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="278b6-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

