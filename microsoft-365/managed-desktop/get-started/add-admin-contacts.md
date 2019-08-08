---
title: Agregar contactos de administrador en el portal de administración de escritorio administrado de Microsoft
description: Indíquenos con quién ponerse en contacto para cada área de enfoque.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2178b871da412d12bf20dae9b72d7562e2bc4654
ms.sourcegitcommit: 4460975970ae13e917d4d336e92dbd76ae26493b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243951"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Agregar contactos de administrador en el portal de administración de escritorio administrado de Microsoft

Hay varias formas en las que el servicio de escritorio administrado de Microsoft se comunica con los clientes. Para simplificar la comunicación y asegurarse de que estamos comprobando los mejores contactos, debe proporcionar un conjunto de contactos de administración. Las operaciones de TI de escritorio administradas por Microsoft se contactan con estas personas para obtener ayuda para solucionar problemas relacionados con el espacio empresarial. 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Portal de Azure Active Directory Access para la administración del escritorio administrado de Microsoft

El portal de administración de escritorio administrado de Microsoft requiere que las personas que accedan al portal tengan uno de estos roles de Azure Active Directory (AD):
- Administrador global
- Administrador de servicios de Intune
- Administrador de facturación
- Administrador de soporte de servicio

El administrador global debe ser el que inscriba al cliente en el escritorio administrado de Microsoft. Los cinco roles tienen el mismo acceso dentro del portal de administración para iniciar y ver las tareas. Para obtener más información sobre la asignación de estos roles en Azure AD, vea [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Áreas de contacto del administrador enfocadas

Los contactos de administrador deben ser la mejor persona o grupo que pueda responder preguntas y tomar decisiones para diferentes áreas de interés. Las operaciones de escritorio administradas de Microsoft se comunicarán con estos contactos de administrador para obtener preguntas relacionadas con las solicitudes de soporte técnico que haya archivado el cliente. Estos contactos de administración recibirán notificaciones de actualizaciones de solicitud de soporte y mensajes nuevos. Estas áreas incluyen:

Área de foco | Para preguntas sobre
--- | ---
Empaquetado de aplicaciones | Solución de problemas de empaquetado de aplicaciones
Dispositivos | Estado del dispositivo, solución de problemas con dispositivos de escritorio administrados por Microsoft
Seguridad | Solución de problemas de seguridad de los dispositivos de escritorio administrados por Microsoft
Departamento de soporte técnico de ti | en los casos donde Microsoft Managed Desktop Support ofrece a los tíquets del usuario final fuera de las áreas de soporte técnico de MMD 
Otros | Para problemas no cubiertos por otras áreas

La persona que elija para estos contactos debe tener el conocimiento y la autoridad para tomar decisiones en su entorno de escritorio administrado por Microsoft. Cuando incorpore su entorno de escritorio administrado de Microsoft, se le pedirá que agregue contactos para el Departamento de soporte técnico y la seguridad locales. 

Los contactos de administración son necesarios cuando [envía una solicitud de soporte técnico](../working-with-managed-desktop/support.md). Necesitará tener un contacto de administrador para el área de enfoque de la solicitud de soporte técnico. 

**Para agregar contactos de administrador**

1.  Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal). 

2.  En **soporte**, seleccione **contactos de administración**. 

    ![Menú soporte, contactos de administración](images/admincontacts.png)

3. Seleccione **Agregar**.

    ![Botón Agregar portal de administración](images/adminadd.png)

4.  Seleccione un **área de enfoque** y escriba la información del contacto. 

    ![la lista de áreas de foco](images/areaoffocus.png)

5. Repita este procedimiento para cada área de enfoque. 

