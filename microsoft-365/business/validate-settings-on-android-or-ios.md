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
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Validar la configuración de protección de aplicaciones en dispositivos Android o iOS

Siga las instrucciones de las siguientes secciones para validar la configuración de protección de aplicaciones en dispositivos Android o iOS.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Comprobar que la configuración de protección de aplicaciones está funcionando en dispositivos de usuario

Después de [establecer las configuraciones de la aplicación para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger las aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona. 
  
En primer lugar, asegúrese de que la Directiva se aplica a la aplicación en la que va a validarla.
  
1. En el [centro de administración](https://portal.office.com) de Microsoft 365 Business, vaya a **Directivas** \> **Editar directiva**.
    
2. Elija **Directiva de aplicación para Android** para la configuración que creó durante la instalación o cualquier otra directiva que haya creado y compruebe que se aplica a Outlook, por ejemplo. 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Validar la opción Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office

En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.
  
![Asegúrese de que la necesidad de tener un PIN o una huella digital para acceder a las aplicaciones de Office se establece en activado.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.
    
2. También se le pedirá que escriba un PIN o use una huella digital.
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar la opción Restablecer el PIN después del número de intentos fallidos indicado

En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que la opción **restablecer PIN tras número de intentos erróneos** esté establecida en un número determinado. Es 5 de forma predeterminada. 
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.
    
2. Escriba un PIN incorrecto tantas veces como haya especificado en la directiva. Verá un mensaje que indica que se ha **alcanzado el límite de intentos de PIN** para restablecer el PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Pulse **Restablecer PIN**. Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Business del usuario y, a continuación, que sea necesario para establecer un nuevo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.
    
2. Abra un correo electrónico que contenga un archivo adjunto y pulse el icono de flecha abajo situado junto a la información del archivo adjunto.
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Verá **no se puede guardar en el dispositivo** en la parte inferior de la pantalla. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Guardar en OneDrive para la Empresa no está habilitado para Android en este momento, por lo que solo puede ver que la opción de guardar de forma local está bloqueada. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado

En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que **requerir que los usuarios vuelvan a iniciar sesión después de que las aplicaciones de Office hayan estado inactivos** se haya establecido en un número de minutos. Este valor predeterminado es de 30 minutos. 
  
1. En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.
    
2. Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo Android durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.
    
3. Vuelva a obtener acceso a Outlook en el dispositivo Android.
    
4. Se le pedirá que escriba el PIN para poder acceder a Outlook de nuevo.
    
### <a name="validate-protect-work-files-with-encryption"></a>Validar la opción Proteger los archivos de trabajo mediante cifrado

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.
  
1. En el dispositivo Android del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.
    
2. Abra un correo electrónico que contenga algunos archivos adjuntos de imagen.
    
3. Pulse el icono de flecha abajo situado junto a la información del archivo adjunto para guardarlo.
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Es posible que se le pida que permita a Outlook obtener acceso a fotos, multimedia y archivos del dispositivo. Pulse **Permitir**.
    
5. En la parte inferior de la pantalla, elija a **Guardar en el dispositivo** y abra la aplicación **Galería**. 
    
6. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) en la lista. Puede aparecer en la lista Imágenes como un cuadrado gris con un signo de exclamación blanco dentro de un círculo blanco en el centro del cuadrado gris.
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario

Después de [establecer las configuraciones de la aplicación para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona. 
  
En primer lugar, asegúrese de que la Directiva se aplica a la aplicación en la que va a validarla.
  
1. En el [centro de administración](https://portal.office.com) de Microsoft 365 Business, vaya a **Directivas** \> **Editar directiva**.
    
2. Elija **Directiva de aplicación para iOS** para la configuración que ha creado en la configuración o cualquier otra directiva que haya creado y compruebe que se aplica a Outlook, por ejemplo. 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Validar la opción Requerir un PIN para obtener acceso a las aplicaciones de Office

En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.
  
![Asegúrese de que la necesidad de tener un PIN o una huella digital para acceder a las aplicaciones de Office se establece en activado.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.
    
2. También se le pedirá que escriba un PIN o use una huella digital.
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar la opción Restablecer el PIN después del número de intentos fallidos indicado

En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que la opción **restablecer PIN tras número de intentos erróneos** esté establecida en un número determinado. Es 5 de forma predeterminada. 
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Business del usuario.
    
2. Escriba un PIN incorrecto tantas veces como haya especificado en la directiva. Verá un mensaje que indica que se ha **alcanzado el límite de intentos de PIN** para restablecer el PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Pulse **Aceptar**. Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Business del usuario y, a continuación, que sea necesario para establecer un nuevo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.
    
2. Abra un correo electrónico que contenga un archivo adjunto, abra ese archivo adjunto y elija **Guardar** en la parte inferior de la pantalla. 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Solo debería ver una opción para OneDrive para la Empresa. Si no es así, pulse **Agregar cuenta** y seleccione **OneDrive para la empresa** en la pantalla **Agregar cuenta de almacenamiento** . Proporcione el Microsoft 365 Business del usuario final para iniciar sesión cuando se le pida. 
    
    Pulse **Guardar** y seleccione **OneDrive para la Empresa**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado

En el panel **Editar Directiva** , elija **Editar** junto a **documento de Office control de acceso**, expanda **administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles**y asegúrese de que **requerir que los usuarios vuelvan a iniciar sesión después de que las aplicaciones de Office hayan estado inactivos** se haya establecido en un número de minutos. Este valor predeterminado es de 30 minutos. 
  
1. En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.
    
2. Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo iOS durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.
    
3. Vuelva a obtener acceso a Outlook en el dispositivo iOS.
    
4. Se le pedirá que escriba el PIN para poder acceder a Outlook de nuevo.
    
### <a name="validate-protect-work-files-with-encryption"></a>Validar la opción Proteger los archivos de trabajo mediante cifrado

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.
  
1. En el dispositivo iOS del usuario, abra Outlook, inicie sesión con las credenciales de Microsoft 365 Business del usuario e introduzca el PIN si se le pide.
    
2. Abra un correo electrónico que contenga algunos archivos adjuntos de imagen.
    
3. Pulse el archivo adjunto y, después, pulse la opción **Guardar** debajo de él. 
    
4. Abra la aplicación **Fotos** desde la pantalla principal. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) guardada, pero cifrada. 
    
---

