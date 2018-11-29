---
title: Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Obtenga información sobre cómo crear, editar o eliminar una directiva de administración de la aplicación y proteger archivos de trabajo en dispositivos Android o iOS.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871729"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="dc3f0-103">Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="dc3f0-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="dc3f0-104">Crear una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dc3f0-104">Create an app management policy</span></span>

1. <span data-ttu-id="dc3f0-105">Inicie sesión en [Microsoft 365 Business](https://portal.office.com) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="dc3f0-106">En el centro de administración, en la tarjeta **Directivas de dispositivos**, seleccione **Agregar directiva**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="dc3f0-108">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="dc3f0-109">En **Tipo de directiva**, elija **Administración de aplicaciones para Android** o **Administración de aplicaciones para iOS** según el conjunto de directivas que quiera crear.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="dc3f0-p101">Expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y **Administrar la forma en la que los usuarios tienen acceso a los archivos de Office en dispositivos móviles** \> configure las opciones como quiera. La opción **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** está **desactivada** de forma predeterminada, pero se recomienda que la **active** y acepte los valores predeterminados. Vea [Configuración disponible](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="dc3f0-113">Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="dc3f0-p102">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="dc3f0-117">Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="dc3f0-118">Editar una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dc3f0-118">Edit an app management policy</span></span>

1. <span data-ttu-id="dc3f0-119">En la ficha **directivas** , elija **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="dc3f0-120">En el panel **Editar directiva**, seleccione la directiva que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="dc3f0-p103">Elija **Editar** junto a cada configuración para cambiar los valores de la directiva. Cuando cambia un valor, se guarda automáticamente en la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="dc3f0-123">Cuando haya terminado, cierre el panel **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="dc3f0-124">Eliminar una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dc3f0-124">Delete an app management policy</span></span>

1. <span data-ttu-id="dc3f0-125">En la tarjeta **Directivas**, seleccione **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="dc3f0-126">En el panel **Eliminar directiva**, elija las directivas que quiere eliminar \> **Seleccionar** y después **Confirmar** para eliminar la directiva o las directivas que haya elegido.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="dc3f0-127">Configuración disponible</span><span class="sxs-lookup"><span data-stu-id="dc3f0-127">Available settings</span></span>

<span data-ttu-id="dc3f0-128">En las siguientes tablas, se ofrece información detallada sobre la configuración disponible para proteger los archivos de trabajo en dispositivos y la configuración que controla la forma en que los usuarios obtienen acceso a archivos de Office desde sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="dc3f0-129">Consulte [Cómo se asignan las características de protección de Microsoft 365 Empresa a la configuración de Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f0-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="dc3f0-130">Configuración que protegen los archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dc3f0-130">Settings that protect work files</span></span>

<span data-ttu-id="dc3f0-131">Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:</span><span class="sxs-lookup"><span data-stu-id="dc3f0-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc3f0-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="dc3f0-132">Setting</span></span>  <br/> |<span data-ttu-id="dc3f0-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc3f0-133">Description</span></span>  <br/> |
|<span data-ttu-id="dc3f0-134">Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días</span><span class="sxs-lookup"><span data-stu-id="dc3f0-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="dc3f0-135">Si un dispositivo no se usa durante el número de días que especifique aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="dc3f0-136">Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="dc3f0-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="dc3f0-137">Si esta configuración está **activada**, la única ubicación de almacenamiento disponible para los archivos de trabajo será OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="dc3f0-138">Cifrar los archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dc3f0-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="dc3f0-p104">Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo. Incluso si el dispositivo se pierde o lo roban, nadie podrá leer los datos de la compañía.  </span><span class="sxs-lookup"><span data-stu-id="dc3f0-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="dc3f0-141">Configuraciones que controlan la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="dc3f0-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="dc3f0-142">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="dc3f0-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc3f0-143">Configuración</span><span class="sxs-lookup"><span data-stu-id="dc3f0-143">Setting</span></span>  <br/> |<span data-ttu-id="dc3f0-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc3f0-144">Description</span></span>  <br/> |
|<span data-ttu-id="dc3f0-145">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="dc3f0-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="dc3f0-146">Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="dc3f0-147">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="dc3f0-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="dc3f0-148">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="dc3f0-149">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="dc3f0-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="dc3f0-150">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="dc3f0-151">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="dc3f0-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="dc3f0-p105">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  </span><span class="sxs-lookup"><span data-stu-id="dc3f0-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="dc3f0-155">Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="dc3f0-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="dc3f0-p106">Permitir esto de forma predeterminada, pero si la opción está **activada**, el usuario puede copiar información en un archivo de trabajo a un archivo personal. Si la configuración está **desactivada**, el usuario estará no se puede copiar información desde una cuenta de trabajo en una aplicación de personal o el personal de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="dc3f0-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

