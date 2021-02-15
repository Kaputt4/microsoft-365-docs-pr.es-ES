---
title: Importar administradores a un caso de eDiscovery avanzado
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
description: Use la herramienta de importación para agregar rápidamente varios administradores y sus orígenes de datos asociados a un caso en eDiscovery avanzado.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740307"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="2cb38-103">Importar administradores a un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="2cb38-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="2cb38-104">Para los casos de eDiscovery avanzados en los que participan muchos administradores, puede importar varios administradores a la vez mediante un archivo CSV que contiene la información necesaria para agregarlos a un caso.</span><span class="sxs-lookup"><span data-stu-id="2cb38-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="2cb38-105">Importar administradores</span><span class="sxs-lookup"><span data-stu-id="2cb38-105">Import custodians</span></span>

1. <span data-ttu-id="2cb38-106">Abra el caso de eDiscovery avanzado y seleccione la **pestaña Orígenes de** datos.</span><span class="sxs-lookup"><span data-stu-id="2cb38-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="2cb38-107">Haga **clic en Agregar administradores de** importación de orígenes de  >  **datos.**</span><span class="sxs-lookup"><span data-stu-id="2cb38-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="2cb38-108">En la **página desplegable Importar administradores,** haga clic en Descargar una plantilla en blanco **para** descargar un archivo CSV de plantilla de administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Descargar una plantilla CSV desde la página desplegable Importar administradores](../media/ImportCustodians1.png)

4. <span data-ttu-id="2cb38-110">Agregue la información de custodia al archivo CSV y guárdela en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="2cb38-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="2cb38-111">Consulte la [sección archivo CSV de](#custodian-csv-file) administrador para obtener información sobre las propiedades necesarias en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2cb38-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="2cb38-112">Después de preparar el archivo CSV con la información  del administrador, vuelva a la pestaña Orígenes de datos y haga clic en Agregar administradores de importación de origen de datos de  >   nuevo.</span><span class="sxs-lookup"><span data-stu-id="2cb38-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="2cb38-113">En la **página desplegable Importar administradores,** haga clic en Examinar y, a continuación, cargue el archivo CSV que contiene la información del administrador. </span><span class="sxs-lookup"><span data-stu-id="2cb38-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="2cb38-114">Después de cargar el archivo CSV, se crea un trabajo denominado **BulkAddCustodian** y se muestra en la **pestaña** Trabajos. El trabajo valida los administradores y sus orígenes de datos asociados y, a continuación, los agrega a la página **Orígenes** de datos del caso.</span><span class="sxs-lookup"><span data-stu-id="2cb38-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="2cb38-115">Archivo CSV de administrador</span><span class="sxs-lookup"><span data-stu-id="2cb38-115">Custodian CSV file</span></span>

<span data-ttu-id="2cb38-116">Después de descargar la plantilla de administrador csv, puede agregar administradores y su origen de datos en cada fila.</span><span class="sxs-lookup"><span data-stu-id="2cb38-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="2cb38-117">Asegúrese de no cambiar los nombres de columna en la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="2cb38-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="2cb38-118">Use el tipo de carga de trabajo y las columnas de ubicación de carga de trabajo para asociar otros orígenes de datos a un administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="2cb38-119">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="2cb38-119">Column name</span></span>|<span data-ttu-id="2cb38-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cb38-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="2cb38-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="2cb38-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="2cb38-122">La dirección de correo electrónico UPN del administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-122">The custodian's UPN email address.</span></span> <span data-ttu-id="2cb38-123">Por ejemplo, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2cb38-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="2cb38-124">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="2cb38-124">**Exchange Enabled**</span></span> | <span data-ttu-id="2cb38-125">Valor TRUE/FALSE para incluir o no incluir el buzón del administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="2cb38-126">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="2cb38-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="2cb38-127">Valor TRUE/FALSE para incluir o no incluir la cuenta de OneDrive para la Empresa del administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="2cb38-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="2cb38-128">**Is OnHold**</span></span>        | <span data-ttu-id="2cb38-129">Valor TRUE/FALSE para indicar si se deben poner en espera los orígenes de datos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="2cb38-130">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="2cb38-130">**Workload1 Type**</span></span>         |<span data-ttu-id="2cb38-131">Valor de cadena que indica el tipo de origen de datos que se asociará con el administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="2cb38-132">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="2cb38-132">Possible values include:</span></span> <br/><span data-ttu-id="2cb38-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="2cb38-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="2cb38-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="2cb38-134">- SharePointSite</span></span><br/><span data-ttu-id="2cb38-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="2cb38-135">- TeamsMailbox</span></span><br/><span data-ttu-id="2cb38-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="2cb38-136">- TeamsSite</span></span><br/> <span data-ttu-id="2cb38-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="2cb38-137">- YammerMailbox</span></span><br/><span data-ttu-id="2cb38-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="2cb38-138">- YammerSite</span></span> |
|<span data-ttu-id="2cb38-139">**Ubicación de carga de trabajo1**</span><span class="sxs-lookup"><span data-stu-id="2cb38-139">**Workload1 Location**</span></span>     | <span data-ttu-id="2cb38-140">Según el tipo de carga de trabajo, esta sería la ubicación del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2cb38-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="2cb38-141">Por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cb38-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="2cb38-142">Este es un ejemplo de un archivo CSV con información de administrador:</span><span class="sxs-lookup"><span data-stu-id="2cb38-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="2cb38-143">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="2cb38-143">Custodian contactEmail</span></span>      | <span data-ttu-id="2cb38-144">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="2cb38-144">Exchange Enabled</span></span> | <span data-ttu-id="2cb38-145">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="2cb38-145">OneDrive Enabled</span></span> | <span data-ttu-id="2cb38-146">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="2cb38-146">Is OnHold</span></span> | <span data-ttu-id="2cb38-147">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="2cb38-147">Workload1 Type</span></span> | <span data-ttu-id="2cb38-148">Ubicación de carga de trabajo1</span><span class="sxs-lookup"><span data-stu-id="2cb38-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="2cb38-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cb38-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="2cb38-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="2cb38-150">TRUE</span></span>             | <span data-ttu-id="2cb38-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="2cb38-151">TRUE</span></span>             | <span data-ttu-id="2cb38-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="2cb38-152">TRUE</span></span>      | <span data-ttu-id="2cb38-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="2cb38-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="2cb38-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cb38-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="2cb38-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="2cb38-155">TRUE</span></span>             | <span data-ttu-id="2cb38-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="2cb38-156">TRUE</span></span>             | <span data-ttu-id="2cb38-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="2cb38-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="2cb38-158">Validación de administrador y origen de datos</span><span class="sxs-lookup"><span data-stu-id="2cb38-158">Custodian and data source validation</span></span>

