---
title: Configurar Microsoft Defender para las características de Punto de conexión en Android
description: Describe cómo configurar Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, atp, mde, android, configuration
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
ms.openlocfilehash: 8ec4a19bdd641c721bfcd7be2ceb59de1de92963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688038"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>Configurar Defender para las características de Endpoint para Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Acceso condicional con Defender para endpoint para Android  
Microsoft Defender para Endpoint en Android junto con Microsoft Intune y Azure Active Directory permite aplicar directivas de cumplimiento de dispositivos y acceso condicional en función de los niveles de riesgo del dispositivo. Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.

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
- [Información general sobre Microsoft Defender para endpoint en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para endpoint en Android con Microsoft Intune](android-intune.md)
