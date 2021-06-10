---
title: Configurar la compatibilidad con el proveedor de servicios de seguridad administrado
description: Siga los pasos necesarios para configurar la integración de MSSP con Microsoft Defender para endpoint
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165254"
---
# <a name="configure-managed-security-service-provider-integration"></a>Configurar la integración del proveedor de servicios de seguridad administrados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Deberá seguir los siguientes pasos de configuración para habilitar la integración del proveedor de servicios de seguridad administrado (MSSP).

>[!NOTE]
>En este artículo se usan los siguientes términos para distinguir entre el proveedor de servicios y el consumidor de servicios:
> - MSSP: organizaciones de seguridad que ofrecen supervisar y administrar dispositivos de seguridad para una organización.
> - Clientes de MSSP: organizaciones que interactúan con los servicios de MSSP.

La integración permitirá a los MSSP realizar las siguientes acciones:

- Obtener acceso al portal de Centro de seguridad de Microsoft Defender MSSP
- Obtener notificaciones por correo electrónico y 
- Capturar alertas a través de herramientas de administración de eventos y de información de seguridad (SIEM)

Antes de que los MSSP puedan llevar a cabo estas acciones, el cliente de MSSP tendrá que conceder acceso a su inquilino de Defender for Endpoint para que el MSSP pueda acceder al portal. 
 

Normalmente, los clientes de MSSP toman los pasos de configuración iniciales para conceder a los MSSP acceso a su inquilino Windows Defender Security Central. Una vez concedido el acceso, el cliente MSSP o el MSSP pueden realizar otros pasos de configuración.


En general, deben realizarse los siguientes pasos de configuración:


- **Conceda al MSSP acceso a Centro de seguridad de Microsoft Defender** <br>
Esta acción debe realizarla el cliente de MSSP. Concede al MSSP acceso al inquilino Defender for Endpoint del cliente de MSSP.
 

- **Configurar notificaciones de alerta enviadas a MSSP** <br>
Esta acción puede realizarla el cliente de MSSP o MSSP. Esto permite a los MSSP saber qué alertas deben abordar para el cliente de MSSP.

- **Capturar alertas del inquilino del cliente de MSSP en el sistema SIEM** <br> El MSSP toma esta acción. Permite a los MSSP capturar alertas en herramientas SIEM.

- **Capturar alertas desde el inquilino del cliente de MSSP mediante API** <br>
El MSSP toma esta acción. Permite a los MSSP capturar alertas mediante API.

## <a name="multi-tenant-access-for-mssps"></a>Acceso multiinquilino para MSSP
Para obtener información sobre cómo implementar un acceso delegado multiinquilino, vea [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).



## <a name="related-topics"></a>Temas relacionados
- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)

