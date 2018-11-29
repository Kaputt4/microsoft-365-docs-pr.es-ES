---
title: Validar la configuración de protección de aplicación en dispositivos Android o iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: 300f59e81a93cc3dfc03fd1d98891be1ac4f7795
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871737"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="af3ce-103">Validar la configuración de protección de aplicación en dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="af3ce-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="af3ce-104">Siga las instrucciones que aparecen en las fichas para validar la configuración de la protección de aplicación en dispositivos Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="af3ce-104">Follow the instructions in the tabs to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="androidtab"></a>[<span data-ttu-id="af3ce-105">Android</span><span class="sxs-lookup"><span data-stu-id="af3ce-105">Android</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="af3ce-106">Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="af3ce-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="af3ce-107">Después de [establecer las configuraciones de la aplicación para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger las aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona.</span><span class="sxs-lookup"><span data-stu-id="af3ce-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="af3ce-108">En primer lugar, asegúrese de que la directiva se aplica a la aplicación en la que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="af3ce-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="af3ce-109">En el [centro de administración](https://portal.office.com) de Microsoft 365 Business, vaya a **Directivas** \> **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="af3ce-110">Elija la **Directiva de aplicación para Android** de la configuración que ha creado en la configuración o cualquier otra directiva que haya creado y compruebe que se exige en Outlook, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="af3ce-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="af3ce-112">Validar la opción Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="af3ce-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="af3ce-113">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="af3ce-115">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="af3ce-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="af3ce-116">También se le pedirá que especifique un PIN o use una huella digital.</span><span class="sxs-lookup"><span data-stu-id="af3ce-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="af3ce-118">Validar la opción Restablecer el PIN después del número de intentos fallidos indicado</span><span class="sxs-lookup"><span data-stu-id="af3ce-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="af3ce-119">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Restablecer el PIN después del número de intentos fallidos indicado** esté establecido en algún número (el valor predeterminado es 5).</span><span class="sxs-lookup"><span data-stu-id="af3ce-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="af3ce-120">En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="af3ce-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="af3ce-p101">Escriba un PIN incorrecto tantas veces como haya especificado en la directiva. Verá un mensaje que dice **Se ha alcanzado el límite de intentos de PIN** para restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p101">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="af3ce-p102">Pulse **Restablecer PIN**. Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Business del usuario y, después, se le requerirá que establezca un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p102">Press **Reset PIN**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="af3ce-126">Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="af3ce-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="af3ce-127">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="af3ce-129">En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="af3ce-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="af3ce-130">Abra un correo electrónico que contenga un archivo adjunto y pulse el icono de flecha abajo situado junto a la información del archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="af3ce-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="af3ce-132">Verá **No puede guardar en el dispositivo** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="af3ce-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="af3ce-134">Guardar en OneDrive para la Empresa no está habilitado para Android en este momento, por lo que solo puede ver que la opción de guardar de forma local está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="af3ce-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="af3ce-135">Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="af3ce-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="af3ce-136">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante** esté establecido en algún número de minutos (el valor predeterminado es 30 minutos).</span><span class="sxs-lookup"><span data-stu-id="af3ce-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="af3ce-137">En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="af3ce-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="af3ce-p103">Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo Android durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="af3ce-141">Vuelva a obtener acceso a Outlook en el dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="af3ce-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="af3ce-142">Se le pedirá que introduzca el PIN para que pueda volver a obtener acceso a Outlook.</span><span class="sxs-lookup"><span data-stu-id="af3ce-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="af3ce-143">Validar la opción Proteger los archivos de trabajo mediante cifrado</span><span class="sxs-lookup"><span data-stu-id="af3ce-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="af3ce-144">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="af3ce-145">En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="af3ce-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="af3ce-146">Abra un correo electrónico que contenga algunas imágenes adjuntas.</span><span class="sxs-lookup"><span data-stu-id="af3ce-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="af3ce-147">Pulse el icono de flecha abajo situado junto a la información del archivo adjunto para guardarlo.</span><span class="sxs-lookup"><span data-stu-id="af3ce-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="af3ce-p104">Es posible que se le pida que permita a Outlook obtener acceso a fotos, multimedia y archivos del dispositivo. Pulse **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p104">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="af3ce-151">En la parte inferior de la pantalla, elija a **Guardar en el dispositivo** y abra la aplicación **Galería**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="af3ce-p105">Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) en la lista. Puede aparecer en la lista Imágenes como un cuadrado gris con un signo de exclamación blanco dentro de un círculo blanco en el centro del cuadrado gris.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[<span data-ttu-id="af3ce-155">iOS</span><span class="sxs-lookup"><span data-stu-id="af3ce-155">iOS</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="af3ce-156">Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="af3ce-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="af3ce-157">Después de [establecer las configuraciones de la aplicación para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona.</span><span class="sxs-lookup"><span data-stu-id="af3ce-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="af3ce-158">En primer lugar, asegúrese de que la directiva se aplica a la aplicación en la que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="af3ce-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="af3ce-159">En el [centro de administración](https://portal.office.com) de Microsoft 365 Business, vaya a **Directivas** \> **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="af3ce-160">Elija la **Directiva de aplicación para iOS** de la configuración que ha creado en la configuración o cualquier otra directiva que haya creado y compruebe que se exige en Outlook, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="af3ce-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="af3ce-162">Validar la opción Requerir un PIN para obtener acceso a las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="af3ce-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="af3ce-163">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="af3ce-165">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="af3ce-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="af3ce-166">También se le pedirá que especifique un PIN o use una huella digital.</span><span class="sxs-lookup"><span data-stu-id="af3ce-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="af3ce-168">Validar la opción Restablecer el PIN después del número de intentos fallidos indicado</span><span class="sxs-lookup"><span data-stu-id="af3ce-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="af3ce-169">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Restablecer el PIN después del número de intentos fallidos indicado** esté establecido en algún número (el valor predeterminado es 5).</span><span class="sxs-lookup"><span data-stu-id="af3ce-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="af3ce-170">En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.</span><span class="sxs-lookup"><span data-stu-id="af3ce-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="af3ce-p106">Escriba un PIN incorrecto tantas veces como haya especificado en la directiva. Verá un mensaje que dice **Se ha alcanzado el límite de intentos de PIN** para restablecer el PIN.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p106">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="af3ce-p107">Pulse **Aceptar**. Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Business del usuario y, después, se le requerirá que establezca un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p107">Press **OK**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="af3ce-176">Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="af3ce-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="af3ce-177">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="af3ce-179">En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="af3ce-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="af3ce-180">Abra un correo electrónico que contenga un archivo adjunto, abra ese archivo adjunto y elija **Guardar** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="af3ce-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="af3ce-p108">Solo debería ver una opción para OneDrive para la Empresa. Si no es así, pulse **Agregar cuenta** y seleccione **OneDrive para la Empresa** en la pantalla **Agregar cuenta de almacenamiento**. Proporcione el Microsoft 365 Business del usuario final para iniciar sesión cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p108">You should only see an option for OneDrive for Business. If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen. Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="af3ce-185">Pulse **Guardar** y seleccione **OneDrive para la Empresa**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="af3ce-186">Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="af3ce-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="af3ce-187">En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante** esté establecido en algún número de minutos (el valor predeterminado es 30 minutos).</span><span class="sxs-lookup"><span data-stu-id="af3ce-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="af3ce-188">En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="af3ce-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="af3ce-p109">Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo iOS durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="af3ce-192">Vuelva a obtener acceso a Outlook en el dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="af3ce-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="af3ce-193">Se le pedirá que introduzca el PIN para que pueda volver a obtener acceso a Outlook.</span><span class="sxs-lookup"><span data-stu-id="af3ce-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="af3ce-194">Validar la opción Proteger los archivos de trabajo mediante cifrado</span><span class="sxs-lookup"><span data-stu-id="af3ce-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="af3ce-195">En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="af3ce-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="af3ce-196">En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.</span><span class="sxs-lookup"><span data-stu-id="af3ce-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="af3ce-197">Abra un correo electrónico que contenga algunas imágenes adjuntas.</span><span class="sxs-lookup"><span data-stu-id="af3ce-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="af3ce-198">Pulse el archivo adjunto y, después, pulse la opción **Guardar** debajo de él.</span><span class="sxs-lookup"><span data-stu-id="af3ce-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="af3ce-p110">Abra la aplicación **Fotos** desde la pantalla principal. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) guardada, pero cifrada.</span><span class="sxs-lookup"><span data-stu-id="af3ce-p110">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

