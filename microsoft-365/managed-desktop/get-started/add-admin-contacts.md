---
title: 'Agregar y verificar los contactos de administración en el portal de administración '
description: Indíquenos con quién ponerse en contacto para cada área de enfoque.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d34d7082150b4131634fb695ce6664ded50e6f9d
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823842"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Agregar y verificar los contactos de administración en el portal de administración 

Hay varias formas en las que el servicio de escritorio administrado de Microsoft se comunica con los clientes. Para simplificar la comunicación y asegurarse de que estamos comprobando con las personas adecuadas, debe proporcionar un conjunto de contactos de administración. Las operaciones de TI de escritorio administradas por Microsoft se contactan con estas personas para obtener ayuda para solucionar problemas relacionados con el espacio empresarial.

> [!IMPORTANT]
> Es posible que ya haya agregado estos contactos en el portal de administración. Si es así, dedique un momento a comprobar que la lista de contactos es precisa, ya que el escritorio administrado de Microsoft **debe** poder llegar a ellos si se produce un incidente grave.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Portal de Azure Active Directory Access para la administración del escritorio administrado de Microsoft

El portal de administración de escritorio administrado de Microsoft requiere que las personas que accedan al portal tengan uno de estos roles de Azure Active Directory (AD):
- Administrador global
- Administrador de servicios de Intune
- Administrador de facturación
- Administrador de soporte de servicio

El administrador global debe ser el único que inscriba a su organización en el escritorio administrado de Microsoft. Los cinco roles tienen el mismo acceso dentro del portal de administración para iniciar y ver las tareas. Para obtener más información sobre la asignación de estos roles en Azure AD, vea [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Áreas de contacto del administrador enfocadas

Los contactos de administrador deben ser la mejor persona o grupo que pueda responder preguntas y tomar decisiones para diferentes áreas de interés. **Las operaciones de escritorio administradas de Microsoft se comunicarán con estos contactos de administrador para obtener preguntas relacionadas con las solicitudes de soporte técnico que haya archivado el cliente.** Estos contactos de administración recibirán notificaciones de actualizaciones de solicitud de soporte y mensajes nuevos. Estas áreas incluyen:

Área de foco | Para preguntas sobre
--- | ---
Empaquetado de aplicaciones | Solución de problemas de empaquetado de aplicaciones
Dispositivos | Estado del dispositivo, solución de problemas con dispositivos de escritorio administrados por Microsoft
Seguridad | Solución de problemas de seguridad de los dispositivos de escritorio administrados por Microsoft
Departamento de soporte técnico de ti | en los casos en los que el personal de soporte técnico pasa a través de los vales de usuario final fuera de las áreas de soporte técnico de Microsoft administradas 
Otros | Para problemas no cubiertos por otras áreas

**La persona que elija para estos contactos debe tener el conocimiento y la autoridad para tomar decisiones en su entorno de escritorio administrado por Microsoft.** Cuando incorpore su entorno de escritorio administrado de Microsoft, se le pedirá que agregue contactos para el Departamento de soporte técnico y la seguridad locales. 

Los contactos de administración son necesarios cuando [envía una solicitud de soporte técnico](../service-description/support.md). Necesitará tener un contacto de administrador para el área de enfoque de la solicitud de soporte técnico. 

**Para agregar contactos de administrador**

1.  Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal). 

2.  En **soporte**, seleccione **contactos de administración**. 

    ![Menú soporte, contactos de administración cerca de la parte superior seleccionada](images/admincontacts.png)

3. Seleccione **Agregar**.

    ![Portal de administración, botón Agregar, a la izquierda de exportar y actualizar](images/adminadd.png)

4.  Seleccione un **área de enfoque** y escriba la información del contacto. 

    ![la lista de áreas de foco, como otras, aplicaciones y seguridad](images/areaoffocus.png)

5. Repita este procedimiento para cada área de enfoque. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a trabajar con el escritorio administrado de Microsoft

1. Agregar y comprobar los contactos de administrador en el portal de administración (este tema)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. [Instalar el portal de empresa de Intune en los dispositivos](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurar dispositivos de escritorio administrados por Microsoft](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones en dispositivos](deploy-apps.md)