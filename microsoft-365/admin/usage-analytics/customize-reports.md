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
ms.openlocfilehash: 4f0c85802ecb5db9c57add2fa6dd561827e8fa22
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140714"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="9fd1b-103">Personalizar los informes en análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9fd1b-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9fd1b-104">El centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-104">The admin center is changing.</span></span> <span data-ttu-id="9fd1b-105">Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9fd1b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="9fd1b-106">El análisis de uso de Microsoft 365 proporciona un panel en Power BI que ofrece información sobre cómo los usuarios adoptan y usan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="9fd1b-107">El panel es tan solo un punto de inicio para interactuar con los datos de uso.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="9fd1b-108">Los informes se pueden ajustar para obtener información más personalizada.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="9fd1b-109">También puede usar Power BI Desktop para personalizar aún más los informes al conectarlos a otros orígenes de datos para obtener información avanzada sobre su negocio.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="9fd1b-110">Personalizar informes en el explorador</span><span class="sxs-lookup"><span data-stu-id="9fd1b-110">Customizing reports in the browser</span></span>

<span data-ttu-id="9fd1b-111">En los dos ejemplos siguientes se muestra cómo modificar un objeto visual existente y cómo crear uno.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="9fd1b-112">Modificar un objeto visual existente</span><span class="sxs-lookup"><span data-stu-id="9fd1b-112">Modify an existing visual</span></span>

