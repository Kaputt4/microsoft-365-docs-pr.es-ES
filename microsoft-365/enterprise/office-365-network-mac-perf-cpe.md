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
# <a name="microsoft-365-informed-network-routing-preview"></a>Enrutamiento de red informado de Microsoft 365 (versión preliminar)

El enrutamiento de red informado es una característica que integra diversas aplicaciones de Microsoft 365 con soluciones de red definida por software (SD-WAN) de terceros para optimizar y mejorar la conectividad de red con los puntos de conexión de servicio de Microsoft. La conectividad SD-WAN optimizada puede mejorar el rendimiento y las experiencias del usuario.

>[!IMPORTANT]
>El enrutamiento de red informado de Microsoft 365 se encuentra actualmente en estado de versión preliminar. Para obtener más información sobre esta vista previa, incluidas las instrucciones para recibir asistencia, consulte [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Información general

El enrutamiento de red informado proporciona un canal de uso compartido de datos bidireccional entre Microsoft y la solución SD-WAN. Para cada ubicación de oficina y circuito de Internet que configure, Microsoft comparte periódicamente comentarios con la solución SD-WAN sobre la calidad de las experiencias de aplicación de Microsoft 365 seleccionadas para el tráfico de red asociado a cada circuito de Internet específico. Con estos comentarios, la solución SD-WAN puede realizar acciones de recuperación inteligentes enrutando el tráfico de aplicaciones de Microsoft 365 a través de vínculos disponibles alternativos. 

Las degradaciones de la calidad del servicio en la ruta de acceso de un circuito de Internet determinado, como el aumento de la latencia o la pérdida elevada de paquetes, son difíciles de detectar de forma continua. Estas degradaciones pueden ser perjudiciales para las experiencias del usuario para aplicaciones como Exchange Online, SharePoint, OneDrive y Microsoft Teams. Los síntomas comunes incluyen una búsqueda lenta de contenido de Exchange, tiempos de transferencia elevados al interactuar con bibliotecas de documentos de SharePoint o OneDrive, o mala calidad de llamadas o reuniones en Microsoft Teams.

El mecanismo de comentarios y recuperación en el enrutamiento informado de red busca detectar dinámicamente estos problemas casi en tiempo real e informa a la solución SD-WAN implementada para que tome medidas de recuperación automática.

El canal de uso compartido de datos también se usa para recibir periódicamente datos de óptica de nivel de red de la solución SD-WAN, incluida la información de configuración y las estadísticas de uso asociadas con el dispositivo y los circuitos conectados. No se recopila ni almacena información personal. Toda la información recopilada se agrega a ubicaciones de oficinas y circuitos de Internet conectados. Esta información puede ayudar a Microsoft a resolver de forma más eficaz y eficaz los problemas notificados con el uso de servicios y aplicaciones de Microsoft 365.

>[!NOTE]
>El enrutamiento de red informado de Microsoft 365 admite inquilinos en la nube comercial de WW, pero no las nubes GCC Moderate, GCC High, DoD, Germany o China.

## <a name="requirements"></a>Requirements

### <a name="integrated-sd-wan-solutions"></a>Soluciones SD-WAN integradas

Microsoft está trabajando con varios partners para habilitar la integración con el enrutamiento de red informado de Microsoft 365. Entre las soluciones habilitadas actualmente se incluyen las siguientes:

| Device Maker | Nombre de la solución | Versión mínima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topología de red

Actualmente, el enrutamiento de red informado identifica el tráfico asociado con una ubicación de oficina específica y un circuito de Internet en función de la dirección IP pública usada para enviar tráfico de red a Microsoft. 

En el caso de que no haya al menos un circuito de red que proporcione acceso directo a Internet en una ubicación de sucursal, es posible que el enrutamiento con información de red no proporcione un valor significativo.

### <a name="application-usage"></a>Uso de la aplicación

Los datos de la experiencia de la aplicación (reflejados a través de métricas de calidad de red) se recopilan mediante el uso de Microsoft Outlook en dispositivos que ejecutan Windows, Teams, SharePoint y OneDrive. No se tiene en cuenta otro tráfico de aplicación al evaluar el estado de un circuito de red.

## <a name="enabling-informed-network-routing"></a>Habilitar el enrutamiento de red informado

La habilitación del enrutamiento de red informado requiere varios pasos, algunos de los cuales deberán realizarse dentro de la interfaz de configuración de la solución SD-WAN. Consulta a tu proveedor de soluciones SD-WAN para obtener instrucciones sobre cómo iniciar el proceso de habilitar el enrutamiento informado de red dentro de la solución SD-WAN antes de continuar con la configuración en el Centro de administración de Microsoft 365.

Cuando esté listo para habilitar el enrutamiento de red informado en el Centro de administración de Microsoft 365, asegúrese de que tiene los permisos de administrador global necesarios.

>[!IMPORTANT]
>Para proporcionar los permisos de aplicaciones de nivel de inquilino necesarios para que la solución SD-WAN seleccionada tenga acceso al canal de uso compartido de datos de enrutamiento de red informado, debe realizar los siguientes pasos como administrador global.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Paso 1: Abrir las opciones de configuración de la solución SD-WAN

En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com/)seleccione Estado > **conectividad** de red en el panel de navegación izquierdo.

