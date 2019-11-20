---
title: Validar la configuración de protección de aplicaciones en dispositivos Android o iOS
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 3879084b42e8c00cc4abcd86c1a3d6761c0697a6
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718907"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="90aa8-103">Validar la configuración de protección de aplicaciones en dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="90aa8-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="90aa8-104">Siga las instrucciones de las siguientes secciones para validar la configuración de protección de aplicaciones en dispositivos Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="90aa8-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="90aa8-105">Android</span><span class="sxs-lookup"><span data-stu-id="90aa8-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="90aa8-106">Comprobar que la configuración de protección de aplicaciones está funcionando en dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="90aa8-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="90aa8-107">Después de [establecer las configuraciones de la aplicación para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger las aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona.</span><span class="sxs-lookup"><span data-stu-id="90aa8-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="90aa8-108">En primer lugar, asegúrese de que la Directiva se aplica a la aplicación en la que va a validarla.</span><span class="sxs-lookup"><span data-stu-id="90aa8-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="90aa8-109">En el [centro de administración](https://portal.office.com) de Microsoft 365 Business, vaya a **Directivas** \> **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-109">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="90aa8-110">Elija **Directiva de aplicación para Android** para la configuración que creó durante la instalación o cualquier otra directiva que haya creado y compruebe que se aplica a Outlook, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="90aa8-112">Validar la opción Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="90aa8-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="90aa8-113">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Asegúrese de que la necesidad de tener un PIN o una huella digital para acceder a las aplicaciones de Office se establece en activado.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="90aa8-115">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="90aa8-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="90aa8-116">También se le pedirá que escriba un PIN o use una huella digital.</span><span class="sxs-lookup"><span data-stu-id="90aa8-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="90aa8-118">Validar la opción Restablecer el PIN después del número de intentos fallidos indicado</span><span class="sxs-lookup"><span data-stu-id="90aa8-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="90aa8-119">En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que la opción **restablecer PIN tras número de intentos erróneos** esté establecida en un número determinado.</span><span class="sxs-lookup"><span data-stu-id="90aa8-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="90aa8-120">Es 5 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90aa8-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="90aa8-121">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="90aa8-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="90aa8-122">Escriba un PIN incorrecto tantas veces como haya especificado en la directiva.</span><span class="sxs-lookup"><span data-stu-id="90aa8-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="90aa8-123">Verá un mensaje que indica que se ha **alcanzado el límite de intentos de PIN** para restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="90aa8-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="90aa8-125">Pulse **Restablecer PIN**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-125">Press **Reset PIN**.</span></span> <span data-ttu-id="90aa8-126">Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Business del usuario y, a continuación, que sea necesario para establecer un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="90aa8-126">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="90aa8-127">Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="90aa8-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="90aa8-128">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="90aa8-130">En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="90aa8-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="90aa8-131">Abra un correo electrónico que contenga un archivo adjunto y pulse el icono de flecha abajo situado junto a la información del archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="90aa8-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="90aa8-133">Verá **no se puede guardar en el dispositivo** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="90aa8-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="90aa8-135">Guardar en OneDrive para la Empresa no está habilitado para Android en este momento, por lo que solo puede ver que la opción de guardar de forma local está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="90aa8-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="90aa8-136">Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="90aa8-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="90aa8-137">En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que **requerir que los usuarios vuelvan a iniciar sesión después de que las aplicaciones de Office hayan estado inactivos** se haya establecido en un número de minutos.</span><span class="sxs-lookup"><span data-stu-id="90aa8-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="90aa8-138">Este valor predeterminado es de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="90aa8-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="90aa8-139">En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="90aa8-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="90aa8-p105">Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo Android durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="90aa8-143">Vuelva a obtener acceso a Outlook en el dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="90aa8-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="90aa8-144">Se le pedirá que escriba el PIN para poder acceder a Outlook de nuevo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="90aa8-145">Validar la opción Proteger los archivos de trabajo mediante cifrado</span><span class="sxs-lookup"><span data-stu-id="90aa8-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="90aa8-146">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="90aa8-147">En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="90aa8-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="90aa8-148">Abra un correo electrónico que contenga algunos archivos adjuntos de imagen.</span><span class="sxs-lookup"><span data-stu-id="90aa8-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="90aa8-149">Pulse el icono de flecha abajo situado junto a la información del archivo adjunto para guardarlo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="90aa8-p106">Es posible que se le pida que permita a Outlook obtener acceso a fotos, multimedia y archivos del dispositivo. Pulse **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="90aa8-153">En la parte inferior de la pantalla, elija a **Guardar en el dispositivo** y abra la aplicación **Galería**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="90aa8-p107">Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) en la lista. Puede aparecer en la lista Imágenes como un cuadrado gris con un signo de exclamación blanco dentro de un círculo blanco en el centro del cuadrado gris.</span><span class="sxs-lookup"><span data-stu-id="90aa8-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="90aa8-157">iOS</span><span class="sxs-lookup"><span data-stu-id="90aa8-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="90aa8-158">Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="90aa8-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="90aa8-159">Después de [establecer las configuraciones de la aplicación para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona.</span><span class="sxs-lookup"><span data-stu-id="90aa8-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="90aa8-160">En primer lugar, asegúrese de que la Directiva se aplica a la aplicación en la que va a validarla.</span><span class="sxs-lookup"><span data-stu-id="90aa8-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="90aa8-161">En el [centro de administración](https://portal.office.com) de Microsoft 365 Business, vaya a **Directivas** \> **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-161">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="90aa8-162">Elija **Directiva de aplicación para iOS** para la configuración que ha creado en la configuración o cualquier otra directiva que haya creado y compruebe que se aplica a Outlook, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="90aa8-164">Validar la opción Requerir un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="90aa8-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="90aa8-165">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Asegúrese de que la necesidad de tener un PIN o una huella digital para acceder a las aplicaciones de Office se establece en activado.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="90aa8-167">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="90aa8-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="90aa8-168">También se le pedirá que escriba un PIN o use una huella digital.</span><span class="sxs-lookup"><span data-stu-id="90aa8-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="90aa8-170">Validar la opción Restablecer el PIN después del número de intentos fallidos indicado</span><span class="sxs-lookup"><span data-stu-id="90aa8-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="90aa8-171">En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que la opción **restablecer PIN tras número de intentos erróneos** esté establecida en un número determinado.</span><span class="sxs-lookup"><span data-stu-id="90aa8-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="90aa8-172">Es 5 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90aa8-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="90aa8-173">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="90aa8-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="90aa8-174">Escriba un PIN incorrecto tantas veces como haya especificado en la directiva.</span><span class="sxs-lookup"><span data-stu-id="90aa8-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="90aa8-175">Verá un mensaje que indica que se ha **alcanzado el límite de intentos de PIN** para restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="90aa8-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="90aa8-177">Pulse **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-177">Press **OK**.</span></span> <span data-ttu-id="90aa8-178">Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Business del usuario y, a continuación, que sea necesario para establecer un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="90aa8-178">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="90aa8-179">Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="90aa8-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="90aa8-180">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="90aa8-182">En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="90aa8-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="90aa8-183">Abra un correo electrónico que contenga un archivo adjunto, abra ese archivo adjunto y elija **Guardar** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="90aa8-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="90aa8-185">Solo debería ver una opción para OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="90aa8-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="90aa8-186">Si no es así, pulse **Agregar cuenta** y seleccione **OneDrive para la empresa** en la pantalla **Agregar cuenta de almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="90aa8-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="90aa8-187">Proporcione el Microsoft 365 Business del usuario final para iniciar sesión cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="90aa8-187">Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="90aa8-188">Pulse **Guardar** y seleccione **OneDrive para la Empresa**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="90aa8-189">Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="90aa8-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="90aa8-190">En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que **requerir que los usuarios vuelvan a iniciar sesión después de que las aplicaciones de Office hayan estado inactivos** se haya establecido en un número de minutos.</span><span class="sxs-lookup"><span data-stu-id="90aa8-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="90aa8-191">Este valor predeterminado es de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="90aa8-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="90aa8-192">En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="90aa8-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="90aa8-p113">Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo iOS durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="90aa8-196">Vuelva a obtener acceso a Outlook en el dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="90aa8-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="90aa8-197">Se le pedirá que escriba el PIN para poder acceder a Outlook de nuevo.</span><span class="sxs-lookup"><span data-stu-id="90aa8-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="90aa8-198">Validar la opción Proteger los archivos de trabajo mediante cifrado</span><span class="sxs-lookup"><span data-stu-id="90aa8-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="90aa8-199">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="90aa8-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="90aa8-200">En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="90aa8-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="90aa8-201">Abra un correo electrónico que contenga algunos archivos adjuntos de imagen.</span><span class="sxs-lookup"><span data-stu-id="90aa8-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="90aa8-202">Pulse el archivo adjunto y, después, pulse la opción **Guardar** debajo de él.</span><span class="sxs-lookup"><span data-stu-id="90aa8-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="90aa8-p114">Abra la aplicación **Fotos** desde la pantalla principal. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) guardada, pero cifrada.</span><span class="sxs-lookup"><span data-stu-id="90aa8-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

