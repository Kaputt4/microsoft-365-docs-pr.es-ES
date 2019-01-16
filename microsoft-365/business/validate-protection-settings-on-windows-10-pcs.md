---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo validar la configuración de protección de aplicación de Microsoft 365 Business en los dispositivos de Windows 10.
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871566"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de aplicaciones en PC con Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos corporativos.

Después de [configurar directivas de protección de la aplicación](protection-settings-for-windows-10-devices.md), puede tardar unas pocas horas en tener efecto la directiva en los dispositivos de los usuarios. Si ha **activado** la configuración **Impedir que los usuarios copien los datos de la compañía en los archivos personales y forzarlos a guardar los archivos de trabajo en OneDrive para la Empresa** para los dispositivos que son propiedad de la empresa, puede comprobarlo en el dispositivo del usuario después de que se hayan conectado a Azure AD e iniciado sesión. 
  
 **Comprobar la configuración de conexión**
  
1. Después de iniciar sesión con credenciales de Microsoft 365 empresa y conectarse a Azure AD tal como se describe en [configurar los dispositivos de Windows para usuarios profesionales de 365 de Microsoft](set-up-windows-devices.md), vaya a **Configuración de Windows** \> **cuentas** \> **acceso trabajo o escuela **. Elija **conectado a \<nombre del inquilino\> Azure AD**y, a continuación, elija **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. En la página **Administrado por** \< nombre del inquilino \> puede ver la **información de conexión** que incluye una **dirección del servidor de administración** como la que se muestra en la siguiente ilustración. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Compruebe que no puede pegar datos de la compañía a una aplicación no administrada**
  
1. Abra Outlook 2016 que fue instalada por Microsoft 365 Business.
    
2. Abra un correo electrónico y copie parte del contenido de él.
    
    Abra el Bloc de notas e intente pegar el contenido.
    
    Recibirá un error que indica que la aplicación no puede obtener acceso al contenido.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sin embargo, puede pegar el mismo contenido en Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos personales.

 **Comprobar la configuración de conexión**
  
1. En el dispositivo personal de Windows 10 donde está conectado como un usuario local, vaya a **Configuración de Windows** y haga clic o pulse **Cuentas** \> **Acceso profesional o educativo**.
    
2. En **Acceso profesional o educativo**, elija **Conectar**.
    
3. Escriba sus Microsoft 365 Business credenciales en el **diálogo Configurar una cuenta profesional o educativa** \> **Inicio de sesión**.
    
4. En la página **Acceso profesional o educativo**, elija **Cuenta profesional o educativa** y, a continuación, elija **Información**.
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. En la página **Acceso profesional o educativo** puede ver **Información de conexión** que incluye una **dirección de servidor de administración** como la que se muestra en la siguiente imagen e incluye las palabras  *wip*  y  *mam*  . 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Compruebe que no puede pegar datos de la compañía a una aplicación no administrada**
  
1. Abra Outlook 2016 y agregue su Microsoft 365 Business cuenta si es necesario e inicie sesión con sus Microsoft 365 Business credenciales.
    
2. Abra un correo electrónico y copie parte del contenido de él.
    
    Abra el Bloc de notas e intente pegar el contenido.
    
    Recibirá un error que indica que la aplicación no puede obtener acceso al contenido.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sin embargo, puede pegar el mismo contenido en Word 2016.
    