<span data-ttu-id="9fd1b-113">En este ejemplo se muestra cómo modificar la pestaña **activación** en el informe de **activación/licencias** .</span><span class="sxs-lookup"><span data-stu-id="9fd1b-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="9fd1b-114">En el informe de **activación/licencia** , haga clic en la pestaña **activación** .</span><span class="sxs-lookup"><span data-stu-id="9fd1b-114">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="9fd1b-115">Para entrar en el modo de edición **Edit** , haga clic en el botón Editar ![en la parte superior con el botón](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) más página del botón Power BI.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-115">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="9fd1b-117">En la parte superior derecha, haga clic en **duplicar esta página**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-117">On the top right, click **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="9fd1b-119">En la parte inferior derecha, haga clic en cualquiera de los gráficos de barras que muestren el número de usuarios que se activan según el sistema operativo, como Android, iOS, Mac, etc.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-119">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="9fd1b-120">En el área **visualizaciones** de la derecha, para quitar el **recuento de Mac** del objeto visual, haga clic en la **X** junto a él.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![Quitar recuento Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="9fd1b-122">Crear un objeto visual</span><span class="sxs-lookup"><span data-stu-id="9fd1b-122">Create a new visual</span></span>

<span data-ttu-id="9fd1b-123">En el ejemplo siguiente se muestra cómo crear un objeto visual para realizar un seguimiento de nuevos usuarios de Yammer de forma mensual.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="9fd1b-124">Vaya al informe de **uso del producto** usando el panel de navegación izquierdo y haga clic en la pestaña **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="9fd1b-124">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="9fd1b-125">Cambie al modo de edición haciendo clic ![en el botón más página en Power](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI y **editando**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-125">Switch to edit mode by clicking on ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="9fd1b-126">En la parte inferior de la página, haz clic en</span><span class="sxs-lookup"><span data-stu-id="9fd1b-126">At the bottom of the page, click on</span></span> ![Botón Agregar página de Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="9fd1b-128">para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-128">to create a new page.</span></span>
  
4. <span data-ttu-id="9fd1b-129">En el área **visualizaciones** de la derecha, haga clic en el **gráfico de barras apiladas** (fila superior, primero desde la izquierda).</span><span class="sxs-lookup"><span data-stu-id="9fd1b-129">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![Seleccionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="9fd1b-131">Haga clic en la esquina inferior derecha de esa visualización y arrástrela para ampliar su tamaño.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-131">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="9fd1b-132">En el área **campos** a la derecha, expanda la tabla de **calendarios** .</span><span class="sxs-lookup"><span data-stu-id="9fd1b-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="9fd1b-133">Arrastre **MonthName** al área de campos, directamente debajo del título **Ejes**, en el área **Visualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Arrastrar nombre del mes](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="9fd1b-135">En el área **Campos** de la parte derecha, expanda la tabla **TenantProductUsage**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="9fd1b-136">Arrastre **FirstTimeUsers** al área de campos, directamente debajo del encabezado **Valor**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="9fd1b-137">Arrastre **Productos** hasta el área **Filtros**, directamente debajo del encabezado **Filtros de nivel de objeto visual**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="9fd1b-138">En el área **Tipo de filtro** que se muestre, active la casilla **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Casilla de verificación seleccionar Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="9fd1b-140">Justo debajo de la lista de visualizaciones, haga **Format** clic en ![el icono formato de formato de](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)icono de Power BI Visualizaions.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-140">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="9fd1b-141">Expanda el título y cambie el valor de **Texto del título** a **Nuevos usuarios de Yammer por mes**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="9fd1b-142">Cambie el valor de **Tamaño del texto** a **12**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="9fd1b-143">Cambie el título de la página nueva editando el nombre de la página en la parte inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="9fd1b-144">Guarde el informe haciendo clic en **vista de lectura** en la parte superior y, a continuación, en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="9fd1b-145">Personalizar los informes en Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="9fd1b-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="9fd1b-p103">Para la mayoría de los clientes, modificar los informes y los objetos visuales de gráficos en la web de Power BI será suficiente. Otros, en cambio, puede que necesiten combinar estos datos con otros orígenes de datos para obtener información contextual más avanzada para su propio negocio; en ese caso, pueden personalizar y crear informes adicionales con Power BI Desktop. Puede descargar [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="9fd1b-149">Usar las API de informes</span><span class="sxs-lookup"><span data-stu-id="9fd1b-149">Use the reporting APIs</span></span>

<span data-ttu-id="9fd1b-150">Puede empezar conectando directamente a las API de informes de ODATA desde Microsoft 365 que se exportan estos informes.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="9fd1b-151">Vaya a **Obtener datos** \> **Otros** \> **Fuente de OData** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="9fd1b-152">En la ventana URL, escriba "<i></i>https://\<Reports.Office.com/PBI/v1.0/\>tenantid"</span><span class="sxs-lookup"><span data-stu-id="9fd1b-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="9fd1b-153">**Nota:** Las API de informes se encuentran en versión preliminar y están sujetas a cambios hasta que entran en producción.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="9fd1b-155">Escriba sus credenciales de administrador de Microsoft 365 (organización o escuela) para autenticar a Microsoft 365 cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="9fd1b-156">Consulte las [preguntas más frecuentes](usage-analytics.md#faq) para obtener más información sobre quién puede acceder a los informes de la aplicación plantilla de adopción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="9fd1b-157">Cuando se autorice la conexión, verá la ventana Navegador, donde se muestran los conjuntos de datos a los que puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="9fd1b-158">Seleccione todo y haga clic en **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-158">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="9fd1b-p104">Se descargarán los datos en Power BI Desktop. Guarde el archivo y, después, ya podrá empezar a crear los informes que necesite.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-p104">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![Valores de ODATA disponibles en la API de informes](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="9fd1b-162">Usar la plantilla de análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9fd1b-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="9fd1b-163">También puede usar el archivo de plantilla de Power BI que corresponde a los informes de análisis de uso de Microsoft 365 como punto de partida para conectarse a los datos.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="9fd1b-164">La ventaja de usar el archivo pbit es que ya tiene establecida la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="9fd1b-165">También puede aprovecharse de todas las medidas personalizadas creadas, además de los datos devueltos por el esquema base.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="9fd1b-166">Puede descargar el archivo de plantilla de Power BI desde el centro de descarga de Microsoft desde el [centro de descarga](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="9fd1b-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="9fd1b-167">Después de descargar el archivo de plantilla de Power BI, siga estos pasos para empezar:</span><span class="sxs-lookup"><span data-stu-id="9fd1b-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="9fd1b-168">Abra el archivo pbit.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="9fd1b-169">Escriba el valor del id. de espacio empresarial en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="9fd1b-171">Escriba sus credenciales de administrador para autenticar a Microsoft 365 cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="9fd1b-172">para obtener más información acerca de quién puede tener acceso a los informes de análisis de uso de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="9fd1b-173">Cuando reciba la autorización, los datos se actualizarán en el archivo de Power BI.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="9fd1b-174">La carga de datos puede tardar un tiempo; cuando se complete, puede guardar el archivo como .pbix y seguir personalizando los informes, o bien puede agregar un origen de datos adicional al informe.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="9fd1b-p107">Vea la documentación en [Introducción a Power BI](https://go.microsoft.com/fwlink/?linkid=849802) para conocer cómo crear informes, publicarlos en el servicio de Power BI y compartirlos con su organización. Para seguir estos pasos de personalización y uso compartido, puede que necesite licencias adicionales de Power BI. Para obtener más información, vea la [guía de licencia](https://go.microsoft.com/fwlink/p/?linkid=849803) de Power BI.</span><span class="sxs-lookup"><span data-stu-id="9fd1b-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

