---
title: Borrar un dispositivo móvil en la movilidad y la seguridad básicas
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use la movilidad y la seguridad básicas integradas para quitar información de dispositivos inscritos.
ms.openlocfilehash: 4627b0cb2d0963ae724c425a6a7ea6279f271856
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429955"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="8130c-103">Borrar un dispositivo móvil en la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="8130c-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="8130c-104">Puede usar la movilidad básica integrada y la seguridad de Microsoft 365 para quitar la información de la organización, o realizar un restablecimiento de fábrica para eliminar toda la información de un dispositivo móvil y restaurarla a la configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="8130c-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8130c-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8130c-105">Before you begin</span></span>

<span data-ttu-id="8130c-106">Los dispositivos móviles pueden almacenar información de la organización confidencial y proporcionar acceso a los recursos de Microsoft 365 de la organización.</span><span class="sxs-lookup"><span data-stu-id="8130c-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="8130c-107">Para ayudar a proteger la información de su organización, puede restablecer o quitar datos de la compañía:</span><span class="sxs-lookup"><span data-stu-id="8130c-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="8130c-108">**Restablecimiento de fábrica**: elimina todos los datos en el dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, las fotos y la información personal.</span><span class="sxs-lookup"><span data-stu-id="8130c-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="8130c-109">Una vez finalizado el borrado, el dispositivo se restaura a su configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="8130c-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="8130c-110">**Quitar datos**de la compañía: quita solo los datos de la organización y deja las aplicaciones instaladas, las fotos y la información personal en el dispositivo móvil de un usuario.</span><span class="sxs-lookup"><span data-stu-id="8130c-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="8130c-111">**Cuando se borra un dispositivo (restablecimiento de fábrica o eliminación de datos de la empresa)**, el dispositivo se quita de la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="8130c-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="8130c-112">**Restablecer automáticamente un dispositivo**: puede configurar una directiva básica de movilidad y seguridad que Factory restablece automáticamente un dispositivo después de que el usuario no intente escribir la contraseña del dispositivo un número específico de veces.</span><span class="sxs-lookup"><span data-stu-id="8130c-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="8130c-113">Para ello, siga los pasos descritos en [Create Device Security policies in Basic Mobility and Security](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8130c-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="8130c-114">**Si quiere conocer la experiencia del usuario** al borrar el dispositivo, consulte  [¿cuál es el impacto del dispositivo y el usuario?](#whats-the-user-and-device-impact)</span><span class="sxs-lookup"><span data-stu-id="8130c-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="8130c-115">Borrar un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="8130c-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="8130c-116">Vaya al [centro de administración de Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="8130c-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="8130c-117">Escriba administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles** en la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="8130c-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Movilidad básica y opción de administración de dispositivos móviles de secruity":::

3. <span data-ttu-id="8130c-119">Seleccione **administrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8130c-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="8130c-120">Seleccione el dispositivo que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="8130c-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="8130c-121">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="8130c-121">Select **Manage**.</span></span>

6. <span data-ttu-id="8130c-122">Seleccione el tipo de eliminación remota que desea realizar.</span><span class="sxs-lookup"><span data-stu-id="8130c-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="8130c-123">Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, seleccione **restablecimiento de fábrica**.</span><span class="sxs-lookup"><span data-stu-id="8130c-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="8130c-124">Para realizar un borrado selectivo y eliminar solo la información de la organización de Microsoft 365, seleccione **Quitar datos**de la compañía.</span><span class="sxs-lookup"><span data-stu-id="8130c-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="8130c-125">Para quitar el dispositivo de la organización, seleccione **quitar dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8130c-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="8130c-126">Seleccione **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="8130c-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="8130c-127">¿Cómo sé que funcionó?</span><span class="sxs-lookup"><span data-stu-id="8130c-127">How do I know it worked?</span></span>

