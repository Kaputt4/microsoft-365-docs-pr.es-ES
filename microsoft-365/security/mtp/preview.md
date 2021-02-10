---
title: Características de vista previa de Microsoft 365 Defender
description: Conozca las nuevas características de la seguridad de Microsoft 365
keywords: Versión preliminar, novedades, seguridad m365, seguridad, 365, funciones
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
ms.openlocfilehash: 9156025990e8da61006ac1d3b81a71be5580e00c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167388"
---
# <a name="microsoft-365-defender-preview-features"></a>Características de vista previa de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
>Las versiones preliminares se proporcionan sin un contrato de nivel de servicio y no se recomienda para cargas de trabajo de producción. Es posible que algunas características no sean compatibles o que tengan funcionalidades restringidas.

**Se aplica a:**
- Microsoft 365 Defender

El servicio de Microsoft 365 Defender se actualiza constantemente para incluir nuevas mejoras y funcionalidades de características.

Obtenga información sobre las nuevas características de la versión preliminar de Microsoft 365 Defender y sea uno de los primeros en probar las próximas características al activar la experiencia de vista previa.

Para obtener más información sobre las nuevas funcionalidades que están generalmente disponibles, consulte Novedades [de Microsoft 365 Defender.](whats-new.md)

## <a name="turn-on-preview-features"></a>Activar la versión preliminar de las características
Tendrás acceso a las próximas características sobre las que puedes proporcionar comentarios para ayudar a mejorar la experiencia general antes de que las características estén generalmente disponibles.

Active la configuración de la experiencia de la versión preliminar para estar entre los primeros en probar las próximas características.

1. En el panel de navegación, seleccione **Configuración**.

2. Seleccione **Microsoft 365 Defender.**

3. Seleccione **Versión preliminar de las características** > **Activar la versión preliminar de las características**. 

4. Seleccione **Guardar**.

Sabrá que tiene activada la versión preliminar de las características cuando vea que la casilla **Activar versión preliminar de las características** está seleccionada. 

## <a name="preview-features"></a>Versión preliminar de las características
Las siguientes características y mejoras están disponibles actualmente en la versión preliminar:

### <a name="improved-microsoft-365-security-center"></a>Centro de seguridad de Microsoft 365 mejorado
Ahora, el [Centro de seguridad de Microsoft 365](https://security.microsoft.com) está accesible en forma de versión preliminar pública. Esta nueva experiencia lleva a Defender para Endpoint, Defender para Office 365, Microsoft 365 Defender y mucho más en el Centro de seguridad de Microsoft 365. Este es el nuevo hogar para administrar los controles de seguridad. [Ver las novedades](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).

- Informe de análisis de amenazas de **[Microsoft 365 Defender:](threat-analytics.md)** análisis de amenazas le ayuda a responder y minimizar el impacto de los ataques activos. También puede obtener información sobre los intentos de ataque bloqueados por las soluciones de Microsoft 365 Defender y tomar medidas preventivas que mitigan el riesgo de una mayor exposición y aumentan la resistencia. Como parte de la experiencia de seguridad unificada, el análisis de amenazas ahora está disponible para los poseedores de licencias de Microsoft Defender para Endpoint y Microsoft Defender para Office E5.
- API de **[Microsoft 365 Defender:](api-overview.md)** las API de Microsoft 365 Defender de nivel superior le permitirán automatizar flujos de trabajo en función de las tablas de incidentes compartidos y búsqueda avanzada. 
- **[Tomar medidas en la búsqueda avanzada:](advanced-hunting-take-action.md)** contener rápidamente amenazas o solucionar activos comprometidos que encuentre en la [búsqueda avanzada.](advanced-hunting-overview.md)
- **[Referencia de esquema en el portal:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** obtenga información sobre las tablas de esquema de búsqueda avanzada directamente en el centro de seguridad. Además de las descripciones de tabla y columna, esta referencia incluye tipos de eventos admitidos `ActionType` (valores) y consultas de ejemplo.
- **[Función DeviceFromIP():](advanced-hunting-devicefromip-function.md)** obtenga información sobre los dispositivos a los que se ha asignado una dirección IP o direcciones específicas en un intervalo de tiempo determinado.
