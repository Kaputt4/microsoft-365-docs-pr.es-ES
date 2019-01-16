---
title: Establecer la configuración de protección de aplicaciones para dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Obtenga información sobre cómo crear una directiva de administración de aplicaciones y protección de archivos de trabajo en los dispositivos de Windows 10.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871361"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Establecer la configuración de protección de aplicaciones para dispositivos Windows 10

## <a name="create-an-app-management-policy-for-windows-10"></a>Crear una directiva de administración de aplicaciones para Windows 10

Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.
  
1. Inicie sesión en [Microsoft 365 Business](https://portal.office.com) con credenciales de administrador global. Elija el icono **Administrador** para ir al centro de administración. 
    
2. En la tarjeta **Directivas de dispositivos** del portal de administración, elija **Agregar directiva**.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
    
4. En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.
    
5. Bajo ** tipo de dispositivo **, elija **Personal** o **Propietaria de la empresa**.
    
6. La opción **Cifrar archivos de trabajo** se activa automáticamente. 
    
7. Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo. 
    
8. Expanda **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos** \> configure las opciones como quiera. La opción **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** está **desactivada** de forma predeterminada, pero se recomienda que la **active** y acepte los valores predeterminados. Vea [Configuración disponible](protection-settings-for-windows-10-devices.md#bkmk_settings) para obtener más información. 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
9. Expanda la opción **Recuperar datos en dispositivos Windows** y se recomienda que la **active**.
    
    Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, vea [Crear y comprobar un certificado del Agente de recuperación de datos (DRA) del Sistema de cifrado de archivos (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).
    
    De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado. El certificado del agente de recuperación de datos (ARD) puede ser utilizado por un administrador para descifrar el archivo.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expanda la opción **Proteger otras ubicaciones de red y nube** si quiere agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones de la lista están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos. 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
    
12. Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos. 
    
## <a name="available-settings"></a>Configuración disponible

La siguiente configuración está disponible para administrar la forma de obtener acceso a archivos de trabajo de Office.
  
Para obtener más información, consulte [Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune](map-protection-features-to-intune-settings.md).
  
|**Configuración**|**Descripción**|
|:-----|:-----|
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  <br/> |Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.  <br/> |
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  <br/> |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  <br/> |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  <br/> |Esta configuración determina el tiempo que un usuario puede estar inactivo antes de que se le pida que vuelva a iniciar sesión.  <br/> |
   

