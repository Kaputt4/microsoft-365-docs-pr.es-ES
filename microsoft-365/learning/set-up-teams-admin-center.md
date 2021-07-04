---
title: Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Obtenga información sobre cómo configurar Microsoft Viva Learning (versión preliminar) en el centro Teams administración.
ms.openlocfilehash: 99e63210e8f8c10e3721c35fb69df7880c7e1929
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290224"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración

> [!NOTE]
> La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial. 

El Teams debe realizar determinados pasos para habilitar Viva Learning (versión preliminar) para sus usuarios en el espacio empresarial. Estos pasos varían en función de cómo se habilita el espacio empresarial: [*Vista previa*](set-up-teams-admin-center.md#public-preview-tenants) pública o Vista [ *previa privada* (o Beta).](set-up-teams-admin-center.md#private-preview-tenants)

## <a name="public-preview-tenants"></a>Inquilinos de vista previa pública

### <a name="administrator-steps-for-public-preview-tenants"></a>Pasos de administrador para inquilinos de vista previa pública

Dado que viva Learning (versión preliminar) todavía no está disponible en general, se requieren ciertos pasos para habilitar las características y establecer permisos para usuarios o grupos específicos. 

1. Habilitar las características de vista previa pública para los Learning (versión preliminar) de Viva.

    a. Modifique Teams de actualización para habilitar las características de Vista previa pública. Vea [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).

    b. Habilite la directiva de actualización para los usuarios o grupos que realizarán las pruebas de Viva Learning (versión preliminar). Vea [Asignar directivas a usuarios y grupos.](/microsoftteams/assign-policies-users-and-groups)

2. Modifique la directiva de permisos de la aplicación para los Learning (versión preliminar) de Viva.

    a. A menos que actualmente forma parte de la directiva global, permita todas las aplicaciones de Microsoft en la directiva de permisos de la aplicación. Consulta [Administrar directivas de permisos de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-permission-policies). 

    b. Habilite la directiva de permisos de la aplicación para los usuarios o grupos que realizarán las pruebas de Viva Learning (versión preliminar). Vea [Asignar directivas a usuarios y grupos.](/microsoftteams/assign-policies-users-and-groups)

3. Notificar a los usuarios que probarán Viva Learning (versión preliminar) para cambiar su cliente de compilación a [Public Preview para Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).

> [!IMPORTANT]
> Para inquilinos de vista previa pública, Viva Learning (versión  preliminar) no se mostrará en aplicaciones administradas en el centro de administración de Teams hasta la versión final del producto. Sin embargo, los usuarios habilitados para la vista previa pública pueden encontrar Viva Learning (versión preliminar) en la tienda de aplicaciones de Teams y usarlo, una vez configuradas las directivas y permisos correctos.

### <a name="user-steps-for-public-preview-tenants"></a>Pasos de usuario para inquilinos de vista previa pública

Los usuarios que se han habilitado para las pruebas de vista previa pública (habilitando las directivas descritas [anteriormente)](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) deben cambiar a [Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) en su Teams cliente.

1. Los usuarios deben seleccionar su imagen de perfil > **Acerca de** la vista  >  **previa pública**.

    ![Navegación superior en la Teams que muestra el perfil del usuario](../media/learning/learning-app-select-profile-teams.png)

2. Los usuarios deben aceptar los términos y condiciones de Public Preview.

    ![Cambiar a la compilación de vista previa pública](../media/learning/learning-app-switch-to-public-preview.png)

3. Los usuarios ahora pueden encontrar Viva Learning (versión preliminar) en la Teams de aplicaciones y empezar a usarlo.

## <a name="private-preview-tenants"></a>Inquilinos de vista previa privada

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a>Pasos de administrador para inquilinos de versión preliminar privada (o beta)

Para los inquilinos de versión preliminar privada, no hay directivas adicionales que deba habilitarse. Sin embargo, Viva Learning (versión preliminar) debe estar disponible para los usuarios de la organización.

1. En la navegación izquierda del Centro Teams administración, ve a **Teams aplicaciones Administrar**  >  **aplicaciones**.

   ![Navegación izquierda en el Centro Teams administración que muestra Teams aplicaciones y administrar aplicaciones.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. En la página Administrar **aplicaciones,** en el cuadro de búsqueda, escriba *Viva Learning* y, a continuación, seleccione Viva **Learning (vista previa).**

   ![Página Administrar aplicaciones en el centro Teams administración que muestra el cuadro de búsqueda.](../media/learning/learning-app-teams-manage-apps-page.png)

3. En la **página Viva Learning (vista** previa),  en **Estado**, seleccione Permitido activar Viva Learning (vista previa).

   ![Learning página en el Centro Teams de administración que muestra la sección Estado y configuración de la aplicación.](../media/learning/learning-app-teams-learning-page.png)

<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a>Paso siguiente

[Configurar orígenes de contenido de aprendizaje para Viva Learning (versión preliminar) en el Centro de administración de Microsoft 365](content-sources-365-admin-center.md)
