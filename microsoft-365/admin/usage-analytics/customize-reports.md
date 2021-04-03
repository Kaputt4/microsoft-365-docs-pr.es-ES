---
title: Personalizar los informes en análisis de uso de Microsoft 365
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
description: Aprenda a personalizar informes en el explorador y Power BI Desktop.
ms.openlocfilehash: 0ef2364c82318dfea93e8df4e64d53a66caa8d74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580779"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="5dc2e-103">Personalizar los informes en análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5dc2e-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="5dc2e-104">El análisis de uso de Microsoft 365 proporciona un panel en Power BI que ofrece información sobre cómo los usuarios adoptan y usan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="5dc2e-105">El panel es tan solo un punto de inicio para interactuar con los datos de uso.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="5dc2e-106">Los informes se pueden ajustar para obtener información más personalizada.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="5dc2e-107">También puede usar Power BI Desktop para personalizar aún más los informes al conectarlos a otros orígenes de datos para obtener información avanzada sobre su negocio.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="5dc2e-108">Personalizar informes en el explorador</span><span class="sxs-lookup"><span data-stu-id="5dc2e-108">Customizing reports in the browser</span></span>

<span data-ttu-id="5dc2e-109">En los dos ejemplos siguientes se muestra cómo modificar un objeto visual existente y cómo crear uno.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="5dc2e-110">Modificar un objeto visual existente</span><span class="sxs-lookup"><span data-stu-id="5dc2e-110">Modify an existing visual</span></span>

