---
title: Personalizar los informes en el análisis Microsoft 365 de uso
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Aprenda a personalizar los informes en el explorador y Power BI Desktop.
ms.openlocfilehash: c48e20d234e6e3de75ab54daaf2c169eef3a42ad
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288616"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalizar los informes en el análisis Microsoft 365 de uso

Microsoft 365 análisis de uso proporciona un panel en Power BI que ofrece información sobre cómo los usuarios adoptan y usan Microsoft 365. El panel es tan solo un punto de inicio para interactuar con los datos de uso. Los informes se pueden ajustar para obtener información más personalizada.

También puede usar Power BI Desktop para personalizar aún más los informes al conectarlos a otros orígenes de datos para obtener información avanzada sobre su negocio.

## <a name="customizing-reports-in-the-browser"></a>Personalizar informes en el explorador

En los dos ejemplos siguientes se muestra cómo modificar un objeto visual existente y cómo crear uno.

### <a name="modify-an-existing-visual"></a>Modificar un objeto visual existente

En este ejemplo se muestra cómo modificar la pestaña **Activación** del **informe Activación/Licencias.**

1. Dentro del **informe Activación/licencias,** seleccione la **pestaña** Activación.

2. Para entrar en el  modo de edición, elija el botón Editar de la parte superior a través del botón Más página ![ en Power BI ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) página.

    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. En la parte superior derecha, elija **Duplicar esta página**.

    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. En la parte inferior derecha, elija cualquiera de los gráficos de barras que muestran el recuento de usuarios que se activan en función del sistema operativo, como Android, iOS, Mac, etc.

5. En el **área Visualizaciones** a la derecha, para quitar **Mac Count** del objeto visual, selecciona **la X** junto a él.

    ![Quitar recuento de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>Crear un objeto visual

En el ejemplo siguiente se muestra cómo crear un objeto visual para realizar un seguimiento de nuevos usuarios de Yammer de forma mensual.

1. Vaya al informe **de uso del** producto con la navegación izquierda y seleccione Yammer pestaña. 

2. Cambie al modo de edición seleccionando El botón más página en ![ Power BI ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) y **Editar**.

3. En la parte inferior de la página, seleccione el ![El botón agregar página en Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) para crear una nueva página.

4. En el **área Visualizaciones** a la derecha, elija el gráfico de barras **apiladas** (fila superior, primero desde la izquierda).

    ![Seleccionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. Seleccione la parte inferior derecha de esa visualización y arrástrela para hacerla más grande.

6. En el **área Campos** a la derecha, expanda la **tabla** Calendario.

7. Arrastre **MonthName** al área de campos, directamente debajo del título **Ejes**, en el área **Visualizaciones**.

    ![Drag Month Name](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. En el área **Campos** de la parte derecha, expanda la tabla **TenantProductUsage**.

9. Arrastre **FirstTimeUsers** al área de campos, directamente debajo del encabezado **Valor**.

10. Arrastre **Productos** hasta el área **Filtros**, directamente debajo del encabezado **Filtros de nivel de objeto visual**.

11. En el área **Tipo de filtro** que se muestre, active la casilla **Yammer**.

    ![Active Yammer casilla de verificación](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. Justo debajo de la lista de visualizaciones, elija **el** icono Formato icono Formato en ![ Power BI Visualizaions ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .

13. Expanda el título y cambie el valor de **Texto del título** a **Nuevos usuarios de Yammer por mes**.

14. Cambie el valor de **Tamaño del texto** a **12**.

15. Cambie el título de la nueva página editando el nombre de la página en la parte inferior derecha.

16. Guarde el informe haciendo clic en **la vista de lectura** en la parte superior y, a continuación, **guarde**.

## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizar los informes en Power BI Desktop

Para la mayoría de los clientes, modificar los informes y los objetos visuales de gráficos en la web de Power BI será suficiente. Otros, en cambio, puede que necesiten combinar estos datos con otros orígenes de datos para obtener información contextual más avanzada para su propio negocio; en ese caso, pueden personalizar y crear informes adicionales con Power BI Desktop. Puede descargar [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) de forma gratuita.

### <a name="use-the-reporting-apis"></a>Usar las API de informes

Para empezar, puede conectarse directamente a las API de informes de ODATA Microsoft 365 que enciendan estos informes.

1. Vaya a **Obtener datos** \> **Otros** \> **Fuente de OData** \> **Conectar**.

2. En la ventana dirección URL, escriba "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"

    **NOTA:** Las API de informes están en versión preliminar y están sujetas a cambios hasta que entren en producción.

    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. Escriba sus Microsoft 365 de administrador (organización o escuela) para autenticarse en Microsoft 365 cuando se le pida.

    Consulta las [preguntas más](usage-analytics.md#faq) frecuentes para obtener más información acerca de quién tiene permiso para acceder a los Microsoft 365 de aplicación de plantilla de adopción.

4. Cuando se autorice la conexión, verá la ventana Navegador, donde se muestran los conjuntos de datos a los que puede conectarse.

    Seleccione todo y elija **Cargar**.

    Se descargarán los datos en Power BI Desktop. Guarde el archivo y, después, ya podrá empezar a crear los informes que necesite.

    ![Valores de ODATA disponibles en la API de informes](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>Usar la plantilla Microsoft 365 análisis de uso

También puede usar el archivo de plantilla Power BI que corresponde a los informes Microsoft 365 análisis de uso como punto de partida para conectarse a los datos. La ventaja de usar el archivo pbit es que ya tiene establecida la cadena de conexión. También puede aprovecharse de todas las medidas personalizadas creadas, además de los datos devueltos por el esquema base.

Puede descargar el archivo Power BI de plantilla desde el [Centro de descarga de Microsoft](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). Después de descargar el archivo Power BI plantilla, siga estos pasos para empezar:

1. Abra el archivo pbit.

2. Escriba el valor del id. de espacio empresarial en el cuadro de diálogo.

    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. Escriba sus credenciales de administrador para autenticarse en Microsoft 365 cuando se le pida.

     para obtener más información sobre quién tiene permiso para acceder a los Microsoft 365 de análisis de uso.

    Cuando reciba la autorización, los datos se actualizarán en el archivo de Power BI.

    La carga de datos puede tardar un tiempo; cuando se complete, puede guardar el archivo como .pbix y seguir personalizando los informes, o bien puede agregar un origen de datos adicional al informe.

4. Vea la documentación en [Introducción a Power BI](/power-bi/fundamentals/desktop-getting-started) para conocer cómo crear informes, publicarlos en el servicio de Power BI y compartirlos con su organización. Para seguir estos pasos de personalización y uso compartido, puede que necesite licencias adicionales de Power BI. Para obtener más información, vea la [guía de licencia](https://go.microsoft.com/fwlink/p/?linkid=849803) de Power BI.
