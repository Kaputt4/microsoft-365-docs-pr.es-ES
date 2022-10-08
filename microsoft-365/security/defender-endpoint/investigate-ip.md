---
title: Investigación de una dirección IP asociada a una alerta
description: Use las opciones de investigación para examinar la posible comunicación entre dispositivos y direcciones IP externas.
keywords: investigar, investigar, dirección IP, alerta, Microsoft Defender para punto de conexión, DIRECCIÓN IP externa
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
- tier2
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 41557fc56e9ccbe64a05f3aad3d280ff544473c4
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232306"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigación de una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Examine la posible comunicación entre los dispositivos y las direcciones de protocolo de Internet (IP) externas.

La identificación de todos los dispositivos de la organización que se comunicaron con una dirección IP malintencionada sospechosa o conocida, como servidores de comandos y control (C2), ayuda a determinar el posible ámbito de la infracción, los archivos asociados y los dispositivos infectados.

Puede encontrar información de las secciones siguientes en la vista de direcciones IP:

- P.I. en todo el mundo
- Nombres DNS inversos
- Alertas relacionadas con esta dirección IP
- IP en la organización
- Prevalencia

## <a name="ip-worldwide-and-reverse-dns-names"></a>Ip en todo el mundo y nombres DNS inversos

En la sección Detalles de la dirección IP se muestran los atributos de la dirección IP, como su ASN y sus nombres DNS inversos.

## <a name="alerts-related-to-this-ip"></a>Alertas relacionadas con esta dirección IP

La sección **Alertas relacionadas con esta dirección IP** proporciona una lista de alertas asociadas a la dirección IP.

## <a name="ip-in-organization"></a>IP en la organización

La sección **IP en la organización** proporciona detalles sobre la prevalencia de la dirección IP en la organización.

## <a name="prevalence"></a>Prevalencia

En la sección **Prevalencia** se muestra cuántos dispositivos se han conectado a esta dirección IP y cuándo se ha visto por primera y última vez la dirección IP. Puede filtrar los resultados de esta sección por período de tiempo; el período predeterminado es de 30 días.

## <a name="most-recent-observed-devices-with-ip"></a>Dispositivos observados más recientes con IP

La sección **Dispositivos observados más recientes** con IP proporciona una vista cronológica sobre los eventos y las alertas asociadas que se observaron en la dirección IP.

**Investigar una dirección IP externa:**

1. Seleccione **IP** en el menú desplegable **De la barra de búsqueda** .
2. Escriba la dirección IP en el campo **Buscar** .
3. Haga clic en el icono de búsqueda o presione **Entrar**.

Se muestran detalles sobre la dirección IP, incluidos: detalles de registro (si está disponible), direcciones IP inversas (por ejemplo, dominios), prevalencia de dispositivos de la organización que se comunicaron con esta dirección IP (durante el período de tiempo seleccionable) y los dispositivos de la organización que se observaron comunicándose con esta dirección IP.

> [!NOTE]
> Los resultados de la búsqueda solo se devolverán para las direcciones IP observadas en la comunicación con los dispositivos de la organización.

Use los filtros de búsqueda para definir los criterios de búsqueda. También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección IP, el archivo asociado a la comunicación y la última fecha observada.

Hacer clic en cualquiera de los nombres de dispositivo le llevará a la vista de ese dispositivo, donde puede continuar investigando las alertas, los comportamientos y los eventos notificados.

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
- [Investigación de un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión](investigate-user.md)
