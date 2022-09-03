---
title: Solucionar problemas de servicio de Microsoft Defender para punto de conexión
description: Busque soluciones y soluciones alternativas a problemas conocidos, como errores de servidor al intentar acceder al servicio.
keywords: solución de problemas de Microsoft Defender para punto de conexión, error del servidor, acceso denegado, credenciales no válidas, sin datos, portal de panel, permitir, visor de eventos
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: c4dba4a85985bdbfa2bcc03421327bd35ae35928
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585540"
---
# <a name="troubleshoot-service-issues"></a>Solucionar problemas de servicio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

En esta sección se abordan los problemas que pueden surgir al usar el servicio de Microsoft Defender para punto de conexión.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Error del servidor: se deniega el acceso debido a credenciales no válidas

Si encuentra un error de servidor al intentar acceder al servicio, tendrá que cambiar la configuración de cookies del explorador.
Configure el explorador para permitir cookies.

## <a name="elements-or-data-missing-on-the-portal"></a>Faltan elementos o datos en el portal

Si faltan algunos elementos o datos en Microsoft 365 Defender es posible que la configuración del proxy los bloquee.

Asegúrese de que `*.security.microsoft.com` se incluye la lista de permitidos de proxy.

> [!NOTE]
> Debe usar el protocolo HTTPS al agregar los siguientes puntos de conexión.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender para punto de conexión servicio muestra registros de eventos o errores en el Visor de eventos

Consulte [Revisar eventos y errores mediante Visor de eventos](event-error-codes.md) para obtener una lista de los identificadores de evento que notifica el servicio de Microsoft Defender para punto de conexión. El artículo también contiene los pasos para solucionar problemas de errores de eventos.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender para punto de conexión servicio no se puede iniciar después de un reinicio y muestra el error 577

Si la incorporación de dispositivos se completa correctamente, pero Microsoft Defender para punto de conexión no se inicia después de un reinicio y muestra el error 577, compruebe que una directiva no deshabilita Windows Defender.

Para obtener más información, vea [Asegurarse de que el antivirus de Microsoft Defender no está deshabilitado por directiva](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="known-issues-with-regional-formats"></a>Problemas conocidos con formatos regionales

### <a name="date-and-time-formats"></a>Formatos de fecha y hora

Hay algunos problemas conocidos con los formatos de fecha y hora.

Se admiten los siguientes formatos de fecha:

- MM/dd/aaaa
- dd/MM/aaaa

Actualmente no se admiten los siguientes formatos de fecha y hora:

- Formato de fecha aaaa/MM/dd
- Formato de fecha dd/MM/aaaa
- Formato de fecha con yy. Sólo se mostrará yyyy.
- No se admite el formato de hora HH:mm:ss (no se admite el formato de 12 horas a.m./PM). Solo se admite el formato de 24 horas.

### <a name="use-of-comma-to-indicate-thousand"></a>Uso de comas para indicar miles

No se admite el uso de comas como separador en números. Las regiones en las que un número se separa con una coma para indicar un millar, solo verán el uso de un punto como separador. Por ejemplo, 15 5 000 se muestra como 15,5 K.

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender para punto de conexión inquilino se creó automáticamente en Europa

Cuando se usa Microsoft Defender for Cloud para supervisar servidores, se crea automáticamente un inquilino de Microsoft Defender para punto de conexión. Los datos Microsoft Defender para punto de conexión se almacenan en Europa de forma predeterminada.

## <a name="related-topics"></a>Temas relacionados

- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
- [Revisar eventos y errores mediante Visor de eventos](event-error-codes.md)
