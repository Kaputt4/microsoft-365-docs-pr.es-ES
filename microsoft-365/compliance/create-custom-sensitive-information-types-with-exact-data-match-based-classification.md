---
title: Crear un tipo de información confidencial personalizado con coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda a crear tipos de información confidencial personalizada con la clasificación basada en la coincidencia exacta de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b120e2bffa4554fb435fe8de2e22d6de2f851544
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604342"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="bc7f1-103">Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="bc7f1-104">[Los tipos de información confidencial personalizada](custom-sensitive-info-types.md) se usan para ayudar a identificar los elementos confidenciales y así evitar que se compartan de forma inadvertida o inapropiada.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="bc7f1-105">Defina un tipo de información confidencial personalizada a partir de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="bc7f1-106">patrones</span><span class="sxs-lookup"><span data-stu-id="bc7f1-106">patterns</span></span>
- <span data-ttu-id="bc7f1-107">evidencia de palabras clave como *empleado*, *distintivo* o *id.*</span><span class="sxs-lookup"><span data-stu-id="bc7f1-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="bc7f1-108">proximidad de caracteres a la evidencia en un patrón determinado</span><span class="sxs-lookup"><span data-stu-id="bc7f1-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="bc7f1-109">niveles de confianza</span><span class="sxs-lookup"><span data-stu-id="bc7f1-109">confidence levels</span></span>

 <span data-ttu-id="bc7f1-110">Estos tipos de información confidencial personalizada satisfacen las necesidades de negocio para muchas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="bc7f1-111">Pero, ¿qué ocurre si quiere un tipo de información confidencial personalizada que use valores de datos exactos, en lugar de uno que encuentre coincidencias a partir de patrones genéricos?</span><span class="sxs-lookup"><span data-stu-id="bc7f1-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="bc7f1-112">Con la clasificación basada en la coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizada que está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="bc7f1-113">ser dinámico y actualizable</span><span class="sxs-lookup"><span data-stu-id="bc7f1-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="bc7f1-114">ser más escalable</span><span class="sxs-lookup"><span data-stu-id="bc7f1-114">be more scalable</span></span>
- <span data-ttu-id="bc7f1-115">generar menos falsos positivos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-115">result in fewer false-positives</span></span>
- <span data-ttu-id="bc7f1-116">funcionar con datos confidenciales estructurados</span><span class="sxs-lookup"><span data-stu-id="bc7f1-116">work with structured sensitive data</span></span>
- <span data-ttu-id="bc7f1-117">trabajar con información confidencial de forma más segura</span><span class="sxs-lookup"><span data-stu-id="bc7f1-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="bc7f1-118">usarse con varios servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-118">be used with several Microsoft cloud services</span></span>

![Clasificación basada en EDM](../media/EDMClassification.png)

