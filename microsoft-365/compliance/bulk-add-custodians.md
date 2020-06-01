---
title: Adición de custodios en masa a un caso de eDiscovery avanzado
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432443"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="43719-102">Adición de custodios en masa a un caso de eDiscovery avanzado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="43719-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="43719-103">Para los casos de eDiscovery avanzados que implican un gran número de custodios, puede importar varios custodios a la vez mediante un archivo CSV que contenga toda la información necesaria para agregarlos a un caso.</span><span class="sxs-lookup"><span data-stu-id="43719-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="43719-104">Custodios de adición en masa</span><span class="sxs-lookup"><span data-stu-id="43719-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="43719-105">Escriba mayúsculas y navegue a la pestaña **orígenes** .</span><span class="sxs-lookup"><span data-stu-id="43719-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="43719-106">Haga clic en **importar custodios**</span><span class="sxs-lookup"><span data-stu-id="43719-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="43719-107">En la página de flotante, haga clic en **descargar una plantilla en blanco** para descargar un archivo de plantilla de custodio de CSV.</span><span class="sxs-lookup"><span data-stu-id="43719-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="43719-108">Agregue la información de la Private al archivo CSV y guárdelo en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="43719-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="43719-109">Consulte la sección siguiente para obtener información sobre las propiedades del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="43719-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="43719-110">En la pestaña **orígenes** , haga clic en **importar custodios** nuevamente.</span><span class="sxs-lookup"><span data-stu-id="43719-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="43719-111">En la página de flotante, haga clic en **examinar** y en cargar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="43719-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="43719-112">Una vez cargado el archivo CSV, se crea un trabajo de BulkAddCustodian y se muestra en la pestaña **trabajos** . El trabajo valida los custodios y sus orígenes de datos correspondientes y, a continuación, los agrega a la ficha **custodios** de la página **orígenes** del caso.</span><span class="sxs-lookup"><span data-stu-id="43719-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="43719-113">Archivo CSV de custodio</span><span class="sxs-lookup"><span data-stu-id="43719-113">Custodian CSV file</span></span>

<span data-ttu-id="43719-114">Una vez que haya descargado la plantilla CSV, puede Agregar custodios y su origen de datos en cada fila.</span><span class="sxs-lookup"><span data-stu-id="43719-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="43719-115">Asegúrese de no cambiar los nombres de columna en la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="43719-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="43719-116">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="43719-116">Column name</span></span>|<span data-ttu-id="43719-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="43719-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="43719-118">**Asociada de custodios**</span><span class="sxs-lookup"><span data-stu-id="43719-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="43719-119">Correo electrónico UPN de custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-119">UPN email of custodian.</span></span> <span data-ttu-id="43719-120">Ejemplo: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43719-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="43719-121">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="43719-121">**Exchange Enabled**</span></span> | <span data-ttu-id="43719-122">Valor TRUE/FALSE si se va a agregar el buzón de custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="43719-123">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="43719-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="43719-124">Valor TRUE/FALSE si se va a agregar la cuenta de OneDrive para la empresa de custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="43719-125">**Es pamantente**</span><span class="sxs-lookup"><span data-stu-id="43719-125">**Is OnHold**</span></span>        | <span data-ttu-id="43719-126">Valor verdadero/falso si desea poner la custodia en espera.</span><span class="sxs-lookup"><span data-stu-id="43719-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="43719-127">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="43719-127">**Workload1 Type**</span></span>         | <span data-ttu-id="43719-128">Valor de cadena que indica el tipo de origen de datos que se va a asociar con el custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="43719-129">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="43719-129">Possible values include:</span></span> <br /><span data-ttu-id="43719-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="43719-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="43719-131">**Ubicación de Workload1**</span><span class="sxs-lookup"><span data-stu-id="43719-131">**Workload1 Location**</span></span>     | <span data-ttu-id="43719-132">Según el tipo de carga de trabajo, sería la ubicación de los datos de la carga de trabajo (por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint).</span><span class="sxs-lookup"><span data-stu-id="43719-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="43719-133">Este es un ejemplo de un archivo CSV con información de custodios:</span><span class="sxs-lookup"><span data-stu-id="43719-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="43719-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="43719-134">ContactEmail</span></span>      | <span data-ttu-id="43719-135">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="43719-135">Exchange Enabled</span></span> | <span data-ttu-id="43719-136">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="43719-136">OneDrive Enabled</span></span> | <span data-ttu-id="43719-137">Es pamantente</span><span class="sxs-lookup"><span data-stu-id="43719-137">Is OnHold</span></span> | <span data-ttu-id="43719-138">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="43719-138">Workload1 Type</span></span> | <span data-ttu-id="43719-139">Ubicación de Workload1</span><span class="sxs-lookup"><span data-stu-id="43719-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="43719-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43719-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="43719-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="43719-141">TRUE</span></span>             | <span data-ttu-id="43719-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="43719-142">TRUE</span></span>             | <span data-ttu-id="43719-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="43719-143">TRUE</span></span>      | <span data-ttu-id="43719-144">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="43719-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="43719-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="43719-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="43719-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="43719-146">TRUE</span></span>             | <span data-ttu-id="43719-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="43719-147">TRUE</span></span>             | <span data-ttu-id="43719-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="43719-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="43719-149">Validación de custodios y orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="43719-149">Custodian and data source validation</span></span>

