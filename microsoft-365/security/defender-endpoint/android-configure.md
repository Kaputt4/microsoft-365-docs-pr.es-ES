---
title: Configurar Microsoft Defender para punto de conexión en funciones de Android
description: Describe cómo configurar Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, Microsoft Defender para Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 264ebbe0ceb6d6b83c006dbd1dd071a78ae219c3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841359"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Configurar Defender para las características de Endpoint en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Acceso condicional con Defender para endpoint en Android  
Microsoft Defender para Endpoint en Android junto con Microsoft Intune y Azure Active Directory permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de los niveles de riesgo del dispositivo. Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información acerca de cómo configurar Defender para Endpoint en Android y acceso condicional, vea [Defender for Endpoint e Intune](/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados  

> [!NOTE]
> Defender for Endpoint en Android solo admite la creación de indicadores personalizados para direcciones IP y direcciones URL/dominios.

Defender para Endpoint en Android permite a los administradores configurar indicadores personalizados para admitir dispositivos Android también. Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](manage-indicators.md).

## <a name="configure-web-protection"></a>Configurar la protección web
Defender for Endpoint en Android permite a los administradores de TI configurar la característica de protección web. Esta funcionalidad está disponible en el Centro Microsoft Endpoint Manager administración.

> [!NOTE]
> Defender for Endpoint en Android usaría una VPN para proporcionar la característica de Protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo. Para obtener más información, vea [Configure web protection on devices that run Android](/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="related-topics"></a>Temas relacionados
- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
