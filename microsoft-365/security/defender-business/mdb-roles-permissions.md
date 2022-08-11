---
title: Asignación de roles y permisos en Microsoft Defender para Empresas
description: Asigne roles al equipo de ciberseguridad. Obtenga información sobre estos roles y permisos en Defender para empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: b8e884c207479a7d2781e1ea4e31b9ee91bd25db
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300900"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>Asignación de roles y permisos en Microsoft Defender para Empresas

Para realizar tareas en el portal de Microsoft 365 Defender, como configurar Defender para empresas, ver informes o realizar acciones de respuesta sobre amenazas detectadas, se deben asignar permisos adecuados al equipo de seguridad. Los permisos se conceden a través de roles asignados en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) o en [Azure Active Directory](/azure/active-directory/roles/manage-roles-portal). 

## <a name="what-to-do"></a>Qué hacer

1. [Obtener información sobre los roles en Defender para Empresas](#roles-in-defender-for-business).
2. [Ver o editar las asignaciones de roles para el equipo de seguridad](#view-or-edit-role-assignments).
3. [Continúe con los pasos siguientes](#next-steps).


## <a name="roles-in-defender-for-business"></a>Roles en Defender para empresas

En la tabla siguiente se describen los tres roles que se pueden asignar en Defender para empresas. [Obtenga más información acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).

| Nivel de permisos | Descripción |
|:---|:---|
| **Administradores globales** (también conocidos como administradores globales) <p> *Como procedimiento recomendado, limite el número de administradores globales.* | Los administradores globales pueden realizar todo tipo de tareas. La persona que registró su empresa para Microsoft 365 o para Defender para empresas es un administrador global de forma predeterminada. <p> Los administradores globales pueden modificar la configuración en todos los portales de Microsoft 365, como: <ul><li>El Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))</li><li>portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com))</li></ul> |
| **Administradores de seguridad** (también conocidos como administradores de seguridad) | Los administradores de seguridad pueden realizar las siguientes tareas: <ul><li>Visualización y administración de directivas de seguridad</li><li>Visualización y administración de amenazas y alertas de seguridad (estas actividades incluyen la realización de acciones de respuesta en puntos de conexión)</li><li>Visualización de información e informes de seguridad</li></ul> |
| **Lector de seguridad** | Los lectores de seguridad pueden realizar las siguientes tareas:<ul><li>Ver directivas de seguridad</li><li>Visualización de amenazas y alertas de seguridad</li><li>Visualización de información e informes de seguridad</li></ul>  |


## <a name="view-or-edit-role-assignments"></a>Visualización o edición de asignaciones de roles

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Permisos & roles** y, en **Azure AD**, seleccione **Roles**.

3. Seleccione uno de los siguientes roles para abrir su panel lateral:

   - Administrador global
   - Administrador de seguridad
   - Lector de seguridad

   > [!IMPORTANT]
   > Microsoft recomienda conceder a los usuarios acceso solo a lo que necesitan para realizar sus tareas. A este concepto se le llama *privilegio mínimo* para los permisos. Para obtener más información, consulte [Procedimientos recomendados para el acceso con privilegios mínimos para las aplicaciones](/azure/active-directory/develop/secure-least-privileged-access). 

4. En el panel lateral, seleccione el vínculo **Administrar miembros en Azure AD** . Esta acción le lleva a Azure Active Directory (Azure AD), donde puede ver y administrar las asignaciones de roles.

5. Seleccione un usuario para abrir su perfil y, a continuación, elija **Roles asignados**.

   - Para agregar un rol, elija **+ Agregar asignaciones**.
   - Para quitar un rol, elija **X Quitar asignaciones**. 

## <a name="need-to-add-users"></a>¿Necesita agregar usuarios?

Si aún no ha agregado usuarios a su suscripción, consulte [Agregar usuarios y asignar licencias al mismo tiempo](mdb-add-users.md).

## <a name="next-steps"></a>Siguientes pasos

Vete a:

- [Paso 3: Configurar notificaciones por correo electrónico](mdb-email-notifications.md)
- [Paso 4: Incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md)