<span data-ttu-id="43719-150">Cuando se carga el archivo CSV de custodio, la exhibición avanzada de documentos electrónicos realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="43719-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="43719-151">Valida los custodios y sus orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="43719-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="43719-152">Indiza todos los orígenes de datos para cada custodio y los coloca en retención (si la propiedad is alhold se establece en TRUE).</span><span class="sxs-lookup"><span data-stu-id="43719-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="43719-153">Validación de custodios</span><span class="sxs-lookup"><span data-stu-id="43719-153">Custodian validation</span></span>

<span data-ttu-id="43719-154">Actualmente, solo se admite la importación de custodios que estén en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="43719-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="43719-155">Validamos y buscamos custodios mediante el valor UPN en la columna de **correo electrónico del contacto** en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="43719-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="43719-156">Los custodios que se validan se agregan automáticamente al caso y se enumeran en la ficha **custodio** en la página **orígenes** del caso.</span><span class="sxs-lookup"><span data-stu-id="43719-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="43719-157">Si no se puede validar un custodio, se enumeran en el registro de errores del trabajo BulkAddCustodian que aparece en la ficha **trabajos** en el caso.</span><span class="sxs-lookup"><span data-stu-id="43719-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="43719-158">Los custodios no validados no se agregan al caso.</span><span class="sxs-lookup"><span data-stu-id="43719-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="43719-159">Validación de origen de datos</span><span class="sxs-lookup"><span data-stu-id="43719-159">Data source validation</span></span>

<span data-ttu-id="43719-160">Una vez validados y agregados los custodios al caso, se validan todos los orígenes de datos asociados con un custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="43719-161">Si no se encuentra ningún origen de datos para un custodio, el valor **no validado** se mostraría en la columna **validada** en la ficha **custodio** de ese custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="43719-162">Corrección de orígenes de datos no validados</span><span class="sxs-lookup"><span data-stu-id="43719-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="43719-163">Para corregir los custodios con orígenes de datos no validados:</span><span class="sxs-lookup"><span data-stu-id="43719-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="43719-164">En la ficha **custodio** , seleccione un custodio que no se haya validado.</span><span class="sxs-lookup"><span data-stu-id="43719-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="43719-165">En la página flotante de custodios, desplácese hasta la sección **orígenes de datos** para ver los orígenes de datos asociados con custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="43719-166">Se enumeran los orígenes de datos validados y no validados.</span><span class="sxs-lookup"><span data-stu-id="43719-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="43719-167">En la sección **orígenes de datos** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="43719-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="43719-168">En la página **elegir ubicaciones de apoyo** , quite un origen de datos no validado.</span><span class="sxs-lookup"><span data-stu-id="43719-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="43719-169">En la página **seleccionar ubicaciones adicionales** , haga clic en **Actualizar** para agregar más orígenes de datos para un custodio.</span><span class="sxs-lookup"><span data-stu-id="43719-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
