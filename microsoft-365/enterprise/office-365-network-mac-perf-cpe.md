---
title: Microsoft 365 enrutamiento de red informado
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 enrutamiento de red informado
ms.openlocfilehash: fc946b3a1de057605b89bcadeb4e5b7269aebcb0
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622473"
---
# <a name="microsoft-365-informed-network-routing"></a>Microsoft 365 enrutamiento de red informado

El enrutamiento de red informado es una característica que integra varias aplicaciones de Microsoft 365 con soluciones de red definidas por software (SD-WAN) de terceros con el fin de optimizar y mejorar la conectividad de red con los puntos de conexión de servicio de Microsoft. La conectividad SD-WAN optimizada puede dar lugar a experiencias y rendimiento mejorados del usuario.

## <a name="overview"></a>Información general

El enrutamiento de red informado proporciona un canal de uso compartido de datos bidireccional entre Microsoft y la solución SD-WAN. Para cada ubicación de oficina y circuito de Internet que configure, Microsoft comparte periódicamente comentarios con la solución SD-WAN sobre la calidad de las experiencias de aplicación de Microsoft 365 seleccionadas para el tráfico de red asociado a cada circuito de Internet específico. Con estos comentarios, la solución SD-WAN puede realizar acciones de recuperación inteligente mediante el enrutamiento Microsoft 365 tráfico de aplicaciones a través de vínculos disponibles alternativos. 

La calidad de las degradaciones del servicio en la ruta de acceso de un circuito de Internet determinado, como el aumento de la latencia o la alta pérdida de paquetes, son difíciles de detectar de forma continua. Estas degradaciones pueden ser perjudiciales para las experiencias del usuario para aplicaciones como Exchange Online, SharePoint, OneDrive y Microsoft Teams. Los síntomas comunes incluyen búsqueda lenta de contenido Exchange, tiempos de transferencia elevados al interactuar con bibliotecas de documentos SharePoint o OneDrive, o una mala calidad de llamadas o reuniones en Microsoft Teams.

El mecanismo de comentarios y recuperación dentro del enrutamiento de red informado busca detectar dinámicamente estos problemas casi en tiempo real e informa a la solución SD-WAN implementada para realizar acciones de recuperación automática.

El canal de uso compartido de datos también se usa para recibir periódicamente datos ópticos de nivel de red de la solución SD-WAN, incluida la información de configuración y las estadísticas de uso asociadas con el dispositivo y los circuitos conectados. No se recopila ni almacena información personal. Toda la información recopilada se agrega a las ubicaciones de la oficina y a los circuitos de Internet conectados. Esta información puede ayudar a Microsoft a resolver de forma más eficaz y eficaz los problemas notificados con el uso de aplicaciones y servicios de Microsoft 365.

>[!NOTE]
>Microsoft 365 enrutamiento de red informado admite inquilinos en la nube comercial de WW, pero no las nubes GCC Moderada, GCC Alta, DoD, Alemania o China.

## <a name="requirements"></a>Requirements

### <a name="integrated-sd-wan-solutions"></a>Soluciones de SD-WAN integradas

Microsoft está trabajando con varios asociados para habilitar la integración con Microsoft 365 enrutamiento de red informado. Entre las soluciones habilitadas actualmente se incluyen las siguientes:

| Device Maker | Nombre de la solución | Versión mínima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topología de red

El enrutamiento de red informado identifica actualmente el tráfico asociado a una ubicación de oficina específica y a un circuito de Internet en función de la dirección IP pública que se usa para enviar tráfico de red a Microsoft. 

En el caso de que no haya al menos un circuito de red que proporcione acceso directo a Internet en una ubicación de sucursal, el enrutamiento de red informado puede no proporcionar un valor significativo.

### <a name="application-usage"></a>Uso de la aplicación

Los datos de la experiencia de la aplicación (que se reflejan a través de métricas de calidad de red) se recopilan mediante el uso de aplicaciones cliente específicas de Microsoft. Exchange métricas reflejan el uso del cliente de Outlook y algunos Outlook Web App uso. las métricas SharePoint y OneDrive reflejan el uso de los puntos de conexión de SharePoint específicos del inquilino, independientemente de la aplicación cliente. Teams métricas reflejan el uso del cliente de escritorio de Teams. No se tiene en cuenta otro tráfico de aplicación al evaluar el estado de un circuito de red.

