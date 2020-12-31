---
title: Importar custodios a un caso de eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use la herramienta de importación dto rápidamente para agregar varios custodios y sus orígenes de datos asociados a un caso en eDiscovery avanzado.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740307"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="7e015-103">Importar custodios a un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="7e015-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="7e015-104">Para los casos de eDiscovery avanzados que involucran muchos custodios, puede importar varios custodios a la vez mediante un archivo CSV que contenga la información necesaria para agregarlos a un caso.</span><span class="sxs-lookup"><span data-stu-id="7e015-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="7e015-105">Importación de custodios</span><span class="sxs-lookup"><span data-stu-id="7e015-105">Import custodians</span></span>

1. <span data-ttu-id="7e015-106">Abra el caso de exhibición avanzada de documentos electrónicos y seleccione la pestaña **orígenes de datos** .</span><span class="sxs-lookup"><span data-stu-id="7e015-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="7e015-107">Haga clic en **Agregar**  >  **custodios de importación** de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7e015-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="7e015-108">En la página de control flotante **importar administradores** , haga clic en **descargar una plantilla en blanco** para descargar un archivo CSV de plantilla de custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Descargar una plantilla CSV desde la página de control de custodios para importación](../media/ImportCustodians1.png)

4. <span data-ttu-id="7e015-110">Agregue la información de la Private al archivo CSV y guárdelo en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="7e015-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="7e015-111">Consulte la sección [archivo CSV de custodio](#custodian-csv-file) para obtener información sobre las propiedades necesarias en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7e015-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="7e015-112">Una vez que haya preparado el archivo CSV con la información de custodios, vuelva a la pestaña **orígenes de datos** y haga clic en **Agregar**  >  **custodios de importación** de origen de datos de nuevo.</span><span class="sxs-lookup"><span data-stu-id="7e015-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="7e015-113">En la página de control flotante **importar administradores** , haga clic en **examinar** y, a continuación, cargue el archivo CSV que contiene la información de custodios.</span><span class="sxs-lookup"><span data-stu-id="7e015-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="7e015-114">Una vez cargado el archivo CSV, se crea un trabajo denominado **BulkAddCustodian** y se muestra en la pestaña **trabajos** . El trabajo valida los custodios y sus orígenes de datos asociados y, a continuación, los agrega a la página de **orígenes de datos** del caso.</span><span class="sxs-lookup"><span data-stu-id="7e015-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="7e015-115">Archivo CSV de custodio</span><span class="sxs-lookup"><span data-stu-id="7e015-115">Custodian CSV file</span></span>

<span data-ttu-id="7e015-116">Una vez que haya descargado la plantilla de custodio de CSV, puede Agregar custodios y su origen de datos en cada fila.</span><span class="sxs-lookup"><span data-stu-id="7e015-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="7e015-117">Asegúrese de no cambiar los nombres de columna de la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="7e015-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="7e015-118">Use las columnas tipo de carga de trabajo y ubicación de carga de trabajo para asociar otros orígenes de datos a un custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="7e015-119">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="7e015-119">Column name</span></span>|<span data-ttu-id="7e015-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e015-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="7e015-121">**Asociada de custodios**</span><span class="sxs-lookup"><span data-stu-id="7e015-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="7e015-122">La dirección de correo electrónico UPN del custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-122">The custodian's UPN email address.</span></span> <span data-ttu-id="7e015-123">Por ejemplo, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7e015-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="7e015-124">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="7e015-124">**Exchange Enabled**</span></span> | <span data-ttu-id="7e015-125">Valor TRUE/FALSE para incluir o no el buzón del custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="7e015-126">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="7e015-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="7e015-127">Valor TRUE/FALSE para incluir o no la cuenta de OneDrive para la empresa del custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="7e015-128">**Es pamantente**</span><span class="sxs-lookup"><span data-stu-id="7e015-128">**Is OnHold**</span></span>        | <span data-ttu-id="7e015-129">Valor TRUE/FALSE para indicar si se deben retener los orígenes de datos de custodios.</span><span class="sxs-lookup"><span data-stu-id="7e015-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="7e015-130">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="7e015-130">**Workload1 Type**</span></span>         |<span data-ttu-id="7e015-131">Valor de cadena que indica el tipo de origen de datos que se va a asociar con el custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="7e015-132">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7e015-132">Possible values include:</span></span> <br/><span data-ttu-id="7e015-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="7e015-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="7e015-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="7e015-134">- SharePointSite</span></span><br/><span data-ttu-id="7e015-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="7e015-135">- TeamsMailbox</span></span><br/><span data-ttu-id="7e015-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="7e015-136">- TeamsSite</span></span><br/> <span data-ttu-id="7e015-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="7e015-137">- YammerMailbox</span></span><br/><span data-ttu-id="7e015-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="7e015-138">- YammerSite</span></span> |
|<span data-ttu-id="7e015-139">**Ubicación de Workload1**</span><span class="sxs-lookup"><span data-stu-id="7e015-139">**Workload1 Location**</span></span>     | <span data-ttu-id="7e015-140">Según el tipo de carga de trabajo, sería la ubicación del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7e015-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="7e015-141">Por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e015-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="7e015-142">Este es un ejemplo de un archivo CSV con información de custodios:</span><span class="sxs-lookup"><span data-stu-id="7e015-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="7e015-143">Asociada de custodios</span><span class="sxs-lookup"><span data-stu-id="7e015-143">Custodian contactEmail</span></span>      | <span data-ttu-id="7e015-144">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="7e015-144">Exchange Enabled</span></span> | <span data-ttu-id="7e015-145">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="7e015-145">OneDrive Enabled</span></span> | <span data-ttu-id="7e015-146">Es pamantente</span><span class="sxs-lookup"><span data-stu-id="7e015-146">Is OnHold</span></span> | <span data-ttu-id="7e015-147">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="7e015-147">Workload1 Type</span></span> | <span data-ttu-id="7e015-148">Ubicación de Workload1</span><span class="sxs-lookup"><span data-stu-id="7e015-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="7e015-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e015-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="7e015-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e015-150">TRUE</span></span>             | <span data-ttu-id="7e015-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e015-151">TRUE</span></span>             | <span data-ttu-id="7e015-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e015-152">TRUE</span></span>      | <span data-ttu-id="7e015-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="7e015-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="7e015-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e015-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="7e015-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e015-155">TRUE</span></span>             | <span data-ttu-id="7e015-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e015-156">TRUE</span></span>             | <span data-ttu-id="7e015-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e015-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="7e015-158">Validación de custodios y orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="7e015-158">Custodian and data source validation</span></span>

