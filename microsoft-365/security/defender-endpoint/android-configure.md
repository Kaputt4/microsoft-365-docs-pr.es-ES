---
title: Configurar ATP de Microsoft Defender para características de Android
description: Describe cómo configurar ATP de Microsoft Defender para Android
keywords: microsoft, defender, atp, android, configuration
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163452"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>Configurar Defender para las características de Endpoint para Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Acceso condicional con Defender para endpoint para Android  
Microsoft Defender para Endpoint para Android, junto con Microsoft Intune y Azure Active Directory, permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de los niveles de riesgo del dispositivo. Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información acerca de cómo configurar Defender para Endpoint para Android y acceso condicional, vea [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados  

> [!NOTE]
> Defender para Endpoint para Android solo admite la creación de indicadores personalizados para direcciones IP y direcciones URL/dominios.

Defender para Endpoint para Android permite a los administradores configurar indicadores personalizados para admitir dispositivos Android también. Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](manage-indicators.md).

## <a name="configure-web-protection"></a>Configurar la protección web
Defender para Endpoint para Android permite a los administradores de TI configurar la característica de protección web. Esta funcionalidad está disponible en el Centro de administración de Microsoft Endpoint Manager.

> [!NOTE]
> Defender para Endpoint para Android usaría una VPN para proporcionar la característica de Protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo. Para obtener más información, vea [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre Microsoft Defender para endpoint para Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para endpoint para Android con Microsoft Intune](android-intune.md)
