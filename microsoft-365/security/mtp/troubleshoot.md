---
title: Solución de problemas del servicio Microsoft 365 defender
description: Buscar soluciones y trabajos relacionados con problemas conocidos de Microsoft 365 defender
keywords: solucionar problemas de protección contra amenazas de Microsoft, solución de problemas, ATP de Azure, problemas, complemento, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760463"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solución de problemas del servicio Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

En esta sección se tratan los problemas que pueden surgir al usar el servicio de Microsoft 365 defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>No veo contenido de Microsoft 365 defender

Si no ve funcionalidades en el panel de navegación, como los incidentes, el centro de actividades o la caza, deberá comprobar que el inquilino tiene las licencias adecuadas.

Para obtener más información, vea [Requisitos previos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft defender para las alertas de identidad no se muestra en los incidentes de Microsoft 365 defender

Si tiene Microsoft defender para la identidad implementada en su entorno pero no ve defender para las alertas de identidad como parte de los incidentes de Microsoft 365 defender, deberá asegurarse de que esté habilitada la seguridad de Microsoft Cloud App y defender para la integración de identidades.

Para obtener más información, consulte [Microsoft defender para la integración de identidades](https://docs.microsoft.com/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>¿Dónde se encuentra la página de configuración para activar el servicio?

Para activar Microsoft 365 defender, obtenga acceso a la **configuración** desde el panel de navegación del centro de seguridad de Microsoft 365. Este elemento de navegación es visible solo si tiene los [permisos y licencias necesarios](mtp-enable.md#check-license-eligibility-and-required-permissions).
