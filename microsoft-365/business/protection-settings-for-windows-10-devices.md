---
title: Editar o establecer la configuración de protección de aplicaciones para dispositivos Windows 10
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
description: Aprende a crear o editar directivas de administración de aplicaciones y a proteger los archivos de trabajo en los dispositivos personales de Windows 10 de los usuarios.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580022"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Establecer o editar la configuración de protección de aplicaciones para dispositivos Windows 10

Este artículo se aplica a Microsoft 365 Empresa Premium.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Editar una directiva de administración de aplicaciones para Windows 10

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. En el panel de navegación izquierdo, elija **Directivas de** \> **dispositivos** .
1. Elija una directiva de aplicación de Windows existente y, a **continuación, Edit**.
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
9. Expande **Recuperar datos en dispositivos Windows**. Se recomienda **activarlo**.
    Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, vea [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).
    
    De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y está asociada con el perfil de usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina un usuario, un archivo puede permanecer es estado cifrado. Un administrador puede usar el certificado agente de recuperación de datos (DRA) para descifrar el archivo.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expanda **Proteger ubicaciones de red** y nube adicionales si desea agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones enumeradas están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use un punto y coma (;) entre los elementos.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
12. Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.