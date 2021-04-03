---
title: Validar la configuración de protección de aplicaciones en dispositivos Android o iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Obtén información sobre cómo validar la configuración de protección de aplicaciones de Microsoft 365 Empresa Premium en tus dispositivos Android o iOS.
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578075"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="113ff-103">Validar la configuración de protección de aplicaciones en dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="113ff-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="113ff-104">Siga las instrucciones de las secciones siguientes para validar la configuración de protección de aplicaciones en dispositivos Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="113ff-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="113ff-105">Android</span><span class="sxs-lookup"><span data-stu-id="113ff-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="113ff-106">Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="113ff-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="113ff-107">Después de [establecer las configuraciones de la aplicación para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger las aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona.</span><span class="sxs-lookup"><span data-stu-id="113ff-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="113ff-108">En primer lugar, asegúrate de que la directiva se aplica a la aplicación en la que vas a validarla.</span><span class="sxs-lookup"><span data-stu-id="113ff-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="113ff-109">En el Centro de administración de Microsoft 365 Empresa [Premium,](https://portal.office.com)vaya a **Directiva** \> **de edición de directivas.**</span><span class="sxs-lookup"><span data-stu-id="113ff-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="113ff-110">Elija **Directiva de aplicación para Android** para la configuración que creó en el programa de instalación u otra directiva que creó y compruebe que se aplica para Outlook, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="113ff-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="113ff-112">Validar la opción Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="113ff-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="113ff-113">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="113ff-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Asegúrese de que requerir un PIN o huella digital para tener acceso a las aplicaciones de Office está establecido en On.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="113ff-115">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.</span><span class="sxs-lookup"><span data-stu-id="113ff-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="113ff-116">También se le pedirá que escriba un PIN o use una huella digital.</span><span class="sxs-lookup"><span data-stu-id="113ff-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="113ff-118">Validar la opción Restablecer el PIN después del número de intentos fallidos indicado</span><span class="sxs-lookup"><span data-stu-id="113ff-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="113ff-119">En el **panel** Editar  directiva, elija Editar junto al control de acceso de documentos de **Office,** expanda Administrar cómo los usuarios acceden a los archivos de **Office** en dispositivos móviles y asegúrese de que restablecer el **PIN** después del número de intentos fallidos esté establecido en algún número.</span><span class="sxs-lookup"><span data-stu-id="113ff-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="113ff-120">Esto es 5 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="113ff-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="113ff-121">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.</span><span class="sxs-lookup"><span data-stu-id="113ff-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="113ff-122">Escriba un PIN incorrecto tantas veces como haya especificado en la directiva.</span><span class="sxs-lookup"><span data-stu-id="113ff-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="113ff-123">Verá un mensaje que indica el límite **de intento de PIN alcanzado** para restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="113ff-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="113ff-125">Pulse **Restablecer PIN**.</span><span class="sxs-lookup"><span data-stu-id="113ff-125">Press **Reset PIN**.</span></span> <span data-ttu-id="113ff-126">Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y, a continuación, se le pedirá que establezca un NUEVO PIN.</span><span class="sxs-lookup"><span data-stu-id="113ff-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="113ff-127">Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="113ff-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="113ff-128">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="113ff-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="113ff-130">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.</span><span class="sxs-lookup"><span data-stu-id="113ff-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="113ff-131">Abra un correo electrónico que contenga un archivo adjunto y pulse el icono de flecha abajo situado junto a la información del archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="113ff-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="113ff-133">Verás No se **puede guardar en el dispositivo** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="113ff-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="113ff-135">Guardar en OneDrive para la Empresa no está habilitado para Android en este momento, por lo que solo puede ver que la opción de guardar de forma local está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="113ff-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="113ff-136">Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="113ff-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="113ff-137">En  el panel Editar  directiva, elija Editar junto al control de acceso de documentos de **Office,** expanda Administrar cómo los usuarios tienen acceso a los archivos de **Office** en dispositivos móviles y asegúrese de que Requerir que los usuarios inicien sesión de nuevo después de que las aplicaciones de **Office** hayan estado inactivas se establezca en un número de minutos.</span><span class="sxs-lookup"><span data-stu-id="113ff-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="113ff-138">Esto es 30 minutos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="113ff-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="113ff-139">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.</span><span class="sxs-lookup"><span data-stu-id="113ff-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="113ff-p105">Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo Android durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="113ff-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="113ff-143">Vuelva a tener acceso a Outlook en el dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="113ff-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="113ff-144">Se te pedirá que escribas el PIN antes de poder volver a tener acceso a Outlook.</span><span class="sxs-lookup"><span data-stu-id="113ff-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="113ff-145">Validar la opción Proteger los archivos de trabajo mediante cifrado</span><span class="sxs-lookup"><span data-stu-id="113ff-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="113ff-146">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="113ff-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="113ff-147">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.</span><span class="sxs-lookup"><span data-stu-id="113ff-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="113ff-148">Abra un correo electrónico que contenga algunos datos adjuntos de archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="113ff-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="113ff-149">Pulse el icono de flecha abajo situado junto a la información del archivo adjunto para guardarlo.</span><span class="sxs-lookup"><span data-stu-id="113ff-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="113ff-p106">Es posible que se le pida que permita a Outlook obtener acceso a fotos, multimedia y archivos del dispositivo. Pulse **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="113ff-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="113ff-153">En la parte inferior de la pantalla, elija a **Guardar en el dispositivo** y abra la aplicación **Galería**.</span><span class="sxs-lookup"><span data-stu-id="113ff-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="113ff-p107">Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) en la lista. Puede aparecer en la lista Imágenes como un cuadrado gris con un signo de exclamación blanco dentro de un círculo blanco en el centro del cuadrado gris.</span><span class="sxs-lookup"><span data-stu-id="113ff-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="113ff-157">iOS</span><span class="sxs-lookup"><span data-stu-id="113ff-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="113ff-158">Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="113ff-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="113ff-159">Después de [establecer las configuraciones de la aplicación para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona.</span><span class="sxs-lookup"><span data-stu-id="113ff-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="113ff-160">En primer lugar, asegúrate de que la directiva se aplica a la aplicación en la que vas a validarla.</span><span class="sxs-lookup"><span data-stu-id="113ff-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="113ff-161">En el Centro de administración de Microsoft 365 Empresa [Premium,](https://portal.office.com)vaya a **Directiva** \> **de edición de directivas.**</span><span class="sxs-lookup"><span data-stu-id="113ff-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="113ff-162">Elija **Directiva de aplicación para iOS** para la configuración que creó en el programa de instalación u otra directiva que creó y compruebe que se aplica para Outlook, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="113ff-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="113ff-164">Validar la opción Requerir un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="113ff-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="113ff-165">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="113ff-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Asegúrese de que requerir un PIN o huella digital para tener acceso a las aplicaciones de Office está establecido en On.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="113ff-167">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.</span><span class="sxs-lookup"><span data-stu-id="113ff-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="113ff-168">También se le pedirá que escriba un PIN o use una huella digital.</span><span class="sxs-lookup"><span data-stu-id="113ff-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="113ff-170">Validar la opción Restablecer el PIN después del número de intentos fallidos indicado</span><span class="sxs-lookup"><span data-stu-id="113ff-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="113ff-171">En el **panel** Editar  directiva, elija Editar junto al control de acceso de documentos de **Office,** expanda Administrar cómo los usuarios acceden a los archivos de **Office** en dispositivos móviles y asegúrese de que restablecer el **PIN** después del número de intentos fallidos esté establecido en algún número.</span><span class="sxs-lookup"><span data-stu-id="113ff-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="113ff-172">Esto es 5 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="113ff-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="113ff-173">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.</span><span class="sxs-lookup"><span data-stu-id="113ff-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="113ff-174">Escriba un PIN incorrecto tantas veces como haya especificado en la directiva.</span><span class="sxs-lookup"><span data-stu-id="113ff-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="113ff-175">Verá un mensaje que indica el límite **de intento de PIN alcanzado** para restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="113ff-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="113ff-177">Pulse **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="113ff-177">Press **OK**.</span></span> <span data-ttu-id="113ff-178">Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y, a continuación, se le pedirá que establezca un NUEVO PIN.</span><span class="sxs-lookup"><span data-stu-id="113ff-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="113ff-179">Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="113ff-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="113ff-180">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="113ff-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="113ff-182">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.</span><span class="sxs-lookup"><span data-stu-id="113ff-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="113ff-183">Abra un correo electrónico que contenga un archivo adjunto, abra ese archivo adjunto y elija **Guardar** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="113ff-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="113ff-185">Solo debería ver una opción para OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="113ff-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="113ff-186">Si no es así, pulsa **Agregar cuenta** y **selecciona OneDrive para** la Empresa en la pantalla Agregar cuenta **de** almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="113ff-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="113ff-187">Proporcione a Microsoft 365 Empresa Premium del usuario final que inicie sesión cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="113ff-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="113ff-188">Pulse **Guardar** y seleccione **OneDrive para la Empresa**.</span><span class="sxs-lookup"><span data-stu-id="113ff-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="113ff-189">Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="113ff-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="113ff-190">En  el panel Editar  directiva, elija Editar junto al control de acceso de documentos de **Office,** expanda Administrar cómo los usuarios tienen acceso a los archivos de **Office** en dispositivos móviles y asegúrese de que Requerir que los usuarios inicien sesión de nuevo después de que las aplicaciones de **Office** hayan estado inactivas se establezca en un número de minutos.</span><span class="sxs-lookup"><span data-stu-id="113ff-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="113ff-191">Esto es 30 minutos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="113ff-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="113ff-192">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.</span><span class="sxs-lookup"><span data-stu-id="113ff-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="113ff-p113">Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo iOS durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="113ff-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="113ff-196">Vuelva a tener acceso a Outlook en el dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="113ff-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="113ff-197">Se te pedirá que escribas el PIN antes de poder volver a tener acceso a Outlook.</span><span class="sxs-lookup"><span data-stu-id="113ff-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="113ff-198">Validar la opción Proteger los archivos de trabajo mediante cifrado</span><span class="sxs-lookup"><span data-stu-id="113ff-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="113ff-199">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="113ff-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="113ff-200">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.</span><span class="sxs-lookup"><span data-stu-id="113ff-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="113ff-201">Abra un correo electrónico que contenga algunos datos adjuntos de archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="113ff-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="113ff-202">Pulse el archivo adjunto y, después, pulse la opción **Guardar** debajo de él.</span><span class="sxs-lookup"><span data-stu-id="113ff-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="113ff-p114">Abra la aplicación **Fotos** desde la pantalla principal. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) guardada, pero cifrada.</span><span class="sxs-lookup"><span data-stu-id="113ff-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

