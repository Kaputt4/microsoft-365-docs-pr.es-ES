---
title: Informe de estado del sensor de estado del dispositivo & informe del sistema operativo
description: Use el informe de estado del dispositivo para realizar un seguimiento del estado del dispositivo, las plataformas del sistema operativo y las versiones de Windows 10.
keywords: estado de mantenimiento, antivirus, plataforma del sistema operativo, versión de Windows 10, versión, estado, cumplimiento, estado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/06/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: 611fa76162094b8dd24a56c92f7f3b9b6e75a635
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68168409"
---
# <a name="device-health-sensor-health--os-report"></a>Estado del dispositivo, informe de estado del sensor & sistema operativo

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

El informe Estado del dispositivo proporciona información sobre los dispositivos de la organización. El informe incluye información de tendencias que muestra el estado de mantenimiento del sensor, el estado del antivirus, las plataformas del sistema operativo, las versiones de Windows 10 y Microsoft Defender versiones de actualización del antivirus.

> [!IMPORTANT]
> Para que Windows&nbsp;Server 2012 R2&nbsp;y Windows&nbsp;Server&nbsp;2016 aparezcan en los informes de estado del dispositivo, estos dispositivos deben incorporarse mediante el paquete de solución unificado&nbsp;moderno. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

En el panel de navegación del panel de seguridad de Microsoft 365, seleccione **Informes** y, a continuación, abra **Estado y cumplimiento del dispositivo**.

