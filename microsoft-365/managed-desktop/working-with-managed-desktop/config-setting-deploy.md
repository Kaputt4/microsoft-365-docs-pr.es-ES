---
title: Implementar la configuración configurable en El escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en Microsoft Managed Desktop.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, implementación, implementación por fases, configuración configurable
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: a52995ff9ab2f946ca11417d4ed7bfa13825353f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326790"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implementar y realizar un seguimiento de la configuración configurable: Escritorio administrado de Microsoft

Después de realizar cambios en las categorías de configuración y la fase de una implementación, la página Estado de implementación le permite empezar a implementar la configuración en grupos. Esta página muestra un resumen de cada configuración configurable. Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.

## <a name="deployment-statuses"></a>Estados de implementación

Los siguientes son los estados que verá para cada implementación.

Estado | Explicación
--- | ---
Implementar | El cambio está a la espera de implementarse en este grupo.
En curso | El cambio se aplica a los dispositivos activos de este grupo.
Completo | El cambio completado en todos los dispositivos activos de este grupo.
Error | Error en el cambio en el 10 % de los dispositivos activos del grupo. La implementación se detuvo.<br><br> Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de Escritorio administrado de Microsoft para solucionar problemas de la implementación.
Reverted | El cambio se reviró al último cambio que se implementó correctamente en todos los grupos de implementación.

## <a name="deploy-changes"></a>Implementar cambios

Por ejemplo, usaremos una imagen de fondo de escritorio en estas instrucciones. Una vez que haya realizado una implementación, implemente los cambios desde la página Estado de implementación.

**Para implementar cambios:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el **área de trabajo Estado de** implementación, seleccione la configuración que desea implementar. A continuación, seleccione la implementación por fases que se implementará.
4. Seleccione **Implementar** para implementar el cambio en uno de los grupos de implementación.

> [!NOTE]
> El icono de precaución naranja indica que hay un grupo anterior disponible para la implementación, ya que se recomienda implementar en orden.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Se recomienda implementar en grupos de implementación en este orden: Test, First, Fast y, a continuación, Broad.

Cuando los cambios se completan en cada grupo, el estado cambia a **Completado**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Revertir implementación

Después de implementar un cambio, puede revertir desde **el estado de implementación**. Cuando se revierte un cambio que está **en curso** o **completado**, se detiene la implementación actual. La configuración volverá a la última versión que se implementó en todos los grupos.

Por ejemplo, revertiremos la imagen en segundo plano del escritorio.

**Para revertir un cambio:**

1. Inicie sesión para [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
2. En la sección Escritorio administrado de Microsoft, **seleccione Configuración**.
3. En el **área de trabajo Estado de** implementación, seleccione la configuración que desea revertir. A continuación, seleccione la implementación por fases que desea revertir.
4. En **¿Necesita revertir este cambio?**, seleccione **Revertir implementación**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Recursos adicionales

- [Introducción a la configuración configurable](config-setting-overview.md)
- [Referencia de parámetros configurables](config-setting-ref.md)
