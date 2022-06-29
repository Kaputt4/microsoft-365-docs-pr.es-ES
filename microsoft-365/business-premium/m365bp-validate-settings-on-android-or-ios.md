---
title: Validación de la configuración de protección de aplicaciones en dispositivos Android o iOS
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: Obtenga información sobre cómo validar la configuración de protección de aplicaciones Microsoft 365 Empresa Premium en los dispositivos Android o iOS. La configuración de seguridad de las aplicaciones es fundamental para proteger los archivos de las aplicaciones móviles y los dispositivos frente a cualquier tipo de amenaza de seguridad.
ms.openlocfilehash: c1a4868b7139735571e4e873fa2ff1a7aff199b1
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489846"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Validación de la configuración de protección de aplicaciones en dispositivos Android o iOS


Siga las instrucciones de las secciones siguientes para validar la configuración de protección de aplicaciones en dispositivos Android o iOS.
  
## <a name="android"></a>[Android](#tab/Android)  

### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Compruebe que la configuración de protección de aplicaciones funciona en dispositivos de usuario.

Después de [establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](../business-premium/m365bp-app-protection-settings-for-android-and-ios.md) para proteger las aplicaciones, puede seguir estos pasos para validar la configuración que eligió.
  
En primer lugar, asegúrese de que la directiva se aplica a la aplicación en la que va a validarla.
  
