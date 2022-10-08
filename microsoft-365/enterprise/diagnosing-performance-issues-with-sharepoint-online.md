---
title: Diagnosticar problemas de rendimiento con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2021
audience: Admin
ms.topic: troubleshooting
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: En este artículo se muestra cómo diagnosticar problemas comunes con el sitio de SharePoint Online mediante herramientas para desarrolladores de Internet Explorer.
ms.openlocfilehash: 800cdce53e3c80c1d1a385e6671b1dd710a70592
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68179381"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnosticar problemas de rendimiento con SharePoint Online

En este artículo se muestra cómo diagnosticar problemas comunes con el sitio de SharePoint Online mediante herramientas para desarrolladores de Internet Explorer.
  
Hay cuatro maneras diferentes de identificar que una página de un sitio de SharePoint Online tiene un problema de rendimiento con las personalizaciones.

- Diagnóstico de rendimiento del sitio y la página
  
- Monitor de red de la barra de herramientas F12

- Comparación con una línea base no personalizada

- Métricas del encabezado de respuesta de SharePoint Online

En este tema se describe cómo usar cada uno de estos métodos para diagnosticar problemas de rendimiento. Una vez que haya descubierto la causa del problema, puede trabajar hacia una solución mediante los artículos sobre la mejora del rendimiento de SharePoint que puede encontrar en https://aka.ms/tune.  

## <a name="use-the-site-and-page-performance-diagnostic-from-the-microsoft-365-admin-center"></a>Uso del diagnóstico de rendimiento del sitio y la página desde el Centro de Administración de Microsoft 365

> [!NOTE]
> Si es administrador y tiene problemas con el rendimiento en SharePoint, seleccione **Ejecutar pruebas** a continuación, que rellenará el diagnóstico de rendimiento del sitio y la página en el Centro de Administración de Microsoft 365. Estas pruebas comprobarán la configuración y recomendarán rápidamente los pasos siguientes para ayudar a mejorar el rendimiento de SharePoint para el inquilino.
>> [!div class="nextstepaction"]
>> [Ejecutar pruebas: Comprobar el rendimiento de SharePoint](https://aka.ms/PillarSiteandPagePerf)

> [!NOTE] 
> Esta característica no está disponible para Microsoft 365 Government, Microsoft 365 operado por 21Vianet o Microsoft 365 Alemania.
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Uso de la barra de herramientas F12 para diagnosticar el rendimiento en SharePoint Online
<a name="F12ToolInfo"> </a>

En este artículo, usamos Internet Explorer 11. Las versiones de las herramientas de desarrollo de F12 en otros exploradores tienen características similares, aunque pueden parecer ligeramente diferentes. Para obtener información sobre las herramientas para desarrolladores de F12, consulte:
  
- [Novedades de F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [Usar las herramientas de desarrollo F12](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

Para abrir las herramientas de desarrollo, presione **F12** y, a continuación, haga clic en el icono de Wi-Fi:
  
![Captura de pantalla del icono wifi de las herramientas de desarrollo de F12.](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
En la pestaña **Red** , presione el botón de reproducción verde para cargar una página. La herramienta devuelve todos los archivos que solicita el explorador para obtener la página que solicitó. En la captura de pantalla siguiente se muestra una de estas listas.
  
![Captura de pantalla de la lista de archivos que se devuelve con una solicitud de página.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
También puede ver las horas de descarga de los archivos en el lado derecho, como se muestra en esta captura de pantalla.
  
![Diagrama que muestra el tiempo necesario para cargar las páginas solicitadas desde SharePoint.](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Esto proporciona una representación visual del tiempo que tardó el archivo en cargarse. La línea verde representa cuándo está lista la página para que la represente el explorador. Esto puede proporcionarle una vista rápida de los diferentes archivos que podrían estar causando cargas lentas de páginas en el sitio.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Configuración de una línea base no personalizada para SharePoint Online
<a name="F12ToolInfo"> </a>

La mejor manera de determinar los puntos débiles de rendimiento del sitio es configurar una colección de sitios completamente lista para usar en SharePoint Online. De este modo, puede comparar todos los diversos aspectos de su sitio con lo que obtendría sin personalización en la página. La página principal OneDrive para la Empresa es un buen ejemplo de una colección de sitios independiente que es poco probable que tenga personalizaciones.
  
## <a name="viewing-sharepoint-response-header-information"></a>Visualización de la información del encabezado de respuesta de SharePoint
<a name="F12ToolInfo"> </a>

En SharePoint Online, puede acceder a la información que se devuelve al explorador en el encabezado de respuesta de cada archivo. El valor más útil para diagnosticar problemas de rendimiento es **SPRequestDuration**, que muestra la cantidad de tiempo que la solicitud tardó en procesarse en el servidor. Esto puede ayudar a determinar si la solicitud es pesada y consume muchos recursos. Esta es la mejor información que tiene sobre cuánto trabajo está realizando el servidor para atender la página.

### <a name="to-view-sharepoint-response-header-information"></a>Para ver la información del encabezado de respuesta de SharePoint
  
1. Asegúrese de que tiene instaladas las herramientas F12. Para obtener más información sobre cómo descargar e instalar estas herramientas, consulte [Novedades de las herramientas de F12](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).

2. En las herramientas F12, en la pestaña **Red** , presione el botón de reproducción verde para cargar una página.

3. Haga clic en uno de los archivos .aspx devueltos por la herramienta y, a continuación, haga clic en **DETALLES**.

    ![Muestra los detalles del encabezado de respuesta.](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Haga clic en **Encabezados de respuesta**.

    ![Diagrama que muestra la dirección URL del encabezado de respuesta.](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>¿Qué causa problemas de rendimiento en SharePoint Online?
<a name="F12ToolInfo"> </a>

En el artículo [Opciones de navegación para SharePoint Online](navigation-options-for-sharepoint-online.md) se muestra un ejemplo de uso del valor SPRequestDuration para determinar que la complicada navegación estructural estaba provocando que la página tardara mucho tiempo en procesarse en el servidor. Al tomar un valor para un sitio de línea base (sin personalización), es posible determinar si un archivo determinado tarda mucho tiempo en cargarse. El ejemplo usado en [opciones de navegación para SharePoint Online](navigation-options-for-sharepoint-online.md) es el archivo .aspx principal. Ese archivo contiene la mayor parte del código de ASP.NET que se ejecuta para la carga de página. En función de la plantilla de sitio que use, podría ser start.aspx, home.aspx, default.aspx u otro nombre si personaliza la página principal. Si este número es considerablemente mayor que el sitio de línea base, es una buena indicación de que hay algo complejo en la página que está causando problemas de rendimiento.
  
Una vez que haya identificado que un problema específico del sitio, la manera recomendada de averiguar lo que provoca un rendimiento deficiente es eliminar todas las causas posibles, como las personalizaciones de página, y luego agregarlas de nuevo al sitio una por una. Una vez que haya quitado suficientes personalizaciones que la página tenga un buen rendimiento, puede agregar personalizaciones específicas una por una.
  
Por ejemplo, si tiene una navegación compleja, intente cambiar la navegación para no mostrar subsitios y compruebe las herramientas para desarrolladores para ver si esto hace una diferencia. O bien, si tiene una gran cantidad de roll-ups de contenido, intente quitarlos de la página y ver si esto mejora las cosas. Si elimina todas las causas posibles y las agrega de nuevo de uno en uno, puede identificar fácilmente qué características son el mayor problema y, a continuación, trabajar hacia una solución.
