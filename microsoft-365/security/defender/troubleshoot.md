---
title: Solución de problemas del servicio Microsoft 365 Defender
description: Búsqueda de soluciones y soluciones alternativas a problemas conocidos de Microsoft 365 Defender
keywords: solución de problemas de Microsoft 365 Defender, solución de problemas, Microsoft Defender for Identity, problemas, complemento, página de configuración
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security-compliance
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1909756f77f48d96dc997726019f4d2eb518d22e
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069521"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solución de problemas del servicio Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>No veo Microsoft 365 Defender contenido

Si no ve funcionalidades en el panel de navegación, como incidentes, centro de acciones o búsqueda en el portal, tendrá que comprobar que el inquilino tiene las licencias adecuadas.

Para obtener más información, consulte [Requisitos previos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity alertas no se muestran en los incidentes de Microsoft 365 Defender

Si Microsoft Defender for Identity ha implementado en su entorno, pero no ve alertas de Defender for Identity como parte de Microsoft 365 Defender incidentes, deberá asegurarse de que el Microsoft Defender for Cloud Apps  y la integración de Defender for Identity está habilitada.

Para obtener más información, consulte [integración Microsoft Defender for Identity](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>¿Dónde está la página de configuración para activar el servicio?

Para activar Microsoft 365 Defender, acceda a **Configuración** desde el panel de navegación del portal de Microsoft 365 Defender. Este elemento de navegación solo está visible si tiene los [permisos y licencias de requisitos previos](m365d-enable.md#check-license-eligibility-and-required-permissions).

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Cómo crear una excepción para mi archivo o dirección URL?

Un falso positivo es un archivo o dirección URL que se detecta como malintencionado, pero no es una amenaza. Puede crear indicadores y definir exclusiones para desbloquear y permitir determinados archivos o direcciones URL. Consulte [Dirección de falsos positivos o negativos en Defender para punto de conexión](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).
