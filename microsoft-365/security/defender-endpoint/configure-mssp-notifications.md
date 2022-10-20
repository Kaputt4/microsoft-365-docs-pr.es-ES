---
title: Configuración de las notificaciones de alertas que se envían a los CSP
description: Configuración de las notificaciones de alertas que se envían a los CSP
keywords: proveedor de servicios de seguridad administrados, mssp, configure, integration
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 81f2d696ba1f66316a2623539cee841f35e267bd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638508"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Configuración de las notificaciones de alertas que se envían a los CSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> Este paso lo pueden realizar el cliente de MSSP o MSSP. Los MSSP deben tener los permisos adecuados para configurarlo en nombre del cliente de MSSP.

Una vez concedido el acceso al portal, se pueden crear reglas de notificación de alertas para que los correos electrónicos se envíen a los MSSP cuando se creen alertas asociadas al inquilino y se cumplan las condiciones establecidas.

Para obtener más información, consulte [Creación de reglas para notificaciones de alertas](configure-email-notifications.md#create-rules-for-alert-notifications).

Estas casillas deben estar activadas:

- **Incluir nombre de la organización** : el nombre del cliente se agregará a las notificaciones por correo electrónico
- **Incluir vínculo de portal específico del inquilino** : la dirección URL del vínculo de alerta tendrá un parámetro específico del inquilino (tid=target_tenant_id) que permite el acceso directo al portal de inquilinos de destino.

## <a name="related-topics"></a>Temas relacionados

- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
