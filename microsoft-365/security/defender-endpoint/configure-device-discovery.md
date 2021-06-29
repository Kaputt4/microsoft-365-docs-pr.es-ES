---
title: Configuración de la detección de dispositivo
description: Obtenga información sobre cómo configurar la detección de dispositivos Microsoft 365 Defender con la detección básica o estándar
keywords: básico, estándar, configurar la detección de puntos de conexión, la detección de dispositivos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e1efeff77657e04223b21d639a0a09287f3707cc
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177590"
---
# <a name="configure-device-discovery"></a>Configuración de la detección de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

La detección se puede configurar para que esté en modo estándar o básico. Usa la opción estándar para buscar activamente dispositivos en tu red, lo que garantizará mejor la detección de puntos de conexión y proporcionará una clasificación de dispositivos más enriquecte. 

Puedes personalizar la lista de dispositivos que se usan para realizar la detección estándar. Puedes habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente, solo dispositivos Windows 10) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo. 


> [!IMPORTANT]
> Para obtener una vista previa, primero tendrás que activar las características de vista previa en Centro de seguridad de Microsoft Defender.
> A continuación, puedes acceder a la configuración de detección de dispositivos Microsoft 365 centro de seguridad. La lista de dispositivos no administrados y recomendaciones de seguridad estará disponible en el centro de seguridad de Centro de seguridad de Microsoft Defender y Microsoft 365, mientras que los iconos del panel solo estarán disponibles en Microsoft 365 centro de seguridad.


Siga los siguientes pasos de configuración en Microsoft 365 de seguridad:

1.  Vaya a **Configuración > detección de dispositivos**.
2.  Selecciona el modo de detección que quieres usar en los dispositivos integrados. 
3.  Si has seleccionado usar la detección estándar, selecciona qué dispositivos usar para el sondeo activo: todos los dispositivos o en un subconjunto especificando sus etiquetas de dispositivo.
4. Haga clic en **Guardar**.


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Excluir dispositivos de ser sondeados activamente en la detección estándar
Si hay dispositivos en la red que no deben examinarse activamente (por ejemplo, dispositivos usados como almacenes de miel para otra herramienta de seguridad), también puede definir una lista de exclusiones para evitar que se puedan examinar. Ten en cuenta que los dispositivos aún se pueden detectar mediante el modo de detección básico. Esos dispositivos se detectarán pasivamente, pero no se sondean activamente. 

## <a name="select-networks-to-monitor"></a>Seleccionar redes para supervisar
 Microsoft Defender para endpoint analiza una red y determina si es una red corporativa que debe supervisarse o una red no corporativa que se puede ignorar. Las redes corporativas suelen elegirse para supervisarse. Sin embargo, puedes invalidar esta decisión si eliges supervisar redes no corporativas donde se encuentran dispositivos incorporados. 

Puedes configurar dónde se puede realizar la detección de dispositivos especificando qué redes supervisar. Cuando se supervisa una red, se puede realizar la detección de dispositivos en ella. 

En la página Redes supervisadas se muestra una lista de redes en las que se puede realizar la detección **de** dispositivos. 


>[!NOTE]
> Solo las 50 redes principales (según el número de dispositivos asociados) estarán disponibles en la lista de red. 


La lista de redes supervisadas se ordena en función del número total de dispositivos vistos en la red en los últimos 7 días.


Puede aplicar un filtro para ver cualquiera de los siguientes estados de detección de red:

- **Redes supervisadas:** redes donde se realiza la detección de dispositivos.
- **Redes ignoradas:** se omitirá esta red y no se realizará la detección de dispositivos en ella.
- **All:** se mostrarán las redes supervisadas e ignoradas. 


### <a name="configure-the-network-monitor-state"></a>Configurar el estado del monitor de red
Controlas dónde se realiza la detección de dispositivos. Las redes supervisadas es donde se realizará la detección de dispositivos y normalmente son redes corporativas. También puede elegir omitir las redes o seleccionar la clasificación de detección inicial después de modificar un estado. 

Elegir la clasificación de detección inicial significa aplicar el estado predeterminado del monitor de red hecho por el sistema. Seleccionar el estado predeterminado del monitor de red hecho por el sistema significa que las redes que se identificaron como corporativas, se supervisarán y las identificadas como no corporativas se omitirán automáticamente.
 
1. Seleccione **Configuración > Detección de dispositivos**.
2. Seleccione **Redes supervisadas**. 
3. Ver la lista de redes. 
4. Seleccione los tres puntos junto al nombre de red. 
5. Elija si desea supervisar, omitir o usar la clasificación de detección inicial. 
    
    > [!WARNING]
    >- La elección de supervisar una red que no se identificó por Microsoft Defender para Endpoint como una red corporativa puede provocar la detección de dispositivos fuera de la red corporativa y, por lo tanto, detectar dispositivos hogareños u otros dispositivos no corporativos. 
    > - Si se elige omitir una red, se dejará de supervisar y detectar dispositivos en esa red. Los dispositivos que ya se detectaron no se quitarán del inventario, pero ya no se actualizarán y los detalles se conservarán hasta que expire el período de retención de datos de Defender for Endpoint.
    > - Antes de elegir supervisar redes no corporativas, debe asegurarse de que tiene permiso para hacerlo. <br>


6. Confirme que desea realizar el cambio. 


## <a name="explore-devices-in-the-network"></a>Explorar dispositivos en la red

Puede usar la siguiente consulta de búsqueda avanzada para obtener más contexto sobre cada nombre de red descrito en la lista de redes. La consulta enumera todos los dispositivos incorporados que se conectaron a una red determinada en los últimos 7 días.



```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"


```

## <a name="see-also"></a>Vea también
- [Información general de la detección de dispositivo](device-discovery.md)
- [Preguntas frecuentes sobre detección de dispositivos](device-discovery-faq.md)