- La [pestaña **Estado del sensor & sistema operativo**](#sensor-health--os-tab) proporciona información general del sistema operativo, dividida en tres tarjetas que muestran los siguientes atributos de dispositivo:
  - [Tarjeta de estado del sensor](#sensor-health-card)
  - [Tarjeta de sistemas operativos y plataformas](#operating-systems-and-platforms-card)
  - [Tarjeta de versiones de Windows](#windows-versions-card)

## <a name="report-access-permissions"></a>Permisos de acceso de informes

Para acceder al informe de cumplimiento de antivirus y estado del dispositivo en el panel seguridad de Microsoft 365, se requieren los siguientes permisos:

| Nombre del permiso | Tipo de permiso |
|:---|:---|
| Ver datos | Administración de amenazas y vulnerabilidades (TVM) |

Para asignar estos permisos:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta con el administrador de seguridad o Administrador global rol asignado.
1. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).
1. Seleccione el rol que desea editar.
1. Seleccione **Editar**.
1. En **Editar rol**, en la pestaña **General** , en **Nombre del** rol, escriba un nombre para el rol.
1. En **Descripción** , escriba un breve resumen del rol.
1. En **Permisos**, seleccione **Ver datos** y, en **Ver datos** , seleccione **Administración de amenazas y vulnerabilidades** (TVM).

Para obtener más información sobre la administración de roles de usuario, consulte [Creación y administración de roles para el control de acceso basado en rol](user-roles.md).

## <a name="sensor-health--os-tab"></a>Pestaña del sistema operativo & estado del sensor

El estado del sensor y las tarjetas del sistema operativo informan sobre el estado general del sistema operativo, que incluye el estado del sensor de detección, los sistemas operativos actualizados frente a los obsoletos y las versiones Windows 10.

>:::image type="content" source="images/device-health-sensor-health-os-tab.png" alt-text="Muestra información sobre el estado del sensor y el sistema operativo." lightbox="images/device-health-sensor-health-os-tab.png":::

Cada una de las tres tarjetas de la pestaña **Estado del sensor** tiene dos secciones de informes: _Estado actual_ y _tendencias del dispositivo_, presentadas como gráficos:

### <a name="current-state-graph"></a>Gráfico de estado actual

En cada tarjeta, el estado Actual (al que se hace referencia en alguna documentación como _Resumen del dispositivo_) es el gráfico de barras horizontal superior. El estado actual es una instantánea que muestra la información recopilada sobre los dispositivos de su organización, con el ámbito del día actual. Este gráfico representa la distribución de dispositivos en toda la organización que notifican el estado o se detectan que están en un estado específico.

>:::image type="content" source="images/device-health-sensor-health-os-current-state-graph.png" alt-text="Muestra el gráfico de estado actual." lightbox="images/device-health-sensor-health-os-current-state-graph.png":::

### <a name="device-trends-graph"></a>Gráfico de tendencias de dispositivos

El gráfico inferior de cada una de las tres tarjetas no se denomina, pero se conoce normalmente como _tendencias de dispositivos_. El gráfico de tendencias de dispositivos muestra la colección de dispositivos en toda la organización, a lo largo del intervalo de tiempo indicado directamente encima del gráfico.
De forma predeterminada, el gráfico tendencias del dispositivo muestra la información del dispositivo del período de 30 días, que termina en el último día completo. Para obtener una mejor perspectiva sobre las tendencias que se producen en su organización, puede ajustar el período de informes ajustando el período de tiempo mostrado. Para ajustar el período de tiempo, abra el filtro y seleccione un día de inicio y un día de finalización.

>:::image type="content" source="images/device-health-sensor-health-os-device-trends-graph.png" alt-text="Muestra el gráfico tendencias de las versiones de Device Health." lightbox="images/device-health-sensor-health-os-device-trends-graph.png":::

### <a name="filtering-data"></a>Filtrado de datos

Use los filtros proporcionados para incluir o excluir dispositivos con determinados atributos. Puede seleccionar varios filtros para aplicar desde los atributos del dispositivo. Cuando se aplica, los filtros se aplican a las tres tarjetas del informe.

Por ejemplo, para mostrar datos sobre Windows 10 dispositivos con estado de mantenimiento del sensor activo:

1. En Estado de **mantenimiento** >  del sensor **de filtros** > **activo**.
2. A continuación, seleccione **Plataformas** >  del sistema operativo **Windows 10**.
3. Seleccione **Aplicar**.

### <a name="sensor-health-card"></a>Tarjeta de estado del sensor

La tarjeta de estado del sensor muestra información sobre el estado del sensor en los dispositivos. El estado del sensor proporciona una vista agregada de los dispositivos que son:

- Activo
- Inactivo
- experimentando problemas de comunicaciones
- o donde no se notifica ningún dato del sensor

Los dispositivos que experimentan comunicaciones deterioradas o dispositivos desde los que no se detecta ningún dato de sensor podrían exponer a su organización a riesgos y justificar la investigación. Del mismo modo, los dispositivos que están inactivos durante períodos prolongados de tiempo podrían exponer su organización a amenazas debido a software obsoleto. Los dispositivos que están inactivos durante largos períodos de tiempo también garantizan la investigación.

> [!NOTE]
>
> En un pequeño porcentaje de casos, los números y distribuciones notificados al hacer clic en el gráfico de la barra de estado del sensor horizontal estarán fuera de sincronización con los valores que se muestran en la página **Inventario** de dispositivos. La disparidad de valores puede producirse porque los informes de estado del sensor tienen una cadencia de actualización diferente a la de la página Inventario de dispositivos.

### <a name="operating-systems-and-platforms-card"></a>Tarjeta de sistemas operativos y plataformas

Esta tarjeta muestra la distribución de los sistemas operativos y las plataformas que existen dentro de la organización.
_Los sistemas y plataformas del sistema operativo_ pueden proporcionar información útil sobre si los dispositivos de su organización ejecutan sistemas operativos actuales o obsoletos. Cuando se introducen nuevos sistemas operativos, se incluyen con frecuencia mejoras de seguridad que mejoran la posición de su organización frente a amenazas de seguridad.

Por ejemplo, el arranque seguro (introducido en Windows 8) prácticamente eliminó la amenaza de algunos de los tipos de malware más dañinos. Las mejoras en Windows 10 proporcionan a los fabricantes de equipos la opción de impedir que los usuarios deshabiliten el arranque seguro. Impedir que los usuarios deshabiliten el arranque seguro elimina casi cualquier posibilidad de que los rootkits malintencionados u otro malware de bajo nivel infecten el proceso de arranque.

Idealmente, el gráfico "Estado actual" muestra que el número de sistemas operativos se pondera en favor del sistema operativo más actual que las versiones anteriores. De lo contrario, el gráfico de tendencias indica que se están adoptando nuevos sistemas o que se están actualizando o reemplazando sistemas anteriores.

### <a name="windows-versions-card"></a>Tarjeta de versiones de Windows

La tarjeta Windows 10 versiones muestra la distribución de dispositivos Windows y sus versiones en su organización.
De la misma manera que una actualización de Windows 8 a Windows 10 mejora la seguridad de su organización, cambiar de versiones tempranas de Windows a versiones más actuales mejora su posición frente a posibles amenazas.

El gráfico de tendencias de la versión de Windows puede ayudarle a determinar rápidamente si su organización se mantiene al día actualizando a las versiones más recientes y seguras de Windows 10.

## <a name="see-also"></a>Vea también

[estado del antivirus de Microsoft Defender](device-health-microsoft-defender-antivirus-health.md#microsoft-defender-antivirus-health-tab)