<span data-ttu-id="7e015-159">Después de cargar el archivo CSV de custodio, la exhibición avanzada de documentos electrónicos realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7e015-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="7e015-160">Valida los custodios y sus orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="7e015-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="7e015-161">Indiza todos los orígenes de datos para cada custodio y los coloca en retención (si la propiedad **is alhold** en el archivo CSV se establece en true).</span><span class="sxs-lookup"><span data-stu-id="7e015-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="7e015-162">Validación de custodios</span><span class="sxs-lookup"><span data-stu-id="7e015-162">Custodian validation</span></span>

<span data-ttu-id="7e015-163">Actualmente, solo se admite la importación de custodios que se incluyen en Azure Active Directory de la organización (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7e015-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="7e015-164">La herramienta de importación de custodios busca y valida a los custodios mediante el valor UPN en la columna **asociada de custodios** del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="7e015-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="7e015-165">Los custodios que se validan se agregan automáticamente al caso y se enumeran en la ficha **orígenes de datos** del caso.</span><span class="sxs-lookup"><span data-stu-id="7e015-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="7e015-166">Si no se puede validar un custodio, se enumeran en el registro de errores del trabajo BulkAddCustodian que aparece en la ficha **trabajos** en el caso.</span><span class="sxs-lookup"><span data-stu-id="7e015-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="7e015-167">Los custodios no validados no se agregan al caso o aparecen en la pestaña **orígenes de datos** .</span><span class="sxs-lookup"><span data-stu-id="7e015-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="7e015-168">Validación de origen de datos</span><span class="sxs-lookup"><span data-stu-id="7e015-168">Data source validation</span></span>

<span data-ttu-id="7e015-169">Una vez que los custodios se validan y agregan al caso, se agregan todos los buzones de correo principales y de OneDrive asociados a un custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="7e015-170">Sin embargo, si no se encuentra alguno de los otros orígenes de datos (como sitios de SharePoint, Microsoft Teams, grupos de Microsoft 365 o grupos de Yammer) asociados a un custodio, ninguno de ellos se asigna al custodio y el valor **no validado** se muestra en la columna **Estado** junto al custodio en la pestaña **orígenes de datos** .</span><span class="sxs-lookup"><span data-stu-id="7e015-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="7e015-171">Para agregar orígenes de datos validados para un custodio:</span><span class="sxs-lookup"><span data-stu-id="7e015-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="7e015-172">En la pestaña **orígenes de datos** , seleccione un custodio que contenga orígenes de datos que no se validen.</span><span class="sxs-lookup"><span data-stu-id="7e015-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="7e015-173">En la página flotante de custodios, desplácese hasta la sección **ubicaciones de Private** para ver los orígenes de datos validados y no validados asociados con el custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="7e015-174">Haga clic en **Editar** en la parte superior de la página de control flotante para quitar orígenes de datos no válidos o agregar otros nuevos.</span><span class="sxs-lookup"><span data-stu-id="7e015-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="7e015-175">Después de quitar los orígenes de datos no validados o agregar uno nuevo, el valor **activo** se muestra en la columna **Estado** del custodio en la ficha **orígenes de datos** . Para agregar orígenes que antes aparecían como no válidos, siga los pasos de corrección que se describen a continuación para agregarlos manualmente a un custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="7e015-176">Corregir orígenes de datos no válidos</span><span class="sxs-lookup"><span data-stu-id="7e015-176">Remediating invalid data sources</span></span>

<span data-ttu-id="7e015-177">Para agregar y asociar manualmente un origen de datos que anteriormente no era válido:</span><span class="sxs-lookup"><span data-stu-id="7e015-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="7e015-178">En la pestaña **orígenes de datos** , seleccione un custodio para agregar y asociar manualmente un origen de datos que antes no era válido.</span><span class="sxs-lookup"><span data-stu-id="7e015-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="7e015-179">Haga clic en **Editar** en la parte superior de la página de control flotante para asociar buzones de correo, sitios, equipos o grupos de Yammer al custodio.</span><span class="sxs-lookup"><span data-stu-id="7e015-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="7e015-180">Para ello, haga clic en **Editar** junto al tipo de ubicación de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7e015-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="7e015-181">Haga clic en **siguiente** para mostrar la página **configuración de suspensión** y configurar la opción de suspensión para los orígenes de datos que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="7e015-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="7e015-182">Haga clic en **siguiente** para mostrar la página de **revisión de custodios** y, a continuación, haga clic en **Enviar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7e015-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
