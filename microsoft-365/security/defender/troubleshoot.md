---
title: Solucionar problemas Microsoft 365 Defender de servicio
description: Buscar soluciones y soluciones alternativas a problemas Microsoft 365 Defender conocidos
keywords: solucionar Microsoft 365 Defender, solucionar problemas, Microsoft Defender para identidad, problemas, complemento, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 14033ffeb3d08efad7f45eb4c319ac0401b7df09
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028480"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solucionar problemas Microsoft 365 Defender de servicio

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

En esta sección se abordan los problemas que pueden surgir al usar el servicio Microsoft 365 Defender cliente.

## <a name="i-dont-see-microsoft-365-defender-content"></a>No veo contenido Microsoft 365 Defender contenido

Si no ve funcionalidades en el panel de navegación como incidentes, centro de acciones o búsqueda en el portal, deberá comprobar que el inquilino tiene las licencias adecuadas.

Para obtener más información, consulte [Requisitos previos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Las alertas de Identidad de Microsoft Defender no se muestran en los Microsoft 365 Defender de seguridad

Si tienes Microsoft Defender para identity implementado en el entorno pero no ves alertas de Defender for Identity como parte de incidentes de Microsoft 365 Defender, tendrás que asegurarte de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.

Para obtener más información, vea [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>¿Dónde está la página de configuración para activar el servicio?

Para activar el Microsoft 365 Defender, acceda a **Configuración** desde el panel de navegación en el centro Microsoft 365 seguridad. Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>¿Cómo puedo crear una excepción para mi archivo/dirección URL?

Un falso positivo es un archivo o dirección URL que se detecta como malintencionado pero no es una amenaza. Puede crear indicadores y definir exclusiones para desbloquear y permitir determinados archivos/direcciones URL. Consulte [Dirección de falsos positivos/negativos en Defender para Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


