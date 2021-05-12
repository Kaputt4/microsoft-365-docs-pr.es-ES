---
title: Configurar Microsoft Viva Learning (versión preliminar) en el Centro de administración de Teams
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
description: Obtenga información sobre cómo configurar Microsoft Viva Learning (versión preliminar) en el Centro de administración de Teams.
ms.openlocfilehash: 40e659796b22097f42515c0cbb704bdaa4ccc972
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333523"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurar Microsoft Viva Learning (versión preliminar) en el Centro de administración de Teams

> [!NOTE]
> La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial. 

El administrador de Teams instala Viva Learning (versión preliminar) y aplica directivas de permisos a través del Centro de administración de Teams.

## <a name="manage-settings-for-viva-learning-preview"></a>Administrar la configuración de Viva Learning (versión preliminar)

Debe ser administrador en el Centro de administración de Teams para realizar estas tareas.

Para que Viva Learning (versión preliminar) esté disponible para los usuarios de su organización, siga estos pasos:

1. En la navegación izquierda del Centro de administración de Teams, ve a **Aplicaciones de Teams** Administrar  >  **aplicaciones.**

   ![Navegación izquierda en el Centro de administración de Teams que muestra las aplicaciones de Teams y la sección Administrar aplicaciones.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *Viva learning* y, a continuación, seleccione Viva **Learning (vista previa).**

   ![Página Administrar aplicaciones en el Centro de administración de Teams que muestra el cuadro de búsqueda.](../media/learning/learning-app-teams-manage-apps-page.png)

3. En la **página Viva Learning (versión preliminar):**

   1. En **Estado**, seleccione **Permitido** activar Viva Learning (versión preliminar).

   2. En la **pestaña Configuración,** en **Configuración de la** aplicación, vaya al Centro de administración de Microsoft 365 para configurar orígenes de contenido de [aprendizaje.](content-sources-365-admin-center.md)

   ![Página de aprendizaje en el Centro de administración de Teams que muestra la sección Estado y configuración de la aplicación.](../media/learning/learning-app-teams-learning-page.png)

4. Después **de** administrar la  configuración  de la aplicación, ve a Directivas de permisos y directivas de configuración para conceder permiso a los empleados que deben tener acceso a Viva Learning (versión preliminar) como parte de la participación de la organización en la versión preliminar.

> [!NOTE]
>  Si su organización está en anillo 4.0 como parte del programa TAP100 de Teams, es posible que deba habilitar a los usuarios aprobados en anillo 3.0 para tener acceso a Viva Learning (versión preliminar). <br><br>Como parte de la vista previa, Viva Learning (versión preliminar) se publica en Ring 3.0. Si su organización está en anillo 4.0, no verá Viva Learning (versión preliminar) en la **página Administrar aplicaciones.** Para probar la aplicación, debes crear una directiva de permisos de aplicaciones personalizadas, establecerla en **Permitir** todas las aplicaciones y asignarla a los usuarios aprobados de Ring 3.0. <br><br>   ![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Paso siguiente

[Configurar orígenes de contenido de aprendizaje para Viva Learning (versión preliminar) en el Centro de administración de Microsoft 365](content-sources-365-admin-center.md)