En esta sección del centro de administración se proporcionan métricas de conectividad de red agregadas para su organización y instrucciones sobre cómo mejorar la conectividad. Consulte Conectividad de red en el Centro de administración de [Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md) para obtener información adicional sobre estas características disponibles en el centro de administración.

Selecciona **Configuración > solución SD-WAN** para abrir el panel de configuración de enrutamiento de red informado. Las otras opciones que aparecen en **Configuración** se aplican a las instrucciones generales de conectividad de red en el centro de administración y no son necesarias para habilitar el enrutamiento de red informado.

En el panel de configuración, **selecciona Agregar la solución SD-WAN (versión preliminar).**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Paso 2: Seleccionar la solución SD-WAN y la ubicación de almacenamiento de datos

En los cuadros desplegables, selecciona la solución SD-WAN que has implementado y la ubicación donde quieres almacenar los datos asociados con el enrutamiento informado de red. Vea la [sección de almacenamiento de](#data-storage) datos para obtener información adicional.

Seleccione **Siguiente**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Paso 3: Aceptar términos para compartir datos

Lee cuidadosamente y confirma los términos proporcionados asociados con el uso compartido de datos entre Microsoft y la solución SD-WAN seleccionada y, a continuación, selecciona la casilla indicada.

Seleccione **Siguiente**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Paso 4: Conceder permisos a la solución SD-WAN

Este paso iniciará una solicitud de concesión de permisos con Azure Active Directory (Azure AD). Se le solicita que conceda permisos de nivel de inquilino que permitan a la solución SD-WAN seleccionada acceder al almacenamiento de datos de enrutamiento de red informado y a la información de estado del servicio asociada con su inquilino. Esta acción requiere permisos de rol de administrador global.

Selecciona el **vínculo Conceder permiso a esta aplicación** y sigue las solicitudes de Azure AD.

Una vez que haya completado la concesión de permisos, seleccione **Siguiente**.

### <a name="step-5-confirm-your-configuration-settings"></a>Paso 5: Confirmar las opciones de configuración

El último paso para habilitar el enrutamiento informado de red para su espacio empresarial es una página de confirmación que muestra la configuración que ha proporcionado. 

El enrutamiento de red informado ahora está habilitado para su espacio empresarial.

Selecciona **Listo y,** a continuación, cierra el panel de configuración de la solución SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configuración del enrutamiento informado de red

Realizarás gran parte de la configuración para el enrutamiento de red informado dentro de la solución SD-WAN, como configurar cómo se debe enrutar el tráfico en circunstancias normales y las rutas alternativas que se deben usar si se detectan problemas. Consulta a tu proveedor de soluciones SD-WAN para obtener más información sobre estos pasos de configuración.

Cada ubicación de la oficina debe configurarse en el Centro de administración de Microsoft 365 para que el enrutamiento de red informado pueda identificar correctamente el tráfico asociado con los circuitos de red que proporcionan conectividad a estas ubicaciones.

Las ubicaciones de Office pueden detectarse automáticamente como parte de la colección continua de telemetría de red de Microsoft. Como resultado, es posible que algunas ubicaciones se rellenen previamente en el centro de administración de su espacio empresarial. 

Si estas ubicaciones son precisas, solo tendrá que habilitar la característica de enrutamiento de red informado para cada ubicación deseada y configurar los circuitos de Internet y sus direcciones IP públicas. 

Si las ubicaciones detectadas automáticamente no son precisas o no hay ubicaciones rellenadas previamente en el espacio empresarial, tendrá que agregar o editar las ubicaciones manualmente para reflejar una topología precisa de su organización.

### <a name="updating-locations"></a>Actualización de ubicaciones

Las ubicaciones de su espacio empresarial se pueden encontrar en la **pestaña Ubicaciones.** Las ubicaciones se pueden editar directamente en la lista o actualizarse mediante un archivo CSV.

Asegúrese de que cada ubicación de la oficina en la que desea habilitar el enrutamiento de red informado esté presente en esta lista.

>[!NOTE]
>Las columnas de la **lista ubicaciones** para los ejemplos recopilados y otra información relacionada con la evaluación no están relacionadas con la característica de enrutamiento de red informado.

### <a name="enabling-a-location-for-informed-network-routing"></a>Habilitar una ubicación para el enrutamiento de red informado

1. En la **lista Ubicaciones,** seleccione **Editar** en el menú acciones rápidas para abrir el panel de configuración de ubicaciones.

2. Seleccione Usar enrutamiento de red informado de **Microsoft 365 en esta ubicación.**

3. Agregue todos los circuitos de red que proporcionan conectividad a Internet a esta ubicación de la oficina en los **intervalos** de direcciones IP de salida en esta sección de ubicación de la oficina. Asegúrese de que cada circuito está asociado a las subredes de direcciones IP públicas únicas que representan el tráfico de red.

4. Seleccione **Guardar** para guardar los cambios.

## <a name="disabling-network-informed-routing"></a>Deshabilitar el enrutamiento informado de red

La característica de enrutamiento de red informado puede deshabilitarse para todo el inquilino mediante el restablecimiento de la configuración de la solución SD-WAN. Aunque esto detendrá todo el procesamiento de datos en Microsoft 365, también debe deshabilitar el enrutamiento informado de red dentro del centro de administración.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Paso 1: Abrir las opciones de configuración de la solución SD-WAN

En el [Centro de administración de Microsoft 365,](https://admin.microsoft.com/) seleccione Estado > **conectividad** de red en el panel de navegación izquierdo.

Selecciona **Configuración > solución SD-WAN** para abrir el panel de configuración de enrutamiento de red informado.

El panel de configuración muestra un resumen de la solución SD-WAN configurada actualmente.

### <a name="step-2-reset-your-configuration"></a>Paso 2: Restablecer la configuración

En el panel de configuración, selecciona **Restablecer la configuración de la solución SD-WAN.**

La configuración se ha restablecido y se ha deshabilitado el enrutamiento de red informado. Puede volver a habilitarlo en cualquier momento siguiendo los pasos descritos en [Habilitar el enrutamiento de red informado.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Almacenamiento de datos

Los datos intercambiados entre Microsoft y el proveedor de soluciones SD-WAN se almacenan en la ubicación de almacenamiento de datos seleccionada durante la habilitación inicial del enrutamiento informado de red. Las opciones de ubicación de almacenamiento de datos representan áreas geográficas que contienen las regiones de Microsoft Azure donde se almacenan los datos.

>[!NOTE]
>Durante la fase de vista previa, la única ubicación de almacenamiento de datos disponible es **Norteamérica.** Las ubicaciones de almacenamiento de datos adicionales estarán disponibles antes de la disponibilidad general del enrutamiento de red informado.

Los datos se conservan en esta ubicación durante un máximo de 30 días. Cuando se deshabilita, todos los datos restantes se quitan dentro de esta ventana de retención de 30 días.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de administración de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md)

[Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)](office-365-network-mac-location-services.md)
