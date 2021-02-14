---
title: Usar la herramienta de diagnóstico de páginas para SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Use la herramienta Diagnóstico de páginas para SharePoint para analizar el portal moderno de SharePoint Online y las páginas de publicación clásicas con un conjunto predefinido de criterios de rendimiento.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696589"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Usar la herramienta Diagnóstico de páginas para SharePoint

En este artículo se describe cómo usar la herramienta Diagnóstico de páginas para SharePoint para analizar páginas de sitio modernas y **clásicas** de SharePoint Online con un conjunto predefinido de criterios de rendimiento.

La herramienta Diagnóstico de páginas para SharePoint se puede instalar para:

- **Microsoft Edge** [(extensión de Edge)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(extensión de Chrome)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>La **versión 2.0.0 y posteriores** incluye compatibilidad con páginas modernas además de páginas de sitio clásicas. Si no está seguro de qué versión de la  herramienta está usando, puede seleccionar el vínculo Acerca de o los puntos suspensivos (...) para comprobar la versión. **Actualiza siempre a la versión más reciente** al usar la herramienta.

La herramienta de Diagnóstico de páginas para SharePoint es una extensión de explorador para los nuevos exploradores de Microsoft Edge (https://www.microsoft.com/edge) y Chrome que analiza las páginas del sitio de publicación clásicas y las modernas del portal de SharePoint Online. Esta herramienta solo funciona para SharePoint Online y no se puede usar en una página del sistema de SharePoint.

La herramienta genera un informe para cada página analizada que muestra el rendimiento de la página con respecto a un conjunto predefinido de reglas y muestra información detallada cuando los resultados de una prueba están fuera del valor de línea base. Los diseñadores y administradores de SharePoint Online pueden usar la herramienta para solucionar problemas de rendimiento y garantizar que las páginas nuevas estén optimizadas antes de la publicación.

La herramienta diagnóstico de páginas está diseñada para analizar solo páginas de sitio de SharePoint, no páginas del sistema como *allitems.aspx* o *sharepoint.aspx*. Si intenta ejecutar la herramienta en una página del sistema o en cualquier otra página que no sea de sitio, recibirá un mensaje de error que le indica que la herramienta no se puede ejecutar para ese tipo de página.

![Debe ejecutarse en una página de SharePoint](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Esto no es un error en la herramienta, ya que no hay ningún valor en la evaluación de bibliotecas o páginas del sistema. Vaya a una página del sitio de SharePoint para usar la herramienta. Si este error se produce en una página de SharePoint, compruebe la página maestra para asegurarse de que no se han quitado las metatags de SharePoint.

Para proporcionar comentarios sobre la herramienta, seleccione los puntos suspensivos en la esquina superior derecha de la herramienta y, a continuación, [seleccione Enviar comentarios.](https://go.microsoft.com/fwlink/?linkid=874109)

![Enviar comentarios](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Instalación de la herramienta Diagnóstico de página para SharePoint

El procedimiento de instalación de esta sección funcionará para los exploradores Chrome y Microsoft Edge.

> [!IMPORTANT]
> Microsoft no lee los datos ni el contenido de la página que analiza la herramienta Diagnóstico de páginas para SharePoint y no capturamos información personal, sitio web ni información de descarga. La única información identificable registrada en Microsoft por la herramienta es el nombre del inquilino, los recuentos de reglas que han fallado y la fecha y hora en que se ha ejecutado la herramienta. Microsoft usa esta información para comprender mejor las tendencias de uso de sitios de publicación y portales modernos y los problemas comunes de rendimiento.

1. Instale la herramienta Diagnóstico de página para SharePoint **para Microsoft Edge** [(extensión Edge)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) o **Chrome** [(extensión chrome).](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi) Revisa la directiva de privacidad del usuario proporcionada en la página de descripción de la tienda. Al agregar la herramienta al explorador, verá el siguiente aviso de permisos.

    ![Permisos de extensión](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Este aviso está en su lugar porque una página puede contener contenido de ubicaciones fuera de SharePoint en función de los elementos web y las personalizaciones de la página. Esto significa que la herramienta leerá las solicitudes y respuestas cuando se haga clic en el botón Inicio y solo para la pestaña activa de SharePoint donde se ejecuta la herramienta. El explorador web captura esta información localmente y está disponible a través del botón Exportar  a **JSON** o Exportar a **HAR** en la pestaña Seguimiento de red de la herramienta. Microsoft no envía ni captura la **información.** (La herramienta respeta la directiva de privacidad de Microsoft accesible [aquí).](https://go.microsoft.com/fwlink/p/?linkid=857875)

    El _permiso Administrar las descargas_ cubre el uso de la funcionalidad Exportar a JSON de **la** herramienta. Siga las directrices de privacidad de su empresa antes de compartir el archivo JSON fuera de su organización, ya que los resultados contienen direcciones URL y se pueden clasificar como PII (Información de identificación personal).
1. Si desea usar la herramienta en modo Incógnito o InPrivate, siga el procedimiento para el explorador:
    1. En Microsoft Edge, vaya **a Extensiones** o _escriba edge://extensions_ en la barra de direcciones URL y seleccione **Detalles** para la extensión. En la configuración de extensión, active la casilla para **permitir en InPrivate**.
    1. En Chrome, vaya **a Extensiones** o _escriba chrome://extensions_ en la barra de direcciones URL y seleccione **Detalles** para la extensión. En la configuración de extensión, selecciona el control deslizante para **permitir en incógnito.**
1. Vaya a la página del sitio de SharePoint en SharePoint Online que le gustaría revisar. Hemos permitido "retrasar la carga" de elementos en las páginas; por lo tanto, la herramienta no se detendrá automáticamente (esto es por diseño para dar cabida a todos los escenarios de carga de página). Para detener la colección, seleccione **Detener**. Asegúrese de que la carga de la página se haya completado antes de detener la recopilación de datos o de capturar solo un seguimiento parcial.
1. Haga clic en el botón de la barra de herramientas de la extensión ![Logotipo de Diagnóstico de página para SharePoint](../media/page-diagnostics-for-spo/pagediag-icon32.png) para cargar la herramienta y se te mostrará la siguiente ventana emergente de extensión:

    ![Elemento emergente de la herramienta de diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Seleccione **Inicio para** empezar a recopilar datos para su análisis.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Lo que verá en la herramienta Diagnóstico de páginas para SharePoint

1. Haga clic en los puntos suspensivos (...) en la esquina superior derecha de la herramienta para encontrar los siguientes vínculos:
   1. El **vínculo Recursos adicionales** proporciona instrucciones generales y detalles sobre la herramienta, incluido un vínculo a este artículo.
   1. El **vínculo Enviar comentarios** proporciona un vínculo al sitio de _SharePoint Sites y Collaboration User Voice._
   1. El **vínculo** Acerca de incluye la versión instalada actualmente de la herramienta y un vínculo directo al aviso de terceros de la herramienta.  
1. Los detalles de id. de **correlación, SPRequestDuration, SPIISLatency,** **tiempo** de carga de página y **dirección URL** son informativos y se pueden usar con algunos fines.

    ![Detalles de diagnósticos de página](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** es un elemento importante al trabajar con el Soporte técnico de Microsoft, ya que les permite recopilar datos de diagnóstico adicionales para la página específica.
   - **SPRequestDuration es** el tiempo que SharePoint necesita para procesar la página. La navegación estructural, imágenes de gran tamaño y muchas llamadas API podrían contribuir a duraciones más largas.
   - **SPIISLatency es** el tiempo en milisegundos que se toma para que SharePoint Online empiece a cargar la página. Este valor no incluye el tiempo necesario para que la aplicación web responda.
   - **El tiempo de carga de** la página es el tiempo total registrado por la página desde el momento de la solicitud hasta el momento en que se recibió y representó la respuesta en el explorador. Este valor se ve afectado por diversos factores, como la latencia de red, el rendimiento del equipo y el tiempo que tarda el explorador en cargar la página.
   - La **dirección URL de** página (Localizador uniforme de recursos) es la dirección web de la página actual.

1. La [**pestaña Pruebas**](#how-to-use-the-diagnostic-tests-tab) de diagnóstico muestra los resultados del análisis en tres categorías; **No se requiere ninguna acción,** **se requieren oportunidades de mejora** y **atención.** Cada resultado de la prueba se representa mediante un elemento de una de estas categorías, tal como se describe en la tabla siguiente:

    |Categoría  |Color  |Description  |
    |---------|---------|---------|
    |**Se requiere atención** |Rojo |El resultado de la prueba queda fuera del valor de línea base y afecta al rendimiento de la página. Siga las instrucciones de corrección.|
    |**Oportunidades de mejora** |Amarillo |El resultado de la prueba queda fuera del valor de línea base y podría estar contribuyendo a problemas de rendimiento. Se pueden aplicar criterios específicos de la prueba.|
    |**No se requiere ninguna acción.** |Verde |El resultado de la prueba se encuentra dentro del valor de línea base de la prueba.|

    ![Diagnósticos de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Una [**pestaña de seguimiento de**](#how-to-use-the-network-trace-tab) red proporciona detalles sobre las solicitudes y respuestas de compilación de página.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Cómo usar la pestaña Pruebas de diagnóstico

Cuando analiza una página del portal moderno de SharePoint o una página de sitio de publicación clásica con la herramienta Diagnóstico de páginas  para SharePoint, los resultados se analizan mediante reglas predefinidas que comparan los resultados con los valores de línea base y se muestran en la pestaña Pruebas de diagnóstico. Las reglas para determinadas pruebas pueden usar valores de línea base diferentes para el portal moderno y los sitios de publicación clásicos en función de la diferencia entre las características de rendimiento específicas entre los dos.

Los resultados de las pruebas que aparecen en las categorías Oportunidades de mejora o Atención requerida indican áreas que deben revisarse según las prácticas **recomendadas** y se pueden seleccionar para mostrar información adicional sobre el resultado.  Los detalles de cada elemento incluyen un vínculo _Más_ información que te llevará directamente a las instrucciones adecuadas relacionadas con la prueba. Los resultados de las pruebas que aparecen en la categoría **Sin** acción requerida indican el cumplimiento de la regla relevante y no muestran detalles adicionales cuando se seleccionan.

La información de la pestaña Pruebas de diagnóstico no le mostrará cómo diseñar páginas, pero resaltará los factores que pueden afectar al rendimiento de la página. Algunas personalizaciones y funcionalidades de página tienen un impacto inevitable en el rendimiento de la página y deben revisarse para ver si la página puede corregirse u omisión si su impacto es considerable.

Los resultados rojos o amarillos también pueden indicar elementos web que actualizan los datos con demasiada frecuencia. Por ejemplo, las noticias corporativas no se actualizan cada segundo, pero los elementos web personalizados se suelen crear para capturar las últimas noticias cada segundo en lugar de implementar elementos de almacenamiento en caché que podrían mejorar la experiencia general del usuario. Al incluir elementos web en una página, tenga en cuenta que a menudo hay formas sencillas de reducir su impacto en el rendimiento evaluando el valor de cada parámetro disponible para asegurarse de que se establece correctamente para su propósito previsto.

>[!NOTE]
>Los sitios de grupo clásicos que no tienen habilitada la característica de publicación no pueden usar CDN. Al ejecutar la herramienta en estos sitios, se espera que la prueba de red CDN falle y se pueda omitir, pero todas las pruebas restantes son aplicables. La funcionalidad adicional de la característica de publicación de SharePoint puede aumentar los tiempos de carga de la página, por lo que no debe habilitarse solo para permitir la funcionalidad de la red CDN.

>[!IMPORTANT]
>Las reglas de prueba se agregan y actualizan periódicamente, por lo que consulte la versión más reciente de la herramienta para obtener más información sobre las reglas actuales y la información específica incluida en los resultados de las pruebas. Puede comprobar la versión administrando las extensiones y la extensión le informará si hay disponible una actualización.

## <a name="how-to-use-the-network-trace-tab"></a>Cómo usar la pestaña Seguimiento de red

La **pestaña Seguimiento de** red proporciona información detallada sobre las solicitudes para crear la página y las respuestas recibidas de SharePoint.

1. **Busque tiempos de carga de elementos marcados como rojos.** Cada solicitud y respuesta se codifica en color para indicar su impacto en el rendimiento general de la página mediante las siguientes métricas de latencia:
    - Verde: \< 500 ms
    - Amarillo: 500-1000 ms
    - Rojo: \> 1000 ms

    ![Seguimiento de red](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    En la imagen anterior, el elemento rojo pertenece a la página predeterminada. Siempre se mostrará en rojo a menos que la página se cargue en \< 1000 ms (menos de 1 segundo).

2. **Tiempos de carga de elementos de prueba.** En algunos casos no habrá ningún indicador de hora o color porque el explorador ya ha almacenado en caché los elementos. Para probar esto correctamente, abra la página,  borre la memoria caché del explorador y, a continuación, haga clic en Inicio, ya que eso forzará una carga de página "en frío" y será un verdadero reflejo de la carga inicial de la página. A continuación, debe compararse con la carga de página "templada", ya que también ayudará a determinar qué elementos se almacenan en caché en la página.

3. **Compartir detalles relevantes con otras personas que puedan ayudar a investigar problemas.** Para compartir los detalles o la información proporcionada en la herramienta con los desarrolladores o con una persona de soporte técnico, haga clic en Exportar a **JSON** (como se muestra en la imagen anterior). Esto le permitirá descargar los resultados, que se pueden ver con un visor de archivos JSON.

    Si ha optado por usar la característica de vista previa, habilite Exportar a *HAR,* el tipo de exportación se mostrará **como Exportar a HAR.**

    ![Seguimiento de red](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> Estos resultados contienen direcciones URL que se pueden clasificar como PII (información de identificación personal). Asegúrese de seguir las directrices de su organización antes de distribuir esa información.

## <a name="engaging-with-microsoft-support"></a>Interactuar con el soporte técnico de Microsoft

Hemos incluido una característica de **nivel de soporte** técnico de Microsoft que solo debe usarse cuando se trabaja directamente en un caso de soporte técnico. El uso de esta característica no le proporcionará ninguna ventaja cuando se usa sin la participación del equipo de soporte técnico y puede hacer que el rendimiento de la página sea significativamente más lento. No hay información adicional al usar esta característica en la herramienta, ya que la información adicional se agrega al registro en el servicio.

No hay ningún cambio visible, excepto que se le notificará que lo ha habilitado y que el rendimiento de la página se verá significativamente degradado en 2-3 veces más lento rendimiento mientras está habilitado. Solo será relevante para la página concreta y la sesión activa. Por este motivo, debe usarse con moderación y solo cuando se deba usar activamente con soporte técnico.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Para habilitar la característica de nivel de soporte técnico de Microsoft

1. Abra la herramienta Diagnóstico de página para SharePoint.
2. En el teclado, presione **ALT-Mayús-L**. Se mostrará la casilla Habilitar **registro de** compatibilidad.
3. Active la casilla y, a continuación, haga clic en **Inicio** para volver a cargar la página y generar un registro detallado.

    ![Opción de soporte técnico habilitada](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    Debes tener en cuenta el CorrelationID (que se muestra en la parte superior de la herramienta) y proporcionarlo a tu representante de soporte técnico para que pueda recopilar información adicional sobre la sesión de diagnóstico.

## <a name="related-topics"></a>Temas relacionados

[Ajustar el rendimiento de SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar el rendimiento de Office 365](tune-microsoft-365-performance.md)

[Rendimiento en la experiencia moderna de SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Redes de entrega de contenido](content-delivery-networks.md)

[Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