## <a name="enabling-informed-network-routing"></a>Habilitación del enrutamiento de red informado

La habilitación del enrutamiento de red informado requiere varios pasos, algunos de los cuales tendrán que realizarse dentro de la interfaz de configuración de la solución SD-WAN. Consulte al proveedor de la solución SD-WAN para obtener instrucciones sobre cómo iniciar el proceso de habilitación del enrutamiento de red informado dentro de la solución SD-WAN antes de continuar con la configuración en el Centro de administración de Microsoft 365.

Una vez que esté listo para habilitar el enrutamiento de red informado en el Centro de administración de Microsoft 365, asegúrese de que tiene los permisos de administrador **global** o **Admin de usuario** necesarios.

>[!IMPORTANT]
>Para proporcionar el consentimiento de permisos de aplicaciones de nivel de inquilino necesarios para que la solución SD-WAN seleccionada acceda al canal de uso compartido de datos de enrutamiento de red informado, debe realizar los pasos siguientes como administrador global.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Paso 1: Abrir las opciones de configuración de la solución SD-WAN

En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/), seleccione **Estado > Conectividad de red** en el panel de navegación izquierdo.

En esta sección del centro de administración se proporcionan métricas de conectividad de red agregadas para su organización e instrucciones sobre cómo mejorar la conectividad. Consulte [Conectividad de red en el Centro de Administración de Microsoft 365](office-365-network-mac-perf-overview.md) para obtener información adicional sobre estas características disponibles en el centro de administración.

Seleccione **Configuración > solución SD-WAN** para abrir el panel de configuración de enrutamiento de red informado. Las otras opciones que aparecen en **Configuración** son aplicables a la guía general de conectividad de red del Centro de administración y no son necesarias para habilitar el enrutamiento de red informado.

En el panel de configuración, seleccione **Agregar la solución SD-WAN**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Paso 2: Seleccionar la solución SD-WAN y la ubicación de almacenamiento de datos

