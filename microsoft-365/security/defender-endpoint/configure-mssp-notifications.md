---
title: Configurar las notificaciones de alerta que se envían a los MSSP
description: Configurar las notificaciones de alerta que se envían a los MSSP
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166058"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Configurar las notificaciones de alerta que se envían a los MSSP 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Este paso lo puede realizar el cliente de MSSP o MSSP. Los MSSP deben tener los permisos adecuados para configurarlo en nombre del cliente de MSSP.

Una vez concedido el acceso al portal, se pueden crear reglas de notificación de alertas para que los correos electrónicos se envíen a los MSSP cuando se crean alertas asociadas con el espacio empresarial y se cumplen las condiciones establecidas.

 
Para obtener más información, vea [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).
 

Estas casillas deben estar activadas:
- **Incluir nombre de organización:** el nombre del cliente se agregará a las notificaciones por correo electrónico
- **Incluir vínculo de portal específico del** inquilino: la dirección URL del vínculo de alerta tendrá un parámetro específico del inquilino (tid=target_tenant_id) que permite el acceso directo al portal de inquilinos de destino


## <a name="related-topics"></a>Temas relacionados
- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
