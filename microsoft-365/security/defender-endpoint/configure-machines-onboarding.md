---
title: Incorporación de dispositivos a Microsoft Defender para punto de conexión
description: Realice un seguimiento de la incorporación de dispositivos administrados por Intune para Microsoft Defender para punto de conexión y aumente la tasa de incorporación.
keywords: onboard, Intune management, Microsoft Defender para punto de conexión, Microsoft Defender, Windows Defender, configuration management
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 8a4a97e082e0f3b6d129e8c1bf86c6918de29b89
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67678611"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Incorporación de dispositivos a Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Cada dispositivo incorporado agrega un sensor adicional de detección y respuesta de puntos de conexión (EDR) y aumenta la visibilidad sobre la actividad de infracciones en la red. La incorporación también garantiza que un dispositivo se pueda comprobar si hay componentes vulnerables, así como problemas de configuración de seguridad y puede recibir acciones de corrección críticas durante los ataques.

Antes de poder realizar un seguimiento y administrar la incorporación de dispositivos:

- [Inscribir los dispositivos en la administración de Intune](configure-machines.md#enroll-devices-to-intune-management)
- [Asegúrese de que tiene los permisos necesarios.](configure-machines.md#obtain-required-permissions)

Vea este vídeo para obtener información sobre cómo incorporar fácilmente clientes con Microsoft Defender para punto de conexión.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr?rel=0]

## <a name="discover-and-track-unprotected-devices"></a>Detección y seguimiento de dispositivos no protegidos

La tarjeta **de incorporación** proporciona información general de alto nivel de la velocidad de incorporación comparando el número de dispositivos Windows que realmente se han incorporado a Defender para punto de conexión con el número total de dispositivos Windows administrados por Intune.

:::image type="content" source="images/secconmgmt_onboarding_card.png" alt-text="Tarjeta de incorporación de administración de configuración de dispositivos" lightbox="images/secconmgmt_onboarding_card.png":::

*Tarjeta que muestra los dispositivos incorporados en comparación con el número total de dispositivos Windows administrados por Intune*

> [!NOTE]
> Si ha usado Configuration Manager, el script de incorporación u otros métodos de incorporación que no usan perfiles Intune, es posible que encuentre discrepancias de datos. Para resolver estas discrepancias, cree un perfil de configuración de Intune correspondiente para la incorporación de Defender para punto de conexión y asígnelo a los dispositivos.

## <a name="onboard-more-devices-with-intune-profiles"></a>Incorporación de más dispositivos con perfiles de Intune

Defender para punto de conexión proporciona varias opciones prácticas para [la incorporación de dispositivos Windows](onboard-configure.md). Sin embargo, en el caso de los dispositivos administrados por Intune, puede aprovechar los perfiles de Intune para implementar cómodamente el sensor de Defender para punto de conexión para seleccionar dispositivos, incorporando de forma eficaz estos dispositivos al servicio.

En la tarjeta **Incorporación**, seleccione **Incorporar más dispositivos** para crear y asignar un perfil en Intune. El vínculo le lleva a la página de cumplimiento del dispositivo en Intune, que proporciona una información general similar del estado de incorporación.

:::image type="content" source="images/secconmgmt_onboarding_1deviceconfprofile.png" alt-text="Página de cumplimiento de dispositivos de Microsoft Defender para punto de conexión en Intune administración de dispositivos" lightbox="images/secconmgmt_onboarding_1deviceconfprofile.png":::

*Microsoft Defender para punto de conexión página de cumplimiento de dispositivos en Intune administración de dispositivos*

> [!TIP]
> Como alternativa, puede navegar a la página Cumplimiento de incorporación de Defender para punto de conexión en [Microsoft Azure Portal](https://portal.azure.com/) desde **Todos los servicios > Intune > Cumplimiento de dispositivos > ATP de Microsoft Defender**.

> [!NOTE]
> Si desea ver los datos del dispositivo más actualizados, haga clic en **Lista de dispositivos sin sensor ATP**.

En la página cumplimiento del dispositivo, cree un perfil de configuración específicamente para la implementación del sensor de Defender para punto de conexión y asígnelo a los dispositivos que quiera incorporar. Para ello, puede hacer lo siguiente:

- Seleccione **Crear un perfil de configuración de dispositivo para configurar el sensor ATP** para que comience con un perfil de configuración de dispositivo predefinido.
- Cree el perfil de configuración del dispositivo desde cero.

Para obtener más información, [lea sobre el uso de Intune perfiles de configuración de dispositivos para incorporar dispositivos a Defender para punto de conexión](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Asegurarse de que los dispositivos estén configurados de manera adecuada](configure-machines.md)
- [Aumento del cumplimiento de la línea base de seguridad de Defender para punto de conexión](configure-machines-security-baseline.md)
- [Optimizar la implementación y las detecciones de reglas de ASR](configure-machines-asr.md)
