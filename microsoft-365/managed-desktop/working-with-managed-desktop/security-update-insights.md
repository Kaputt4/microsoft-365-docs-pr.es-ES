---
title: Información de actualización de seguridad de Windows
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341259"
---
# <a name="windows-security-update-insights"></a>Información de actualización de seguridad de Windows
En esta vista se proporciona información general sobre el estado de las actualizaciones de seguridad para los dispositivos de escritorio administrados por Microsoft. 

Para ver los datos de uso, seleccione la pestaña <strong>actualizaciones de seguridad de Windows</strong> .

![Panel de actualizaciones de seguridad de Windows: gráficos de barras del estado del dispositivo y versión de actualización en la columna izquierda, actualizar el progreso de la implementación a lo largo del tiempo en la columna central y el porcentaje de dispositivos activos por grupo de implementación, así como el número de días que se tarda en llegar a la implementación del 95% destino en la columna derecha.](../../media/update-insights.jpg)

## <a name="device-status"></a>Estado del dispositivo

Para que los dispositivos se actualicen mediante Windows Update, deben estar conectados a Internet y no hibernar durante un mínimo de seis horas, dos de los cuales deben ser continuos. Siempre que un dispositivo esté conectado y no esté en hibernación, se considerará que está "en uso". Aunque es posible que se actualice un dispositivo que no cumple estos requisitos, los dispositivos que los cumplen tendrán la probabilidad más alta de que se actualicen. 

Clasificamos la actividad de los dispositivos en el contexto de Windows Update con estos términos:

- <strong>Activo:</strong> Dispositivos que cumplen los criterios de uso mínimos (seis horas, dos continuas) para la versión de actualización de seguridad más reciente y que se han protegido con Microsoft Intune como mínimo cada cinco días
- <strong>Sincronizado:</strong> Dispositivos que se han protegido con Intune en los últimos 28 días
- No <strong>sincronizado:</strong> Dispositivos que <i>no</i> se han protegido con Intune en los últimos 28 días




## <a name="update-version-status"></a>Actualizar el estado de la versión

Microsoft publica actualizaciones de seguridad cada segundo martes del mes. Cada versión agrega actualizaciones importantes para las vulnerabilidades de seguridad conocidas. Microsoft Managed Desktop garantiza que el 95% de los dispositivos administrados se actualiza con la última actualización de seguridad disponible todos los meses. A veces, las actualizaciones de seguridad se publican en otras ocasiones para solucionar nuevas amenazas de forma urgente. Microsoft Managed Desktop implementa estas actualizaciones de manera similar.

Clasificamos el estado de las versiones de actualización de seguridad con estos términos:

- <strong>Actual:</strong> Dispositivos que ejecutan la actualización comercializada en el mes actual
- <strong>Anterior:</strong> Dispositivos que ejecutan la actualización que se ha lanzado en el mes anterior
- <strong>Anterior:</strong> Dispositivos que ejecutan cualquier actualización de seguridad que se haya lanzado antes del mes anterior

Debe ver pocos dispositivos en la categoría <strong>anterior</strong> : un llenado grande o en crecimiento probablemente indica un problema sistémico que debe informar al escritorio administrado por Microsoft para que podamos investigar.


## <a name="deployment-progress"></a>Progreso de la implementación

Al principio de cada ciclo de publicación de actualizaciones de seguridad, el escritorio administrado de Microsoft toma una instantánea de la población del dispositivo y establece su destino de implementación en el 95% de ese llenado. En el área progreso de la <strong>implementación</strong> se muestra una tendencia histórica, actualizada diariamente, que hace un seguimiento de la exactitud con que la implementación de la actualización cumple este objetivo para cada versión. Este gráfico solo muestra los dispositivos con estado activo.

Puede ver estos datos para ciclos de actualización anteriores mediante el menú desplegable de la esquina superior derecha. El período que seleccione en este menú se aplica a toda la información de toda la página.

El área de <strong>grupo de dispositivos activos actualizados por implementación</strong> ofrece una vista diferente al mostrar el progreso de la instalación de actualización de cada uno de los grupos de implementación de escritorio administrado por Microsoft.

La zona de <strong>destino días para llegar</strong> muestra el tiempo que tardó el 95% en actualizar el número total de dispositivos con la actualización de seguridad actual. Mientras se está llevando a cabo la implementación, en esta área se muestra la <strong>actualización</strong> hasta que se alcanza el destino 95% para la actualización seleccionada.

## <a name="device-details-area"></a>Área detalles del dispositivo

La parte inferior del panel es una tabla que muestra información detallada de los dispositivos, incluido el estado del [dispositivo](#device-status) y el estado de la [versión de actualización](#update-version-status). Puede buscar en esta lista o filtrarla por cualquier valor de la lista.


![Tabla detalles de dispositivo donde se muestran las columnas del nombre del dispositivo, el usuario asignado, el estado del dispositivo, la versión de actualización, la versión del sistema operativo y la fecha en que el dispositivo se sincronizó por última vez.](../../media/security-update-insights-device-table-sterile.png)
