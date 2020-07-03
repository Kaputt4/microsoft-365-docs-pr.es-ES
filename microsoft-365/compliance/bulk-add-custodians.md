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
description: Use la herramienta de adición en masa para agregar rápidamente varios custodios y sus orígenes de datos asociados a un caso en eDiscovery avanzado.
ms.openlocfilehash: ab9626be01814fa95a959141433b431df9bf7724
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024670"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="365b5-103">Adición de custodios en masa a un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="365b5-103">Bulk-add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="365b5-104">Para los casos de eDiscovery avanzados que implican un gran número de custodios, puede importar varios custodios a la vez mediante un archivo CSV que contenga toda la información necesaria para agregarlos a un caso.</span><span class="sxs-lookup"><span data-stu-id="365b5-104">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="365b5-105">Custodios de adición en masa</span><span class="sxs-lookup"><span data-stu-id="365b5-105">Bulk-add custodians</span></span>

1. <span data-ttu-id="365b5-106">Escriba mayúsculas y navegue a la pestaña **orígenes** .</span><span class="sxs-lookup"><span data-stu-id="365b5-106">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="365b5-107">Haga clic en **importar custodios**</span><span class="sxs-lookup"><span data-stu-id="365b5-107">Click **Import custodians**</span></span>

3. <span data-ttu-id="365b5-108">En la página de flotante, haga clic en **descargar una plantilla en blanco** para descargar un archivo de plantilla de custodio de CSV.</span><span class="sxs-lookup"><span data-stu-id="365b5-108">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="365b5-109">Agregue la información de la Private al archivo CSV y guárdelo en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="365b5-109">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="365b5-110">Consulte la sección siguiente para obtener información sobre las propiedades del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="365b5-110">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="365b5-111">En la pestaña **orígenes** , haga clic en **importar custodios** nuevamente.</span><span class="sxs-lookup"><span data-stu-id="365b5-111">On the **Sources** tab, click **Import Custodians** again.</span></span>

6. <span data-ttu-id="365b5-112">En la página de flotante, haga clic en **examinar** y en cargar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="365b5-112">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="365b5-113">Una vez cargado el archivo CSV, se crea un trabajo de BulkAddCustodian y se muestra en la pestaña **trabajos** . El trabajo valida los custodios y sus orígenes de datos correspondientes y, a continuación, los agrega a la ficha **custodios** de la página **orígenes** del caso.</span><span class="sxs-lookup"><span data-stu-id="365b5-113">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="365b5-114">Archivo CSV de custodio</span><span class="sxs-lookup"><span data-stu-id="365b5-114">Custodian CSV file</span></span>

<span data-ttu-id="365b5-115">Una vez que haya descargado la plantilla CSV, puede Agregar custodios y su origen de datos en cada fila.</span><span class="sxs-lookup"><span data-stu-id="365b5-115">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="365b5-116">Asegúrese de no cambiar los nombres de columna de la fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="365b5-116">Be sure not to change the column names in the header row.</span></span>

| <span data-ttu-id="365b5-117">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="365b5-117">Column name</span></span>|<span data-ttu-id="365b5-118">Description</span><span class="sxs-lookup"><span data-stu-id="365b5-118">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="365b5-119">**Asociada de custodios**</span><span class="sxs-lookup"><span data-stu-id="365b5-119">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="365b5-120">Correo electrónico UPN de custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-120">UPN email of custodian.</span></span> <span data-ttu-id="365b5-121">Ejemplo: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="365b5-121">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="365b5-122">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="365b5-122">**Exchange Enabled**</span></span> | <span data-ttu-id="365b5-123">Valor TRUE/FALSE si se va a agregar el buzón de custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-123">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="365b5-124">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="365b5-124">**OneDrive Enabled**</span></span> | <span data-ttu-id="365b5-125">Valor TRUE/FALSE si se va a agregar la cuenta de OneDrive para la empresa de custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-125">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="365b5-126">**Es pamantente**</span><span class="sxs-lookup"><span data-stu-id="365b5-126">**Is OnHold**</span></span>        | <span data-ttu-id="365b5-127">Valor verdadero/falso si desea poner la custodia en espera.</span><span class="sxs-lookup"><span data-stu-id="365b5-127">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="365b5-128">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="365b5-128">**Workload1 Type**</span></span>         | <span data-ttu-id="365b5-129">Valor de cadena que indica el tipo de origen de datos que se va a asociar con el custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-129">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="365b5-130">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="365b5-130">Possible values include:</span></span> <br /><span data-ttu-id="365b5-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="365b5-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="365b5-132">**Ubicación de Workload1**</span><span class="sxs-lookup"><span data-stu-id="365b5-132">**Workload1 Location**</span></span>     | <span data-ttu-id="365b5-133">Según el tipo de carga de trabajo, sería la ubicación de los datos de la carga de trabajo (por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint).</span><span class="sxs-lookup"><span data-stu-id="365b5-133">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="365b5-134">Este es un ejemplo de un archivo CSV con información de custodios:</span><span class="sxs-lookup"><span data-stu-id="365b5-134">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="365b5-135">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="365b5-135">ContactEmail</span></span>      | <span data-ttu-id="365b5-136">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="365b5-136">Exchange Enabled</span></span> | <span data-ttu-id="365b5-137">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="365b5-137">OneDrive Enabled</span></span> | <span data-ttu-id="365b5-138">Es pamantente</span><span class="sxs-lookup"><span data-stu-id="365b5-138">Is OnHold</span></span> | <span data-ttu-id="365b5-139">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="365b5-139">Workload1 Type</span></span> | <span data-ttu-id="365b5-140">Ubicación de Workload1</span><span class="sxs-lookup"><span data-stu-id="365b5-140">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="365b5-141">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="365b5-141">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="365b5-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="365b5-142">TRUE</span></span>             | <span data-ttu-id="365b5-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="365b5-143">TRUE</span></span>             | <span data-ttu-id="365b5-144">TRUE</span><span class="sxs-lookup"><span data-stu-id="365b5-144">TRUE</span></span>      | <span data-ttu-id="365b5-145">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="365b5-145">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="365b5-146">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="365b5-146">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="365b5-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="365b5-147">TRUE</span></span>             | <span data-ttu-id="365b5-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="365b5-148">TRUE</span></span>             | <span data-ttu-id="365b5-149">TRUE</span><span class="sxs-lookup"><span data-stu-id="365b5-149">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="365b5-150">Validación de custodios y orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="365b5-150">Custodian and data source validation</span></span>

