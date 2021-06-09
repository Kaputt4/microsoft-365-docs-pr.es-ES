---
title: Obtener dispositivos incorporados a Microsoft Defender para endpoint
description: Realice un seguimiento de la incorporación de dispositivos administrados por Intune a Microsoft Defender para Endpoint y aumente la velocidad de incorporación.
keywords: onboard, administración de Intune, Microsoft Defender para endpoint, Microsoft Defender, Windows Defender, administración de configuración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841575"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Obtener dispositivos incorporados a Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Cada dispositivo incorporado agrega un sensor detección y respuesta de puntos de conexión (EDR) adicional y aumenta la visibilidad sobre la actividad de vulneración en la red. La incorporación también garantiza que un dispositivo se pueda comprobar si hay componentes vulnerables, así como problemas de configuración de seguridad y puede recibir acciones críticas de corrección durante los ataques.

Antes de poder realizar un seguimiento y administrar la incorporación de dispositivos:
- [Inscribir los dispositivos en la administración de Intune](configure-machines.md#enroll-devices-to-intune-management)
- [Asegúrese de que tiene los permisos necesarios](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>Detectar y realizar un seguimiento de dispositivos sin protección

La **tarjeta** de incorporación proporciona una descripción general de alto nivel de la tasa de incorporación comparando el número de dispositivos Windows 10 que realmente se han incorporado a Defender for Endpoint con el número total de dispositivos Windows 10 administrados por Intune.

![Tarjeta de incorporación de administración de configuración de dispositivos](images/secconmgmt_onboarding_card.png)<br>
*Tarjeta que muestra dispositivos incorporados en comparación con el número total de dispositivos administrados Windows 10 Intune*

>[!NOTE]
>Si usó Security Center Configuration Manager, el script de incorporación u otros métodos de incorporación que no usan perfiles de Intune, es posible que encuentre discrepancias de datos. Para resolver estas discrepancias, crea un perfil de configuración de Intune correspondiente para la incorporación de Defender for Endpoint y asigna ese perfil a los dispositivos.

## <a name="onboard-more-devices-with-intune-profiles"></a>Incorporación de más dispositivos con perfiles de Intune

Defender for Endpoint proporciona varias opciones convenientes para [la incorporación Windows 10 dispositivos](onboard-configure.md). Sin embargo, en el caso de los dispositivos administrados por Intune, puede aprovechar los perfiles de Intune para implementar cómodamente el sensor Defender for Endpoint para seleccionar dispositivos, incorporando estos dispositivos de forma eficaz al servicio.

En la **tarjeta incorporación,** selecciona **Incorporar más dispositivos** para crear y asignar un perfil en Intune. El vínculo te lleva a la página de cumplimiento del dispositivo en Intune, que proporciona una introducción similar al estado de incorporación.

![Página de cumplimiento de dispositivos de Microsoft Defender para endpoint en la administración de dispositivos de Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Página de cumplimiento de dispositivos de Microsoft Defender para endpoint en la administración de dispositivos de Intune*

>[!TIP]
>Como alternativa, puede navegar a la página De defender para el cumplimiento de la incorporación de puntos de conexión en el portal de [Microsoft Azure](https://portal.azure.com/) desde Todos los servicios > Intune > Cumplimiento de **dispositivos > ATP de Microsoft Defender**.

>[!NOTE]
> Si quieres ver los datos de dispositivo más actualizados, haz clic en Lista de **dispositivos sin sensor ATP**.

Desde la página de cumplimiento del dispositivo, crea un perfil de configuración específicamente para la implementación del sensor Defender for Endpoint y asigna ese perfil a los dispositivos que quieras incorporar. Para ello, puede:

- Selecciona **Crear un perfil de configuración de dispositivo para configurar el sensor DE ATP** para empezar con un perfil de configuración de dispositivo predefinido.
- Crea el perfil de configuración del dispositivo desde cero.

Para obtener más información, [lea acerca del uso de perfiles](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)de configuración de dispositivos de Intune para incorporar dispositivos a Defender para endpoint .

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados
- [Asegurarse de que los dispositivos estén configurados de manera adecuada](configure-machines.md)
- [Aumentar el cumplimiento de la línea base de seguridad de Defender for Endpoint](configure-machines-security-baseline.md)
- [Optimizar la implementación y detecciones de reglas ASR](configure-machines-asr.md)
