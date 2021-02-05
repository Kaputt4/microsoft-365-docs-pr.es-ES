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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Aprenda a personalizar informes en el explorador y Power BI Desktop.
ms.openlocfilehash: 0375b61b6922c99acf927a4283571451deabaf14
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114302"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="81413-103">Personalizar los informes en análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="81413-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="81413-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="81413-104">The admin center is changing.</span></span> <span data-ttu-id="81413-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="81413-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="81413-106">El análisis de uso de Microsoft 365 proporciona un panel en Power BI que ofrece información sobre cómo los usuarios adoptan y usan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81413-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="81413-107">El panel es tan solo un punto de inicio para interactuar con los datos de uso.</span><span class="sxs-lookup"><span data-stu-id="81413-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="81413-108">Los informes se pueden ajustar para obtener información más personalizada.</span><span class="sxs-lookup"><span data-stu-id="81413-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="81413-109">También puede usar Power BI Desktop para personalizar aún más los informes al conectarlos a otros orígenes de datos para obtener información avanzada sobre su negocio.</span><span class="sxs-lookup"><span data-stu-id="81413-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="81413-110">Personalizar informes en el explorador</span><span class="sxs-lookup"><span data-stu-id="81413-110">Customizing reports in the browser</span></span>

<span data-ttu-id="81413-111">En los dos ejemplos siguientes se muestra cómo modificar un objeto visual existente y cómo crear uno.</span><span class="sxs-lookup"><span data-stu-id="81413-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="81413-112">Modificar un objeto visual existente</span><span class="sxs-lookup"><span data-stu-id="81413-112">Modify an existing visual</span></span>

<span data-ttu-id="81413-113">En este ejemplo se muestra cómo modificar la pestaña **Activación** en el **informe de activación y** licencias.</span><span class="sxs-lookup"><span data-stu-id="81413-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="81413-114">En el **informe de activación y** licencias, seleccione la **pestaña** Activación.</span><span class="sxs-lookup"><span data-stu-id="81413-114">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="81413-115">Para entrar en el modo de edición, elija el botón **Editar** en la parte superior hasta el botón Más página en el botón de ![ Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI.</span><span class="sxs-lookup"><span data-stu-id="81413-115">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="81413-117">En la parte superior derecha, elija **Duplicar esta página.**</span><span class="sxs-lookup"><span data-stu-id="81413-117">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="81413-119">En la parte inferior derecha, elija cualquiera de los gráficos de barras que muestran el número de usuarios que se activan en función del sistema operativo, como Android, iOS, Mac, etc.</span><span class="sxs-lookup"><span data-stu-id="81413-119">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="81413-120">En el **área Visualizaciones** a la derecha, para quitar el recuento de **Mac** del elemento visual, seleccione la **X** junto a él.</span><span class="sxs-lookup"><span data-stu-id="81413-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Quitar recuento de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="81413-122">Crear un objeto visual</span><span class="sxs-lookup"><span data-stu-id="81413-122">Create a new visual</span></span>

<span data-ttu-id="81413-123">En el ejemplo siguiente se muestra cómo crear un objeto visual para realizar un seguimiento de nuevos usuarios de Yammer de forma mensual.</span><span class="sxs-lookup"><span data-stu-id="81413-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="81413-124">Vaya al informe **de uso del** producto con el panel de navegación izquierdo y seleccione la pestaña **Yammer.**</span><span class="sxs-lookup"><span data-stu-id="81413-124">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="81413-125">Cambie al modo de edición eligiendo El botón Más ![ página en Power BI y ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="81413-125">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="81413-126">En la parte inferior de la página, seleccione la</span><span class="sxs-lookup"><span data-stu-id="81413-126">At the bottom of the page, select the</span></span> ![El botón Agregar página en Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="81413-128">para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="81413-128">to create a new page.</span></span>
  
