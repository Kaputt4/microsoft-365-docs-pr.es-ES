---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/12/2019
ms.openlocfilehash: fd0e0750332fa8f650cfc4756f8eb108be2a71df
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051131"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft

Después de realizar cambios en las categorías de configuración y ensayar una implementación, puede implementar y realizar un seguimiento del progreso de la implementación en el estado de la implementación. En esta página se muestra un resumen de cada configuración configurable. Abra una categoría de configuración para ver cada implementación y sus detalles, para implementar los cambios. 

## <a name="deployment-statuses"></a>Estados de implementación 

Estos son los statues que verá para cada implementación.

Estado  | Explicación 
--- | --- 
Implementar | El cambio está esperando a que se implemente en este anillo.
En curso | El cambio se aplica a los dispositivos de esta llamada. 
Completa | El cambio se aplica a los dispositivos de esta llamada. 
Failed | Se produjo un error en el cambio en un 10% de los dispositivos del anillo, por lo que se detuvo la implementación.<br><br> Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación. 
Revierten | El cambio se revirtió al último cambio que se implementó correctamente en todos los anillos de implementación.

## <a name="deploy-changes"></a>Implementar cambios

En estas instrucciones se mostrará la imagen de fondo del escritorio. Una vez que haya ensayado una implementación, implemente los cambios desde el estado de implementación. 

**Para implementar los cambios**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.
4. Seleccione **implementar** para implementar el cambio en uno de los anillos de implementación.

![Introducción al estado de implementación de configuración configurable](images/deploy-cs-overview.png)

Microsoft manAged Desktop recomienda la implementación en los anillos de implementación en este orden: test, First, Fast y, a continuación, amplio. 

Cuando se completen los cambios en cada timbre, el estado cambiará a **completa**.

![Implementación de la configuración configurable completada](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Revertir la implementación

En estas instrucciones se mostrará la imagen de fondo del escritorio. 

Después de implementar un cambio, puede revertir el estado de **implementación**. Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene. La configuración se revertirá a la última versión que se implementó en todos los anillos. 

**Para revertir un cambio**
1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.
4. En **es necesario revertir este cambio**, seleccione **revertir la implementación**.

![Reversión de implementación de la configuración configurable](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Otros recursos
- [Información general de configuración configurable](config-setting-overview.md)
- [Referencia de opciones conFigurables](config-setting-ref.md) 