1. En el [centro de administración](https://admin.microsoft.com) de Microsoft 365 Empresa Premium, vaya a **Directivas** \> **de edición**.

2. Elija **Directiva de aplicación para Android** para la configuración que creó durante la instalación u otra directiva que creó y compruebe que se aplica para Outlook, por ejemplo. 

    ![Captura de pantalla que muestra todas las aplicaciones para las que esta directiva protege los archivos.](../business-premium/media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Validar la opción Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office

En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.
  
![Asegúrese de que requerir un PIN o una huella digital para acceder a las aplicaciones de Office esté establecido en Activado.](../business-premium/media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.

2. También se le pedirá que escriba un PIN o use una huella digital.

    ![Enter a PIN on your Android device to access Office apps.](../business-premium/media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar la opción Restablecer el PIN después del número de intentos fallidos indicado

En el panel **Editar directiva** , elija **Editar** junto al **control de acceso a documentos de Office**, expanda **Administrar cómo los usuarios acceden a los archivos de Office en dispositivos móviles** y asegúrese **de que Restablecer PIN después de que el número de intentos fallidos** esté establecido en algún número. Esto es 5 de forma predeterminada. 
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.

2. Escriba un PIN incorrecto tantas veces como haya especificado en la directiva. Verá un mensaje que indica Límite de **intento de PIN alcanzado** para restablecer el PIN. 

    ![Captura de pantalla que indica que después de demasiados intentos de PIN incorrectos, debe restablecer el PIN.](../business-premium/media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Pulse **Restablecer PIN**. Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y, a continuación, se le pedirá que establezca un nuevo PIN.

### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../business-premium/media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.

2. Abra un correo electrónico que contenga un archivo adjunto y pulse el icono de flecha abajo situado junto a la información del archivo adjunto.

    ![Tap the down arrow next to an attachment to try to save it.](../business-premium/media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Verá **No se puede guardar** en el dispositivo en la parte inferior de la pantalla. 

    ![Warning text that indicates cannot save a file locally to an Android.](../business-premium/media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Guardar en OneDrive para la Empresa no está habilitado para Android en este momento, por lo que solo puede ver que la opción de guardar de forma local está bloqueada. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado

En el panel **Editar directiva** , elija **Editar** junto al **control de acceso a documentos de Office**, expanda **Administrar cómo los usuarios acceden a los archivos de Office en dispositivos móviles** y asegúrese de que **Requerir que los usuarios inicien sesión de nuevo después de que las aplicaciones de Office hayan estado inactivas se** establece en un número determinado de minutos. Esto es 30 minutos de forma predeterminada. 
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.

1. Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo Android durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.

1. Vuelva a acceder a Outlook en el dispositivo Android.

1. Se le pedirá que escriba el PIN para poder acceder de nuevo a Outlook.

### <a name="validate-protect-work-files-with-encryption"></a>Validar la opción Proteger los archivos de trabajo mediante cifrado

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.
  
1. En el dispositivo Android del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.

1. Abra un correo electrónico que contenga algunos datos adjuntos de archivos de imagen.

1. Pulse el icono de flecha abajo situado junto a la información del archivo adjunto para guardarlo.

    ![Tap the down arrow to save the figure file to the Android device.](../business-premium/media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
1. Es posible que se le pida que permita a Outlook obtener acceso a fotos, multimedia y archivos del dispositivo. Pulse **Permitir**.

1. En la parte inferior de la pantalla, elija a **Guardar en el dispositivo** y abra la aplicación **Galería**.

1. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) en la lista. Puede aparecer en la lista Imágenes como un cuadrado gris con un signo de exclamación blanco dentro de un círculo blanco en el centro del cuadrado gris.

    ![An encrypted image file in the Gallery app.](../business-premium/media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
### <a name="ios"></a>[iOS](#tab/iOS)

## <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Comprobar que la configuración de protección de aplicaciones funciona en dispositivos de usuario

Después de [establecer las configuraciones de la aplicación para dispositivos iOS](../business-premium/m365bp-protection-settings-for-windows-10-devices.md) para proteger aplicaciones, puede seguir estos pasos para validar que la configuración que ha elegido funciona. 
  
En primer lugar, asegúrese de que la directiva se aplica a la aplicación en la que va a validarla.
  
1. En el [centro de administración](https://admin.microsoft.com) de Microsoft 365 Empresa Premium, vaya a **Directivas** \> **de edición**.

1. Elija **Directiva de aplicación para iOS** para la configuración que creó durante la instalación u otra directiva que creó y compruebe que se aplica para Outlook, por ejemplo. 

    ![Captura de pantalla que muestra todas las aplicaciones para las que esta directiva protege los archivos.](../business-premium/media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Validar la opción Requerir un PIN para obtener acceso a las aplicaciones de Office

En el panel **Editar directiva**, elija **Editar** junto a **Control de acceso a documentos de Office**, expanda **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** y asegúrese de que **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office** esté establecido en **Activado**.
  
![Asegúrese de que requerir un PIN o una huella digital para acceder a las aplicaciones de Office esté establecido en Activado.](../business-premium/media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.

1. También se le pedirá que escriba un PIN o use una huella digital.

    ![Enter a PIN on your IOS device to access Office apps.](../business-premium/media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar la opción Restablecer el PIN después del número de intentos fallidos indicado

En el panel **Editar directiva** , elija **Editar** junto al **control de acceso a documentos de Office**, expanda **Administrar cómo los usuarios acceden a los archivos de Office en dispositivos móviles** y asegúrese **de que Restablecer PIN después de que el número de intentos fallidos** esté establecido en algún número. Esto es 5 de forma predeterminada.
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario.

1. Escriba un PIN incorrecto tantas veces como haya especificado en la directiva. Verá un mensaje que indica Límite de **intento de PIN alcanzado** para restablecer el PIN.

    ![Captura de pantalla en la que se advierte el restablecimiento del PIN después de demasiados intentos incorrectos.](../business-premium/media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
1. Pulse **Aceptar**. Se le pedirá que inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y, a continuación, se le pedirá que establezca un nuevo PIN.

### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar la opción Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Activado**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../business-premium/media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.

1. Abra un correo electrónico que contenga un archivo adjunto, abra ese archivo adjunto y elija **Guardar** en la parte inferior de la pantalla. 

    ![Tap the Save option after you open an attachment to try to save it.](../business-premium/media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
1. Solo debería ver una opción para OneDrive para la Empresa. Si no es así, pulse **Agregar cuenta** y seleccione **OneDrive para la Empresa** en la pantalla **Agregar cuenta de almacenamiento**. Proporcione la Microsoft 365 Empresa Premium del usuario final para iniciar sesión cuando se le solicite.

    Pulse **Guardar** y seleccione **OneDrive para la Empresa**.

### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar la opción Requerir que un usuario inicie sesión de nuevo si las aplicaciones de Office han estado inactivas durante un período de tiempo especificado

En el panel **Editar directiva** , elija **Editar** junto al **control de acceso a documentos de Office**, expanda **Administrar cómo los usuarios acceden a los archivos de Office en dispositivos móviles** y asegúrese de que **Requerir que los usuarios inicien sesión de nuevo después de que las aplicaciones de Office hayan estado inactivas se** establece en un número determinado de minutos. Esto es 30 minutos de forma predeterminada.
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.

1. Ahora debería ver la Bandeja de entrada de Outlook. No toque el dispositivo iOS durante al menos 30 minutos (o algún otro período de tiempo, más de lo que ha especificado en la directiva). Es probable que se atenúe el dispositivo.

1. Vuelva a tener acceso a Outlook en el dispositivo iOS.

1. Se le pedirá que escriba el PIN para poder acceder de nuevo a Outlook.

### <a name="validate-protect-work-files-with-encryption"></a>Validar la opción Proteger los archivos de trabajo mediante cifrado

En el panel **Editar directiva**, elija **Editar** junto a **Protección ante la pérdida o el robo del dispositivo**, expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y asegúrese de que **Proteger los archivos de trabajo mediante cifrado** esté establecido en **Activado** y **Forzar el almacenamiento por parte de los usuarios de todos los archivos de trabajo en OneDrive para la Empresa** esté establecido en **Desactivado**.
  
1. En el dispositivo iOS del usuario, abra Outlook e inicie sesión con las credenciales de Microsoft 365 Empresa Premium del usuario y escriba un PIN si se solicita.

1. Abra un correo electrónico que contenga algunos datos adjuntos de archivos de imagen.

1. Pulse el archivo adjunto y, después, pulse la opción **Guardar** debajo de él. 

1. Abra la aplicación **Fotos** desde la pantalla principal. Debería ver una foto cifrada (o más, si guardó varias imágenes adjuntas) guardada, pero cifrada. 

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)