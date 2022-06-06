---
title: Editar o establecer la configuración de protección de aplicaciones para dispositivos Windows
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
description: Obtenga información sobre cómo crear o editar directivas de administración de aplicaciones y proteger archivos de trabajo en los dispositivos de Windows personales de los usuarios.
ms.openlocfilehash: 5fb3da72ef5254a7428342554ac87ce996fb2204
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893160"
---
# <a name="set-or-edit-application-protection-settings-for-windows-devices"></a>Establecer o editar la configuración de protección de aplicaciones para dispositivos Windows

Ahora debe configurar directivas de protección de aplicaciones para los dispositivos Windows de la organización para asegurarse de que todos los usuarios estén protegidos cuando usen aplicaciones para el trabajo.

## <a name="edit-an-app-management-policy-for-windows-devices"></a>Editar una directiva de administración de aplicaciones para dispositivos Windows

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     

1. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas**.

1. Elija una directiva de aplicación de Windows existente y, a continuación, **Editar**.

1. Elija **Editar** junto a una configuración que quiera cambiar y, luego, **Guardar**.

## <a name="create-an-app-management-policy-for-windows-devices"></a>Crear una directiva de administración de aplicaciones para dispositivos Windows

Si los usuarios tienen dispositivos de Windows personales en los que realizan tareas de trabajo puede proteger los datos en ellos.
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 

1. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas** \> **Agregar**.

1. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 

1. En **Tipo de directiva**, elija **Administración de aplicaciones para Windows 10**.

1. En **Tipo de dispositivo**, elija **Personal** o **Propiedad de la empresa**.

1. La opción **Cifrar archivos de trabajo** se activa automáticamente. 

1. Establezca la opción **Impedir que los usuarios copien datos de la empresa en archivos personales y obligarlos a guardar los archivos de trabajo en OneDrive para la Empresa** en **Activado** si no quiere que los usuarios guarden archivos de trabajo en su equipo. 

1. Expanda **Recuperar datos en dispositivos Windows**. Se recomienda que esté **Activo**.
    Para poder examinar la ubicación del certificado de Agente de recuperación de datos, primero debe crear uno. Para obtener instrucciones, consulte [Crear y comprobar un certificado del Agente de recuperación de datos (DRA) de Sistema de cifrado de archivos (EFS)](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).

    De forma predeterminada, los archivos de trabajo están cifrados con una clave secreta que se almacena en el dispositivo y se asocia con el perfil del usuario. Solo el usuario puede abrir y descifrar el archivo. Sin embargo, si un dispositivo se pierde o se elimina a un usuario, un archivo puede quedarse en estado de cifrado. Un administrador puede usar el certificado del Agente de recuperación de datos (DRA) para descifrar el archivo.

    ![Desplácese hasta el certificado de Agente de recuperación de datos.](./../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
1. Expanda la opción **Proteger otras ubicaciones de red y nube** si quiere agregar dominios adicionales o ubicaciones de SharePoint Online para asegurarse de que los archivos de todas las aplicaciones de la lista están protegidos. Si necesita especificar más de un elemento en cualquiera de los campos, use punto y coma (;) entre los elementos.

    ![Expanda Proteger las ubicaciones de red y de nube adicionales y escriba dominios o sitios de SharePoint Online de los que sea propietario.](./../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
1. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
1. Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Siguiente objetivo

[Validar la configuración de Windows](m365bp-validate-settings-on-windows-10-pcs.md).