---
title: Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Obtenga información sobre cómo crear, editar o eliminar una directiva de administración de aplicaciones y proteger los archivos de trabajo en dispositivos Android o iOS.
ms.openlocfilehash: 04479360bf13a8ff685a91ed95440c08f8cf80b4
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660592"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="53a10-103">Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="53a10-103">Set app protection settings for Android or iOS devices</span></span>

![Pancarta que apunta a https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="53a10-105">Crear una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="53a10-105">Create an app management policy</span></span>

1. <span data-ttu-id="53a10-106">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="53a10-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="53a10-107">En el panel de navegación izquierdo, elija **Agregar** **directivas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="53a10-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="53a10-108">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="53a10-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="53a10-109">En **Tipo de directiva**, elija **Administración de aplicaciones para Android** o **Administración de aplicaciones para iOS** según el conjunto de directivas que quiera crear.</span><span class="sxs-lookup"><span data-stu-id="53a10-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="53a10-110">Expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y **Administrar la forma en la que los usuarios tienen acceso a los archivos de Office en dispositivos móviles** \> configure las opciones como quiera.</span><span class="sxs-lookup"><span data-stu-id="53a10-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="53a10-111">La opción **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** está **desactivada** de forma predeterminada, pero se recomienda que la **active** y acepte los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="53a10-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="53a10-112">Vea [available Settings](#available-settings) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="53a10-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="53a10-113">Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="53a10-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="53a10-p102">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="53a10-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="53a10-117">Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="53a10-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="53a10-118">Editar una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="53a10-118">Edit an app management policy</span></span>

1. <span data-ttu-id="53a10-119">En la tarjeta **directivas** , elija **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="53a10-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="53a10-120">En el panel **Editar directiva**, seleccione la directiva que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="53a10-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="53a10-p103">Elija **Editar** junto a cada configuración para cambiar los valores de la directiva. Cuando cambia un valor, se guarda automáticamente en la directiva.</span><span class="sxs-lookup"><span data-stu-id="53a10-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="53a10-123">Cuando haya terminado, cierre el panel **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="53a10-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="53a10-124">Eliminar una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="53a10-124">Delete an app management policy</span></span>

1. <span data-ttu-id="53a10-125">En la página **directivas** , elija una directiva y, a continuación, **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="53a10-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="53a10-126">En el panel **eliminar Directiva** , seleccione **confirmar** para eliminar la Directiva o las directivas que ha elegido.</span><span class="sxs-lookup"><span data-stu-id="53a10-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="53a10-127">Configuración disponible</span><span class="sxs-lookup"><span data-stu-id="53a10-127">Available settings</span></span>

<span data-ttu-id="53a10-128">En las siguientes tablas, se ofrece información detallada sobre la configuración disponible para proteger los archivos de trabajo en dispositivos y la configuración que controla la forma en que los usuarios obtienen acceso a archivos de Office desde sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="53a10-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="53a10-129">Consulte [Cómo se asignan las características de protección de Microsoft 365 Empresa a la configuración de Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="53a10-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="53a10-130">Configuración que protegen los archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="53a10-130">Settings that protect work files</span></span>

<span data-ttu-id="53a10-131">Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:</span><span class="sxs-lookup"><span data-stu-id="53a10-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="53a10-132">Valor</span><span class="sxs-lookup"><span data-stu-id="53a10-132">Setting</span></span>  <br/> |<span data-ttu-id="53a10-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="53a10-133">Description</span></span>  <br/> |
|<span data-ttu-id="53a10-134">Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días</span><span class="sxs-lookup"><span data-stu-id="53a10-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="53a10-135">Si un dispositivo no se usa durante el número de días que especifique aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="53a10-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="53a10-136">Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="53a10-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="53a10-137">Si esta configuración está **activada**, la única ubicación de almacenamiento disponible para los archivos de trabajo será OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="53a10-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="53a10-138">Cifrar los archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="53a10-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="53a10-p104">Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo. Incluso en caso de pérdida o robo del dispositivo, nadie podrá leer los datos de la compañía.  </span><span class="sxs-lookup"><span data-stu-id="53a10-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="53a10-141">Configuraciones que controlan la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="53a10-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="53a10-142">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="53a10-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="53a10-143">Valor</span><span class="sxs-lookup"><span data-stu-id="53a10-143">Setting</span></span>  <br/> |<span data-ttu-id="53a10-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="53a10-144">Description</span></span>  <br/> |
|<span data-ttu-id="53a10-145">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="53a10-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="53a10-146">Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="53a10-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="53a10-147">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="53a10-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="53a10-148">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="53a10-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="53a10-149">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="53a10-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="53a10-150">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="53a10-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="53a10-151">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="53a10-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="53a10-p105">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  </span><span class="sxs-lookup"><span data-stu-id="53a10-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="53a10-155">Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="53a10-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="53a10-156">Se permite de manera predeterminada, pero si la configuración está **activada**, el usuario podría copiar información de un archivo de trabajo en uno personal.</span><span class="sxs-lookup"><span data-stu-id="53a10-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="53a10-157">Si la configuración está **desactivada**, el usuario no podrá copiar información de una cuenta de trabajo a una aplicación o cuenta personales.</span><span class="sxs-lookup"><span data-stu-id="53a10-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

