---
title: Editar o establecer la configuración de protección de aplicaciones para dispositivos Windows
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
f1.keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo crear o editar directivas de administración de aplicaciones y proteger archivos de trabajo en los dispositivos de Windows personales de los usuarios.
ms.openlocfilehash: 067cacfdd52b2d0a10bb221d426c54e8cbe9bb16
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67712613"
---
# <a name="set-or-edit-application-protection-settings-for-windows-devices"></a>Establecer o editar la configuración de protección de aplicaciones para dispositivos Windows

Ahora debe configurar directivas de protección de aplicaciones para los dispositivos Windows de la organización para asegurarse de que todos los usuarios estén protegidos cuando usen aplicaciones para el trabajo.

## <a name="edit-an-app-management-policy-for-windows-devices"></a>Editar una directiva de administración de aplicaciones para dispositivos Windows

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas**.

3. Elija una directiva de aplicación de Windows existente y, a continuación, **Editar**.

4. Elija **Editar** junto a una configuración que quiera cambiar y, luego, **Guardar**.

## <a name="create-an-app-management-policy-for-windows-devices"></a>Crear una directiva de administración de aplicaciones para dispositivos Windows

Si los usuarios tienen dispositivos de Windows personales en los que realizan tareas de trabajo puede proteger los datos en ellos.
  
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
  
10. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
11. Por último, elija **Agregar** para guardar la directiva y asignarla a los dispositivos.

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Siguiente objetivo

[Validar la configuración de Windows](m365bp-validate-settings-on-windows-10-pcs.md).