4. <span data-ttu-id="81413-129">En el **área Visualizaciones** a la derecha, elija el gráfico de barras apiladas (fila superior, primero desde la izquierda). </span><span class="sxs-lookup"><span data-stu-id="81413-129">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Seleccionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="81413-131">Seleccione la parte inferior derecha de esa visualización y arrástrela para que sea más grande.</span><span class="sxs-lookup"><span data-stu-id="81413-131">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="81413-132">En el **área Campos** a la derecha, expanda la **tabla** Calendario.</span><span class="sxs-lookup"><span data-stu-id="81413-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="81413-133">Arrastre **MonthName** al área de campos, directamente debajo del título **Ejes**, en el área **Visualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="81413-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Drag Month Name](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="81413-135">En el área **Campos** de la parte derecha, expanda la tabla **TenantProductUsage**.</span><span class="sxs-lookup"><span data-stu-id="81413-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="81413-136">Arrastre **FirstTimeUsers** al área de campos, directamente debajo del encabezado **Valor**.</span><span class="sxs-lookup"><span data-stu-id="81413-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="81413-137">Arrastre **Productos** hasta el área **Filtros**, directamente debajo del encabezado **Filtros de nivel de objeto visual**.</span><span class="sxs-lookup"><span data-stu-id="81413-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="81413-138">En el área **Tipo de filtro** que se muestre, active la casilla **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="81413-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Casilla Seleccionar Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="81413-140">Justo debajo de la lista de visualizaciones, elija **el** icono Formato del icono formato ![ en Visualizaciones de Power BI ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .</span><span class="sxs-lookup"><span data-stu-id="81413-140">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="81413-141">Expanda el título y cambie el valor de **Texto del título** a **Nuevos usuarios de Yammer por mes**.</span><span class="sxs-lookup"><span data-stu-id="81413-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="81413-142">Cambie el valor de **Tamaño del texto** a **12**.</span><span class="sxs-lookup"><span data-stu-id="81413-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="81413-143">Cambie el título de la nueva página editando el nombre de la página en la parte inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="81413-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="81413-144">Guarde el informe haciendo clic en **la vista de lectura** en la parte superior y, a continuación, **guarde**.</span><span class="sxs-lookup"><span data-stu-id="81413-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="81413-145">Personalizar los informes en Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="81413-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="81413-p103">Para la mayoría de los clientes, modificar los informes y los objetos visuales de gráficos en la web de Power BI será suficiente. Otros, en cambio, puede que necesiten combinar estos datos con otros orígenes de datos para obtener información contextual más avanzada para su propio negocio; en ese caso, pueden personalizar y crear informes adicionales con Power BI Desktop. Puede descargar [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="81413-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="81413-149">Usar las API de informes</span><span class="sxs-lookup"><span data-stu-id="81413-149">Use the reporting APIs</span></span>

<span data-ttu-id="81413-150">Puede empezar conectándose directamente a las API de informes de ODATA de Microsoft 365 que se conectan a estos informes.</span><span class="sxs-lookup"><span data-stu-id="81413-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="81413-151">Vaya a **Obtener datos** \> **Otros** \> **Fuente de OData** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="81413-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="81413-152">En la ventana dirección URL, escriba "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"</span><span class="sxs-lookup"><span data-stu-id="81413-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="81413-153">**NOTA:** Las API de informes están en versión preliminar y están sujetas a cambios hasta que entren en producción.</span><span class="sxs-lookup"><span data-stu-id="81413-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="81413-155">Escriba sus credenciales de administrador de Microsoft 365 (organización o escuela) para autenticarse en Microsoft 365 cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="81413-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="81413-156">Consulte las [preguntas más frecuentes](usage-analytics.md#faq) para obtener más información sobre quién puede acceder a los informes de la aplicación de plantilla de adopción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81413-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="81413-157">Cuando se autorice la conexión, verá la ventana Navegador, donde se muestran los conjuntos de datos a los que puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="81413-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="81413-158">Seleccione todo y elija **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="81413-158">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="81413-159">Se descargarán los datos en Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="81413-159">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="81413-160">Guarde el archivo y, después, ya podrá empezar a crear los informes que necesite.</span><span class="sxs-lookup"><span data-stu-id="81413-160">Save this file and then you can start creating the reports you need.</span></span>
    
    ![Valores de ODATA disponibles en la API de informes](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="81413-162">Usar la plantilla de análisis de uso de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="81413-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="81413-163">También puede usar el archivo de plantilla de Power BI que corresponde a los informes de análisis de uso de Microsoft 365 como punto de partida para conectarse a los datos.</span><span class="sxs-lookup"><span data-stu-id="81413-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="81413-164">La ventaja de usar el archivo pbit es que ya tiene establecida la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="81413-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="81413-165">También puede aprovecharse de todas las medidas personalizadas creadas, además de los datos devueltos por el esquema base.</span><span class="sxs-lookup"><span data-stu-id="81413-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="81413-166">Puede descargar el archivo de plantilla de Power BI desde el Centro de descarga de Microsoft desde el [Centro de descarga.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)</span><span class="sxs-lookup"><span data-stu-id="81413-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="81413-167">Después de descargar el archivo de plantilla de Power BI, siga estos pasos para empezar:</span><span class="sxs-lookup"><span data-stu-id="81413-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="81413-168">Abra el archivo pbit.</span><span class="sxs-lookup"><span data-stu-id="81413-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="81413-169">Escriba el valor del id. de espacio empresarial en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="81413-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="81413-171">Escriba sus credenciales de administrador para autenticarse en Microsoft 365 cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="81413-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="81413-172">para obtener más información sobre quién tiene permiso para acceder a los informes de análisis de uso de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81413-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="81413-173">Cuando reciba la autorización, los datos se actualizarán en el archivo de Power BI.</span><span class="sxs-lookup"><span data-stu-id="81413-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="81413-174">La carga de datos puede tardar un tiempo; cuando se complete, puede guardar el archivo como .pbix y seguir personalizando los informes, o bien puede agregar un origen de datos adicional al informe.</span><span class="sxs-lookup"><span data-stu-id="81413-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="81413-p107">Vea la documentación en [Introducción a Power BI](https://go.microsoft.com/fwlink/?linkid=849802) para conocer cómo crear informes, publicarlos en el servicio de Power BI y compartirlos con su organización. Para seguir estos pasos de personalización y uso compartido, puede que necesite licencias adicionales de Power BI. Para obtener más información, vea la [guía de licencia](https://go.microsoft.com/fwlink/p/?linkid=849803) de Power BI.</span><span class="sxs-lookup"><span data-stu-id="81413-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

