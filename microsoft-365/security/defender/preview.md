---
title: Características de vista previa en Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c82e1abf9e539ad169bbc488ade9cd21bb8e6727
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029079"
---
# <a name="microsoft-365-defender-preview-features"></a>Características de vista previa de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Las versiones preliminares se proporcionan sin un contrato de nivel de servicio y no se recomienda para cargas de trabajo de producción. Es posible que algunas características no sean compatibles o que tengan capacidades limitadas.

**Se aplica a:**
- Microsoft 365 Defender

El servicio de Microsoft 365 Defender se actualiza constantemente para incluir nuevas mejoras y capacidades de características.

Obtén información sobre las nuevas características de la versión preliminar de Microsoft 365 Defender y sé uno de los primeros en probar las próximas características al activar la experiencia de vista previa.

Para obtener más información sobre las nuevas funcionalidades que están disponibles en general, vea [Novedades de Microsoft 365 Defender](whats-new.md).

## <a name="required-permissions"></a>Permisos necesarios

Las cuentas asignadas a los siguientes roles de Azure Active Directory (Azure AD) pueden activar las características de Microsoft 365 Defender Preview:

- Administrador global
- Administrador de seguridad
- Operador de seguridad

## <a name="turn-on-preview-features"></a>Activar la versión preliminar de las características

Tendrás acceso a las próximas características sobre las que puedes proporcionar comentarios para mejorar la experiencia general antes de que las características estén disponibles en general.

Active la configuración de la experiencia de la versión preliminar para estar entre los primeros en probar las próximas características.

1. En el panel de navegación, seleccione **Configuración**.
2. Seleccione **Microsoft 365 Defender**.
3. Seleccione **Versión preliminar de las características** > **Activar la versión preliminar de las características**. 
4. Seleccione **Guardar**.

Sabrá que tiene activada la versión preliminar de las características cuando vea que la casilla **Activar versión preliminar de las características** está seleccionada. 

## <a name="preview-features"></a>Versión preliminar de las características

Las siguientes características y mejoras están disponibles actualmente en la versión preliminar:

- API de **[Microsoft 365 Defender:](api-overview.md)** las API de Nivel superior de Microsoft 365 Defender le permitirán automatizar los flujos de trabajo en función de los incidentes compartidos y las tablas avanzadas de búsqueda. 
- **[Tomar medidas en la búsqueda avanzada:](advanced-hunting-take-action.md)** contiene rápidamente amenazas o aborda los activos comprometidos que encuentras en la [búsqueda avanzada.](advanced-hunting-overview.md)
- **[Referencia de esquema en el portal:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** obtenga información sobre las tablas de esquema de búsqueda avanzada directamente en el centro de seguridad. Además de las descripciones de tabla y columna, esta referencia incluye tipos de eventos admitidos `ActionType` (valores) y consultas de ejemplo.
- **[Función DeviceFromIP():](advanced-hunting-devicefromip-function.md)** obtenga información sobre los dispositivos a los que se ha asignado una dirección IP específica o direcciones en un intervalo de tiempo determinado.
