---
title: Microsoft 365 Defender de zona horaria
description: Usa la información que se incluye aquí para configurar la configuración Microsoft 365 Defender zona horaria y ver la información de licencia.
keywords: configuración, Microsoft Defender, inteligencia de amenazas de ciberseguridad, Microsoft Defender para endpoint, zona horaria, utc, hora local, licencia
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4353bbfc0ce11c4a767ca599ecb23a1ab4f77a56
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214032"
---
# <a name="microsoft-365-defender-time-zone-settings"></a>Microsoft 365 Defender de zona horaria

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-settings-abovefoldlink)

Use el **icono Configuración de zona** horaria del menú Zona ![ horaria1.](images/atp-time-zone.png) para configurar la zona horaria y ver la información de licencia.

## <a name="time-zone-settings"></a>Configuración de zona horaria

El aspecto del tiempo es importante en la evaluación y el análisis de los ciberataques percibidos y reales.

Las investigaciones ciberforensicas suelen basarse en marcas de tiempo para unir la secuencia de eventos. Es importante que el sistema refleje la configuración de zona horaria correcta.

Microsoft Defender para endpoint puede mostrar la hora universal coordinada (UTC) o la hora local.

La configuración actual de zona horaria se muestra en la configuración de Microsoft Defender. Puede cambiar la zona horaria mostrada en el menú **Zona** horaria en **Configuración > Centro de seguridad**.

### <a name="utc-time-zone"></a>Zona horaria UTC

Microsoft Defender para endpoint usa la hora UTC de forma predeterminada.

Al establecer la zona horaria de Microsoft Defender para endpoint en UTC, se mostrarán todas las marcas de tiempo del sistema (alertas, eventos y otros) en UTC para todos los usuarios. Esto puede ayudar a los analistas de seguridad que trabajan en diferentes ubicaciones de todo el mundo a usar las mismas marcas de tiempo mientras investigan eventos.

### <a name="local-time-zone"></a>Zona horaria local

Puedes elegir que Microsoft Defender para endpoint use la configuración de zona horaria local. Todas las alertas y eventos se mostrarán con la zona horaria local.

La zona horaria local se toma de la configuración regional del dispositivo. Si cambia la configuración regional, también cambiará la zona horaria de Microsoft Defender para endpoint. Elegir esta configuración significa que las marcas de tiempo mostradas en Microsoft Defender para endpoint se alinearán a la hora local para todos los usuarios de Microsoft Defender para endpoint. Los analistas ubicados en diferentes ubicaciones globales ahora verán las alertas de Microsoft Defender para endpoint según su configuración regional.

Elegir usar la hora local puede ser útil si los analistas se encuentran en una única ubicación. En este caso, puede ser más fácil correlacionar eventos con la hora local, por ejemplo, cuando un usuario local hizo clic en un vínculo de correo electrónico sospechoso.

### <a name="set-the-time-zone"></a>Establecer la zona horaria

La zona horaria de Microsoft Defender para extremo se establece de forma predeterminada en UTC. Establecer la zona horaria también cambia las horas de todas las vistas de Microsoft Defender para puntos de conexión.

Para establecer la zona horaria:

1. Haga clic **en Configuración** menú en el icono Microsoft 365 Defender configuración de zona horaria del [Portal](https://security.microsoft.com/) ![ de contenido3. ](images/atp-time-zone.png) .
2. Seleccione **Centro de seguridad**.
3. Seleccione **Zona horaria** y establezca la zona horaria en UTC o en la zona horaria local.

### <a name="regional-settings"></a>Configuración regional

Para aplicar diferentes formatos de fecha para Microsoft Defender para Endpoint, usa la configuración regional para Internet Explorer (IE) y Microsoft Edge (Edge). Si usas otro explorador como Google Chrome, sigue los pasos necesarios para cambiar la configuración de hora y fecha de ese explorador. 

#### <a name="internet-explorer-ie-and-microsoft-edge"></a>Internet Explorer (IE) y Microsoft Edge

IE y Microsoft Edge la configuración **de** región configurada en la opción **Relojes, Idioma** y Región del panel de control. 

#### <a name="known-issues-with-regional-formats"></a>Problemas conocidos con formatos regionales

##### <a name="date-and-time-formats"></a>Formatos de fecha y hora

Hay algunos problemas conocidos con los formatos de fecha y hora. Si configura la configuración regional en cualquier otro formato que no sea compatible, es posible que el portal no refleje correctamente la configuración.

Se admiten los siguientes formatos de fecha y hora:

- Formato de fecha MM/dd/yyyy
- Formato de fecha dd/MM/yyyy
- Formato de hora hh:mm:ss (formato de 12 horas)

Actualmente no se admiten los siguientes formatos de fecha y hora:

- Formato de fecha yyyy-MM-dd
- Formato de fecha dd-MMM-yy
- Formato de fecha dd/MM/aa
- Formato de fecha MM/dd/aa
- Formato de fecha con yy. Solo se mostrará yyyy.
- Formato de hora HH:mm:ss (formato de 24 horas)

##### <a name="decimal-symbol-used-in-numbers"></a>Símbolo decimal usado en números

El símbolo decimal usado siempre es un punto, incluso si se selecciona una coma en la **configuración de** formato Números de la **configuración de** región. Por ejemplo, 15,5K se muestra como 15,5K.
