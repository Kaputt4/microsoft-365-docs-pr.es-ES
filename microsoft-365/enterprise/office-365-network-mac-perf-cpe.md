---
title: Enrutamiento de red informado de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Enrutamiento de red informado de Microsoft 365
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749556"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Enrutamiento de red informado de 365 de Microsoft (versión preliminar)

El enrutamiento de red informado es una característica que integra varias aplicaciones de Microsoft 365 con soluciones de red (SD-WAN) de software de terceros con el fin de optimizar y mejorar la conectividad de red a los puntos de conexión del servicio de Microsoft. La conectividad SD-WAN optimizada puede dar como resultado una mejor experiencia de usuario y rendimiento.

>[!IMPORTANT]
>El enrutamiento de red informado de Microsoft 365 se encuentra actualmente en estado de versión preliminar. Para obtener más información sobre esta vista previa, incluidas las instrucciones para recibir asistencia, consulte [Microsoft 365 informativo](https://go.microsoft.com/fwlink/?linkid=2151565)sobre el enrutamiento de red.

## <a name="overview"></a>Información general

El enrutamiento de red informado proporciona un canal bidireccional de uso compartido de datos entre Microsoft y la solución SD-WAN. Por cada ubicación de oficina e circuito de Internet que configure, Microsoft comparte comentarios periódicamente con la solución SD-WAN sobre la calidad de la experiencia de aplicación de Microsoft 365 seleccionada para el tráfico de red asociado con cada circuito de Internet específico. Con estos comentarios, la solución SD-WAN puede realizar acciones de recuperación inteligente mediante el enrutamiento del tráfico de aplicación de Microsoft 365 a través de vínculos alternativos disponibles. 

Las degradaciones de calidad de servicio en la ruta de acceso de un circuito de Internet determinado, como la latencia aumenta o la pérdida de paquetes elevados, son difíciles de detectar de manera continua. Estas degradaciones pueden perjudicar a las experiencias de los usuarios en aplicaciones como Exchange Online, SharePoint, OneDrive y Microsoft Teams. Entre los síntomas más comunes se incluyen la búsqueda lenta de contenido de Exchange, los tiempos de transferencia elevados al interactuar con bibliotecas de documentos de SharePoint o OneDrive, o la calidad de llamadas o reuniones deficientes en Microsoft Teams.

El mecanismo de comentarios y recuperación dentro del enrutamiento informativo de red busca detectar de forma dinámica estos problemas casi en tiempo real e informa a la solución SD-WAN implementada para que realice acciones de recuperación automáticas.

El canal de uso compartido de datos también se usa para recibir periódicamente datos de medios ópticos en el nivel de red de la solución SD-WAN, incluida la información de configuración y las estadísticas de uso asociadas con el dispositivo y los circuitos conectados. No se recopila ni almacena información personal. Toda la información recopilada se agrega a las ubicaciones de Office y a los circuitos de Internet conectados. Esta información puede ayudar a Microsoft a resolver problemas notificados de forma más eficaz y eficaz con el uso de las aplicaciones y los servicios de Microsoft 365.

>[!NOTE]
>El enrutamiento de red informado de Microsoft 365 admite espacios empresariales en la nube WW, pero no las nubes de GCC moderada, GCC High, DoD, Germany o China.

## <a name="requirements"></a>Requisitos

### <a name="integrated-sd-wan-solutions"></a>Soluciones SD-WAN integradas

Microsoft trabaja con varios socios para habilitar la integración con el enrutamiento de red informativo de Microsoft 365. Las soluciones actualmente habilitadas son las siguientes:

| Fabricante de dispositivos | Nombre de la solución | Versión mínima |
| --- | --- | --- |
| Cisco | [XE IOS SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topología de red

El enrutamiento de red informado identifica el tráfico asociado con una ubicación específica de la oficina y el circuito de Internet en función de la dirección IP pública usada para enviar tráfico de red a Microsoft. 

En el caso de que no haya al menos un circuito de red que proporcione acceso directo a Internet en una ubicación de sucursal, es posible que el enrutamiento informativo de red no ofrezca un valor significativo.

### <a name="application-usage"></a>Uso de aplicaciones

Los datos de experiencia de la aplicación (reflejados a través de métricas de calidad de red) se recopilan mediante el uso de Microsoft Outlook en dispositivos que ejecutan Windows, Teams, SharePoint y OneDrive. No se tiene en cuenta el tráfico de otras aplicaciones al evaluar el estado de un circuito de red.

## <a name="enabling-informed-network-routing"></a>Habilitar el enrutamiento de red informado

Habilitar el enrutamiento de la red informada requiere varios pasos, algunos de los cuales deben realizarse en la interfaz de configuración de la solución SD-WAN. Consulte con el proveedor de la solución SD-WAN para obtener instrucciones sobre cómo iniciar el proceso de habilitar el enrutamiento informativo de red dentro de la solución SD-WAN antes de continuar con la configuración en el centro de administración de Microsoft 365.

Una vez que esté preparado para habilitar el enrutamiento de red informado en el centro de administración de Microsoft 365, asegúrese de que dispone de los permisos de administrador global necesarios.

>[!IMPORTANT]
>Para proporcionar el consentimiento necesario de los permisos de las aplicaciones de nivel de inquilino para la solución SD-WAN seleccionada para tener acceso al canal de uso compartido de datos de enrutamiento de red, debe realizar los siguientes pasos como administrador global.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Paso 1: abrir las opciones de configuración de la solución SD-WAN

En el [centro de administración de Microsoft 365](https://admin.microsoft.com/), seleccione **Estado > conectividad de red** en el panel de navegación izquierdo.

En esta sección del centro de administración se proporcionan métricas de conectividad de red agregadas para la organización y se proporciona información sobre cómo mejorar la conectividad. Consulte [conectividad de red en el centro de administración de 365 de Microsoft (versión preliminar)](office-365-network-mac-perf-overview.md) para obtener información adicional sobre estas características disponibles en el centro de administración.

Seleccione **configuración > solución SD-WAN** para abrir el panel Configuración de enrutamiento de red informada. Las otras opciones que aparecen en **configuración** se aplican a la guía de conectividad de red general en el centro de administración y no son necesarias para habilitar el enrutamiento de red informado.

En el panel Configuración, seleccione **Agregar la solución SD-WAN (versión preliminar)**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Paso 2: seleccionar la solución SD-WAN y la ubicación de almacenamiento de datos

En los cuadros desplegables, seleccione la solución SD-WAN que ha implementado y la ubicación donde desea que se almacenen los datos asociados con el enrutamiento informado de la red. Vea la sección [almacenamiento de datos](#data-storage) para obtener información adicional.

Seleccione **Siguiente**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Paso 3: aceptar términos para el uso compartido de datos

Lea atentamente los términos proporcionados asociados con el uso compartido de datos entre Microsoft y su solución SD-WAN seleccionada y, a continuación, active la casilla indicada.

Seleccione **Siguiente**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Paso 4: conceder permisos para la solución SD-WAN

En este paso se iniciará una solicitud de concesión de permisos con Azure Active Directory (Azure AD). Se le pedirá que conceda permisos de nivel de inquilino que permitan a su solución SD-WAN seleccionada acceso al almacenamiento de datos de enrutamiento de red informado y a la información de estado del servicio asociada con su espacio empresarial. Esta acción requiere permisos de rol de administrador global.

Seleccione el vínculo **conceder permisos para esta aplicación** y siga las solicitudes de Azure ad.

Una vez que haya completado la concesión de permisos, seleccione **siguiente**.

### <a name="step-5-confirm-your-configuration-settings"></a>Paso 5: confirmar las opciones de configuración

El último paso para habilitar el enrutamiento informativo de red para el espacio empresarial es una página de confirmación que muestra la configuración que ha proporcionado. 

El enrutamiento de red informado ya está habilitado para su espacio empresarial.

Seleccione **listo** y, a continuación, cierre el panel Configuración de la solución SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configuración del enrutamiento de información de red

Realizará gran parte de la configuración para el enrutamiento de red informada dentro de la solución SD-WAN, por ejemplo, configurar cómo se debe enrutar el tráfico en circunstancias normales y las rutas alternativas que se deben usar si se detectan problemas. Consulte con el proveedor de la solución SD-WAN para obtener más información sobre estos pasos de configuración.

Cada ubicación de Oficina debe estar configurada en el centro de administración de Microsoft 365 para que el enrutamiento de red informado pueda identificar correctamente el tráfico asociado con los circuitos de red que proporcionan conectividad a estas ubicaciones.

Las ubicaciones de oficina se pueden detectar automáticamente como parte de la recopilación constante de Microsoft sobre la telemetría de red. Como resultado, puede que algunas ubicaciones se rellenen previamente en el centro de administración de su espacio empresarial. 

Si estas ubicaciones son exactas, simplemente tendrá que habilitar la característica de enrutamiento de red informada para cada ubicación deseada y configurar los circuitos de Internet y sus direcciones IP públicas. 

Si las ubicaciones detectadas automáticamente no son exactas o no hay ubicaciones que se han rellenado previamente en el espacio empresarial, tendrá que agregar o editar las ubicaciones manualmente para reflejar una topología precisa de la organización.

### <a name="updating-locations"></a>Ubicaciones de actualización

Las ubicaciones de su espacio empresarial se pueden encontrar en la pestaña **ubicaciones** . Las ubicaciones pueden editarse directamente en la lista o actualizarse con un archivo CSV.

Asegúrese de que en esta lista están presentes todas las ubicaciones de oficinas en las que desea habilitar el enrutamiento de red informada.

>[!NOTE]
>Las columnas de la lista de **ubicaciones** para los ejemplos recopilados y otra información relacionada con la evaluación no están relacionadas con la característica de enrutamiento de red informada.

### <a name="enabling-a-location-for-informed-network-routing"></a>Habilitación de una ubicación para el enrutamiento de red informado

1. En la lista **ubicaciones** , seleccione **Editar** en el menú acciones rápidas para abrir el panel Configuración de ubicación.

2. Seleccione **usar el enrutamiento de red informado de Microsoft 365 en esta ubicación**.

3. Agregue todos los circuitos de red que proporcionan conectividad a Internet con esta ubicación de la oficina en la sección **Ubicación de direcciones IP de salida en esta ubicación de oficina** . Asegúrese de que cada circuito está asociado a las subredes de direcciones IP públicas únicas que representan el tráfico de red.

4. Seleccione **Guardar** para guardar los cambios.

## <a name="disabling-network-informed-routing"></a>Deshabilitar el enrutamiento informativo de red

La característica de enrutamiento de red informada puede estar deshabilitada para todo el espacio empresarial restableciendo la configuración de la solución SD-WAN. Aunque esto detendrá todo el procesamiento de datos dentro de Microsoft 365, también debe deshabilitar el enrutamiento informado de red dentro del centro de administración.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Paso 1: abrir las opciones de configuración de la solución SD-WAN

En el [centro de administración de Microsoft 365](https://admin.microsoft.com/) , seleccione **Estado > conectividad de red** en el panel de navegación izquierdo.

Seleccione **configuración > solución SD-WAN** para abrir el panel Configuración de enrutamiento de red informada.

El panel de configuración muestra un resumen de la solución SD-WAN configurada actualmente.

### <a name="step-2-reset-your-configuration"></a>Paso 2: restablecer la configuración

En el panel Configuración, seleccione **restablecer la configuración de la solución SD-WAN**.

La configuración se ha restablecido y se ha informado de que el enrutamiento de red se ha deshabilitado. Puede volver a habilitarla en cualquier momento siguiendo los pasos descritos en [Enabling disformated Network Routing](#enabling-informed-network-routing).

## <a name="data-storage"></a>Almacenamiento de datos

Los datos que se intercambian entre Microsoft y el proveedor de soluciones SD-WAN se almacenan en la ubicación de almacenamiento de datos seleccionada durante la habilitación inicial del enrutamiento de información de red. Las opciones de ubicación de almacenamiento de datos representan áreas geográficas que contienen las regiones de Microsoft Azure en las que se almacenan los datos.

>[!NOTE]
>Durante la fase de vista previa, la única ubicación de almacenamiento de datos disponible es **Norteamérica**. Las ubicaciones de almacenamiento de datos adicionales estarán disponibles antes de la disponibilidad general del enrutamiento de red informado.

Los datos se conservan en esta ubicación hasta 30 días. Cuando está deshabilitado, se quitan todos los datos restantes dentro de esta ventana de retención de 30 días.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el centro de administración de 365 de Microsoft (versión preliminar)](office-365-network-mac-perf-overview.md)

[Servicios de ubicación de conectividad de red 365 de Microsoft (versión preliminar)](office-365-network-mac-location-services.md)
