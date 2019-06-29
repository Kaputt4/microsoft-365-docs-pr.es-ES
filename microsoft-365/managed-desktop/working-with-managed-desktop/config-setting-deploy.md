---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: bfa769cab9f8d812fa2533232f66b0d4f8a4edb7
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390517"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft

Después de realizar cambios en las categorías de configuración y ensayar una implementación, la página estado de implementación le permite comenzar a implementar la configuración en grupos. En esta página se muestra un resumen de cada configuración configurable. Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.

## <a name="deployment-statuses"></a>Estados de implementación 

Estos son los statues que verá para cada implementación.

Estado  | Explicación 
--- | --- 
Implementación | El cambio está esperando a que se implemente en este grupo.
En curso | El cambio se aplica a los dispositivos activos en este grupo. 
Completar | El cambio se completó en todos los dispositivos activos de este grupo. 
Failed | Se produjo un error en el cambio en un 10% de los dispositivos activos del grupo, por lo que se detuvo la implementación.<br><br> Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación. 
Revierten | El cambio se revirtió al último cambio que se implementó correctamente en todos los grupos de implementación.

## <a name="deploy-changes"></a>Implementar cambios

En estas instrucciones se mostrará la imagen de fondo del escritorio. Una vez que haya ensayado una implementación, implemente los cambios desde la página estado de la implementación. 

**Para implementar los cambios**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.
4. Seleccione **implementar** para implementar el cambio en uno de los grupos de implementación.

![Introducción al estado de implementación de configuración configurable](images/deploy-cs-overview.png)

Microsoft Managed Desktop recomienda implementar en grupos de implementación en este orden: test, First, Fast y, a continuación, general. 

Cuando se completen los cambios en cada grupo, el estado cambiará a **completa**.

![Implementación de la configuración configurable completada](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Revertir la implementación

Después de implementar un cambio, puede revertir el estado de **implementación**. Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene. La configuración se revertirá a la última versión que se implementó en todos los grupos. 

Mostraremos los pasos para revertir un cambio con la imagen de fondo de escritorio como ejemplo. 

**Para revertir un cambio**
1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.
4. En **es necesario revertir este cambio**, seleccione **revertir la implementación**.

![Reversión de implementación de la configuración configurable](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Otros recursos
- [Información general de configuración configurable](config-setting-overview.md)
- [Referencia de opciones configurables](config-setting-ref.md) 