En los cuadros desplegables, seleccione la solución SD-WAN que ha implementado y la ubicación donde desea que se almacenen los datos asociados al enrutamiento de red informado. Consulte la sección [almacenamiento de datos](#data-storage) para obtener información adicional.

Seleccione **Siguiente**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Paso 3: Aceptar términos para compartir datos

Lea y confirme cuidadosamente los términos proporcionados asociados con el uso compartido de datos entre Microsoft y la solución SD-WAN seleccionada y, a continuación, active la casilla indicada.

Seleccione **Siguiente**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Paso 4: Concesión de permisos a la solución SD-WAN

Este paso iniciará una solicitud de concesión de permisos con Azure Active Directory (Azure AD). Se le pedirá que conceda permisos de nivel de inquilino que permitan a la solución SD-WAN seleccionada acceder al almacenamiento de datos de enrutamiento de red informado y a la información de estado del servicio asociada al inquilino. Esta acción requiere permisos de administrador de controlador de dominio de **Azure AD** o de **rol de administrador global** .

Seleccione el vínculo **Conceder permiso a esta aplicación** y siga las solicitudes de Azure AD.

Una vez que haya completado la concesión de permisos, seleccione **Siguiente**.

### <a name="step-5-confirm-your-configuration-settings"></a>Paso 5: Confirmar la configuración

El último paso para habilitar el enrutamiento de red informado para el inquilino es una página de confirmación que muestra la configuración que ha proporcionado. 

El enrutamiento de red informado ahora está habilitado para el inquilino.

Seleccione **Listo** y, a continuación, cierre el panel de configuración de la solución SD-WAN.

## <a name="configuring-informed-network-routing"></a>Configuración del enrutamiento de red informado

Realizará gran parte de la configuración para el enrutamiento de red informado dentro de la solución SD-WAN, como configurar cómo se debe enrutar el tráfico en circunstancias normales y las rutas de acceso alternativas que se deben usar si se detectan problemas. Consulte con el proveedor de soluciones de SD-WAN para obtener más información sobre estos pasos de configuración.

Cada ubicación de office debe configurarse en el Centro de administración de Microsoft 365 para que el enrutamiento de red informado pueda identificar correctamente el tráfico asociado a los circuitos de red que proporcionan conectividad a estas ubicaciones.

Office ubicaciones pueden detectarse automáticamente como parte de la recopilación continua de telemetría de red de Microsoft. Como resultado, es posible que algunas ubicaciones se rellenen previamente en el centro de administración del inquilino. 

Si estas ubicaciones son precisas, simplemente tendrá que habilitar la característica de enrutamiento de red informada para cada ubicación deseada y configurar los circuitos de Internet y sus direcciones IP públicas. 

Si las ubicaciones detectadas automáticamente no son precisas o no hay ubicaciones rellenadas previamente en el inquilino, tendrá que agregar o editar ubicaciones manualmente para reflejar una topología precisa de su organización.

### <a name="updating-locations"></a>Actualización de ubicaciones

Las ubicaciones del inquilino se pueden encontrar en la pestaña **Ubicaciones** . Las ubicaciones se pueden editar directamente en la lista o actualizarse mediante un archivo CSV.

Asegúrese de que cada ubicación de la oficina en la que desea habilitar el enrutamiento de red informado esté presente en esta lista.

>[!NOTE]
>Las columnas de la lista **Ubicaciones** de los ejemplos recopilados y otra información relacionada con la evaluación no están relacionadas con la característica de enrutamiento de red informada.

### <a name="enabling-a-location-for-informed-network-routing"></a>Habilitación de una ubicación para el enrutamiento de red informado

1. En la lista **Ubicaciones** , seleccione **Editar** en el menú acciones rápidas para abrir el panel de configuración de ubicación.

2. Seleccione **Usar Microsoft 365 enrutamiento de red informado en esta ubicación**.

3. Agregue todos los circuitos de red que proporcionan conectividad a Internet a esta ubicación de office en la Egress **intervalos de direcciones IP en esta sección de ubicación de la oficina**. Asegúrese de que cada circuito está asociado a las subredes de direcciones IP públicas únicas que representan el tráfico de red.

4. Seleccione **Guardar** para guardar los cambios.

## <a name="disabling-informed-network-routing"></a>Deshabilitación del enrutamiento de red informado

La característica de enrutamiento de red informada puede deshabilitarse para todo el inquilino mediante el restablecimiento de la configuración de la solución SD-WAN. Aunque esto detendrá todo el procesamiento de datos dentro de Microsoft 365, también debe deshabilitar el enrutamiento de red informado en el centro de administración.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Paso 1: Abrir las opciones de configuración de la solución SD-WAN

En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/) seleccione **Health > Network connectivity (Conectividad de red de Health >**) en el panel de navegación izquierdo.

Seleccione **Configuración > solución SD-WAN** para abrir el panel de configuración de enrutamiento de red informado.

En el panel de configuración se muestra un resumen de la solución SD-WAN configurada actualmente.

### <a name="step-2-reset-your-configuration"></a>Paso 2: Restablecer la configuración

En el panel de configuración, seleccione **Restablecer la configuración de la solución SD-WAN**.

La configuración se ha restablecido y se ha deshabilitado el enrutamiento de red informado. Puede volver a habilitarlo en cualquier momento siguiendo los pasos descritos en [Habilitación del enrutamiento de red informado](#enabling-informed-network-routing).

## <a name="data-storage"></a>Almacenamiento de datos

Los datos intercambiados entre Microsoft y el proveedor de soluciones SD-WAN se almacenan en la ubicación de almacenamiento de datos seleccionada durante la habilitación inicial del enrutamiento de red informado. Las opciones de ubicación de almacenamiento de datos representan áreas geográficas que contienen Microsoft Azure regiones donde se almacenan los datos.

Los datos se conservan en esta ubicación durante un máximo de 30 días. Cuando se deshabilita, todos los datos restantes se quitan dentro de esta ventana de retención de 30 días.

Los datos de esta ubicación se intercambian con la solución SD-WAN seleccionada y la ubicación de la solución SD-WAN configurada puede no estar dentro de la misma región. Los clientes deben trabajar con su proveedor de soluciones SD-WAN para evaluar los requisitos de ubicación de almacenamiento de datos antes de la implementación de producción.

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de administración de Microsoft 365](office-365-network-mac-perf-overview.md)

[Microsoft 365 Servicios de ubicación de conectividad de red](office-365-network-mac-location-services.md)
