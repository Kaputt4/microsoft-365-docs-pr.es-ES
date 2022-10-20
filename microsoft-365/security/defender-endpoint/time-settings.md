---
title: Microsoft 365 Defender configuración de zona horaria
description: Use la información que se incluye aquí para configurar los Microsoft 365 Defender zona horaria y ver la información de licencia.
keywords: configuración, Microsoft Defender, inteligencia sobre amenazas de ciberseguridad, Microsoft Defender para punto de conexión, zona horaria, utc, hora local, licencia
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 86b5acf38969a3b110a6b3f7535c25569397d1ea
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636264"
---
# <a name="microsoft-365-defender-time-zone-settings"></a>Microsoft 365 Defender configuración de zona horaria

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-settings-abovefoldlink)

Use el menú **Zona horaria** para configurar la zona horaria y ver la información de licencia.
:::image type="content" source="images/atp-time-zone.png" alt-text="Configuración de la zona horaria-1" lightbox="images/atp-time-zone.png":::

## <a name="time-zone-settings"></a>Configuración de zona horaria

El aspecto del tiempo es importante en la evaluación y el análisis de ciberataques percibidos y reales.

Las investigaciones cibernéticas a menudo se basan en marcas de tiempo para unir la secuencia de eventos. Es importante que el sistema refleje la configuración de zona horaria correcta.

Microsoft Defender para punto de conexión puede mostrar la hora universal coordinada (UTC) o la hora local.

La configuración de zona horaria actual se muestra en el menú Microsoft Defender para punto de conexión. Puede cambiar la zona horaria mostrada en el menú **Zona horaria** .

:::image type="content" source="images/atp-time-zone-menu.png" alt-text="Configuración de la zona horaria-2" lightbox="images/atp-time-zone-menu.png":::

### <a name="utc-time-zone"></a>Zona horaria UTC

Microsoft Defender para punto de conexión usa la hora UTC de forma predeterminada.

Al establecer la zona horaria Microsoft Defender para punto de conexión en UTC se mostrarán todas las marcas de tiempo del sistema (alertas, eventos y otros) en UTC para todos los usuarios. Esto puede ayudar a los analistas de seguridad que trabajan en diferentes ubicaciones de todo el mundo a usar las mismas marcas de tiempo al investigar eventos.

### <a name="local-time-zone"></a>Zona horaria local

Puede elegir que Microsoft Defender para punto de conexión use la configuración de zona horaria local. Todas las alertas y eventos se mostrarán mediante la zona horaria local.

La zona horaria local se toma de la configuración regional del dispositivo. Si cambia la configuración regional, también cambiará la zona horaria Microsoft Defender para punto de conexión. La elección de esta configuración significa que las marcas de tiempo que se muestran en Microsoft Defender para punto de conexión se alinearán con la hora local para todos los usuarios Microsoft Defender para punto de conexión. Los analistas ubicados en diferentes ubicaciones globales verán ahora las alertas de Microsoft Defender para punto de conexión según su configuración regional.

La elección de usar la hora local puede ser útil si los analistas se encuentran en una sola ubicación. En este caso, podría ser más fácil correlacionar eventos con la hora local, por ejemplo, cuando un usuario local hace clic en un vínculo de correo electrónico sospechoso.

### <a name="set-the-time-zone"></a>Establecer la zona horaria

La zona horaria de Microsoft Defender para punto de conexión se establece de forma predeterminada en UTC. Al establecer la zona horaria también se cambian las horas de todas las vistas Microsoft Defender para punto de conexión.

Para establecer la zona horaria:

1. Haga clic en el menú **Zona horaria** .
   :::image type="content" source="images/atp-time-zone.png" alt-text="Configuración de la zona horaria-3" lightbox="images/atp-time-zone.png":::
1. Seleccione el indicador **de zona horaria UTC** .
1. Seleccione **Zona horaria UTC** o la zona horaria local, por ejemplo -7:00.

### <a name="regional-settings"></a>Configuración regional

Para aplicar diferentes formatos de fecha para Microsoft Defender para punto de conexión, use la configuración regional para Internet Explorer (IE) y Microsoft Edge (Edge). Si usa otro explorador, como Google Chrome, siga los pasos necesarios para cambiar la configuración de fecha y hora de ese explorador. 

#### <a name="internet-explorer-ie-and-microsoft-edge"></a>Internet Explorer (IE) y Microsoft Edge

IE y Microsoft Edge usan la configuración **región** configurada en la opción **Relojes, idioma y región** del panel de control. 

#### <a name="known-issues-with-regional-formats"></a>Problemas conocidos con formatos regionales

##### <a name="date-and-time-formats"></a>Formatos de fecha y hora

Hay algunos problemas conocidos con los formatos de fecha y hora. Si configura los valores regionales en cualquier cosa que no sea los formatos admitidos, es posible que el portal no refleje correctamente la configuración.

Se admiten los siguientes formatos de fecha y hora:

- Formato de fecha MM/dd/aaaa
- Formato de fecha dd/MM/aaaa
- Formato de hora hh:mm:ss (formato de 12 horas)

Actualmente no se admiten los siguientes formatos de fecha y hora:

- Formato de fecha aaaa-MM-dd
- Formato de fecha dd-MMM-aaaa
- Formato de fecha dd/MM/aaaa
- Formato de fecha MM/dd/aaaa
- Formato de fecha con yy. Sólo se mostrará yyyy.
- Formato de hora HH:mm:ss (formato de 24 horas)

##### <a name="decimal-symbol-used-in-numbers"></a>Símbolo decimal usado en números

El símbolo decimal usado siempre es un punto, incluso si se selecciona una coma en la configuración de formato **Números** en Configuración **de región** . Por ejemplo, 15 5 000 se muestra como 15,5 K.
