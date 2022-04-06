---
title: Asignar roles y permisos en Microsoft Defender für Unternehmen
description: Obtenga información sobre cómo asignar roles y permisos en Microsoft Defender für Unternehmen
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 33fb7548d2dbd231368a459cd58b9d50e7c4673e
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64638254"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>Asignar roles y permisos en Microsoft Defender für Unternehmen

> [!IMPORTANT]
> Microsoft Defender für Unternehmen se está implementando para [Microsoft 365 Business Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Para realizar tareas en el portal de Microsoft 365 Defender, como configurar Microsoft Defender für Unternehmen, ver informes o realizar acciones de respuesta en las amenazas detectadas, se deben asignar los permisos adecuados al equipo de seguridad. Los permisos se conceden a través de roles asignados en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) o en [Azure Active Directory](/azure/active-directory/roles/manage-roles-portal). 

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los roles en Defender para empresas](#roles-in-defender-for-business).

2. [Ver o editar asignaciones de roles para el equipo de seguridad](#view-or-edit-role-assignments).

3. [Continúe con los pasos siguientes](#next-steps).

>
> **¿Tiene un minuto?**
> Por favor, <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">haga nuestra breve encuesta sobre Microsoft Defender für Unternehmen</a>. Nos encantaría conocer su opinión.
>

## <a name="roles-in-defender-for-business"></a>Roles en Defender para empresas

En la tabla siguiente se describen los tres roles que se pueden asignar en Defender para empresas. [Obtenga más información acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md). <br/><br/>

| Nivel de permisos | Descripción |
|:---|:---|
| **Administradores globales** (también denominados administradores globales) <br/><br/> *Como práctica recomendada, limite el número de administradores globales.* | Los administradores globales pueden realizar todo tipo de tareas. La persona que se ha registrado en la empresa para Microsoft 365 o para Microsoft Defender für Unternehmen es un administrador global de forma predeterminada. <br/><br/> Los administradores globales pueden acceder o cambiar la configuración en todos Microsoft 365 portales, como: <br/>- El Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) |
| **Administradores de seguridad** (también denominados administradores de seguridad) | Los administradores de seguridad pueden realizar las siguientes tareas: <br/>- Ver y administrar directivas de seguridad <br/>- Ver y administrar alertas y amenazas de seguridad (estas actividades incluyen realizar acciones de respuesta en puntos de conexión) <br/>- Ver información e informes de seguridad |
| **Lector de seguridad** | Los lectores de seguridad pueden realizar las siguientes tareas: <br/>- Ver directivas de seguridad <br/>- Ver alertas y amenazas de seguridad <br/>- Ver información e informes de seguridad  |


## <a name="view-or-edit-role-assignments"></a>Ver o editar asignaciones de roles

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Permisos & roles y**, a continuación, en **Azure AD**, seleccione **Roles**.

3. Seleccione uno de los siguientes roles para abrir su panel lateral:

   - Administrador global
   - Administrador de seguridad
   - Lector de seguridad

   > [!IMPORTANT]
   > Microsoft recomienda conceder a los usuarios acceso solo a lo que necesitan para realizar sus tareas. A este concepto se *le llama privilegios mínimos* para los permisos. Para obtener más información, vea [Procedimientos recomendados para el acceso con privilegios mínimos para las aplicaciones](/azure/active-directory/develop/secure-least-privileged-access). 

4. En el panel lateral, seleccione el **vínculo Administrar miembros en Azure AD**. Esta acción le lleva a Azure Active Directory (Azure AD) donde puede ver y administrar las asignaciones de roles.

5. Seleccione un usuario para abrir su perfil y, a continuación, elija **Roles asignados**.

   - Para agregar un rol, elija **+ Agregar asignaciones**.
   - Para quitar un rol, elija **X Quitar asignaciones**. 

## <a name="need-to-add-users"></a>¿Necesita agregar usuarios?

Si aún no ha agregado usuarios a la suscripción, consulte [Agregar usuarios y asignar licencias al mismo tiempo](../../admin/add-users/add-users.md).

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 3: Configurar notificaciones por correo electrónico](mdb-email-notifications.md)

- [Paso 4: Incorporar dispositivos a Microsoft Defender für Unternehmen](mdb-onboard-devices.md)