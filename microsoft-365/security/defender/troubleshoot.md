---
title: Solucionar problemas de servicio de Microsoft 365 Defender
description: Buscar soluciones y soluciones alternativas a problemas conocidos de Microsoft 365 Defender
keywords: solucionar problemas de Microsoft 365 Defender, solucionar problemas, Microsoft Defender para identidad, problemas, complemento, página de configuración
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
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933402"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solucionar problemas de servicio de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>No veo contenido de Microsoft 365 Defender

Si no ve funcionalidades en el panel de navegación como incidentes, centro de acciones o búsqueda en el portal, deberá comprobar que el inquilino tiene las licencias adecuadas.

Para obtener más información, vea [Requisitos previos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Las alertas de Identidad de Microsoft Defender no aparecen en los incidentes de Microsoft 365 Defender

Si tienes Microsoft Defender for Identity implementado en el entorno pero no ves alertas de Defender for Identity como parte de incidentes de Microsoft 365 Defender, tendrás que asegurarte de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.

Para obtener más información, vea [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>¿Dónde está la página de configuración para activar el servicio?

Para activar Microsoft 365 Defender, accede a **Configuración** desde el panel de navegación en el Centro de seguridad de Microsoft 365. Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>¿Cómo puedo crear una excepción para mi archivo/dirección URL?

Un falso positivo es un archivo o dirección URL que se detecta como malintencionado pero no es una amenaza. Puede crear indicadores y definir exclusiones para desbloquear y permitir determinados archivos/direcciones URL. Consulte [Dirección de falsos positivos/negativos en Defender para Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


