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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d30bc5150277dd54a4a38dce8ac515d6be7dfb21
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208534"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Configurar las notificaciones de alerta que se envían a los MSSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> Este paso lo puede realizar el cliente de MSSP o MSSP. Los MSSP deben tener los permisos adecuados para configurarlo en nombre del cliente de MSSP.

Una vez concedido el acceso al portal, se pueden crear reglas de notificación de alertas para que los correos electrónicos se envíen a los MSSP cuando se crean alertas asociadas con el espacio empresarial y se cumplen las condiciones establecidas.

Para obtener más información, vea [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).

Estas casillas deben estar activadas:

- **Incluir nombre de organización:** el nombre del cliente se agregará a las notificaciones por correo electrónico
- **Incluir vínculo de portal específico del** inquilino: la dirección URL del vínculo de alerta tendrá un parámetro específico del inquilino (tid=target_tenant_id) que permite el acceso directo al portal de inquilinos de destino

## <a name="related-topics"></a>Temas relacionados

- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
