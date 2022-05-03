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
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 03295989e1ee44ab43fe0cc53e4029a6c4307ea8
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65172641"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>Asignación de roles y permisos en Microsoft Defender para Empresas

Para realizar tareas en el portal de Microsoft 365 Defender, como configurar Microsoft Defender para Empresas, ver informes o realizar acciones de respuesta sobre amenazas detectadas, se deben asignar permisos adecuados al equipo de seguridad. Los permisos se conceden a través de roles asignados en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) o en [Azure Active Directory](/azure/active-directory/roles/manage-roles-portal). 

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los roles en Defender para empresas](#roles-in-defender-for-business).
2. [Vea o edite las asignaciones de roles para el equipo de seguridad](#view-or-edit-role-assignments).
3. [Continúe con los pasos siguientes](#next-steps).

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="roles-in-defender-for-business"></a>Roles en Defender para empresas

En la tabla siguiente se describen los tres roles que se pueden asignar en Defender para empresas. [Obtenga más información acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).

| Nivel de permisos | Descripción |
|:---|:---|
| **Administradores globales** (también conocidos como administradores globales) <br/><br/> *Como procedimiento recomendado, limite el número de administradores globales.* | Los administradores globales pueden realizar todo tipo de tareas. La persona que registró su empresa para Microsoft 365 o para Microsoft Defender para Empresas es un administrador global de forma predeterminada. <br/><br/> Los administradores globales pueden acceder o cambiar la configuración en todos los portales de Microsoft 365, como: <br/>- El Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) |
| **Administradores de seguridad** (también conocidos como administradores de seguridad) | Los administradores de seguridad pueden realizar las siguientes tareas: <br/>- Visualización y administración de directivas de seguridad <br/>- Ver y administrar alertas y amenazas de seguridad (estas actividades incluyen la realización de acciones de respuesta en puntos de conexión) <br/>- Visualización de información de seguridad e informes |
| **Lector de seguridad** | Los lectores de seguridad pueden realizar las siguientes tareas: <br/>- Visualización de directivas de seguridad <br/>- Visualización de amenazas y alertas de seguridad <br/>- Visualización de información de seguridad e informes  |


## <a name="view-or-edit-role-assignments"></a>Visualización o edición de asignaciones de roles

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Permisos & roles** y, en **Azure AD**, seleccione **Roles**.

3. Seleccione uno de los siguientes roles para abrir su panel lateral:

   - Administrador global
   - Administrador de seguridad
   - Lector de seguridad

   > [!IMPORTANT]
   > Microsoft recomienda conceder a las personas acceso solo a lo que necesitan para realizar sus tareas. A este concepto se le llama *privilegio mínimo* para los permisos. Para obtener más información, consulte [Procedimientos recomendados para el acceso con privilegios mínimos para las aplicaciones](/azure/active-directory/develop/secure-least-privileged-access). 

4. En el panel lateral, seleccione el vínculo **Administrar miembros en Azure AD**. Esta acción le lleva a Azure Active Directory (Azure AD) donde puede ver y administrar las asignaciones de roles.

5. Seleccione un usuario para abrir su perfil y, a continuación, elija **Roles asignados**.

   - Para agregar un rol, elija **+ Agregar asignaciones**.
   - Para quitar un rol, elija **X Quitar asignaciones**. 

## <a name="need-to-add-users"></a>¿Necesita agregar usuarios?

Si aún no ha agregado usuarios a su suscripción, consulte [Agregar usuarios y asignar licencias al mismo tiempo](mdb-add-users.md).

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 3: Configurar notificaciones por correo electrónico](mdb-email-notifications.md)
- [Paso 4: Incorporación de dispositivos a Microsoft Defender para Empresas](mdb-onboard-devices.md)