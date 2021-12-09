---
title: Asignar roles y permisos en Microsoft Defender para empresas
description: Obtenga información sobre cómo asignar roles y permisos en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: bf29e912e248d0aa1a3b559f83699264f2e42bc1
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375379"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>Asignar roles y permisos en Microsoft Defender para empresas

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

Para realizar tareas en el portal de Microsoft 365 Defender, como configurar Microsoft Defender para empresas, ver informes o realizar acciones de respuesta en las amenazas detectadas, se deben asignar los permisos adecuados al equipo de seguridad. Los permisos se conceden a través de roles asignados en el portal de Microsoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) ( ) o en [Azure Active Directory](/azure/active-directory/roles/manage-roles-portal). 

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los roles en Defender para empresas](#roles-in-defender-for-business).

2. [Ver o editar asignaciones de roles para el equipo de seguridad](#view-or-edit-role-assignments).

3. [Continúe con los pasos siguientes](#next-steps).

## <a name="roles-in-defender-for-business"></a>Roles en Defender para empresas

En la tabla siguiente se describen los tres roles que se pueden asignar en Defender para empresas. [Obtenga más información acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md). <br/><br/>

| Nivel de permisos | Descripción |
|:---|:---|
| **Administradores globales** (también denominados administradores globales) <br/><br/> *Como práctica recomendada, limite el número de administradores globales.* | Los administradores globales pueden realizar todo tipo de tareas. La persona que se ha registrado en su empresa para Microsoft 365 o para Microsoft Defender para empresas es un administrador global de forma predeterminada. <br/><br/> Los administradores globales pueden acceder o cambiar la configuración en todos Microsoft 365 portales, como: <br/>- El Centro de administración de Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) <br/>- Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) ) |
| **Administradores de seguridad** (también denominados administradores de seguridad) | Los administradores de seguridad pueden realizar las siguientes tareas: <br/>- Ver y administrar directivas y configuraciones de seguridad <br/>- Ver y administrar alertas y amenazas de seguridad (estas actividades incluyen realizar acciones de respuesta en puntos de conexión) <br/>- Ver información e informes de seguridad |
| **Lector de seguridad** | Los lectores de seguridad pueden realizar las siguientes tareas: <br/>- Ver directivas y configuraciones de seguridad <br/>- Ver alertas y amenazas de seguridad <br/>- Ver información e informes de seguridad  |


## <a name="view-or-edit-role-assignments"></a>Ver o editar asignaciones de roles

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, elija **Permisos & roles y,** a continuación, en **Azure AD**, seleccione **Roles**.

3. Seleccione uno de los siguientes roles para abrir su panel lateral:

   - Administrador global
   - Administrador de seguridad
   - Lector de seguridad

   > [!IMPORTANT]
   > Microsoft recomienda conceder a los usuarios acceso solo a lo que necesitan para realizar sus tareas. A este concepto se *le llama privilegios mínimos* para los permisos. Para obtener más información, vea [Procedimientos recomendados para el acceso con privilegios mínimos para aplicaciones](/azure/active-directory/develop/secure-least-privileged-access). 

4. En el panel lateral, seleccione el vínculo **Administrar miembros en Azure AD** usuario. Esta acción le lleva a Azure Active Directory (Azure AD) donde puede ver y administrar las asignaciones de roles.

5. Seleccione un usuario para abrir su perfil y, a continuación, elija **Roles asignados**.

   - Para agregar un rol, elija **+ Agregar asignaciones**.
   - Para quitar un rol, elija **X Quitar asignaciones**. 

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 3: Configurar notificaciones por correo electrónico](mdb-email-notifications.md)

- [Paso 4: Incorporar dispositivos a Microsoft Defender para empresas](mdb-onboard-devices.md)