<span data-ttu-id="bc7f1-120">La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="bc7f1-121">La base de datos se puede actualizar diariamente y puede contener hasta 100 millones de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="bc7f1-122">Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="bc7f1-123">Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) o [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="bc7f1-124">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="bc7f1-125">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="bc7f1-126">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="bc7f1-127">Coreano</span><span class="sxs-lookup"><span data-stu-id="bc7f1-127">Korean</span></span>
> - <span data-ttu-id="bc7f1-128">Japonés</span><span class="sxs-lookup"><span data-stu-id="bc7f1-128">Japanese</span></span>

><span data-ttu-id="bc7f1-129">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="bc7f1-130">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="bc7f1-131">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="bc7f1-131">Required licenses and permissions</span></span>

<span data-ttu-id="bc7f1-132">Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="bc7f1-133">Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="bc7f1-134">La clasificación basada en EDM se incluye en estas suscripciones</span><span class="sxs-lookup"><span data-stu-id="bc7f1-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="bc7f1-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="bc7f1-135">Office 365 E5</span></span>
- <span data-ttu-id="bc7f1-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bc7f1-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="bc7f1-137">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bc7f1-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="bc7f1-138">Gobierno y protección de información de Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="bc7f1-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="bc7f1-139">Vínculos del portal para la suscripción</span><span class="sxs-lookup"><span data-stu-id="bc7f1-139">Portal links for your subscription</span></span>


|<span data-ttu-id="bc7f1-140">Portal</span><span class="sxs-lookup"><span data-stu-id="bc7f1-140">Portal</span></span>  |<span data-ttu-id="bc7f1-141">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="bc7f1-141">World Wide/GCC</span></span>  |<span data-ttu-id="bc7f1-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="bc7f1-142">GCC-High</span></span>  |<span data-ttu-id="bc7f1-143">DOD</span><span class="sxs-lookup"><span data-stu-id="bc7f1-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="bc7f1-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="bc7f1-144">Office SCC</span></span>     |  <span data-ttu-id="bc7f1-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="bc7f1-145">protection.office.com</span></span>       |<span data-ttu-id="bc7f1-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="bc7f1-146">scc.office365.us</span></span>         |<span data-ttu-id="bc7f1-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="bc7f1-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="bc7f1-148">Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bc7f1-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="bc7f1-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bc7f1-149">security.microsoft.com</span></span>         |<span data-ttu-id="bc7f1-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="bc7f1-150">security.microsoft.us</span></span>         |<span data-ttu-id="bc7f1-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="bc7f1-151">security.apps.mil</span></span>|
|<span data-ttu-id="bc7f1-152">Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bc7f1-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="bc7f1-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bc7f1-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="bc7f1-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="bc7f1-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="bc7f1-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="bc7f1-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="bc7f1-156">El flujo de trabajo de un vistazo</span><span class="sxs-lookup"><span data-stu-id="bc7f1-156">The work flow at a glance</span></span>

|<span data-ttu-id="bc7f1-157">Fase</span><span class="sxs-lookup"><span data-stu-id="bc7f1-157">Phase</span></span>  |<span data-ttu-id="bc7f1-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="bc7f1-159">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="bc7f1-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="bc7f1-160">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-160">(As needed)</span></span><br/><span data-ttu-id="bc7f1-161">- [Editar el esquema de la base de datos](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="bc7f1-162">- [Quitar el esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="bc7f1-163">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="bc7f1-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="bc7f1-164">- Esquema de la base de datos en formato XML (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="bc7f1-165">- Paquete de reglas en formato XML (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="bc7f1-166">- Permisos de administrador para el Centro de seguridad y cumplimiento (con PowerShell)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="bc7f1-167">Parte 2: Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="bc7f1-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="bc7f1-168">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-168">(As needed)</span></span><br/>[<span data-ttu-id="bc7f1-169">Actualizar los datos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="bc7f1-170">- Cuenta de usuario y de grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="bc7f1-170">- Custom security group and user account</span></span><br/><span data-ttu-id="bc7f1-171">- Acceso de administrador local en el equipo con el agente de carga EDM</span><span class="sxs-lookup"><span data-stu-id="bc7f1-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="bc7f1-172">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="bc7f1-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="bc7f1-173">- Procesar y programar la actualización de los datos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="bc7f1-174">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc7f1-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="bc7f1-175">- Suscripción a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="bc7f1-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="bc7f1-176">- Característica de clasificación basada en EDM habilitada</span><span class="sxs-lookup"><span data-stu-id="bc7f1-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="bc7f1-177">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="bc7f1-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="bc7f1-178">La configuración y la configuración de la clasificación basada en EDM incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="bc7f1-179">Guardar datos confidenciales en formato .csv</span><span class="sxs-lookup"><span data-stu-id="bc7f1-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="bc7f1-180">Definir el esquema de la base de datos de su información confidencial</span><span class="sxs-lookup"><span data-stu-id="bc7f1-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="bc7f1-181">Crear un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="bc7f1-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="bc7f1-182">Guardar datos confidenciales en formato .csv</span><span class="sxs-lookup"><span data-stu-id="bc7f1-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="bc7f1-183">Identifique la información confidencial que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="bc7f1-184">Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="bc7f1-185">El archivo de datos puede incluir un máximo de:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="bc7f1-186">Hasta 100 millones de filas de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="bc7f1-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="bc7f1-187">Hasta 32 columnas (campos) por origen de datos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="bc7f1-188">Hasta 5 columnas (campos) marcadas como utilizables en búsquedas</span><span class="sxs-lookup"><span data-stu-id="bc7f1-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="bc7f1-189">Estructure los datos confidenciales en el archivo .csv de forma que la primera fila incluya los nombres de los campos que se usan para la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="bc7f1-190">En el archivo .csv, puede tener nombres de campo como "NSS", "FechaNacimiento", "Nombre", "Apellido", etc.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="bc7f1-191">Los nombres de encabezado de las columnas no pueden contener espacios ni guiones bajos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="bc7f1-192">Por ejemplo, el archivo .csv de ejemplo que usamos en este artículo se denomina *RegistrosPacientes.csv* y sus columnas *IdPaciente*, *NEM*, *Apellido*, *Nombre*, *NSS*, etc.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="bc7f1-193">Preste atención al formato de los campos de datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-193">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="bc7f1-194">En particular, los campos que pueden contener comas en su contenido. Por ejemplo, la herramienta EDM analizará una dirección postal que contenga el valor "Seattle, WA" como dos campos separados.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-194">In particular, fields that may contain commas in their content (e.g. a street address that contains the value "Seattle,WA") would be parsed as two eparate fields when parsed by the EDM tool.</span></span> <span data-ttu-id="bc7f1-195">Para evitar este problema, debe asegurarse de que los campos estén entre comillas simples o dobles en la tabla de datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-195">In order to avoid this, you need to ensure such fields are surrounded by single or double quotes in the sensitive data table.</span></span> <span data-ttu-id="bc7f1-196">Si los campos con comas también pueden contener espacios, tendrá que crear un tipo de información confidencial personalizado que coincida con el formato correspondiente (por ejemplo, una cadena de varias palabras que contenga comas y espacios) para asegurarse de que la cadena se haya emparejado correctamente al digitalizar el documento.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-196">If fields with commas in them may also contain spaces, you would need to create a custom Sensitive Information Type that matches the corresponding format (e.g. a multi-word string with commas and spaces in it) to ensure the string is correctly matched wjen the document is scanned.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="bc7f1-197">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="bc7f1-197">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="bc7f1-198">Defina el esquema de la base de datos de información confidencial en formato XML (similar al siguiente ejemplo).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-198">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="bc7f1-199">Dé un nombre a este archivo de esquema **edm.xml** y configúrelo para que por cada columna de la base de datos haya una línea que use la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-199">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="bc7f1-200">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-200">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="bc7f1-201">Use nombres de columna para los valores *Nombre de campo*.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-201">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="bc7f1-202">Use *searchable="true"* para los campos que quiere que se puedan buscar, hasta un máximo de 5 campos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-202">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="bc7f1-203">Al menos un campo se debe poder utilizar en búsquedas.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-203">At least one field must be searchable.</span></span>

      <span data-ttu-id="bc7f1-204">Por ejemplo, el siguiente archivo XML define el esquema para una base de datos de registros de pacientes, con cinco campos especificados para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-204">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="bc7f1-205">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-205">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

4. <span data-ttu-id="bc7f1-206">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-206">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="bc7f1-207">Para cargar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-207">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="bc7f1-208">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-208">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="bc7f1-209">Confirmar</span><span class="sxs-lookup"><span data-stu-id="bc7f1-209">Confirm</span></span>
      >
      > <span data-ttu-id="bc7f1-210">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="bc7f1-210">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="bc7f1-211">Se importará el nuevo esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="bc7f1-211">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="bc7f1-212">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="bc7f1-212">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="bc7f1-213">Si quiere que los cambios se realicen sin confirmación, en el paso 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="bc7f1-213">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="bc7f1-214">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-214">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="bc7f1-215">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-215">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="bc7f1-216">Configuración de un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="bc7f1-216">Set up a rule package</span></span>

1. <span data-ttu-id="bc7f1-217">Cree un paquete de reglas en formato XML (con codificación Unicode), similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-217">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="bc7f1-218">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-218">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="bc7f1-219">Cuando configure el paquete de reglas, asegúrese de hacer referencia correctamente al archivo .csv y al archivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-219">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="bc7f1-220">Puede copiar, modificar y usar nuestro ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-220">You can copy, modify, and use our example.</span></span> <span data-ttu-id="bc7f1-221">En este XML de ejemplo, debe personalizar los siguientes campos para crear el tipo confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-221">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="bc7f1-222">**RulePack id y ExactMatch id**: use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) para generar un GUID.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-222">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="bc7f1-223">**Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-223">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="bc7f1-224">Debe proporcionar un nombre de origen de datos de un esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-224">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="bc7f1-225">**idMatch**: este campo señala al elemento principal para EDM.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-225">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="bc7f1-226">Matches: especifica el campo que se usará en la búsqueda exacta.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-226">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="bc7f1-227">Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-227">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="bc7f1-228">Classification: este campo especifica la coincidencia de tipo confidencial que desencadena la búsqueda de EDM.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-228">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="bc7f1-229">Puede especificar el nombre o el GUID de una clasificación personalizada o integrada existente.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-229">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="bc7f1-230">**Match:** este campo señala a la evidencia adicional que se encuentra cerca de idMatch.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-230">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="bc7f1-231">Matches: se proporciona un nombre de campo en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-231">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="bc7f1-232">**Resource:** esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-232">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="bc7f1-233">idRef: se proporciona un GUID para Id. de ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-233">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="bc7f1-234">Nombres y descripciones: personalice según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-234">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

1. <span data-ttu-id="bc7f1-235">Cargue el paquete de reglas ejecutando, uno a la vez, los siguientes cmdlets de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-235">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="bc7f1-236">Ya tiene configurada la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-236">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="bc7f1-237">El siguiente paso es crear un hash para los datos confidenciales y luego cargarlo para indexarlo.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-237">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="bc7f1-238">Recuerde del procedimiento anterior que nuestro esquema RegistrosPacientes define cinco campos para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-238">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="bc7f1-239">Nuestro paquete de reglas de ejemplo incluye esos campos y hace referencia al archivo de esquema de la base de datos (**edm.xml**), con un elemento *ExactMatch* por campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-239">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="bc7f1-240">Considere el siguiente elemento ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-240">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="bc7f1-241">En este ejemplo, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-241">In this example, note that:</span></span>

- <span data-ttu-id="bc7f1-242">El nombre de dataStore hace referencia al archivo .csv que hemos creado anteriormente: **dataStore = "RegistrosPacientes"**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-242">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="bc7f1-243">El valor de idMatch hace referencia a un campo para la búsqueda que aparece en el archivo de esquema de la base de datos: **idMatch matches = "NSS"**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-243">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="bc7f1-244">El valor classification hace referencia a un tipo de información confidencial existente o personalizada: **classification = "Número de seguridad social de Estados Unidos (NSS)"**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-244">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="bc7f1-245">(En este caso, usamos el tipo de información confidencial existente del número de la seguridad social de Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-245">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="bc7f1-246">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-246">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="bc7f1-247">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-247">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="bc7f1-248">Editar el esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="bc7f1-248">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="bc7f1-249">Si quiere realizar cambios en el archivo **edm.xml**, como cambiar los campos que se usan para la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-249">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="bc7f1-250">Edite el archivo **edm.xml** (este es el archivo tratado en la sección [Definir el esquema](#define-the-schema-for-your-database-of-sensitive-information) de este artículo).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-250">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="bc7f1-251">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-251">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="bc7f1-252">Para actualizar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-252">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="bc7f1-253">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-253">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="bc7f1-254">Confirmar</span><span class="sxs-lookup"><span data-stu-id="bc7f1-254">Confirm</span></span>
      >
      > <span data-ttu-id="bc7f1-255">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="bc7f1-255">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="bc7f1-256">Se actualizará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="bc7f1-256">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="bc7f1-257">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="bc7f1-257">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="bc7f1-258">Si quiere que los cambios se realicen sin confirmación, en el paso 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="bc7f1-258">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="bc7f1-259">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-259">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="bc7f1-260">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-260">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="bc7f1-261">Eliminación del esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="bc7f1-261">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="bc7f1-262">(Según sea necesario) Si quiere quitar el esquema que está usando de la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-262">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="bc7f1-263">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-263">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="bc7f1-264">Ejecute los siguientes cmdlets de PowerShell y sustituya el nombre del almacén de datos "registros de pacientes" por el que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-264">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="bc7f1-265">Se le pedirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-265">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="bc7f1-266">Confirmar</span><span class="sxs-lookup"><span data-stu-id="bc7f1-266">Confirm</span></span>
      >
      > <span data-ttu-id="bc7f1-267">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="bc7f1-267">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="bc7f1-268">Se quitará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="bc7f1-268">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="bc7f1-269">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="bc7f1-269">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="bc7f1-270">Si quiere que los cambios se realicen sin confirmación, en el paso 2, use este cmdlet: Remove-DlpEdmSchema -Identity registrospacientes -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="bc7f1-270">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="bc7f1-271">Parte 2: Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="bc7f1-271">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="bc7f1-272">En esta fase, configurará una cuenta de usuario y un grupo de seguridad personalizado y configurará la herramienta de agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-272">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="bc7f1-273">Luego, usará la herramienta para aplicar el algoritmo hash con valor de sal a los datos confidenciales y, después, los cargará.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-273">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="bc7f1-274">El algoritmo hash y la carga se pueden realizar con un equipo o puede separar el paso de hash del paso de carga para mayor seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-274">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="bc7f1-275">Si desea aplicar un algoritmo hash y cargar desde un equipo, tendrá que hacerlo desde un equipo que pueda conectarse directamente a su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-275">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="bc7f1-276">Esto requiere que los archivos de datos confidenciales de texto no cifrado se encuentren en el equipo para la aplicación del algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-276">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="bc7f1-277">Si no desea que se muestre el archivo de datos confidenciales de texto no cifrado, puede aplicar un algoritmo hash en un equipo en una ubicación segura y, a continuación, copiar el archivo hash y el archivo de sal en un equipo que pueda conectarse directamente a su espacio empresarial de Microsoft 365 para cargarlo.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-277">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="bc7f1-278">En este escenario, necesitará el EDMUploadAgent en ambos equipos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-278">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="bc7f1-279">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-279">Prerequisites</span></span>

- <span data-ttu-id="bc7f1-280">una cuenta profesional o educativa de Microsoft 365 que se agregará al grupo de seguridad de **EDM\_DataUploaders**</span><span class="sxs-lookup"><span data-stu-id="bc7f1-280">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="bc7f1-281">un equipo con Windows 10 o Windows Server 2016 con .NET versión 4.6.2 para ejecutar el EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="bc7f1-281">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="bc7f1-282">un directorio en el equipo de carga para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-282">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="bc7f1-283">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="bc7f1-283">EDMUploadAgent</span></span>
    - <span data-ttu-id="bc7f1-284">el archivo de elementos confidenciales en formato CSV **RegistrosPacientes.csv** en nuestros ejemplos</span><span class="sxs-lookup"><span data-stu-id="bc7f1-284">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="bc7f1-285">los archivos hash y de sal de salida</span><span class="sxs-lookup"><span data-stu-id="bc7f1-285">and the output hash and salt files</span></span>
    - <span data-ttu-id="bc7f1-286">el nombre del almacén de datos del archivo **edm.xml** que para este ejemplo es `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="bc7f1-286">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="bc7f1-287">Configuración de la cuenta de usuario y del grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="bc7f1-287">Set up the security group and user account</span></span>

1. <span data-ttu-id="bc7f1-288">Como administrador global, vaya al Centro de administración mediante el [vínculo apropiado para su suscripción](#portal-links-for-your-subscription) y [cree un grupo de seguridad](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)llamado **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-288">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="bc7f1-289">Agregue uno o más usuarios al grupo de seguridad **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-289">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="bc7f1-290">(Estos usuarios administrarán la base de datos de información confidencial).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-290">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="bc7f1-291">Crear un hash y cargar desde un equipo</span><span class="sxs-lookup"><span data-stu-id="bc7f1-291">Hash and upload from one computer</span></span>

<span data-ttu-id="bc7f1-292">Este equipo debe tener acceso directo a su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-292">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="bc7f1-293">Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-293">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="bc7f1-294">Vínculos al agente de carga de EDM por tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="bc7f1-294">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="bc7f1-295">Comercial + GCC</span><span class="sxs-lookup"><span data-stu-id="bc7f1-295">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="bc7f1-296">GCC-High</span><span class="sxs-lookup"><span data-stu-id="bc7f1-296">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="bc7f1-297">DoD</span><span class="sxs-lookup"><span data-stu-id="bc7f1-297">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="bc7f1-298">Cree un directorio de trabajo para EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-298">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="bc7f1-299">Por ejemplo: **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-299">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="bc7f1-300">Coloque el archivo **RegistrosPacientes.csv** dentro.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-300">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="bc7f1-301">Descargue e instale el [Agente de carga de EDM](#links-to-edm-upload-agent-by-subscription-type) adecuado para su suscripción en el directorio que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-301">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7f1-302">El EDMUploadAgent de los vínculos anteriores se ha actualizado para agregar automáticamente un valor de sal a los datos hash.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-302">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="bc7f1-303">De forma alternativa, puede brindar su propio valor de sal.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-303">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="bc7f1-304">Una vez que haya usado esta versión, no podrá usar la versión anterior de EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-304">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="bc7f1-305">Puede cargar datos con EDMUploadAgent en cualquier almacén de datos determinado solo dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-305">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="bc7f1-306">Para obtener una lista de los parámetros de comando compatibles, ejecute el agente sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-306">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="bc7f1-307">Por ejemplo, 'EdmUploadAgent.exe'.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-307">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="bc7f1-308">Autorice el agente de carga de EDM, abra la ventana del Símbolo del sistema (como administrador), cambie al directorio **C:\EDM\Data** y, después, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-308">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="bc7f1-309">Inicie sesión con su cuenta profesional o educativa de Microsoft 365 que se ha agregado al grupo de seguridad de EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-309">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="bc7f1-310">La información de inquilino se extrae de la cuenta de usuario para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-310">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="bc7f1-311">Para crear un hash y cargar los datos confidenciales, ejecute el siguiente comando en la ventana del Símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-311">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="bc7f1-312">Por ejemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\RegistrosPacientes.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="bc7f1-312">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="bc7f1-313">Esto agregará automáticamente un valor de sal generado de manera aleatoria al hash para una mayor seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-313">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="bc7f1-314">De forma opcional, si quiere usar su propio valor de sal, agregue **/Salt <saltvalue>** al comando.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-314">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="bc7f1-315">Este valor debe tener 64 caracteres de longitud y solo puede contener los caracteres a-z y 0-9.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-315">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="bc7f1-316">Compruebe el estado de la carga al ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-316">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="bc7f1-317">Ejemplo: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="bc7f1-317">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="bc7f1-318">Verifique que el estado se encuentre en **ProcesamientoEnCurso**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-318">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="bc7f1-319">Verifique nuevamente cada pocos minutos hasta que el estado cambie a **Completado**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-319">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="bc7f1-320">Una vez que el estado se muestre como completado, los datos de EDM ya están listos para su uso.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-320">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="bc7f1-321">Separe el hash y cargue</span><span class="sxs-lookup"><span data-stu-id="bc7f1-321">Separate Hash and upload</span></span>

<span data-ttu-id="bc7f1-322">Aplique el algoritmo hash en un equipo en un entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-322">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="bc7f1-323">Ejecute el siguiente comando en la ventana del Símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-323">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="bc7f1-324">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-324">For example:</span></span>

> <span data-ttu-id="bc7f1-325">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\RegistrosPacientes.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="bc7f1-325">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="bc7f1-326">De este forma, se obtendrá un archivo con hash y un archivo de sal con estas extensiones si no ha especificado la opción **/Salt <saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-326">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="bc7f1-327">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="bc7f1-327">.EdmHash</span></span>
- <span data-ttu-id="bc7f1-328">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="bc7f1-328">.EdmSalt</span></span>

2. <span data-ttu-id="bc7f1-329">Copie estos archivos de forma segura al equipo que usará para cargar el archivo CSV de elementos confidenciales (RegistrosPacientes) en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-329">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="bc7f1-330">Para cargar los datos con hash, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-330">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="bc7f1-331">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-331">For example:</span></span>

> <span data-ttu-id="bc7f1-332">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="bc7f1-332">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="bc7f1-333">Para comprobar que se hayan cargado los datos confidenciales, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-333">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="bc7f1-334">Verá una lista de almacenes de datos y la última vez que se actualizaron.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-334">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="bc7f1-335">Si desea ver todos los datos cargados en una determinada tienda, ejecute el comando siguiente en un símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-335">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="bc7f1-336">Continúe con el proceso de configuración y programación para [actualizar la base de datos de información confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-336">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="bc7f1-337">En este momento, está listo para usar la clasificación basada en EDM con los servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-337">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="bc7f1-338">Por ejemplo, puede [configurar una directiva DLP con clasificación basada en EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-338">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="bc7f1-339">Actualizar la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="bc7f1-339">Refreshing your sensitive information database</span></span>

<span data-ttu-id="bc7f1-340">Puede actualizar la base de datos de información confidencial diariamente y la herramienta de carga de EDM puede volver a indexar los datos confidenciales y cargar de nuevo los datos indexados.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-340">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="bc7f1-341">Determine el proceso y la frecuencia (diaria o semanal) para actualizar la base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-341">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="bc7f1-342">Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-342">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="bc7f1-343">Mantenga el mismo nombre de archivo y ubicación que usó cuando siguió los pasos descritos en [Crear un hash y cargar los datos confidenciales](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-343">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="bc7f1-344">Si no hay ningún cambio en la estructura (nombres de campo) del archivo .csv, no necesita realizar cambios en el archivo de esquema de la base de datos al actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-344">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="bc7f1-345">Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-345">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="bc7f1-346">Use el [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar los pasos 2 y 3 en el procedimiento [Hash y carga de los datos confidenciales](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-346">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="bc7f1-347">Puede programar tareas con varios métodos:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-347">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="bc7f1-348">Método</span><span class="sxs-lookup"><span data-stu-id="bc7f1-348">Method</span></span>             | <span data-ttu-id="bc7f1-349">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="bc7f1-349">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="bc7f1-350">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc7f1-350">Windows PowerShell</span></span>     | <span data-ttu-id="bc7f1-351">Consulte la documentación [TareasProgramadas](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo</span><span class="sxs-lookup"><span data-stu-id="bc7f1-351">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="bc7f1-352">API del Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="bc7f1-352">Task Scheduler API</span></span>     | <span data-ttu-id="bc7f1-353">Consulte la documentación del [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-353">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="bc7f1-354">Interfaz de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="bc7f1-354">Windows user interface</span></span> | <span data-ttu-id="bc7f1-355">En Windows, haga clic en **Inicio** y escriba Programador de tareas.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-355">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="bc7f1-356">A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-356">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="bc7f1-357">Script de PowerShell de ejemplo para el Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="bc7f1-357">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="bc7f1-358">Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de creación de hash para los datos y cargar los datos con hash:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-358">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="bc7f1-359">Para programar la creación del hash y cargar en un paso combinado</span><span class="sxs-lookup"><span data-stu-id="bc7f1-359">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="bc7f1-360">Para programar la creación del hash y cargar en pasos separados</span><span class="sxs-lookup"><span data-stu-id="bc7f1-360">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="bc7f1-361">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc7f1-361">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="bc7f1-362">Estas ubicaciones son compatibles con los tipos de información confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-362">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="bc7f1-363">DLP para Exchange Online (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-363">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="bc7f1-364">OneDrive para la Empresa (archivos)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-364">OneDrive for Business (files)</span></span>
- <span data-ttu-id="bc7f1-365">Microsoft Teams (conversaciones)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-365">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="bc7f1-366">DLP para SharePoint (archivos)</span><span class="sxs-lookup"><span data-stu-id="bc7f1-366">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="bc7f1-367">Directivas DLP para la seguridad de las aplicaciones en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc7f1-367">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="bc7f1-368">Los tipos de información confidencial de EDM para las siguientes situaciones están actualmente en desarrollo, pero todavía no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="bc7f1-368">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="bc7f1-369">Clasificación automática de las etiquetas de sensibilidad y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="bc7f1-369">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="bc7f1-370">Para crear una directiva DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="bc7f1-370">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="bc7f1-371">Vaya al Centro de seguridad y cumplimiento con el [vínculo adecuado para su suscripción](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="bc7f1-371">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="bc7f1-372">Seleccione **Directiva de prevención de pérdida de datos** \> **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-372">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="bc7f1-373">Elija **Crear una directiva** \> **Personalizado** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-373">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="bc7f1-374">En la pestaña **Nombre de la directiva**, especifique un nombre y una descripción y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-374">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="bc7f1-375">En la pestaña **Elegir ubicaciones**, haga clic en **Permitir elegir ubicaciones concretas** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-375">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="bc7f1-376">En la columna **Estado**, seleccione **correo electrónico de Exchange, cuentas de OneDrive, conversación de equipos y mensaje de canal**, y después elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-376">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="bc7f1-377">En la pestaña **Configuración de directiva**, elija **Usar la configuración avanzada** y luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-377">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="bc7f1-378">Elija **+ Nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-378">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="bc7f1-379">En la sección **Nombre**, especifique un nombre y una descripción para la regla.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-379">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="bc7f1-380">En la sección **Condiciones** en la lista **+ Agregar una condición**, elija **El contenido incluye tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-380">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![El contenido incluye tipos de información confidencial](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="bc7f1-382">Busque el tipo de información confidencial que creó al configurar el paquete de reglas y elija **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-382">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="bc7f1-383">Elija **Hecho**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-383">Then choose **Done**.</span></span>

12. <span data-ttu-id="bc7f1-384">Termine de seleccionar las opciones para la regla, como **Notificaciones de usuario**, **Invalidaciones de usuario**, **Informes de incidentes**, etc. y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-384">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="bc7f1-385">En la pestaña **Configuración de directiva**, revise las reglas y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-385">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="bc7f1-386">Especifique si quiere activar la directiva inmediatamente, probarla o dejarla desactivada.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-386">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="bc7f1-387">A continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-387">Then choose **Next**.</span></span>

15. <span data-ttu-id="bc7f1-388">En la pestaña **Revisar la configuración**, revise la directiva.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-388">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="bc7f1-389">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-389">Make any needed changes.</span></span> <span data-ttu-id="bc7f1-390">Cuando haya terminado, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-390">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7f1-391">Espere aproximadamente una hora para que la nueva directiva DLP pase por el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="bc7f1-391">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bc7f1-392">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc7f1-392">Related articles</span></span>

- [<span data-ttu-id="bc7f1-393">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="bc7f1-393">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="bc7f1-394">Tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="bc7f1-394">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="bc7f1-395">Información general de directivas DLP</span><span class="sxs-lookup"><span data-stu-id="bc7f1-395">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="bc7f1-396">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bc7f1-396">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="bc7f1-397">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="bc7f1-397">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)
