---
title: Borrar un dispositivo móvil en movilidad y seguridad básicas
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
description: Usa la movilidad y seguridad básicas integradas para quitar información de los dispositivos inscritos.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876833"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="c482b-103">Borrar un dispositivo móvil en movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="c482b-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="c482b-104">Puede usar la movilidad básica y la seguridad integradas de Microsoft 365 para quitar solo la información de la organización o realizar un restablecimiento de fábrica para eliminar toda la información de un dispositivo móvil y restaurarla a la configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="c482b-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c482b-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c482b-105">Before you begin</span></span>

<span data-ttu-id="c482b-106">Los dispositivos móviles pueden almacenar información confidencial de la organización y proporcionar acceso a los recursos de Microsoft 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="c482b-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="c482b-107">Para ayudar a proteger la información de su organización, puede realizar un restablecimiento de fábrica o quitar los datos de la empresa:</span><span class="sxs-lookup"><span data-stu-id="c482b-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="c482b-108">**Restablecimiento de** fábrica: elimina todos los datos del dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, las fotos y la información personal.</span><span class="sxs-lookup"><span data-stu-id="c482b-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="c482b-109">Una vez completada la eliminación, el dispositivo se restaura a su configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="c482b-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="c482b-110">**Quitar datos de la** empresa: quita solo los datos de la organización y deja las aplicaciones instaladas, las fotos y la información personal en el dispositivo móvil de un usuario.</span><span class="sxs-lookup"><span data-stu-id="c482b-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="c482b-111">**Cuando se elimina un dispositivo (Restablecimiento** de fábrica o Quitar datos de la compañía), el dispositivo se quita de la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="c482b-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="c482b-112">**Restablecer automáticamente** un dispositivo: puedes configurar una directiva básica de movilidad y seguridad que restablece automáticamente un dispositivo de fábrica después de que el usuario intente introducir la contraseña del dispositivo un número específico de veces.</span><span class="sxs-lookup"><span data-stu-id="c482b-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="c482b-113">Para ello, siga los pasos descritos en [Crear directivas de seguridad de dispositivos en movilidad y seguridad básicas.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c482b-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="c482b-114">**Si quieres conocer la experiencia del** usuario al borrar su dispositivo, consulta ¿Cuál es el impacto en el usuario y en el   [dispositivo?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="c482b-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="c482b-115">Borrar un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="c482b-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="c482b-116">Vaya al Centro [de administración de Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="c482b-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="c482b-117">Escriba Administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles** en la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="c482b-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opción básica de administración de dispositivos móviles de movilidad y secruidad":::

3. <span data-ttu-id="c482b-119">Seleccione **Administrar dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="c482b-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="c482b-120">Seleccione el dispositivo que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="c482b-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="c482b-121">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="c482b-121">Select **Manage**.</span></span>

6. <span data-ttu-id="c482b-122">Seleccione el tipo de eliminación remota que desea realizar.</span><span class="sxs-lookup"><span data-stu-id="c482b-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="c482b-123">Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, selecciona **Restablecimiento de fábrica.**</span><span class="sxs-lookup"><span data-stu-id="c482b-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="c482b-124">Para realizar una eliminación selectiva y eliminar solo la información de la organización de Microsoft 365, seleccione **Quitar datos de la empresa.**</span><span class="sxs-lookup"><span data-stu-id="c482b-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="c482b-125">Para quitar el dispositivo de la organización, seleccione **Quitar dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="c482b-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="c482b-126">Seleccione **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="c482b-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="c482b-127">¿Cómo sé que ha funcionado?</span><span class="sxs-lookup"><span data-stu-id="c482b-127">How do I know it worked?</span></span>

