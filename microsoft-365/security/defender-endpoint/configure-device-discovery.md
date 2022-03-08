---
title: Configuración de la detección de dispositivo
description: Obtenga información sobre cómo configurar la detección de dispositivos Microsoft 365 Defender con la detección básica o estándar
keywords: básico, estándar, configurar la detección de puntos de conexión, la detección de dispositivos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 77dbdb290a0f8643bd24e1a3c561b823e5c2e4b3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330599"
---
# <a name="configure-device-discovery"></a>Configuración de la detección de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


La detección se puede configurar para que esté en modo estándar o básico. Usa la opción estándar para buscar activamente dispositivos en tu red, lo que garantizará mejor la detección de puntos de conexión y proporcionará una clasificación de dispositivos más enriquecte.

Puedes personalizar la lista de dispositivos que se usan para realizar la detección estándar. Puede habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente, Windows 10 o posterior y solo dispositivos de Windows Server 2019 o posteriores) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo.

## <a name="set-up-device-discovery"></a>Configurar la detección de dispositivos

Para configurar la detección de dispositivos, siga los siguientes pasos de configuración <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">en Microsoft 365 Defender portal</a>:

Navegar a la **Configuración** >  **dispositivo**

1. Si quieres configurar Basic como modo de detección para usarlo en los dispositivos integrados, selecciona **Básico** y, a continuación, **selecciona Guardar**
2. Si has seleccionado usar la detección estándar, selecciona qué dispositivos usar para el sondeo activo: todos los dispositivos o en un subconjunto especificando sus etiquetas de dispositivo y, a continuación, selecciona **Guardar**

> [!NOTE]
>La detección estándar usa varios scripts de PowerShell para sondear activamente los dispositivos de la red. Esos scripts de PowerShell están firmados por Microsoft y se ejecutan desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`. Por ejemplo, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Excluir dispositivos de ser sondeados activamente en la detección estándar

Si hay dispositivos en la red que no deben examinarse activamente (por ejemplo, dispositivos que se usan como almacenes de miel para otra herramienta de seguridad), también puede definir una lista de exclusiones para evitar que se puedan examinar. Ten en cuenta que los dispositivos aún se pueden detectar mediante el modo de detección básico y también se pueden detectar a través de intentos de detección de multidifusión. Esos dispositivos se detectarán pasivamente, pero no se sondean activamente.

Puedes configurar los dispositivos que se excluirán en la **página Exclusiones** .

## <a name="select-networks-to-monitor"></a>Seleccionar redes para supervisar

Microsoft Defender para endpoint analiza una red y determina si es una red corporativa que debe supervisarse o una red no corporativa que se puede omitir. Para identificar una red como corporativa, correlacionamos los identificadores de red en todos los clientes del inquilino y si la mayoría de los dispositivos de la organización informan de que están conectados al mismo nombre de red, con la misma puerta de enlace predeterminada y la misma dirección del servidor DHCP, se supone que se trata de una red corporativa. Las redes corporativas suelen elegirse para supervisarse. Sin embargo, puedes invalidar esta decisión si eliges supervisar redes no corporativas donde se encuentran dispositivos incorporados.

Puedes configurar dónde se puede realizar la detección de dispositivos especificando qué redes supervisar. Cuando se supervisa una red, se puede realizar la detección de dispositivos en ella.

En la página Redes supervisadas se muestra una lista de redes en las que se puede realizar la detección **de** dispositivos.

> [!NOTE]
> La lista muestra las redes que se identificaron como redes corporativas. Si se identifican menos de 50 redes como redes corporativas, la lista mostrará hasta 50 redes con la mayoría de los dispositivos incorporados.

La lista de redes supervisadas se ordena en función del número total de dispositivos vistos en la red en los últimos 7 días.

Puede aplicar un filtro para ver cualquiera de los siguientes estados de detección de red:

- **Redes supervisadas** : redes donde se realiza la detección de dispositivos.
- **Redes ignoradas** : se omitirá esta red y no se realizará la detección de dispositivos en ella.
- **All** : se mostrarán las redes supervisadas e ignoradas.

### <a name="configure-the-network-monitor-state"></a>Configurar el estado del monitor de red

Controlas dónde se realiza la detección de dispositivos. Las redes supervisadas son donde se realizará la detección de dispositivos y normalmente son redes corporativas. También puede elegir omitir las redes o seleccionar la clasificación de detección inicial después de modificar un estado.

Elegir la clasificación de detección inicial significa aplicar el estado predeterminado del monitor de red hecho por el sistema. Seleccionar el estado predeterminado del monitor de red hecho por el sistema significa que las redes que se identificaron como corporativas, se supervisarán y las identificadas como no corporativas se omitirán automáticamente.

1. Selecciona **Configuración > detección de dispositivos**.
2. Seleccione **Redes supervisadas**.
3. Ver la lista de redes.
4. Seleccione los tres puntos junto al nombre de red.
5. Elija si desea supervisar, omitir o usar la clasificación de detección inicial.

    > [!WARNING]
    >
    > - La elección de supervisar una red que no se identificó por Microsoft Defender para Endpoint como una red corporativa puede provocar la detección de dispositivos fuera de la red corporativa y, por lo tanto, detectar dispositivos hogareños u otros dispositivos no corporativos.
    > - Si se elige omitir una red, se dejará de supervisar y detectar dispositivos en esa red. Los dispositivos que ya se detectaron no se quitarán del inventario, pero ya no se actualizarán y los detalles se conservarán hasta que expire el período de retención de datos de Defender for Endpoint.
    > - Antes de elegir supervisar redes no corporativas, debe asegurarse de que tiene permiso para hacerlo. <br>

6. Confirme que desea realizar el cambio.

## <a name="explore-devices-in-the-network"></a>Explorar dispositivos en la red

Puede usar la siguiente consulta de búsqueda avanzada para obtener más contexto sobre cada nombre de red descrito en la lista de redes. La consulta enumera todos los dispositivos incorporados que se conectaron a una red determinada en los últimos 7 días.

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="get-information-on-device"></a>Obtener información sobre el dispositivo

Puedes usar la siguiente consulta de búsqueda avanzada para obtener la información completa más reciente en un dispositivo específico.

```kusto
DeviceInfo
| where DeviceName == "<device name here>" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="see-also"></a>Vea también

- [Información general de la detección de dispositivo](device-discovery.md)
- [Preguntas frecuentes sobre detección de dispositivos](device-discovery-faq.md)
