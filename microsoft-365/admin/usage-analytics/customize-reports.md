---
title: Personalizar los informes en análisis de uso de Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Obtenga información sobre cómo personalizar los informes en el explorador y en Power BI Desktop.
ms.openlocfilehash: 5fc3b399638b2f1e9b1b2726fbf58e22eda33e01
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248233"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalizar los informes en análisis de uso de Microsoft 365

El análisis de uso de Microsoft 365 proporciona un panel en Power BI que ofrece información sobre cómo los usuarios adoptan y usan Microsoft 365. El panel es tan solo un punto de inicio para interactuar con los datos de uso. Los informes se pueden ajustar para obtener información más personalizada.
  
También puede usar Power BI Desktop para personalizar aún más los informes al conectarlos a otros orígenes de datos para obtener información avanzada sobre su negocio.
  
## <a name="customizing-reports-in-the-browser"></a>Personalizar informes en el explorador

En los dos ejemplos siguientes se muestra cómo modificar un objeto visual existente y cómo crear uno.
  
### <a name="modify-an-existing-visual"></a>Modificar un objeto visual existente

En este ejemplo se muestra cómo modificar la pestaña **activación** en el informe de **activación/licencias** . 
  
1. En el informe de **activación/licencia** , haga clic en la pestaña **activación** .
    
2. Para entrar en el modo de edición **** , haga clic en el botón Editar ![en la parte superior con el botón](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) más página del botón Power BI. 
    
    ![Click Edit report on the top right navigation](../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. En la parte superior derecha, haga clic en **duplicar esta página**.
    
    ![Choose Duplicate this page](../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. En la parte inferior derecha, haga clic en cualquiera de los gráficos de barras que muestren el número de usuarios que se activan según el sistema operativo, como Android, iOS, Mac, etc.
    
5. En el área **visualizaciones** de la derecha, para quitar el **recuento de Mac** del objeto visual, haga clic en la **X** junto a él.

    ![Quitar recuento Mac](../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Crear un objeto visual

En el ejemplo siguiente se muestra cómo crear un objeto visual para realizar un seguimiento de nuevos usuarios de Yammer de forma mensual.
  
1. Vaya al informe de **uso del producto** usando el panel de navegación izquierdo y haga clic en la pestaña **Yammer** .
    
2. Cambie al modo de edición haciendo clic ![en el botón más página en Power](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI y **editando**. 
    
3. En la parte inferior de la página, haz clic en ![Botón Agregar página de Power BI](../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) para crear una nueva página.
  
4. En el área **visualizaciones** de la derecha, haga clic en el **gráfico de barras apiladas** (fila superior, primero desde la izquierda).

    ![Seleccionar gráfico de barras](../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Haga clic en la esquina inferior derecha de esa visualización y arrástrela para ampliar su tamaño.

6. En el área **campos** a la derecha, expanda la tabla de **calendarios** .

7. Arrastre **MonthName** al área de campos, directamente debajo del título **Ejes**, en el área **Visualizaciones**.
 
    ![Arrastrar nombre del mes](../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. En el área **Campos** de la parte derecha, expanda la tabla **TenantProductUsage**.

9. Arrastre **FirstTimeUsers** al área de campos, directamente debajo del encabezado **Valor**.

10. Arrastre **Productos** hasta el área **Filtros**, directamente debajo del encabezado **Filtros de nivel de objeto visual**.

11. En el área **Tipo de filtro** que se muestre, active la casilla **Yammer**.

    ![Casilla de verificación seleccionar Yammer](../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Justo debajo de la lista de visualizaciones, haga **** clic en ![el icono formato de formato de](../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)icono de Power BI Visualizaions.

13. Expanda el título y cambie el valor de **Texto del título** a **Nuevos usuarios de Yammer por mes**.
    
14. Cambie el valor de **Tamaño del texto** a **12**.
    
15. Cambie el título de la página nueva editando el nombre de la página en la parte inferior derecha.

16.  Guarde el informe haciendo clic en **vista de lectura** en la parte superior y, a continuación, en **Guardar**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizar los informes en Power BI Desktop

Para la mayoría de los clientes, modificar los informes y los objetos visuales de gráficos en la web de Power BI será suficiente. Otros, en cambio, puede que necesiten combinar estos datos con otros orígenes de datos para obtener información contextual más avanzada para su propio negocio; en ese caso, pueden personalizar y crear informes adicionales con Power BI Desktop. Puede descargar [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) de forma gratuita. 
  
### <a name="use-the-reporting-apis"></a>Usar las API de informes

Puede empezar conectando directamente a las API de informes de ODATA desde Microsoft 365 que se exportan estos informes.
  
1. Vaya a **Obtener datos** \> **Otros** \> **Fuente de OData** \> **Conectar**.
    
2. En la ventana URL, escriba "<i></i>https://\<Reports.Office.com/PBI/v1.0/\>tenantid"
    
    **Nota:** Las API de informes se encuentran en versión preliminar y están sujetas a cambios hasta que entran en producción. 
  
    ![OData feed URL for Power BI desktop](../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Escriba sus credenciales de administrador de Microsoft 365 (organización o escuela) para autenticar a Microsoft 365 cuando se le solicite.
    
    Consulte las [preguntas más frecuentes](usage-analytics.md#faq) para obtener más información sobre quién puede acceder a los informes de la aplicación plantilla de adopción de Microsoft 365. 
    
4. Cuando se autorice la conexión, verá la ventana Navegador, donde se muestran los conjuntos de datos a los que puede conectarse.
    
    Seleccione todo y haga clic en **Cargar**.
    
    Se descargarán los datos en Power BI Desktop. Guarde el archivo y, después, ya podrá empezar a crear los informes que necesite.
    
    ![Valores de ODATA disponibles en la API de informes](../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Usar la plantilla de análisis de uso de Microsoft 365

También puede usar el archivo de plantilla de Power BI que corresponde a los informes de análisis de uso de Microsoft 365 como punto de partida para conectarse a los datos. La ventaja de usar el archivo pbit es que ya tiene establecida la cadena de conexión. También puede aprovecharse de todas las medidas personalizadas creadas, además de los datos devueltos por el esquema base.
  
Puede descargar el archivo de plantilla de Power BI desde el centro de descarga de Microsoft desde el [centro de descarga](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). Después de descargar el archivo de plantilla de Power BI, siga estos pasos para empezar:
  
1. Abra el archivo pbit.
    
2. Escriba el valor del id. de espacio empresarial en el cuadro de diálogo.
    
    ![Enter your tenant ID to open the pbit file](../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Escriba sus credenciales de administrador para autenticar a Microsoft 365 cuando se le solicite.
    
     para obtener más información acerca de quién puede tener acceso a los informes de análisis de uso de Microsoft 365. 
    
    Cuando reciba la autorización, los datos se actualizarán en el archivo de Power BI.
    
    La carga de datos puede tardar un tiempo; cuando se complete, puede guardar el archivo como .pbix y seguir personalizando los informes, o bien puede agregar un origen de datos adicional al informe.
    
4. Vea la documentación en [Introducción a Power BI](https://go.microsoft.com/fwlink/?linkid=849802) para conocer cómo crear informes, publicarlos en el servicio de Power BI y compartirlos con su organización. Para seguir estos pasos de personalización y uso compartido, puede que necesite licencias adicionales de Power BI. Para obtener más información, vea la [guía de licencia](https://go.microsoft.com/fwlink/p/?linkid=849803) de Power BI. 
    

