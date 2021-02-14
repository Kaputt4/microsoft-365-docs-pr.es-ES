---
title: Agregar y verificar los contactos de administración en el portal de administración
description: Díganos con quién ponerse en contacto para cada área de foco.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289266"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Agregar y verificar los contactos de administración en el portal de administración

Hay varias maneras en que el servicio de escritorio administrado de Microsoft se comunica con los clientes. Para simplificar la comunicación y garantizar que estamos comprobando con las personas correctas, debe proporcionar un conjunto de contactos de administrador. Las operaciones de TI de escritorio administrado de Microsoft se pondrán en contacto con estas personas para obtener ayuda para solucionar problemas de su espacio empresarial.

> [!IMPORTANT]
> Es posible que ya haya agregado estos contactos en el portal de administración. Si es así, tómese un momento para comprobar que  la lista de contactos es precisa, ya que el Escritorio administrado de Microsoft debe ser capaz de llegar a ellos si se produce un incidente grave.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Acceso de Azure Active Directory para el portal de administración de escritorio administrado de Microsoft

El portal de administración de escritorio administrado de Microsoft requiere que los usuarios que accedan al portal tengan uno de estos roles de Azure Active Directory (AD):
- Administrador global
- Administrador de servicios de Intune
- Lector global
- Administrador de soporte técnico del servicio

El administrador global debe ser el que inscriba su organización en el Escritorio administrado de Microsoft. Los cinco roles tienen el mismo acceso en el portal de administración para iniciar y ver tareas. Para obtener más información sobre cómo asignar estos roles en Azure AD, vea Permisos de rol [de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 

## <a name="admin-contact-areas-of-focus"></a>Áreas de contacto de administración de foco

Los contactos de administración deben ser la mejor persona o grupo que pueda responder preguntas y tomar decisiones para diferentes áreas de foco. **Las operaciones de escritorio administrado de Microsoft se pondrán en contacto con estos contactos de administrador para obtener preguntas relacionadas con las solicitudes de soporte técnico que el cliente ha presentado.** Estos contactos de administrador recibirán notificaciones de actualizaciones de solicitudes de soporte técnico y mensajes nuevos. Estas áreas incluyen:

Área de foco | Para preguntas sobre
--- | ---
Empaquetado de la aplicación | Solución de problemas de empaquetado de aplicaciones
Dispositivos | Estado del dispositivo, solución de problemas con dispositivos de Escritorio administrado de Microsoft
Seguridad | Solución de problemas de seguridad con dispositivos de Escritorio administrado de Microsoft
Servicio de ayuda de IT | en los casos en los que nuestro personal de soporte técnico entrega vales de usuario fuera de las áreas de soporte técnico de Escritorio administrado de Microsoft 
Otros | Para problemas no cubiertos por otras áreas

**Quien elija para estos contactos debe tener el conocimiento y la autoridad para tomar decisiones para su entorno de Escritorio administrado de Microsoft.** Cuando incorpore su entorno de Escritorio administrado de Microsoft, se le pedirá que agregue contactos para el departamento de soporte técnico y seguridad local. 

Los contactos de administrador son necesarios cuando [envía una solicitud de soporte técnico.](../service-description/support.md) Deberás tener un contacto de administrador para el área de foco de la solicitud de soporte técnico. 

**Para agregar contactos de administrador**

1.  Inicie sesión en el [portal de administración de Escritorio administrado de Microsoft.](https://aka.ms/mwaasportal) 

2.  En **Soporte técnico,** seleccione **Contactos de administrador.** 

    ![Menú Soporte técnico, contactos de administrador cerca de la parte superior seleccionada](../../media/admincontacts.png)

3. Seleccione **Agregar**.

    ![Portal de administración, botón Agregar, a la izquierda de Exportar y actualizar](../../media/adminadd.png)

4.  Selecciona un **área de foco** y escribe la información del contacto. 

    ![la lista de áreas de foco, como Otras, Aplicaciones y Seguridad](../../media/areaoffocus.png)

5. Repita este paso para cada área de foco. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a usar el Escritorio administrado de Microsoft

1. Agregar y comprobar contactos de administrador en el portal de administración (este tema)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. [Instalar el Portal de empresa de Intune en dispositivos](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurar dispositivos del Escritorio administrado por Microsoft](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones en dispositivos](deploy-apps.md)
