---
title: Solucionar problemas Microsoft 365 servicio de Defender
description: Buscar soluciones y soluciones para problemas conocidos Microsoft 365 Defender
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782746"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solucionar problemas Microsoft 365 servicio de Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

En esta sección se abordan los problemas que pueden surgir al usar el servicio Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>No veo el contenido de Microsoft 365 Defender

Si no ve funcionalidades en el panel de navegación como incidentes, centro de acciones o búsqueda en el portal, deberá comprobar que el inquilino tiene las licencias adecuadas.

Para obtener más información, consulte [Requisitos previos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Las alertas de Microsoft Defender para identidades no aparecen en los incidentes de Microsoft 365 Defender

Si tienes Microsoft Defender for Identity implementado en el entorno, pero no ves alertas de Defender for Identity como parte de incidentes de Microsoft 365 Defender, tendrás que asegurarte de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.

Para obtener más información, vea [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>¿Dónde está la página de configuración para activar el servicio?

Para activar Microsoft 365 Defender, accede a **Configuración** desde el panel de navegación en el centro Microsoft 365 seguridad. Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>¿Cómo puedo crear una excepción para mi archivo/dirección URL?

Un falso positivo es un archivo o dirección URL que se detecta como malintencionado pero no es una amenaza. Puede crear indicadores y definir exclusiones para desbloquear y permitir determinados archivos/direcciones URL. Consulte [Dirección de falsos positivos/negativos en Defender para Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


