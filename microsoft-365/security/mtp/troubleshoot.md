---
title: Solucionar problemas de servicio de Microsoft 365 Defender
description: Buscar soluciones y soluciones a problemas conocidos de Microsoft 365 Defender
keywords: solucionar problemas de Protección contra amenazas de Microsoft, solucionar problemas, Azure ATP, problemas, complemento, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925723"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solucionar problemas de servicio de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>No veo contenido de Microsoft 365 Defender

Si no ve funcionalidades en el panel de navegación como Incidentes, Centro de actividades o Búsqueda en el portal, deberá comprobar que su espacio empresarial tiene las licencias adecuadas.

Para obtener más información, vea [Requisitos previos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Las alertas de Identidad de Microsoft Defender no se muestran en los incidentes de Microsoft 365 Defender

Si ha implementado Microsoft Defender for Identity en su entorno, pero no ve alertas de Defender for Identity como parte de los incidentes de Microsoft 365 Defender, deberá asegurarse de que la integración de Microsoft Cloud App Security y Defender for Identity está habilitada.

Para obtener más información, vea [Microsoft Defender para la integración de Identidad.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>¿Dónde está la página de configuración para activar el servicio?

Para activar Microsoft 365 Defender, acceda a **Configuración** desde el panel de navegación en el Centro de seguridad de Microsoft 365. Este elemento de navegación solo es visible si tiene los permisos y licencias de [requisitos previos.](mtp-enable.md#check-license-eligibility-and-required-permissions)
