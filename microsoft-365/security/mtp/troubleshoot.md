---
title: Solucionar problemas de servicio de Microsoft 365 Defender
description: Buscar soluciones y soluciones para problemas conocidos de Microsoft 365 Defender
keywords: solucionar problemas de Microsoft Threat Protection, troubleshoot, Azure ATP, issues, add-on, settings page
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
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918671"
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

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>¿Dónde está la página de configuración para activar el servicio?

Para activar Microsoft 365 Defender, accede a **Configuración** desde el panel de navegación en el Centro de seguridad de Microsoft 365. Este elemento de navegación solo está visible si tiene los permisos [y licencias de requisitos previos.](mtp-enable.md#check-license-eligibility-and-required-permissions)