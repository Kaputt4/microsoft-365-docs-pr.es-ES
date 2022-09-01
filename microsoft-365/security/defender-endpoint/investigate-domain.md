---
title: Investigación de dominios de Microsoft Defender para punto de conexión
description: Use las opciones de investigación para ver si los dispositivos y servidores se han estado comunicando con dominios malintencionados.
keywords: investigar dominio, dominio, dominio malintencionado, Microsoft Defender para punto de conexión, alerta, dirección URL
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
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
ms.openlocfilehash: 9565d80da339722ba070cb4525f0f7339c1ff6ce
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520981"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigación de un dominio asociado a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)

Investigue un dominio para ver si los dispositivos y servidores de la red empresarial se han estado comunicando con un dominio malintencionado conocido.

Puede investigar un dominio mediante la característica de búsqueda o haciendo clic en un vínculo de dominio desde la **escala de tiempo del dispositivo**.

Puede ver información de las secciones siguientes en la vista URL:

- Detalles de dirección URL, Contactos, Servidores de nombres
- Alertas relacionadas con esta dirección URL 
- Dirección URL en la organización
- Dispositivos observados más recientes con dirección URL

## <a name="url-worldwide"></a>Dirección URL en todo el mundo

En la sección **URL Worldwide se** muestra la dirección URL, un vínculo a más detalles en Whois, el número de incidentes abiertos relacionados y el número de alertas activas.

## <a name="incident"></a>Incidente

La tarjeta **Incidente** muestra un gráfico de barras de todas las alertas activas en incidentes de los últimos 180 días.

## <a name="prevalence"></a>Prevalencia

La tarjeta **De prevalencia** proporciona detalles sobre la prevalencia de la dirección URL dentro de la organización, durante un período de tiempo especificado.

Aunque el período de tiempo predeterminado es de los últimos 30 días, puede personalizar el intervalo seleccionando la flecha hacia abajo en la esquina de la tarjeta. El intervalo más corto disponible es para la prevalencia durante el último día, mientras que el intervalo más largo es en los últimos 6 meses.

## <a name="alerts"></a>Alertas

La pestaña **Alertas** proporciona una lista de alertas asociadas a la dirección URL. La tabla que se muestra aquí es una versión filtrada de las alertas visibles en la pantalla Cola de alertas, que muestra solo las alertas asociadas al dominio, su gravedad, estado, el incidente asociado, clasificación, estado de investigación, etc.

La pestaña Alertas se puede ajustar para mostrar más o menos información; para ello, seleccione **Personalizar columnas** en el menú de acciones situado encima de los encabezados de columna. El número de elementos mostrados también se puede ajustar seleccionando **elementos por página** en el mismo menú.

## <a name="observed-in-organization"></a>Observado en la organización

La pestaña **Observada en la organización** proporciona una vista cronológica sobre los eventos y las alertas asociadas que se observaron en la dirección URL. Esta pestaña incluye una escala de tiempo y una tabla personalizable que enumera los detalles del evento, como la hora, el dispositivo y una breve descripción de lo que ocurrió. 

Puede ver eventos de diferentes períodos de tiempo escribiendo las fechas en los campos de texto situados encima de los encabezados de tabla. También puede personalizar el intervalo de tiempo seleccionando diferentes áreas de la escala de tiempo.

**Investigar un dominio:**

1. Seleccione **DIRECCIÓN URL** en el menú desplegable **De la barra de búsqueda** .
2. Escriba la dirección URL en el campo **Buscar** .
3. Haga clic en el icono de búsqueda o presione **Entrar**. Se muestran detalles sobre la dirección URL. Nota: Los resultados de búsqueda solo se devolverán para las direcciones URL observadas en las comunicaciones desde dispositivos de la organización.
4. Use los filtros de búsqueda para definir los criterios de búsqueda. También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección URL, el archivo asociado a la comunicación y la última fecha observada.
5. Hacer clic en cualquiera de los nombres de dispositivo le llevará a la vista de ese dispositivo, donde puede continuar investigando las alertas, los comportamientos y los eventos notificados.

## <a name="related-topics"></a>Temas relacionados
- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión](investigate-user.md)
