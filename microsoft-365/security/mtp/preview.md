---
title: Características de vista previa de la protección contra amenazas de Microsoft
description: Obtenga información sobre las nuevas características de la seguridad de Microsoft 365
keywords: vista previa, nueva M365 Security, Security, 365, Capabilities
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
ms.openlocfilehash: 8a3e4b8979a346266336e2729d18465d391c28f9
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689271"
---
# <a name="microsoft-threat-protection-preview-features"></a>Características preliminares de Microsoft Threat Protection

**Se aplica a:**
- Protección contra amenazas de Microsoft


El servicio de protección contra amenazas de Microsoft se actualiza constantemente para incluir nuevas funciones y mejoras de características.

Obtenga información sobre las nuevas características de la versión preliminar de Microsoft Threat Protection y realice una de las primeras características para probar la experiencia de vista previa.

Para obtener más información sobre las nuevas funciones disponibles de forma general, consulte la sección de [Novedades en la Protección contra amenazas de Microsoft](whats-new.md).

## <a name="turn-on-preview-features"></a>Activar las características de vista previa
Tendrá acceso a las próximas características en las que puede enviar comentarios para ayudar a mejorar la experiencia general antes de que las características estén disponibles para el público en general.

Active la configuración de la experiencia de vista previa para que sea una de las primeras y pruebe las características futuras.

1. En el panel de navegación, seleccione **configuración**.

2. Seleccione **Microsoft Threat Protection**.


3. Opciones de **vista previa**Active las  >  **características de vista previa**. 

3. Seleccione **Guardar**.

Sabrá que tiene características de vista previa activadas cuando vea que está activada la casilla **de verificación Activar las características de vista previa** . 

## <a name="preview-features"></a>Versión preliminar de las características
Las siguientes características y mejoras están disponibles actualmente en la versión preliminar:

- **[Tablas de identidad y aplicación](advanced-hunting-schema-tables.md)** : obtenga visibilidad de los eventos de autenticación, las consultas de Active Directory y la actividad relacionada con la aplicación con las tablas [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)y [AppFileEvents](advanced-hunting-appfileevents-table.md) en el esquema de búsqueda avanzada.

- **[Go Hunt](advanced-hunting-go-hunt.md)** — rápidamente dinamizando desde la investigación de un incidente hasta la inspección de un evento específico, un usuario, un dispositivo u otros tipos de entidad mediante funciones de [búsqueda avanzada](advanced-hunting-overview.md) basadas en consultas.

- **[Tabla EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** : Use esta tabla para crear consultas de [búsqueda avanzada](advanced-hunting-overview.md) que comprueben las acciones realizadas en los correos electrónicos después de que se hayan entregado a los buzones de correo de los destinatarios.

- **[Función FileProfile ()](advanced-hunting-fileprofile-function.md)** : Úsela en las consultas de [búsqueda avanzada](advanced-hunting-overview.md) para incorporar información de archivo completa.
