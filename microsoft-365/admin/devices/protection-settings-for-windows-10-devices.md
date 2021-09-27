---
title: Editar o establecer la configuración de protección de aplicaciones para Windows 10 dispositivos
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Obtén información sobre cómo crear o editar directivas de administración de aplicaciones y proteger los archivos de trabajo en los dispositivos Windows 10 usuarios.
ms.openlocfilehash: 7525cf1194022e5712f1a661c7176c8066de84e8
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933752"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Establecer o editar la configuración de protección de aplicaciones para Windows 10 dispositivos

Este artículo se aplica a Microsoft 365 Empresa Premium.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Editar una directiva de administración de aplicaciones para Windows 10

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. En el panel de navegación izquierdo, elija **Directivas de** \> **dispositivos** .
1. Elija una directiva de Windows de aplicaciones existente y, a **continuación, Edit**.
1. Elija **Editar** junto a una configuración que desea cambiar y, a continuación, **Guardar**.

## <a name="create-an-app-management-policy-for-windows-10"></a>Crear una directiva de administración de aplicaciones para Windows 10

Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. En la navegación izquierda, elija **Directivas** \> **de** \> **dispositivos Agregar**.
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
4. En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.
5. En **Tipo de dispositivo**, elija **Personal** o Propiedad de **la empresa**.
6. La opción **Cifrar archivos de trabajo** se activa automáticamente. 
7. Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo. 
9. Expanda **Recuperar datos en Windows dispositivos**. Se recomienda **activarlo**.
    Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, vea [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).
    
    De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado. Un administrador puede usar el certificado agente de recuperación de datos (DRA) para descifrar el archivo.
    
    ![Browse to Data Recovery Agent certificate.](../../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expande **Proteger ubicaciones de** red y nube adicionales si quieres agregar dominios adicionales o ubicaciones SharePoint Online para asegurarte de que los archivos de todas las aplicaciones enumeradas están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
12. Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.