<span data-ttu-id="365b5-151">Cuando se carga el archivo CSV de custodio, la exhibición avanzada de documentos electrónicos realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="365b5-151">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="365b5-152">Valida los custodios y sus orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="365b5-152">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="365b5-153">Indiza todos los orígenes de datos para cada custodio y los coloca en retención (si la propiedad is alhold se establece en TRUE).</span><span class="sxs-lookup"><span data-stu-id="365b5-153">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="365b5-154">Validación de custodios</span><span class="sxs-lookup"><span data-stu-id="365b5-154">Custodian validation</span></span>

<span data-ttu-id="365b5-155">Actualmente, solo se admite la importación de custodios que estén en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="365b5-155">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="365b5-156">Validamos y buscamos custodios mediante el valor UPN en la columna de **correo electrónico del contacto** en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="365b5-156">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="365b5-157">Los custodios que se validan se agregan automáticamente al caso y se enumeran en la ficha **custodio** en la página **orígenes** del caso.</span><span class="sxs-lookup"><span data-stu-id="365b5-157">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="365b5-158">Si no se puede validar un custodio, se enumeran en el registro de errores del trabajo BulkAddCustodian que aparece en la ficha **trabajos** en el caso.</span><span class="sxs-lookup"><span data-stu-id="365b5-158">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="365b5-159">Los custodios no validados no se agregan al caso.</span><span class="sxs-lookup"><span data-stu-id="365b5-159">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="365b5-160">Validación de origen de datos</span><span class="sxs-lookup"><span data-stu-id="365b5-160">Data source validation</span></span>

<span data-ttu-id="365b5-161">Una vez validados y agregados los custodios al caso, se validan todos los orígenes de datos asociados con un custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-161">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="365b5-162">Si no se encuentra ningún origen de datos para un custodio, el valor **no validado** se mostraría en la columna **validada** en la ficha **custodio** de ese custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-162">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="365b5-163">Corrección de orígenes de datos no validados</span><span class="sxs-lookup"><span data-stu-id="365b5-163">Remediating unvalidated data sources</span></span>

<span data-ttu-id="365b5-164">Para corregir los custodios con orígenes de datos no validados:</span><span class="sxs-lookup"><span data-stu-id="365b5-164">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="365b5-165">En la ficha **custodio** , seleccione un custodio que no se haya validado.</span><span class="sxs-lookup"><span data-stu-id="365b5-165">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="365b5-166">En la página flotante de custodios, desplácese hasta la sección **orígenes de datos** para ver los orígenes de datos asociados con custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-166">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="365b5-167">Se enumeran los orígenes de datos validados y no validados.</span><span class="sxs-lookup"><span data-stu-id="365b5-167">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="365b5-168">En la sección **orígenes de datos** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="365b5-168">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="365b5-169">En la página **elegir ubicaciones de apoyo** , quite un origen de datos no validado.</span><span class="sxs-lookup"><span data-stu-id="365b5-169">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="365b5-170">En la página **seleccionar ubicaciones adicionales** , haga clic en **Actualizar** para agregar más orígenes de datos para un custodio.</span><span class="sxs-lookup"><span data-stu-id="365b5-170">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
