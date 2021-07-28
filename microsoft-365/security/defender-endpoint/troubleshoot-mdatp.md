---
title: Solucionar problemas de servicio de Microsoft Defender para punto de conexión
description: Busque soluciones y soluciones alternativas a problemas conocidos, como errores de servidor al intentar obtener acceso al servicio.
keywords: solucionar problemas de Microsoft Defender para el extremo, error del servidor, acceso denegado, credenciales no válidas, sin datos, portal de panel, permitir, visor de eventos
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: e5eda862f253f1df2fd4b2d394601b99258ce446
ms.sourcegitcommit: bef7bd019531317d083c1125f7d339750c450b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587890"
---
# <a name="troubleshoot-service-issues"></a>Solucionar problemas de servicio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink)

En esta sección se abordan los problemas que pueden surgir al usar el servicio Microsoft Defender para endpoints.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Error del servidor: se deniega el acceso debido a credenciales no válidas

Si se produce un error de servidor al intentar acceder al servicio, deberá cambiar la configuración de cookies del explorador.
Configure el explorador para permitir cookies.

## <a name="elements-or-data-missing-on-the-portal"></a>Faltan elementos o datos en el portal

Si faltan algunos elementos o datos en Microsoft 365 Defender es posible que la configuración de proxy lo bloquee.

Asegúrese de que `*.security.microsoft.com` se incluye la lista de permitidos de proxy.

> [!NOTE]
> Debe usar el protocolo HTTPS al agregar los siguientes extremos.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>El servicio de Microsoft Defender para endpoints muestra registros de eventos o errores en el Visor de eventos

Consulta [Revisar eventos y errores mediante el Visor](event-error-codes.md) de eventos para obtener una lista de los IDs de eventos notificados por el servicio de Microsoft Defender para puntos de conexión. El artículo también contiene los pasos para solucionar problemas de errores de eventos.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender para el servicio de extremo no se inicia después de un reinicio y muestra el error 577

Si los dispositivos de incorporación se completan correctamente, pero Microsoft Defender para endpoint no se inicia después de un reinicio y muestra el error 577, compruebe que Windows Defender no está deshabilitado por una directiva.

Para obtener más información, vea [Ensure that Antivirus de Microsoft Defender is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="known-issues-with-regional-formats"></a>Problemas conocidos con formatos regionales

### <a name="date-and-time-formats"></a>Formatos de fecha y hora

Hay algunos problemas conocidos con los formatos de fecha y hora.

Se admiten los siguientes formatos de fecha:

- MM/dd/yyyy
- dd/MM/yyyy

Actualmente no se admiten los siguientes formatos de fecha y hora:

- Formato de fechayyy/MM/dd
- Formato de fecha dd/MM/aa
- Formato de fecha con yy. Solo se mostrará yyyy.
- No se admite el formato de hora HH:mm:ss (no se admite el formato de 12 horas a.m./pm). Solo se admite el formato de 24 horas.

### <a name="use-of-comma-to-indicate-thousand"></a>Uso de comas para indicar miles

No se admite el uso de comas como separador en números. Las regiones donde un número está separado con una coma para indicar mil, solo verán el uso de un punto como separador. Por ejemplo, 15,5K se muestra como 15,5K.

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>El inquilino de Microsoft Defender para endpoint se creó automáticamente en Europa

Cuando usa Azure Defender para supervisar los servidores, se crea automáticamente un inquilino de Microsoft Defender para endpoint. Los datos de Microsoft Defender para endpoint se almacenan en Europa de forma predeterminada.

## <a name="related-topics"></a>Temas relacionados

- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
- [Revisar eventos y errores con el Visor de eventos](event-error-codes.md)
