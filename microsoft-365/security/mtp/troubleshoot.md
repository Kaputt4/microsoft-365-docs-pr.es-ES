---
title: Solucionar problemas de los servicios de protección contra amenazas de Microsoft
description: Encontrar soluciones y alternativas para los problemas conocidos de la protección contra amenazas de Microsoft.
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844923"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Solucionar problemas de los servicios de protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

Esta sección trata los problemas que pueden surgir al usar el servicio de protección contra amenazas de Microsoft.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>No veo el contenido de Microsoft Threat Protection
Si no ve funcionalidades en el panel de navegación, como los incidentes, el centro de actividades o la caza, deberá comprobar que el inquilino tiene las licencias adecuadas. 

Para obtener más información, vea [Requisitos previos](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Las alertas de ATP de Azure no se muestran dentro de los incidentes de la protección contra amenazas de Microsoft
Si tiene Azure ATP implementado en su entorno, pero no ve las alertas de ATP de Azure como parte de los incidentes de la protección contra amenazas de Microsoft, deberá asegurarse de que la integración entre Microsoft Cloud App Security y Azure ATP está habilitada. 

Para más información, consulte [Integración de Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration):

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>¿Dónde se encuentra la página de configuración para activar el servicio?
Para activar la protección contra amenazas de Microsoft, obtenga acceso a la **configuración** del panel de navegación del centro de seguridad de Microsoft 365. Este elemento de navegación es visible solo si tiene los [permisos y licencias necesarios](mtp-enable.md#check-license-eligibility-and-required-permissions).
 

