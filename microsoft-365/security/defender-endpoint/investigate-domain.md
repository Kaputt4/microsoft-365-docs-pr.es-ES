---
title: Investigación de dominios y direcciones URL asociados a una alerta de Microsoft Defender para punto de conexión
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
- m365-security
- tier2
ms.topic: conceptual
ms.date: 04/24/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7f218836b3b4fe54533fae623217a7781852e2bf
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769499"
---
# <a name="investigate-domains-and-urls-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigación de dominios y direcciones URL asociados a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)

Investigue un dominio para ver si los dispositivos y servidores de la red empresarial se han estado comunicando con un dominio malintencionado conocido.

Puede investigar una dirección URL o dominio mediante la característica de búsqueda, desde la experiencia de incidente (en la pestaña evidencia o desde el artículo de alertas) o haciendo clic en el vínculo URL o dominio de la **escala de tiempo del dispositivo**.

Puede ver información de las secciones siguientes en la vista URL y dominio:

- Detalles del dominio, información de contacto del solicitante de registro

- Veredicto de Microsoft

- Incidentes relacionados con esta dirección URL o dominio

- Prevalencia de la dirección URL o dominio en la organización

- Dispositivos observados más recientes con dirección URL o dominio

 ![La sección de información general de la nueva dirección URL & página de dominio de un vistazo.](media/domain-url-overview.png)

## <a name="domain-entity"></a>Entidad de dominio

Puede pasar a la página de dominio desde los detalles del dominio en la página url o panel lateral, simplemente haga clic en **el vínculo Ver página de dominio** . La entidad de dominio muestra una agregación de todos los datos de las direcciones URL con el FQDN (nombre de dominio completo). Por ejemplo, si se observa un dispositivo que se comunica con `sub.domain.tld/path1`y se observa que otro dispositivo se comunica con `sub.domain.tld/path2`, cada dirección URL del dispositivo anterior mostrará una observación del dispositivo y el dominio mostrará las dos observaciones del dispositivo. En este caso, un dispositivo que se comunica con no se correlacionará con esta página de dominio, sino `othersub.domain.tld`con `othersub.domain.tld/path` .

## <a name="url-and-domain-overview"></a>Introducción a la dirección URL y el dominio

En la sección URL de todo el mundo se muestra la dirección URL, un vínculo a más detalles en Whois, el número de incidentes abiertos relacionados y el número de alertas activas.

### <a name="url-summary-details"></a>Detalles de resumen de la dirección URL

Muestra la dirección URL original (información de dirección URL existente), con los parámetros de consulta y el protocolo de nivel de aplicación. A continuación encontrará los detalles completos del dominio, como la fecha de registro, la fecha de modificación y la información de contacto del solicitante de registro.

Veredicto de Microsoft sobre la dirección URL o dominio y una sección de prevalencia de dispositivos. En esta área, puede ver el número de dispositivos que se comunicaron con la dirección URL o el dominio en los últimos 30 días y pivotar al primer o último evento de la escala de tiempo del dispositivo de inmediato. Para investigar el acceso inicial o si todavía hay una actividad malintencionada en el entorno.

### <a name="incidents-and-alerts"></a>Incidentes y alertas

La sección Incidentes y alertas muestra un gráfico de barras de todas las alertas activas en incidentes de los últimos 180 días.

### <a name="microsoft-verdict"></a>Veredicto de Microsoft

En la sección Veredicto de Microsoft se muestra el veredicto de la dirección URL o dominio de la biblioteca de Ti de Microsoft. Muestra si la dirección URL o el dominio ya se conoce como suplantación de identidad o entidad malintencionada.

### <a name="prevalence"></a>Prevalencia

En la sección Prevalencia se proporcionan los detalles sobre la prevalencia de la dirección URL dentro de la organización, durante los últimos 30 días, como y el gráfico de tendencias, que muestra el número de dispositivos distintos que se comunicaron con la dirección URL o el dominio durante un período de tiempo específico. A continuación, si puede encontrar detalles de la primera y última observación del dispositivo comunicadas con la dirección URL en los últimos 30 días, donde puede girar a la escala de tiempo del dispositivo de inmediato, para investigar el acceso inicial desde el vínculo phish o si todavía hay una comunicación malintencionada en su entorno.

## <a name="incident-and-alerts"></a>Incidentes y alertas

![La pestaña incidentes y alertas proporciona una lista de incidentes asociados a la dirección URL o el dominio.](media/domain-incidents.png)

La pestaña incidentes y alertas proporciona una lista de incidentes asociados a la dirección URL o el dominio. La tabla que se muestra aquí es una versión filtrada de los incidentes visible en la pantalla Cola de incidentes, que muestra solo los incidentes asociados a la dirección URL o el dominio, su gravedad, los recursos afectados y mucho más.

La pestaña Incidentes y alertas se puede ajustar para mostrar más o menos información; para ello, seleccione **Personalizar columnas** en el menú de acción situado encima de los encabezados de columna. El número de elementos mostrados también se puede ajustar seleccionando elementos por página en el mismo menú.

## <a name="devices"></a>Dispositivos

![La pestaña dispositivo muestra el número de dispositivos distintos que se comunicaron con la dirección URL o el dominio durante un período de tiempo específico.](media/domain-device-overview.png)

La pestaña Dispositivos proporciona una vista cronológica de todos los dispositivos que se observaron para una dirección URL específica o un dominio. Esta pestaña incluye un gráfico de tendencias y una tabla personalizable que enumera los detalles del dispositivo, como el nivel de riesgo, el dominio y mucho más. Más allá de eso, puede ver las primeras y últimas horas de eventos en las que el dispositivo interactuó con la dirección URL o el dominio, y el tipo de acción de este evento. Con el menú situado junto al nombre del dispositivo, puede girar rápidamente a la escala de tiempo del dispositivo para investigar aún más lo que ocurrió antes o después del evento que implicaba esta dirección URL o dominio.

Aunque el período de tiempo predeterminado es de los últimos 30 días, puede personalizarlo desde la lista desplegable disponible en la esquina de la tarjeta. El intervalo más corto disponible es para la prevalencia durante el último día, mientras que el intervalo más largo es en los últimos seis meses.

Con el botón exportar situado encima de la tabla, puede exportar todos los datos a un archivo .csv (incluida la primera y la última hora del evento y el tipo de acción) para realizar más investigaciones e informes.

### <a name="investigate-a-url-or-domain"></a>Investigación de una dirección URL o dominio

1. Seleccione **DIRECCIÓN URL** en el menú desplegable **De la barra de búsqueda** .

2. Escriba la dirección URL en el campo **Buscar** .

3. Haga clic en el icono de búsqueda o presione **Entrar**. Se muestran detalles sobre la dirección URL.

   > [!NOTE]
   > Los resultados de búsqueda solo se devolverán para las direcciones URL observadas en las comunicaciones desde dispositivos de la organización.

4. Use los filtros de búsqueda para definir los criterios de búsqueda. También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección URL, el archivo asociado a la comunicación y la última fecha observada.

5. Hacer clic en cualquiera de los nombres de dispositivo le llevará a la vista de ese dispositivo, donde puede continuar investigando las alertas, los comportamientos y los eventos notificados.

## <a name="related-articles"></a>Artículos relacionados

- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión](investigate-user.md)
