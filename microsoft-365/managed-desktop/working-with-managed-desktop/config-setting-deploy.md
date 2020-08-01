---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530264"
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
Failed | Se produjo un error en el cambio en un 10% de los dispositivos activos del grupo, por lo que se detuvo la implementación.<br><br> Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación. 
Revierten | El cambio se revirtió al último cambio que se implementó correctamente en todos los grupos de implementación.

## <a name="deploy-changes"></a>Implementar cambios

En estas instrucciones se mostrará la imagen de fondo del escritorio. Una vez que haya ensayado una implementación, implemente los cambios desde la página estado de la implementación. 

**Para implementar los cambios**

1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.
4. Seleccione **implementar** para implementar el cambio en uno de los grupos de implementación.

> [!NOTE] 
> El icono de advertencia de color naranja indica que hay un grupo anterior disponible para la implementación, ya que se recomienda que se implemente en orden. 

![Área de trabajo de estado de implementación. Panel sitios de confianza a la derecha. En la sección grupos de implementación hay tres columnas: grupos de implementación, dispositivos y estado. En la columna Estado, se resalta "implementar".](../../media/1deployedit.png)
Se recomienda implementar en los grupos de implementación en este orden: probar, primero, rápido y, a continuación, general. 

Cuando se completen los cambios en cada grupo, el estado cambiará a **completa**.

![Área de trabajo del estado de implementación con columnas para la fecha actualizada, versión, prueba, primera, rápida y amplia. Se expande la fila del proxy, que muestra una configuración con fecha marcada como "completa" en cada uno de los cuatro grupos de implementación.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Revertir la implementación

Después de implementar un cambio, puede revertir el estado de **implementación**. Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene. La configuración se revertirá a la última versión que se implementó en todos los grupos. 

Mostraremos los pasos para revertir un cambio con la imagen de fondo de escritorio como ejemplo. 

**Para revertir un cambio**
1. Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)
2. En **configuración**, seleccione **configurable**.
3. En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.
4. En **¿necesita revertir este cambio?**, seleccione **revertir implementación**.

![Área de trabajo de estado de implementación. Páginas de inicio del explorador está seleccionada, abriendo un panel en el lado derecho con datos sobre el cambio enviado y su estado. En la parte inferior se encuentra el área "es necesario revertir este cambio" donde puede seleccionar "revertir la implementación".](../../media/3revert.png) 

## <a name="additional-resources"></a>Recursos adicionales
- [Información general de configuración configurable](config-setting-overview.md)
- [Referencia de parámetros configurables](config-setting-ref.md) 
