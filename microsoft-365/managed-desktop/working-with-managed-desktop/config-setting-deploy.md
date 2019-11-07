---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7e3827dc12c04d2c7952f9321a70714691c5ed47
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012305"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft

Después de realizar cambios en las categorías de configuración y ensayar una implementación, la página estado de implementación le permite comenzar a implementar la configuración en grupos. En esta página se muestra un resumen de cada configuración configurable. Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.

## <a name="deployment-statuses"></a>Estados de implementación 

Estos son los Estados que verá para cada implementación.

Estado  | Explicación 
--- | --- 
Implementar | El cambio está esperando a que se implemente en este grupo.
En curso | El cambio se aplica a los dispositivos activos en este grupo. 
Completar | El cambio se completó en todos los dispositivos activos de este grupo. 
Error | Se produjo un error en el cambio en un 10% de los dispositivos activos del grupo, por lo que se detuvo la implementación.<br><br> Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación. 
Revierten | El cambio se revirtió al último cambio que se implementó correctamente en todos los grupos de implementación.

## <a name="deploy-changes"></a>Implementar cambios

En estas instrucciones se mostrará la imagen de fondo del escritorio. Una vez que haya ensayado una implementación, implemente los cambios desde la página estado de la implementación. 

**Para implementar los cambios**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.
4. Seleccione **implementar** para implementar el cambio en uno de los grupos de implementación.

![Información general sobre](images/1deployedit.png) la implementación de opciones de estado de implementación Microsoft Managed Desktop recomienda la implementación en grupos de implementación en este orden: test, First, Fast y, a continuación, general. 

Cuando se completen los cambios en cada grupo, el estado cambiará a **completa**.

![Implementación de la configuración configurable completada](images/2completeedit.png)

## <a name="revert-deployment"></a>Revertir la implementación

Después de implementar un cambio, puede revertir el estado de **implementación**. Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene. La configuración se revertirá a la última versión que se implementó en todos los grupos. 

Mostraremos los pasos para revertir un cambio con la imagen de fondo de escritorio como ejemplo. 

**Para revertir un cambio**
1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.
4. En **es necesario revertir este cambio**, seleccione **revertir la implementación**.

![Reversión de implementación de la configuración configurable](images/3revert.png) 

## <a name="additional-resources"></a>Otros recursos
- [Información general de configuración configurable](config-setting-overview.md)
- [Referencia de parámetros configurables](config-setting-ref.md) 
