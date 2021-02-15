---
title: Información de actualización de seguridad de Windows
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941446"
---
# <a name="windows-security-update-insights"></a>Información de actualización de seguridad de Windows
En esta vista se proporciona información general sobre el estado de las actualizaciones de seguridad de los dispositivos de Escritorio administrado de Microsoft. 

Para ver los datos de uso, selecciona la pestaña <strong>Actualizaciones de seguridad de Windows.</strong>

![Panel de actualizaciones de seguridad de Windows: gráficos de barras del estado del dispositivo y la versión de actualización en la columna izquierda, el progreso de la implementación de actualización a lo largo del tiempo en la columna central y el porcentaje de dispositivos activos por grupo de implementación, así como el número de días que se han necesitado para alcanzar el objetivo de implementación del 95 % en la columna derecha.](../../media/update-insights.jpg)

## <a name="device-status"></a>Estado del dispositivo

Para que Windows Update actualice los dispositivos, deben estar conectados a Internet y no hibernarse durante un mínimo de seis horas, dos de las cuales deben ser continuas. Aunque es posible que se actualice un dispositivo que no cumpla estos requisitos, los dispositivos que los cumplan tienen la mayor probabilidad de actualizarse. 

Categorizamos la actividad del dispositivo en el contexto de Windows Update con estos términos:

- <strong>Activo:</strong> Dispositivos que cumplen los criterios mínimos de actividad (seis horas, dos continuas) para la versión de actualización de seguridad más reciente y que se han registrado con Microsoft Intune al menos cada cinco días
- <strong>Sincronizado:</strong> Dispositivos que se han registrado con Intune en los últimos 28 días
- <strong>Sin sincronización:</strong> Dispositivos que <i>no se</i> han registrado con Intune en los últimos 28 días




## <a name="update-version-status"></a>Actualizar el estado de la versión

Microsoft publica actualizaciones de seguridad cada segundo martes del mes. Cada versión agrega actualizaciones importantes para vulnerabilidades de seguridad conocidas. Escritorio administrado de Microsoft garantiza que el 95 % de sus dispositivos administrados se actualicen con la última actualización de seguridad disponible cada mes. A veces, las actualizaciones de seguridad se lanzan en otros momentos para abordar de forma urgente nuevas amenazas. Escritorio administrado de Microsoft implementa estas actualizaciones de forma similar.

Categorizamos el estado de las versiones de actualización de seguridad con estos términos:

- <strong>Actual:</strong> Dispositivos que ejecutan la actualización publicada en el mes actual
- <strong>Anterior:</strong> Dispositivos que ejecutan la actualización que se publicó el mes anterior
- <strong>Más antiguo:</strong> Dispositivos que ejecutan cualquier actualización de seguridad publicada antes del mes anterior

Debería ver pocos dispositivos en la categoría Anterior: una población grande o creciente probablemente indica un problema sistémico que debe notificar al Escritorio administrado de Microsoft para que podamos investigar. <strong></strong>


## <a name="deployment-progress"></a>Progreso de la implementación

Al principio de cada ciclo de lanzamiento de actualización de seguridad, Escritorio administrado de Microsoft toma una instantánea de la población del dispositivo y establece su destino de implementación en el 95 % de esa población. El <strong>área de progreso de</strong> la implementación muestra una tendencia histórica, actualizada diariamente, que hace un seguimiento de la proximidad con la que la implementación de la actualización cumple este objetivo para cada versión. Este gráfico solo muestra los dispositivos con estado Activo.

Puedes ver estos datos de ciclos de actualización anteriores mediante el menú desplegable de la esquina superior derecha. El período seleccionado en este menú se aplica a toda la información de toda la página.

El <strong>área De dispositivos activos</strong> actualizados por área de grupo de implementación ofrece una vista diferente mostrando el progreso de la instalación de la actualización para cada uno de los grupos de implementación de Escritorio administrado de Microsoft.

Los <strong>días para alcanzar el área</strong> de destino muestran el tiempo que se tardó en actualizar el 95 % del número total de dispositivos con la actualización de seguridad actual. Mientras la implementación está en curso, esta área muestra <strong>Aún</strong> actualizando hasta que se alcanza el objetivo del 95 % para la actualización seleccionada.

## <a name="device-details-area"></a>Área de detalles del dispositivo

La parte inferior del panel es una tabla que [](#device-status) muestra información detallada de los dispositivos, incluido el estado del dispositivo y el estado [de la versión de actualización.](#update-version-status) Puede buscar en esta lista o filtrarla por cualquier valor enumerado.


![Tabla de detalles del dispositivo que muestra las columnas para el nombre del dispositivo, el usuario asignado, el estado del dispositivo, la versión de actualización, la versión del sistema operativo y la fecha en que el dispositivo se sincronizó por última vez.](../../media/security-update-insights-device-table-sterile.png)