<span data-ttu-id="c482b-128">Ya no verá el dispositivo móvil en la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="c482b-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="c482b-129">¿Por qué quieres borrar un dispositivo?</span><span class="sxs-lookup"><span data-stu-id="c482b-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="c482b-130">Borre un dispositivo por estos motivos:</span><span class="sxs-lookup"><span data-stu-id="c482b-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="c482b-131">Los dispositivos móviles, como smartphones y tabletas, están cada vez más completos.</span><span class="sxs-lookup"><span data-stu-id="c482b-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="c482b-132">Esto significa que es más fácil para los usuarios almacenar información corporativa confidencial como identificación personal o comunicaciones confidenciales y acceder a ella sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="c482b-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="c482b-133">Si se pierde o se roba uno de estos dispositivos móviles, borrar el dispositivo puede ayudar a evitar que la información de la organización termine en manos equivocadas.</span><span class="sxs-lookup"><span data-stu-id="c482b-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="c482b-134">Cuando un usuario abandona la organización con un dispositivo personal inscrito en Movilidad y Seguridad básica, puede ayudar a evitar que la información de la organización vaya con ese usuario realizando un restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="c482b-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="c482b-135">Si su organización proporciona dispositivos móviles a los usuarios, es posible que deba reasignar dispositivos de vez en cuando.</span><span class="sxs-lookup"><span data-stu-id="c482b-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="c482b-136">Realizar un restablecimiento de fábrica en un dispositivo antes de asignarlo a un nuevo usuario ayuda a garantizar que se elimine cualquier información confidencial del propietario anterior.</span><span class="sxs-lookup"><span data-stu-id="c482b-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="c482b-137">¿Cuál es el impacto en el usuario y el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="c482b-137">What's the user and device impact?</span></span>

<span data-ttu-id="c482b-138">La eliminación se envía inmediatamente al dispositivo móvil y el dispositivo se marca como no compatible en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c482b-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="c482b-139">Aunque todos los datos se quitan cuando un dispositivo se restablece a los valores predeterminados de fábrica, en la tabla siguiente se describe qué contenido se quita para cada tipo de dispositivo cuando se quitan los datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="c482b-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="c482b-140">**Impaciación de contenido**</span><span class="sxs-lookup"><span data-stu-id="c482b-140">**Content impace**</span></span>|<span data-ttu-id="c482b-141">**iOS 10 y versiones posteriores**</span><span class="sxs-lookup"><span data-stu-id="c482b-141">**iOS 10 and later**</span></span>|<span data-ttu-id="c482b-142">**Android 5 y versiones posteriores**</span><span class="sxs-lookup"><span data-stu-id="c482b-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c482b-143">Los datos de la aplicación de Microsoft 365 se borran si el dispositivo está protegido por directivas de Intune App Protection.</span><span class="sxs-lookup"><span data-stu-id="c482b-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="c482b-144">Las aplicaciones no se quitan.</span><span class="sxs-lookup"><span data-stu-id="c482b-144">The apps aren't removed.</span></span> <span data-ttu-id="c482b-145">En el caso de dispositivos no protegidos por directivas de administración de aplicaciones móviles (MAM), Outlook y OneDrive no quitarán los datos almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="c482b-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="c482b-146">**Nota** Para aplicar directivas de Protección de aplicaciones de Intune, debes tener una licencia de Intune.</span><span class="sxs-lookup"><span data-stu-id="c482b-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="c482b-147">Sí</span><span class="sxs-lookup"><span data-stu-id="c482b-147">Yes</span></span>|<span data-ttu-id="c482b-148">Sí</span><span class="sxs-lookup"><span data-stu-id="c482b-148">Yes</span></span>|
|<span data-ttu-id="c482b-149">La configuración de directiva aplicada por movilidad básica y seguridad a los dispositivos ya no se aplica; los usuarios pueden cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c482b-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="c482b-150">Sí</span><span class="sxs-lookup"><span data-stu-id="c482b-150">Yes</span></span>|<span data-ttu-id="c482b-151">Sí</span><span class="sxs-lookup"><span data-stu-id="c482b-151">Yes</span></span>|
|<span data-ttu-id="c482b-152">Los perfiles de correo electrónico creados por Movilidad y seguridad básicas se quitan y se elimina el correo electrónico almacenado en caché en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c482b-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="c482b-153">Sí</span><span class="sxs-lookup"><span data-stu-id="c482b-153">Yes</span></span>|<span data-ttu-id="c482b-154">N/D</span><span class="sxs-lookup"><span data-stu-id="c482b-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="c482b-155">La aplicación Portal de empresa está disponible en la App Store para iOS y la Play Store para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="c482b-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c482b-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c482b-156">Related topics</span></span>

[<span data-ttu-id="c482b-157">Configurar la Seguridad de Movilidad Básica</span><span class="sxs-lookup"><span data-stu-id="c482b-157">Set up Basic Mobility and Security</span></span>](set-up.md)