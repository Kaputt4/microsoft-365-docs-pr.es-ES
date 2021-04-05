---
title: Investigar dominios de Punto de conexión de Microsoft Defender
description: Use las opciones de investigación para ver si los dispositivos y servidores se han estado comunicando con dominios malintencionados.
keywords: investigar dominio, dominio, dominio malintencionado, atp de Microsoft Defender, alerta, DIRECCIÓN URL
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 3d4520c805332bac41746a39bb8b668dbfb1a570
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587496"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

Investigar un dominio para ver si los dispositivos y servidores de la red empresarial se han estado comunicando con un dominio malintencionado conocido.

Puedes investigar un dominio mediante la característica de búsqueda o haciendo clic en un vínculo de dominio desde la escala de tiempo **del dispositivo**.

Puede ver información de las siguientes secciones en la vista DIRECCIÓN URL:

- Detalles de dirección URL, Contactos, Servidores de nombres
- Alertas relacionadas con esta dirección URL 
- DIRECCIÓN URL en la organización
- Dispositivos observados más recientes con dirección URL

## <a name="url-worldwide"></a>DIRECCIÓN URL en todo el mundo

La **sección Dirección URL** en todo el mundo enumera la dirección URL, un vínculo a más detalles en Whois, el número de incidentes abiertos relacionados y el número de alertas activas.

## <a name="incident"></a>Incidente

La **tarjeta Incidentes** muestra un gráfico de barras de todas las alertas activas en incidentes de los últimos 180 días.

## <a name="prevalence"></a>Prevalencia

La **tarjeta de prevalencia** proporciona detalles sobre la prevalencia de la dirección URL dentro de la organización, durante un período de tiempo especificado.

Aunque el período de tiempo predeterminado es de los últimos 30 días, puede personalizar el intervalo seleccionando la flecha hacia abajo en la esquina de la tarjeta. El intervalo más corto disponible es el de prevalencia del último día, mientras que el intervalo más largo es el de los últimos 6 meses.

## <a name="alerts"></a>Alertas

La **pestaña** Alertas proporciona una lista de alertas asociadas a la dirección URL. La tabla que se muestra aquí es una versión filtrada de las alertas visibles en la pantalla Cola de alertas, que muestra solo alertas asociadas con el dominio, su gravedad, estado, incidente asociado, clasificación, estado de investigación, etc.

La pestaña Alertas se puede ajustar para mostrar  más o menos información, seleccionando Personalizar columnas en el menú de acciones encima de los encabezados de columna. El número de elementos que se muestran también se puede ajustar seleccionando elementos **por página** en el mismo menú.

## <a name="observed-in-organization"></a>Observado en la organización

La **pestaña Observed in organization** proporciona una vista cronológica de los eventos y alertas asociadas que se observaron en la dirección URL. Esta pestaña incluye una escala de tiempo y una tabla personalizable que enumera los detalles del evento, como la hora, el dispositivo y una breve descripción de lo que ocurrió. 

Puede ver eventos de diferentes períodos de tiempo especificando las fechas en los campos de texto encima de los encabezados de tabla. También puedes personalizar el intervalo de tiempo seleccionando diferentes áreas de la escala de tiempo.

**Investigar un dominio:**

1. Seleccione **DIRECCIÓN URL** en el **menú** desplegable De la barra de búsqueda.
2. Escriba la dirección URL en el **campo** Búsqueda.
3. Haga clic en el icono de búsqueda o presione **Entrar**. Se muestran los detalles sobre la dirección URL. Nota: los resultados de la búsqueda solo se devolverán para las direcciones URL observadas en las comunicaciones de los dispositivos de la organización.
4. Use los filtros de búsqueda para definir los criterios de búsqueda. También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección URL, el archivo asociado a la comunicación y la última fecha observada.
5. Hacer clic en cualquiera de los nombres de dispositivo te llevará a la vista de ese dispositivo, donde puedes seguir investigando alertas, comportamientos y eventos notificados.

## <a name="related-topics"></a>Temas relacionados
- [Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigar una cuenta de usuario en Microsoft Defender para endpoint](investigate-user.md)
