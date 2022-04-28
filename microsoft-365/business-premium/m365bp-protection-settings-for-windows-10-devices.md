---
title: Editar o establecer la configuración de protección de aplicaciones para dispositivos Windows 10
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
f1.keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
ms.localizationpriority: high
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
description: Obtenga información sobre cómo crear o editar directivas de administración de aplicaciones y proteger archivos de trabajo en los dispositivos de Windows 10 personales de los usuarios.
ms.openlocfilehash: f636c138d9364d9bc4739cc5ee11737707d32913
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096015"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Establecer o editar la configuración de protección de aplicaciones para dispositivos Windows 10

Este artículo aplica a Microsoft 365 Empresa Premium.

> [!NOTE]
> Microsoft Defender para Empresas se está implementando para los clientes de Microsoft 365 Empresa Premium desde el 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

## <a name="edit-an-app-management-policy-for-windows-10"></a>Editar una directiva de administración de aplicaciones para Windows 10

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas**.

3. Elija una directiva de aplicación de Windows existente y, a continuación, **Editar**.

4. Elija **Editar** junto a una configuración que quiera cambiar y, luego, **Guardar**.

## <a name="create-an-app-management-policy-for-windows-10"></a>Crear una directiva de administración de aplicaciones para Windows 10

Si los usuarios tienen dispositivos de Windows 10 personales en los que realizan tareas de trabajo, también puede proteger los datos en ellos.
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas** \> **Agregar**.

3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 

4. En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.

5. En **Tipo de dispositivo**, elija **Personal** o **Propiedad de la empresa**.

6. La opción **Cifrar archivos de trabajo** se activa automáticamente. 

7. Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo. 

8. Expanda **Recuperar datos en dispositivos Windows**. Se recomienda que esté **Activo**.
    Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, consulte [Crear y comprobar un certificado del Agente de recuperación de datos (DRA) de Sistema de cifrado de archivos (EFS)](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).
    
    De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y se asocia con el perfil del usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina a un usuario, un archivo puede quedarse en estado de cifrado. Un administrador puede usar el certificado del Agente de recuperación de datos (DRA) para descifrar el archivo.
    
    ![Desplácese hasta el certificado de Agente de recuperación de datos.](./../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
9. Expanda la opción **Proteger otras ubicaciones de red y nube** si quiere agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones de la lista están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use punto y coma (;) entre los elementos.
    
    ![Expanda Proteger las ubicaciones de red y de nube adicionales y escriba dominios o sitios de SharePoint Online de los que sea propietario.](./../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
12. Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.

## <a name="see-also"></a>Vea también

[10 formas de proteger con planes de Microsoft 365 para empresas](../admin/security-and-compliance/secure-your-business-data.md)