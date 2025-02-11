---
title: Personalización de los informes en análisis de uso de Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
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
ms.openlocfilehash: 1d2931ed5cd956da10bb555c87017da8d8ee2026
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68725636"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalización de los informes en análisis de uso de Microsoft 365

El análisis de uso de Microsoft 365 proporciona un panel en Power BI que ofrece información sobre cómo los usuarios adoptan y usan Microsoft 365. El panel es tan solo un punto de inicio para interactuar con los datos de uso. Los informes se pueden ajustar para obtener información más personalizada.

También puede usar Power BI Desktop para personalizar aún más los informes al conectarlos a otros orígenes de datos para obtener información avanzada sobre su negocio.

## <a name="customizing-reports-in-the-browser"></a>Personalizar informes en el explorador

En los dos ejemplos siguientes se muestra cómo modificar un objeto visual existente y cómo crear uno.

### <a name="modify-an-existing-visual"></a>Modificar un objeto visual existente

En este ejemplo se muestra cómo modificar la pestaña **Activación** en el informe **Activación/Licencias** .

1. En el informe **Activación/licencias** , seleccione la pestaña **Activación** .

2. Escriba el modo de edición eligiendo el botón **Editar** de la parte superior a través del ![botón La página más de Power BI.](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) .

    ![Haga clic en Editar informe en el panel de navegación superior derecho.](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. En la parte superior derecha, elija **Duplicar esta página**.

    ![Elija Duplicar esta página.](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. En la parte inferior derecha, elija cualquiera de los gráficos de barras que muestran el número de usuarios que se activan en función del sistema operativo, como Android, iOS, Mac, etc.

5. En el área **Visualizaciones** de la derecha, para quitar **Mac Count** del objeto visual, seleccione la **X** situada junto a él.

    ![Quitar Recuento de Mac.](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>Crear un objeto visual

En el ejemplo siguiente se muestra cómo crear un objeto visual para realizar un seguimiento de nuevos usuarios de Yammer de forma mensual.

1. Vaya al informe **De uso del producto** con la navegación izquierda y seleccione la pestaña **Yammer** .

2. Cambie al modo de edición eligiendo el ![botón La página más en Power BI.](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) y **Editar**.

3. En la parte inferior de la página, seleccione ![Botón Agregar página en Power BI.](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) para crear una nueva página.

4. En el área **Visualizaciones** de la derecha, elija el **gráfico de barras apiladas** (fila superior, primero a la izquierda).

    ![Seleccione Gráfico de barras.](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. Seleccione la parte inferior derecha de esa visualización y arrástrela para que sea más grande.

6. En el área **Campos** de la derecha, expanda la tabla **Calendario** .

7. Arrastre **MonthName** al área de campos, directamente debajo del título **Ejes**, en el área **Visualizaciones**.

    ![Arrastre Nombre del mes.](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. En el área **Campos** de la parte derecha, expanda la tabla **TenantProductUsage**.

9. Arrastre **FirstTimeUsers** al área de campos, directamente debajo del encabezado **Valor**.

10. Arrastre **Productos** hasta el área **Filtros**, directamente debajo del encabezado **Filtros de nivel de objeto visual**.

11. En el área **Tipo de filtro** que se muestre, active la casilla **Yammer**.

    ![Seleccione la casilla Yammer.](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. Justo debajo de la lista de visualizaciones, elija el icono ![**Formato** icono Formato en Visualizaciones de Power BI.](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)

13. Expanda el título y cambie el valor de **Texto del título** a **Nuevos usuarios de Yammer por mes**.

14. Cambie el valor de **Tamaño del texto** a **12**.

15. Cambie el título de la nueva página editando el nombre de la página en la parte inferior derecha.

16. Guarde el informe haciendo clic en **La vista de lectura** en la parte superior y, a continuación, **guardar**.

## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizar los informes en Power BI Desktop

For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.

### <a name="use-the-reporting-apis"></a>Usar las API de informes

Para empezar, puede conectarse directamente a las API de informes de ODATA desde Microsoft 365 que alimentan estos informes.

1. Vaya a **Obtener datos** \> **Otros** \> **Fuente de OData** \> **Conectar**.

2. En la ventana URL, escriba "https://<i></i> reports.office.com/pbi/v1.0/\<tenantid\>"

    **NOTA:** Las API de informes están en versión preliminar y están sujetas a cambios hasta que entran en producción.

    ![Dirección URL de fuente de OData para Power BI Desktop.](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. Escriba las credenciales de administrador de Microsoft 365 (organización o escuela) para autenticarse en Microsoft 365 cuando se le solicite.

    Consulte las [preguntas más frecuentes](usage-analytics.md#faq) para obtener más información sobre quién tiene permiso para acceder a los informes de aplicaciones de plantilla de adopción de Microsoft 365.

4. Cuando se autorice la conexión, verá la ventana Navegador, donde se muestran los conjuntos de datos a los que puede conectarse.

    Seleccione todo y elija **Cargar**.

    Se descargarán los datos en Power BI Desktop. Guarde el archivo y, después, ya podrá empezar a crear los informes que necesite.

    ![Valores de ODATA disponibles en la API de informes.](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>Uso de la plantilla de análisis de uso de Microsoft 365

También puede usar el archivo de plantilla de Power BI correspondiente a los informes de análisis de uso de Microsoft 365 como punto de partida para conectarse a los datos. La ventaja de usar el archivo pbit es que ya tiene establecida la cadena de conexión. También puede aprovecharse de todas las medidas personalizadas creadas, además de los datos devueltos por el esquema base.

Puede descargar el archivo de plantilla de Power BI desde el [Centro de descarga de Microsoft](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). Después de descargar el archivo de plantilla de Power BI, siga estos pasos para empezar:

1. Abra el archivo pbit.

2. Escriba el valor del id. de espacio empresarial en el cuadro de diálogo.

    ![Escriba el identificador de inquilino para abrir el archivo pbit.](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. Escriba las credenciales de administrador para autenticarse en Microsoft 365 cuando se le solicite.

     para obtener más información sobre quién puede acceder a los informes de análisis de uso de Microsoft 365.

    Cuando reciba la autorización, los datos se actualizarán en el archivo de Power BI.

    La carga de datos puede tardar un tiempo; cuando se complete, puede guardar el archivo como .pbix y seguir personalizando los informes, o bien puede agregar un origen de datos adicional al informe.

4. Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.
