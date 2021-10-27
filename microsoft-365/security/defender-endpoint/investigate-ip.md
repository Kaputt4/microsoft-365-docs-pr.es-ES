---
title: Investigar una dirección IP asociada a una alerta
description: Use las opciones de investigación para examinar posibles comunicaciones entre dispositivos y direcciones IP externas.
keywords: investigar, investigar, dirección IP, alerta, Microsoft Defender para endpoint, IP externa
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: d6a6b9161aa613ff16aba86169eff58ac2cc113e
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588022"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Examine la posible comunicación entre los dispositivos y las direcciones de protocolo de Internet externo (IP).

La identificación de todos los dispositivos de la organización que se comunicaron con una dirección IP malintencionada sospechosa o conocida, como los servidores de comando y control (C2), ayuda a determinar el alcance potencial de la infracción, los archivos asociados y los dispositivos infectados.

Puede encontrar información en las siguientes secciones de la vista Dirección IP:

- IP en todo el mundo
- Nombres DNS inversos
- Alertas relacionadas con esta IP
- IP en la organización
- Prevalencia

## <a name="ip-worldwide-and-reverse-dns-names"></a>Nombres DNS de IP en todo el mundo y inversos

La sección detalles de la dirección IP muestra los atributos de la dirección IP, como su ASN y sus nombres DNS inversos.

## <a name="alerts-related-to-this-ip"></a>Alertas relacionadas con esta IP

La **sección Alertas relacionadas con esta IP** proporciona una lista de alertas asociadas con la IP.

## <a name="ip-in-organization"></a>IP en la organización

La **sección IP en la** organización proporciona detalles sobre la prevalencia de la dirección IP en la organización.

## <a name="prevalence"></a>Prevalencia

La **sección Prevalencia** muestra cuántos dispositivos se han conectado a esta dirección IP y cuándo se ha visto por primera y última vez. Puede filtrar los resultados de esta sección por período de tiempo; el período predeterminado es de 30 días.

## <a name="most-recent-observed-devices-with-ip"></a>Dispositivos observados más recientes con IP

La **sección Dispositivos observados** más recientes con IP proporciona una vista cronológica de los eventos y alertas asociadas que se observaron en la dirección IP.

**Investigar una IP externa:**

1. Seleccione **IP** en el **menú** desplegable de la barra de búsqueda.
2. Escriba la dirección IP en el **campo** Búsqueda.
3. Haga clic en el icono de búsqueda o presione **Entrar**.

Se muestran detalles sobre la dirección IP, incluidos: detalles de registro (si están disponibles), direcciones IP inversas (por ejemplo, dominios), prevalencia de dispositivos de la organización que se comunicaron con esta dirección IP (durante el período de tiempo seleccionable) y los dispositivos de la organización que se observaron comunicándose con esta dirección IP.

> [!NOTE]
> Los resultados de la búsqueda solo se devolverán para las direcciones IP observadas en la comunicación con dispositivos de la organización.

Use los filtros de búsqueda para definir los criterios de búsqueda. También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección IP, el archivo asociado a la comunicación y la última fecha observada.

Hacer clic en cualquiera de los nombres de dispositivo te llevará a la vista de ese dispositivo, donde puedes seguir investigando alertas, comportamientos y eventos notificados.

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigar una cuenta de usuario en Microsoft Defender para endpoint](investigate-user.md)