<span data-ttu-id="5dc2e-111">En este ejemplo se muestra cómo modificar la pestaña **Activación** del **informe Activación/Licencias.**</span><span class="sxs-lookup"><span data-stu-id="5dc2e-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="5dc2e-112">Dentro del **informe Activación/licencias,** seleccione la **pestaña** Activación.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-112">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="5dc2e-113">Para entrar en el modo de edición, elija el botón **Editar** de la parte superior a través del botón Más ![ página en Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-113">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="5dc2e-115">En la parte superior derecha, elija **Duplicar esta página**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-115">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="5dc2e-117">En la parte inferior derecha, elija cualquiera de los gráficos de barras que muestran el recuento de usuarios que se activan en función del sistema operativo, como Android, iOS, Mac, etc.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-117">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="5dc2e-118">En el **área Visualizaciones** a la derecha, para quitar **Mac Count** del objeto visual, selecciona **la X** junto a él.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Quitar recuento de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="5dc2e-120">Crear un objeto visual</span><span class="sxs-lookup"><span data-stu-id="5dc2e-120">Create a new visual</span></span>

<span data-ttu-id="5dc2e-121">En el ejemplo siguiente se muestra cómo crear un objeto visual para realizar un seguimiento de nuevos usuarios de Yammer de forma mensual.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="5dc2e-122">Vaya al informe **de uso del** producto con la navegación izquierda y seleccione la pestaña **Yammer.**</span><span class="sxs-lookup"><span data-stu-id="5dc2e-122">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="5dc2e-123">Cambie al modo de edición seleccionando El botón Más ![ página en Power BI y ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-123">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="5dc2e-124">En la parte inferior de la página, seleccione el</span><span class="sxs-lookup"><span data-stu-id="5dc2e-124">At the bottom of the page, select the</span></span> ![Botón agregar página en Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="5dc2e-126">para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-126">to create a new page.</span></span>
  
4. <span data-ttu-id="5dc2e-127">En el **área Visualizaciones** a la derecha, elija el gráfico de barras **apiladas** (fila superior, primero desde la izquierda).</span><span class="sxs-lookup"><span data-stu-id="5dc2e-127">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Seleccionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="5dc2e-129">Seleccione la parte inferior derecha de esa visualización y arrástrela para hacerla más grande.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-129">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="5dc2e-130">En el **área Campos** a la derecha, expanda la **tabla** Calendario.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="5dc2e-131">Arrastre **MonthName** al área de campos, directamente debajo del título **Ejes**, en el área **Visualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Drag Month Name](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="5dc2e-133">En el área **Campos** de la parte derecha, expanda la tabla **TenantProductUsage**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="5dc2e-134">Arrastre **FirstTimeUsers** al área de campos, directamente debajo del encabezado **Valor**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="5dc2e-135">Arrastre **Productos** hasta el área **Filtros**, directamente debajo del encabezado **Filtros de nivel de objeto visual**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="5dc2e-136">En el área **Tipo de filtro** que se muestre, active la casilla **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Casilla de verificación Seleccionar Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="5dc2e-138">Justo debajo de la lista de visualizaciones, elija **el** icono Formato icono Formato en Power ![ BI Visualizaions ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .</span><span class="sxs-lookup"><span data-stu-id="5dc2e-138">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="5dc2e-139">Expanda el título y cambie el valor de **Texto del título** a **Nuevos usuarios de Yammer por mes**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="5dc2e-140">Cambie el valor de **Tamaño del texto** a **12**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="5dc2e-141">Cambie el título de la nueva página editando el nombre de la página en la parte inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="5dc2e-142">Guarde el informe haciendo clic en **la vista de lectura** en la parte superior y, a continuación, **guarde**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="5dc2e-143">Personalizar los informes en Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="5dc2e-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="5dc2e-p102">Para la mayoría de los clientes, modificar los informes y los objetos visuales de gráficos en la web de Power BI será suficiente. Otros, en cambio, puede que necesiten combinar estos datos con otros orígenes de datos para obtener información contextual más avanzada para su propio negocio; en ese caso, pueden personalizar y crear informes adicionales con Power BI Desktop. Puede descargar [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-p102">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="5dc2e-147">Usar las API de informes</span><span class="sxs-lookup"><span data-stu-id="5dc2e-147">Use the reporting APIs</span></span>

<span data-ttu-id="5dc2e-148">Para empezar, puede conectarse directamente a las API de informes de ODATA de Microsoft 365 que potencian estos informes.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="5dc2e-149">Vaya a **Obtener datos** \> **Otros** \> **Fuente de OData** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="5dc2e-150">En la ventana dirección URL, escriba "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"</span><span class="sxs-lookup"><span data-stu-id="5dc2e-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="5dc2e-151">**NOTA:** Las API de informes están en versión preliminar y están sujetas a cambios hasta que entren en producción.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="5dc2e-153">Escriba sus credenciales de administrador de Microsoft 365 (organización o escuela) para autenticarse en Microsoft 365 cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="5dc2e-154">Consulta las [preguntas más frecuentes](usage-analytics.md#faq) para obtener más información sobre quién puede acceder a los informes de la aplicación de plantilla de adopción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="5dc2e-155">Cuando se autorice la conexión, verá la ventana Navegador, donde se muestran los conjuntos de datos a los que puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="5dc2e-156">Seleccione todo y elija **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-156">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="5dc2e-157">Se descargarán los datos en Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-157">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="5dc2e-158">Guarde el archivo y, después, ya podrá empezar a crear los informes que necesite.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-158">Save this file and then you can start creating the reports you need.</span></span>
    
    ![Valores de ODATA disponibles en la API de informes](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="5dc2e-160">Usar la plantilla de análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5dc2e-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="5dc2e-161">También puede usar el archivo de plantilla de Power BI que corresponde a los informes de análisis de uso de Microsoft 365 como punto de partida para conectarse a los datos.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-161">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="5dc2e-162">La ventaja de usar el archivo pbit es que ya tiene establecida la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-162">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="5dc2e-163">También puede aprovecharse de todas las medidas personalizadas creadas, además de los datos devueltos por el esquema base.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-163">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="5dc2e-164">Puede descargar el archivo de plantilla de Power BI desde el [Centro de descarga de Microsoft](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="5dc2e-164">You can download the Power BI template file from the [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="5dc2e-165">Después de descargar el archivo de plantilla de Power BI, siga estos pasos para empezar:</span><span class="sxs-lookup"><span data-stu-id="5dc2e-165">After you download the Power BI template file, follow these steps to get started:</span></span>
  
1. <span data-ttu-id="5dc2e-166">Abra el archivo pbit.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="5dc2e-167">Escriba el valor del id. de espacio empresarial en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-167">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="5dc2e-169">Escriba sus credenciales de administrador para autenticarse en Microsoft 365 cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="5dc2e-170">para obtener más información sobre quién puede acceder a los informes de análisis de uso de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="5dc2e-171">Cuando reciba la autorización, los datos se actualizarán en el archivo de Power BI.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="5dc2e-172">La carga de datos puede tardar un tiempo; cuando se complete, puede guardar el archivo como .pbix y seguir personalizando los informes, o bien puede agregar un origen de datos adicional al informe.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="5dc2e-p106">Vea la documentación en [Introducción a Power BI](/power-bi/fundamentals/desktop-getting-started) para conocer cómo crear informes, publicarlos en el servicio de Power BI y compartirlos con su organización. Para seguir estos pasos de personalización y uso compartido, puede que necesite licencias adicionales de Power BI. Para obtener más información, vea la [guía de licencia](https://go.microsoft.com/fwlink/p/?linkid=849803) de Power BI.</span><span class="sxs-lookup"><span data-stu-id="5dc2e-p106">Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
