---
title: Implementar la configuración configurable en Escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, implementación, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104539"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implementar y realizar un seguimiento de la configuración configurable: Escritorio administrado de Microsoft

Después de realizar cambios en las categorías de configuración y la fase de una implementación, la página Estado de implementación le permite empezar a implementar la configuración en grupos. Esta página muestra un resumen de cada configuración configurable. Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.

## <a name="deployment-statuses"></a>Estados de implementación 

Estos son los estados que verá para cada implementación.

Estado  | Explicación 
--- | --- 
Implementar | El cambio está a la espera de implementarse en este grupo.
En curso | El cambio se aplica a los dispositivos activos de este grupo. 
Completo | El cambio completado en todos los dispositivos activos de este grupo. 
Failed | El cambio no se pudo hacer en un 10 % de los dispositivos activos del grupo, por lo que se detuvo la implementación.<br><br> Se abrirá automáticamente una solicitud de soporte técnico con Escritorio administrado de Microsoft para solucionar problemas de la implementación. 
Reverted | El cambio se reviró al último cambio que se implementó correctamente en todos los grupos de implementación.

## <a name="deploy-changes"></a>Implementar cambios

Mostraremos la imagen de fondo del escritorio en estas instrucciones. Una vez que haya realizado una implementación, implemente los cambios desde la página Estado de implementación. 

**Para implementar cambios**

1. Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**
2. Busque la sección Escritorio administrado de Microsoft, seleccione **Configuración**.
3. En **área de trabajo** de estado de implementación, seleccione la configuración que desea implementar y, a continuación, seleccione la implementación por fases que desea implementar.
4. Seleccione **Implementar** para implementar el cambio en uno de los grupos de implementación.

> [!NOTE] 
> El icono de precaución naranja indica que hay un grupo anterior disponible para la implementación, ya que se recomienda implementar en orden. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Se recomienda implementar en grupos de implementación en este orden: Test, First, Fast y, a continuación, Broad. 

Cuando los cambios se completan en cada grupo, el estado cambia a **Complete**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Revertir implementación

Después de implementar un cambio, puede revertir desde **el estado de implementación**. Cuando se revierte un cambio que está **en curso** o **completado,** se detiene la implementación actual. La configuración volverá a la última versión que se implementó en todos los grupos. 

Mostraremos los pasos para revertir un cambio con la imagen en segundo plano de escritorio como ejemplo. 

**Para revertir un cambio**
1. Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**
2. Busque la sección Escritorio administrado de Microsoft, seleccione **Configuración**.
3. En **el área de trabajo** Estado de implementación, seleccione la configuración que desea revertir y, a continuación, seleccione la implementación por fases para revertir.
4. En **¿Necesita revertir este cambio?**, seleccione **Revertir implementación**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Recursos adicionales
- [Introducción a la configuración configurable](config-setting-overview.md)
- [Referencia de parámetros configurables](config-setting-ref.md) 
