---
title: Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Obtenga información sobre cómo crear, editar o eliminar una directiva de administración de aplicaciones y proteger los archivos de trabajo en dispositivos Android o iOS.
ms.openlocfilehash: 01c50e6660d8d8640a2bff2794ee0ea8a69188c8
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401062"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="f93a3-103">Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="f93a3-103">Set app protection settings for Android or iOS devices</span></span>

![Pancarta que apunta a https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="f93a3-105">Crear una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f93a3-105">Create an app management policy</span></span>

1. <span data-ttu-id="f93a3-106">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f93a3-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="f93a3-107">En el panel de navegación izquierdo **Devices** , elija \> **Policies** \> **Agregar**directivas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f93a3-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="f93a3-108">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="f93a3-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="f93a3-109">En **tipo de directiva**, elija **Administración de aplicaciones para Android** o **Administración de aplicaciones para iOS**, en función del conjunto de directivas que quiera crear.</span><span class="sxs-lookup"><span data-stu-id="f93a3-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="f93a3-110">Expanda **proteger archivos de trabajo cuando se pierdan o se roben dispositivos** y **administre la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**.</span><span class="sxs-lookup"><span data-stu-id="f93a3-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="f93a3-111">Configure las opciones como desee.</span><span class="sxs-lookup"><span data-stu-id="f93a3-111">Configure the settings how you would like.</span></span> <span data-ttu-id="f93a3-112">**Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** está **desactivada** de forma predeterminada, pero le recomendamos que la **Active y acepte** los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f93a3-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="f93a3-113">Para obtener más información, consulte [configuración disponible](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="f93a3-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="f93a3-114">Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f93a3-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="f93a3-116">Después, decida **a qué usuarios se aplica esta configuración**.</span><span class="sxs-lookup"><span data-stu-id="f93a3-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="f93a3-117">Si no desea usar el grupo de seguridad predeterminado **todos los usuarios** , elija **cambiar**, seleccione los grupos de seguridad que se \> **seleccionan**.</span><span class="sxs-lookup"><span data-stu-id="f93a3-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="f93a3-118">Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f93a3-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="f93a3-119">Editar una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f93a3-119">Edit an app management policy</span></span>

1. <span data-ttu-id="f93a3-120">En la tarjeta **directivas** , elija **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="f93a3-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="f93a3-121">En el panel **Editar directiva**, seleccione la directiva que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="f93a3-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="f93a3-122">Elija **Editar** junto a cada configuración para cambiar los valores de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f93a3-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="f93a3-123">Cuando se cambia un valor, se guarda automáticamente en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f93a3-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="f93a3-124">Cuando haya terminado, cierre el panel **Editar Directiva** .</span><span class="sxs-lookup"><span data-stu-id="f93a3-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="f93a3-125">Eliminar una directiva de administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f93a3-125">Delete an app management policy</span></span>

1. <span data-ttu-id="f93a3-126">En la página **directivas** , elija una directiva y, a continuación, **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f93a3-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="f93a3-127">En el panel **eliminar Directiva** , elija **confirmar** para eliminar la Directiva o las directivas que ha elegido.</span><span class="sxs-lookup"><span data-stu-id="f93a3-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="f93a3-128">Configuración disponible</span><span class="sxs-lookup"><span data-stu-id="f93a3-128">Available settings</span></span>

<span data-ttu-id="f93a3-129">En las siguientes tablas se proporciona información detallada sobre la configuración disponible para proteger los archivos de trabajo en los dispositivos y la configuración que controla la forma en que los usuarios obtienen acceso a los archivos de Office desde sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="f93a3-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="f93a3-130">Para obtener más información, vea [cómo se asignan las características de protección de Microsoft 365 empresa Premium a la configuración de Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f93a3-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="f93a3-131">Opciones de configuración que protegen los archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f93a3-131">Settings that protect work files</span></span>

<span data-ttu-id="f93a3-132">Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:</span><span class="sxs-lookup"><span data-stu-id="f93a3-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f93a3-133">Configuración</span><span class="sxs-lookup"><span data-stu-id="f93a3-133">Setting</span></span>  <br/> |<span data-ttu-id="f93a3-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="f93a3-134">Description</span></span>  <br/> |
|<span data-ttu-id="f93a3-135">Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días</span><span class="sxs-lookup"><span data-stu-id="f93a3-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="f93a3-136">Si un dispositivo no se usa durante el número de días que especifique aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f93a3-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="f93a3-137">Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="f93a3-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="f93a3-138">Si esta configuración está **activada**, la única ubicación de guardado disponible para los archivos de trabajo es OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="f93a3-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="f93a3-139">Cifrar los archivos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f93a3-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="f93a3-140">Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f93a3-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="f93a3-141">Incluso si el dispositivo se pierde o es robado, nadie puede leer los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="f93a3-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="f93a3-142">Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="f93a3-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="f93a3-143">Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:</span><span class="sxs-lookup"><span data-stu-id="f93a3-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f93a3-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="f93a3-144">Setting</span></span>  <br/> |<span data-ttu-id="f93a3-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="f93a3-145">Description</span></span>  <br/> |
|<span data-ttu-id="f93a3-146">Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="f93a3-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="f93a3-147">Si esta configuración está **activada** , los usuarios deben proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar las aplicaciones de Office en sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="f93a3-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="f93a3-148">Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces</span><span class="sxs-lookup"><span data-stu-id="f93a3-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="f93a3-149">Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.</span><span class="sxs-lookup"><span data-stu-id="f93a3-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="f93a3-150">Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante</span><span class="sxs-lookup"><span data-stu-id="f93a3-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="f93a3-151">Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="f93a3-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="f93a3-152">Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting</span><span class="sxs-lookup"><span data-stu-id="f93a3-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="f93a3-p105">Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  </span><span class="sxs-lookup"><span data-stu-id="f93a3-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="f93a3-156">No permitir a los usuarios copiar contenido de las aplicaciones de Office en aplicaciones personales</span><span class="sxs-lookup"><span data-stu-id="f93a3-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="f93a3-157">Se permite de manera predeterminada, pero si la configuración está **activada**, el usuario podría copiar información de un archivo de trabajo en uno personal.</span><span class="sxs-lookup"><span data-stu-id="f93a3-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="f93a3-158">Si la configuración está **desactivada**, el usuario no podrá copiar información de una cuenta de trabajo a una aplicación o cuenta personales.</span><span class="sxs-lookup"><span data-stu-id="f93a3-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
