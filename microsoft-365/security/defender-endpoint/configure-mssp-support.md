---
title: Configuración de la compatibilidad con proveedores de servicios de seguridad administrados
description: Realice los pasos necesarios para configurar la integración de MSSP con el Microsoft Defender para punto de conexión
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
- tier3
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 1e0ab5ee7e038653beebae044cb2517ee5ebf39a
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167261"
---
# <a name="configure-managed-security-service-provider-integration"></a>Configurar la integración del proveedor de servicios de seguridad administrados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Tendrá que realizar los pasos de configuración siguientes para habilitar la integración del proveedor de servicios de seguridad administrado (MSSP).

> [!NOTE]
> En este artículo se usan los siguientes términos para distinguir entre el proveedor de servicios y el consumidor de servicios:
>
> - MSSPs: organizaciones de seguridad que ofrecen supervisar y administrar dispositivos de seguridad para una organización.
> - Clientes de MSSP: organizaciones que interactúan con los servicios de MSSP.

La integración permitirá que los CSP realicen las siguientes acciones:

- Obtener acceso al portal de Microsoft 365 Defender del cliente de MSSP
- Obtener notificaciones por correo electrónico y
- Captura de alertas a través de herramientas de administración de eventos e información de seguridad (SIEM)

Antes de que los MSSP puedan realizar estas acciones, el cliente de MSSP tendrá que conceder acceso a su inquilino de Defender para punto de conexión para que MSSP pueda acceder al portal.

Normalmente, los clientes de MSSP realizan los pasos de configuración iniciales para conceder a los MSSP acceso a su inquilino de Windows Defender Security Central. Una vez concedido el acceso, el cliente MSSP o el MSSP pueden realizar otros pasos de configuración.

En general, es necesario realizar los siguientes pasos de configuración:

- **Conceder acceso al MSSP a Microsoft 365 Defender**

  El cliente de MSSP debe realizar esta acción. Concede al MSSP acceso al inquilino de Defender para punto de conexión del cliente de MSSP.

- **Configuración de las notificaciones de alerta enviadas a los CSP**

  Esta acción puede realizarla el cliente de MSSP o MSSP. Esto permite a los MSSP saber qué alertas deben abordar para el cliente de MSSP.

- **Captura de alertas del inquilino del cliente de MSSP en el sistema SIEM**

  Esta acción la realiza el MSSP. Permite a los MSSP capturar alertas en herramientas SIEM.

- **Captura de alertas del inquilino del cliente de MSSP mediante las API**

  Esta acción la realiza el MSSP. Permite a los MSSP capturar alertas mediante las API.

## <a name="multi-tenant-access-for-mssps"></a>Acceso multiinquilino para MSSP

Para obtener información sobre cómo implementar un acceso delegado multiinquilino, consulte [Acceso multiinquilino para proveedores de servicios de seguridad administrados](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).

## <a name="related-topics"></a>Temas relacionados

- [Conceder acceso a MSSP al portal](grant-mssp-access.md)
- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