<span data-ttu-id="2cb38-159">Después de cargar el archivo CSV de administrador, eDiscovery avanzado hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2cb38-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="2cb38-160">Valida los administradores y sus orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="2cb38-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="2cb38-161">Indiza todos los orígenes de datos de cada administrador y los pone en retención (si la propiedad **Is OnHold** del archivo CSV está establecida en TRUE).</span><span class="sxs-lookup"><span data-stu-id="2cb38-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="2cb38-162">Validación de administrador</span><span class="sxs-lookup"><span data-stu-id="2cb38-162">Custodian validation</span></span>

<span data-ttu-id="2cb38-163">Actualmente, solo se admite la importación de administradores que se incluyen en Azure Active Directory (Azure AD) de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cb38-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="2cb38-164">La herramienta de importación de administrador busca y valida a los administradores con el valor UPN de la columna **ContactEmail** del administrador en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2cb38-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="2cb38-165">Los administradores que se validan se agregan automáticamente al caso y se enumeran en la pestaña **Orígenes** de datos del caso.</span><span class="sxs-lookup"><span data-stu-id="2cb38-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="2cb38-166">Si no se puede validar un administrador, aparecen en el registro de errores del trabajo  BulkAddCustodian que aparece en la pestaña Trabajos en ese caso.</span><span class="sxs-lookup"><span data-stu-id="2cb38-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="2cb38-167">Los administradores no confirmados no se agregan al caso ni aparecen en la **pestaña Orígenes de** datos.</span><span class="sxs-lookup"><span data-stu-id="2cb38-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="2cb38-168">Validación de origen de datos</span><span class="sxs-lookup"><span data-stu-id="2cb38-168">Data source validation</span></span>

<span data-ttu-id="2cb38-169">Después de que los administradores se validan y agregan al caso, se agregan cada buzón de correo principal y cuenta de OneDrive asociada con un administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="2cb38-170">Sin embargo, si no se encuentra ninguno de los demás orígenes de datos (como sitios de SharePoint, Microsoft Teams, Grupos de Microsoft 365  o grupos de Yammer) asociados con un  administrador, ninguno de ellos se asigna al administrador y el valor No validado se muestra en la columna Estado junto al administrador en la pestaña Orígenes de datos. </span><span class="sxs-lookup"><span data-stu-id="2cb38-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="2cb38-171">Para agregar orígenes de datos validados para un administrador:</span><span class="sxs-lookup"><span data-stu-id="2cb38-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="2cb38-172">En la **pestaña Orígenes de** datos, seleccione un administrador que contenga orígenes de datos que no se validan.</span><span class="sxs-lookup"><span data-stu-id="2cb38-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="2cb38-173">En la página desplegable de administrador, desplácese hasta la sección Ubicaciones de administrador para ver los orígenes de datos validados y no validados que están asociados con el administrador. </span><span class="sxs-lookup"><span data-stu-id="2cb38-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="2cb38-174">Haga **clic en** Editar en la parte superior de la página desplegable para quitar orígenes de datos no válidos o agregar nuevos.</span><span class="sxs-lookup"><span data-stu-id="2cb38-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="2cb38-175">Después de quitar orígenes de datos sin validar o agregar uno  nuevo, el valor **Activo** se muestra en la columna Estado del administrador en la ficha **Orígenes de** datos. Para agregar orígenes que anteriormente aparecían como no válidos, siga los pasos de corrección siguientes para agregarlos manualmente a un administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="2cb38-176">Corrección de orígenes de datos no válidos</span><span class="sxs-lookup"><span data-stu-id="2cb38-176">Remediating invalid data sources</span></span>

<span data-ttu-id="2cb38-177">Para agregar y asociar manualmente un origen de datos que no era válido anteriormente:</span><span class="sxs-lookup"><span data-stu-id="2cb38-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="2cb38-178">En la **pestaña Orígenes de** datos, seleccione un administrador para agregar y asociar manualmente un origen de datos que no era válido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2cb38-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="2cb38-179">Haga **clic en** Editar en la parte superior de la página desplegable para asociar buzones, sitios, teams o grupos de Yammer al administrador.</span><span class="sxs-lookup"><span data-stu-id="2cb38-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="2cb38-180">Para ello, haga **clic en Editar** junto al tipo de ubicación de datos adecuado.</span><span class="sxs-lookup"><span data-stu-id="2cb38-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="2cb38-181">Haga **clic en** Siguiente para mostrar la página de configuración **de** retención y configurar la configuración de retención para los orígenes de datos que agregó.</span><span class="sxs-lookup"><span data-stu-id="2cb38-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="2cb38-182">Haga **clic en** Siguiente para mostrar la página **Revisar** administradores y, a continuación, haga clic en Enviar **para** guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="2cb38-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