<span data-ttu-id="8130c-128">Ya no verá el dispositivo móvil en la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="8130c-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="8130c-129">¿Por qué deseas borrar un dispositivo?</span><span class="sxs-lookup"><span data-stu-id="8130c-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="8130c-130">Limpie un dispositivo por estos motivos:</span><span class="sxs-lookup"><span data-stu-id="8130c-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="8130c-131">Los dispositivos móviles, como los smartphones y las tabletas, son cada vez más completos.</span><span class="sxs-lookup"><span data-stu-id="8130c-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="8130c-132">Esto significa que es más fácil para sus usuarios almacenar información confidencial de la empresa, como identificación personal o comunicaciones confidenciales, y tener acceso a ella en el viaje.</span><span class="sxs-lookup"><span data-stu-id="8130c-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="8130c-133">Si se pierde o se roba uno de estos dispositivos móviles, el borrado del dispositivo puede ayudar a evitar que la información de la organización acabe en las manos equivocadas.</span><span class="sxs-lookup"><span data-stu-id="8130c-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="8130c-134">Cuando un usuario deja la organización con un dispositivo personal que está inscrito en la movilidad y la seguridad básicas, puede ayudar a evitar que la información de la organización vaya con ese usuario realizando un restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="8130c-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="8130c-135">Si su organización proporciona dispositivos móviles a los usuarios, es posible que tenga que reasignar los dispositivos de vez en cuando.</span><span class="sxs-lookup"><span data-stu-id="8130c-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="8130c-136">Realizar un restablecimiento de fábrica en un dispositivo antes de asignarlo a un nuevo usuario ayuda a garantizar que se elimina toda la información confidencial del propietario anterior.</span><span class="sxs-lookup"><span data-stu-id="8130c-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="8130c-137">¿Cuál es el impacto de los usuarios y los dispositivos?</span><span class="sxs-lookup"><span data-stu-id="8130c-137">What's the user and device impact?</span></span>

<span data-ttu-id="8130c-138">El barrido se envía inmediatamente al dispositivo móvil y el dispositivo se marca como no compatible en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8130c-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="8130c-139">Mientras se eliminan todos los datos cuando se restablece un dispositivo a los valores predeterminados de fábrica, en la tabla siguiente se describe el contenido que se elimina para cada tipo de dispositivo cuando se quitan datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="8130c-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="8130c-140">**Imvelocidads de contenido**</span><span class="sxs-lookup"><span data-stu-id="8130c-140">**Content impace**</span></span>|<span data-ttu-id="8130c-141">**iOS 10 y versiones posteriores**</span><span class="sxs-lookup"><span data-stu-id="8130c-141">**iOS 10 and later**</span></span>|<span data-ttu-id="8130c-142">**Android 5 y versiones posteriores**</span><span class="sxs-lookup"><span data-stu-id="8130c-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8130c-143">Los datos de la aplicación Microsoft 365 se borran si el dispositivo está protegido por las directivas de protección de aplicaciones de Intune.</span><span class="sxs-lookup"><span data-stu-id="8130c-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="8130c-144">Las aplicaciones no se quitan.</span><span class="sxs-lookup"><span data-stu-id="8130c-144">The apps aren't removed.</span></span> <span data-ttu-id="8130c-145">Para los dispositivos no protegidos por las directivas de administración de aplicaciones móviles (MAM), Outlook y OneDrive no quitarán los datos almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="8130c-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="8130c-146">**Nota:** Para aplicar directivas de protección de aplicaciones de Intune, debe tener una licencia de Intune.</span><span class="sxs-lookup"><span data-stu-id="8130c-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="8130c-147">Sí</span><span class="sxs-lookup"><span data-stu-id="8130c-147">Yes</span></span>|<span data-ttu-id="8130c-148">Sí</span><span class="sxs-lookup"><span data-stu-id="8130c-148">Yes</span></span>|
|<span data-ttu-id="8130c-149">La configuración de la Directiva aplicada por la movilidad básica y la seguridad a los dispositivos ya no se aplican; los usuarios pueden cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="8130c-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="8130c-150">Sí</span><span class="sxs-lookup"><span data-stu-id="8130c-150">Yes</span></span>|<span data-ttu-id="8130c-151">Sí</span><span class="sxs-lookup"><span data-stu-id="8130c-151">Yes</span></span>|
|<span data-ttu-id="8130c-152">Los perfiles de correo electrónico creados por la movilidad básica y la seguridad se eliminan y se elimina el correo electrónico almacenado en caché en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8130c-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="8130c-153">Sí</span><span class="sxs-lookup"><span data-stu-id="8130c-153">Yes</span></span>|<span data-ttu-id="8130c-154">N/D</span><span class="sxs-lookup"><span data-stu-id="8130c-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="8130c-155">La aplicación portal de empresa está disponible en la App Store para iOS y en la tienda de reproducción para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="8130c-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8130c-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8130c-156">Related topics</span></span>

[<span data-ttu-id="8130c-157">Configurar la Seguridad de Movilidad Básica</span><span class="sxs-lookup"><span data-stu-id="8130c-157">Set up Basic Mobility and Security</span></span>](set-up.md)