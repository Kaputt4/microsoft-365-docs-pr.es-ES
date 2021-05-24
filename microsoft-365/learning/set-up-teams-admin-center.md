---
title: Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
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
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625314"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración

> [!NOTE]
> La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial. 

El Teams instala Viva Learning (versión preliminar) y aplica directivas de permisos a través del centro Teams administración.

1. Para Public Preview, primero debe establecer la directiva Update. Para obtener más información, vea el Teams de Microsoft Teams [Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Inicie sesión en el Centro Teams administración.

    2. Seleccione **Teams**  >  **actualizar directivas**.

    3. Seleccione **Agregar**. 

    4. Asigne un nombre a la directiva de actualización, agregue una directiva y active **Mostrar características de vista previa.**

2. El administrador debe notificar a los usuarios la actualización de directivas para que muevan su compilación a Public Preview para Teams. 

    1. El usuario debe seleccionar su imagen de perfil --> Acerca de --> vista previa pública.
   
        ![Navegación superior en la Teams que muestra el perfil del usuario](../media/learning/learning-app-select-profile-teams.png)
    
    2. El usuario debe aceptar los términos de versión preliminar pública.

        ![Cambiar a la compilación de vista previa pública](../media/learning/learning-app-switch-to-public-preview.png)
 
3. Para las organizaciones que tienen directivas restrictivas y necesitan habilitar Viva Learning, siga el proceso en la siguiente sección.

## <a name="manage-settings-for-viva-learning-preview"></a>Administrar la configuración de Viva Learning (versión preliminar)

Debe ser administrador en el centro de administración Teams para realizar estas tareas.

Para que Viva Learning (versión preliminar) esté disponible para los usuarios de su organización, siga estos pasos:

1. En la navegación izquierda del Centro Teams administración, ve a **Teams aplicaciones Administrar**  >  **aplicaciones**.

   ![Navegación izquierda en el Centro Teams administración que muestra Teams aplicaciones y administrar aplicaciones.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *Viva learning* y, a continuación, seleccione Viva **Learning (vista previa).**

   ![Página Administrar aplicaciones en el centro Teams administración que muestra el cuadro de búsqueda.](../media/learning/learning-app-teams-manage-apps-page.png)

3. En la **página Viva Learning (versión preliminar):**

   1. En **Estado**, seleccione **Permitido** activar Viva Learning (versión preliminar).

   2. En la **Configuración,** en Configuración de la **aplicación,** vaya al Centro de administración de Microsoft 365 para configurar orígenes [de contenido de aprendizaje.](content-sources-365-admin-center.md)

   ![Página de aprendizaje en el Centro Teams administración que muestra la sección Estado y configuración de la aplicación.](../media/learning/learning-app-teams-learning-page.png)

4. Después **de** administrar la  configuración  de la aplicación, ve a Directivas de permisos y directivas de configuración para conceder permiso a los empleados que deben tener acceso a Viva Learning (versión preliminar) como parte de la participación de la organización en la versión preliminar.

> [!NOTE]
>  Si su organización está en ring 4.0 como parte del programa TAP100 de Teams, es posible que necesite habilitar a los usuarios aprobados en ring 3.0 para tener acceso a Viva Learning (versión preliminar). <br><br>Como parte de la vista previa, Viva Learning (versión preliminar) se publica en Ring 3.0. Si su organización está en anillo 4.0, no verá Viva Learning (versión preliminar) en la **página Administrar aplicaciones.** Para probar la aplicación, debes crear una directiva de permisos de aplicaciones personalizadas, establecerla en **Permitir** todas las aplicaciones y asignarla a los usuarios aprobados de Ring 3.0. <br><br>   ![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Paso siguiente

[Configurar orígenes de contenido de aprendizaje para Viva Learning (versión preliminar) en el Centro Microsoft 365 administración](content-sources-365-admin-center.md)
