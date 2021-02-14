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
description: Valide la configuración de protección de aplicaciones de Microsoft 365 Empresa Premium en dispositivos Windows 10 y compruebe que los usuarios no puedan copiar datos de la empresa en archivos personales o aplicaciones no administradas.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403398"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de aplicaciones en PC con Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos corporativos.

Después de [configurar directivas de protección de la aplicación](protection-settings-for-windows-10-devices.md), puede tardar unas pocas horas en tener efecto la directiva en los dispositivos de los usuarios. Si ha  activado la opción Impedir que los usuarios copien datos de la empresa en archivos personales y obligarles a guardar los archivos de trabajo en la configuración de **OneDrive** para la Empresa para dispositivos propiedad de la empresa, puede comprobarlo en el dispositivo del usuario después de conectarse a Azure AD e haber iniciado sesión. 
  
 **Comprobar la configuración de conexión**
  
1. Después de iniciar sesión con las credenciales de Microsoft 365 Empresa Premium y conectarse a Azure AD, tal como se describe en Configurar dispositivos Windows para usuarios de [Microsoft 365 Empresa Premium,](set-up-windows-devices.md)vaya a la escuela o trabajo de Configuración de **Windows.** \>  \>  Elija **Conectado a Azure \<tenant name\> AD** y, a continuación, elija **Información.**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. En la **página Administrado por,** puedes ver la información de conexión que incluye una dirección del servidor de administración como la que se muestra \<tenant name\> en la ilustración  siguiente.  
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**
  
1. Abra Outlook 2016 instalado por Microsoft 365 Empresa Premium.
    
2. Abra un correo electrónico y copie parte del contenido de él.
    
    Abra el Bloc de notas e intente pegar el contenido.
    
    Recibirás un error que indica que la aplicación no puede acceder al contenido.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sin embargo, puede pegar el mismo contenido en Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Compruebe que los usuarios no pueden copiar los datos de empresa a los archivos personales en dispositivos personales.

 **Comprobar la configuración de conexión**
  
1. En el dispositivo personal de Windows 10 en el que has iniciado sesión  como usuario local, ve a Configuración de **Windows** y haz clic o pulsa En el acceso a cuentas trabajo \> **o escuela.**
    
2. En **Acceso profesional o educativo**, elija **Conectar**.
    
3. Escribe tu credencial de Microsoft 365 Empresa Premium en el cuadro de diálogo Configurar una cuenta de trabajo o  \> **escuela.**
    
4. En la página **Acceso profesional o educativo**, elija **Cuenta profesional o educativa** y, a continuación, elija **Información**.
    
    ![Haz clic o pulsa Información en el cuadro de diálogo Cuenta de trabajo o escuela.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. En la página trabajo o escuela  de **Access,**  puedes ver la información de conexión que incluye una dirección del servidor de administración como la que se muestra en la figura siguiente e incluye las palabras *wip* y *mam.* 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Comprobar que no se pueden pegar datos de la empresa en una aplicación no administrada**
  
1. Abra Outlook 2016 y agregue su cuenta de Microsoft 365 Empresa Premium si es necesario e inicie sesión con sus credenciales de Microsoft 365 Empresa Premium.
    
2. Abra un correo electrónico y copie parte del contenido de él.
    
    Abra el Bloc de notas e intente pegar el contenido.
    
    Recibirá un error que indica que la aplicación no puede acceder al contenido.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sin embargo, puede pegar el mismo contenido en Word 2016.
    

