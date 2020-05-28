---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
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
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Validar la configuración de protección de aplicaciones de Microsoft 365 Business Premium en dispositivos Windows 10 y comprobar que los usuarios no pueden copiar datos de la empresa en archivos personales o aplicaciones no administradas.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403398"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de aplicaciones en PC con Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos corporativos.

Después de [configurar directivas de protección de la aplicación](protection-settings-for-windows-10-devices.md), puede tardar unas pocas horas en tener efecto la directiva en los dispositivos de los usuarios. Si **activó la** opción evitar que **los usuarios copien los datos de la compañía en archivos personales y forzar que se guarden los archivos de trabajo en OneDrive para** la empresa para los dispositivos que son propiedad de la empresa, puede comprobarlo en el dispositivo del usuario después de que se hayan conectado a Azure ad y hayan iniciado sesión. 
  
 **Comprobar la configuración de conexión**
  
1. Después de iniciar sesión con las credenciales de Microsoft 365 Business Premium y conectarse a Azure ad tal y como se describe en [configurar dispositivos Windows para Microsoft 365 empresa Premium](set-up-windows-devices.md), vaya a **configuración de Windows** \> : **cuentas** de \> **acceso profesional o educativo**. Elija **conectado a \<tenant name\> Azure ad**y, a continuación, elija **información**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. En la página **administrado por** \<tenant name\> , puede ver la **información de conexión** que incluye una **dirección del servidor de administración** como la que se muestra en la siguiente ilustración. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**
  
1. Abra Outlook 2016 que instaló Microsoft 365 empresa Premium.
    
2. Abra un correo electrónico y copie parte del contenido de él.
    
    Abra el Bloc de notas e intente pegar el contenido.
    
    Recibirá un error que indica que la aplicación no puede acceder al contenido.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sin embargo, puede pegar el mismo contenido en Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos personales.

 **Comprobar la configuración de conexión**
  
1. En el dispositivo de Windows 10 personal en el que haya iniciado sesión como usuario local, vaya a **configuración de Windows**y haga clic o pulse **cuentas** de \> **acceso profesional o educativa**.
    
2. En **Acceso profesional o educativo**, elija **Conectar**.
    
3. Escriba su credencial de Microsoft 365 Business Premium en el **cuadro de diálogo Configurar una cuenta de trabajo o escuela** \> **para iniciar sesión**.
    
4. En la página **Acceso profesional o educativo**, elija **Cuenta profesional o educativa** y, a continuación, elija **Información**.
    
    ![Haga clic o pulse en información en el cuadro de diálogo de la cuenta profesional o educativa.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. En la página **tener acceso a la escuela o el trabajo** , puede ver la **información de conexión** que incluye una dirección del servidor de **Administración** como la que se muestra en la figura siguiente, e incluye las palabras *WIP* y *MAM* en. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**
  
1. Abra Outlook 2016 y agregue su cuenta de Microsoft 365 empresa Premium, si es necesario, e inicie sesión con sus credenciales de Microsoft 365 Business Premium.
    
2. Abra un correo electrónico y copie parte del contenido de él.
    
    Abra el Bloc de notas e intente pegar el contenido.
    
    Recibirá un error que indica que la aplicación no puede obtener acceso al contenido.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sin embargo, puede pegar el mismo contenido en Word 2016.
    

