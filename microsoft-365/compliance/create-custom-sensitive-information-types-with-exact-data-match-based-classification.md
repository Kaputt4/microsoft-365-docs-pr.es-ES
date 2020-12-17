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
ms.openlocfilehash: 68546f7ad9f4b97f43611d49054200db4fdd4bbd
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698401"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="60547-103">Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos</span><span class="sxs-lookup"><span data-stu-id="60547-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="60547-104">[Los tipos de información confidencial personalizada](custom-sensitive-info-types.md) se usan para ayudar a identificar los elementos confidenciales y así ayudar a evitar que se compartan de forma inadvertida o inapropiada.</span><span class="sxs-lookup"><span data-stu-id="60547-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can help prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="60547-105">Defina un tipo de información confidencial personalizada a partir de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="60547-106">patrones</span><span class="sxs-lookup"><span data-stu-id="60547-106">patterns</span></span>
- <span data-ttu-id="60547-107">evidencia de palabras clave como *empleado*, *distintivo* o *id.*</span><span class="sxs-lookup"><span data-stu-id="60547-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="60547-108">proximidad de caracteres a la evidencia en un patrón determinado</span><span class="sxs-lookup"><span data-stu-id="60547-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="60547-109">niveles de confianza</span><span class="sxs-lookup"><span data-stu-id="60547-109">confidence levels</span></span>

 <span data-ttu-id="60547-110">Estos tipos de información confidencial personalizada satisfacen las necesidades de negocio para muchas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="60547-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="60547-111">Pero, ¿qué ocurre si quiere un tipo de información confidencial personalizada que use valores de datos exactos, en lugar de uno que encuentre coincidencias a partir de patrones genéricos?</span><span class="sxs-lookup"><span data-stu-id="60547-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="60547-112">Con la clasificación basada en la coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizada que está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="60547-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="60547-113">ser dinámico y actualizarse fácilmente</span><span class="sxs-lookup"><span data-stu-id="60547-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="60547-114">ser más escalable</span><span class="sxs-lookup"><span data-stu-id="60547-114">be more scalable</span></span>
- <span data-ttu-id="60547-115">generar menos falsos positivos</span><span class="sxs-lookup"><span data-stu-id="60547-115">result in fewer false-positives</span></span>
- <span data-ttu-id="60547-116">funcionar con datos confidenciales estructurados</span><span class="sxs-lookup"><span data-stu-id="60547-116">work with structured sensitive data</span></span>
- <span data-ttu-id="60547-117">trabajar con información confidencial de forma más segura</span><span class="sxs-lookup"><span data-stu-id="60547-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="60547-118">usarse con varios servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="60547-118">be used with several Microsoft cloud services</span></span>

![Clasificación basada en EDM](../media/EDMClassification.png)

<span data-ttu-id="60547-120">La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="60547-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="60547-121">La base de datos se puede actualizar diariamente y puede contener hasta 100 millones de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="60547-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="60547-122">Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables.</span><span class="sxs-lookup"><span data-stu-id="60547-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="60547-123">Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) o [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="60547-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="60547-124">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="60547-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="60547-125">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="60547-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="60547-126">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="60547-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="60547-127">Coreano</span><span class="sxs-lookup"><span data-stu-id="60547-127">Korean</span></span>
> - <span data-ttu-id="60547-128">Japonés</span><span class="sxs-lookup"><span data-stu-id="60547-128">Japanese</span></span>

><span data-ttu-id="60547-129">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="60547-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="60547-130">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="60547-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="60547-131">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="60547-131">Required licenses and permissions</span></span>

<span data-ttu-id="60547-132">Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="60547-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="60547-133">Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="60547-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="60547-134">La clasificación basada en EDM se incluye en estas suscripciones</span><span class="sxs-lookup"><span data-stu-id="60547-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="60547-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="60547-135">Office 365 E5</span></span>
- <span data-ttu-id="60547-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="60547-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="60547-137">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="60547-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="60547-138">Gobierno y protección de información de Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="60547-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="60547-139">Vínculos del portal para la suscripción</span><span class="sxs-lookup"><span data-stu-id="60547-139">Portal links for your subscription</span></span>


|<span data-ttu-id="60547-140">Portal</span><span class="sxs-lookup"><span data-stu-id="60547-140">Portal</span></span>  |<span data-ttu-id="60547-141">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="60547-141">World Wide/GCC</span></span>  |<span data-ttu-id="60547-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="60547-142">GCC-High</span></span>  |<span data-ttu-id="60547-143">DOD</span><span class="sxs-lookup"><span data-stu-id="60547-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="60547-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="60547-144">Office SCC</span></span>     |  <span data-ttu-id="60547-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="60547-145">protection.office.com</span></span>       |<span data-ttu-id="60547-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="60547-146">scc.office365.us</span></span>         |<span data-ttu-id="60547-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="60547-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="60547-148">Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60547-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="60547-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="60547-149">security.microsoft.com</span></span>         |<span data-ttu-id="60547-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="60547-150">security.microsoft.us</span></span>         |<span data-ttu-id="60547-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="60547-151">security.apps.mil</span></span>|
|<span data-ttu-id="60547-152">Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60547-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="60547-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="60547-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="60547-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="60547-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="60547-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="60547-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="60547-156">El flujo de trabajo de un vistazo</span><span class="sxs-lookup"><span data-stu-id="60547-156">The work flow at a glance</span></span>

|<span data-ttu-id="60547-157">Fase</span><span class="sxs-lookup"><span data-stu-id="60547-157">Phase</span></span>  |<span data-ttu-id="60547-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60547-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="60547-159">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="60547-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="60547-160">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="60547-160">(As needed)</span></span><br/><span data-ttu-id="60547-161">- [Editar el esquema de la base de datos](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="60547-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="60547-162">- [Quitar el esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="60547-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="60547-163">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="60547-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="60547-164">- Esquema de la base de datos en formato XML (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="60547-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="60547-165">- Paquete de reglas en formato XML (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="60547-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="60547-166">- Permisos de administrador para el Centro de seguridad y cumplimiento (con PowerShell)</span><span class="sxs-lookup"><span data-stu-id="60547-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="60547-167">Parte 2: Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="60547-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="60547-168">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="60547-168">(As needed)</span></span><br/>[<span data-ttu-id="60547-169">Actualizar los datos</span><span class="sxs-lookup"><span data-stu-id="60547-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="60547-170">- Cuenta de usuario y de grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="60547-170">- Custom security group and user account</span></span><br/><span data-ttu-id="60547-171">- Acceso de administrador local en el equipo con el agente de carga EDM</span><span class="sxs-lookup"><span data-stu-id="60547-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="60547-172">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="60547-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="60547-173">- Procesar y programar la actualización de los datos</span><span class="sxs-lookup"><span data-stu-id="60547-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="60547-174">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="60547-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="60547-175">- Suscripción a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="60547-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="60547-176">- Característica de clasificación basada en EDM habilitada</span><span class="sxs-lookup"><span data-stu-id="60547-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="60547-177">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="60547-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="60547-178">La configuración y la configuración de la clasificación basada en EDM incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="60547-179">Guardar datos confidenciales en formato .csv</span><span class="sxs-lookup"><span data-stu-id="60547-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="60547-180">Definir el esquema de la base de datos de su información confidencial</span><span class="sxs-lookup"><span data-stu-id="60547-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="60547-181">Crear un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="60547-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="60547-182">Guardar datos confidenciales en formato .csv</span><span class="sxs-lookup"><span data-stu-id="60547-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="60547-183">Identifique la información confidencial que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="60547-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="60547-184">Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="60547-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="60547-185">El archivo de datos puede incluir un máximo de:</span><span class="sxs-lookup"><span data-stu-id="60547-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="60547-186">Hasta 100 millones de filas de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="60547-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="60547-187">Hasta 32 columnas (campos) por origen de datos</span><span class="sxs-lookup"><span data-stu-id="60547-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="60547-188">Hasta 5 columnas (campos) marcadas como utilizables en búsquedas</span><span class="sxs-lookup"><span data-stu-id="60547-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="60547-189">Estructure los datos confidenciales en el archivo .csv de forma que la primera fila incluya los nombres de los campos que se usan para la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="60547-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="60547-190">En el archivo .csv, puede tener nombres de campo como "NSS", "FechaNacimiento", "Nombre", "Apellido", etc.</span><span class="sxs-lookup"><span data-stu-id="60547-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="60547-191">Los nombres de encabezado de las columnas no pueden contener espacios ni guiones bajos.</span><span class="sxs-lookup"><span data-stu-id="60547-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="60547-192">Por ejemplo, el archivo .csv de ejemplo que usamos en este artículo se denomina *RegistrosPacientes.csv* y sus columnas *IdPaciente*, *NEM*, *Apellido*, *Nombre*, *NSS*, etc.</span><span class="sxs-lookup"><span data-stu-id="60547-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="60547-193">Preste atención al formato de los campos de datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="60547-193">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="60547-194">En particular, los campos que pueden contener comas en su contenido. Por ejemplo, la herramienta EDM analizará una dirección postal que contenga el valor "Seattle, WA" como dos campos separados.</span><span class="sxs-lookup"><span data-stu-id="60547-194">In particular, fields that may contain commas in their content (e.g. a street address that contains the value "Seattle,WA") would be parsed as two eparate fields when parsed by the EDM tool.</span></span> <span data-ttu-id="60547-195">Para evitar este problema, debe asegurarse de que los campos estén entre comillas simples o dobles en la tabla de datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="60547-195">In order to avoid this, you need to ensure such fields are surrounded by single or double quotes in the sensitive data table.</span></span> <span data-ttu-id="60547-196">Si los campos con comas también pueden contener espacios, tendrá que crear un tipo de información confidencial personalizado que coincida con el formato correspondiente (por ejemplo, una cadena de varias palabras que contenga comas y espacios) para asegurarse de que la cadena se haya emparejado correctamente al digitalizar el documento.</span><span class="sxs-lookup"><span data-stu-id="60547-196">If fields with commas in them may also contain spaces, you would need to create a custom Sensitive Information Type that matches the corresponding format (e.g. a multi-word string with commas and spaces in it) to ensure the string is correctly matched wjen the document is scanned.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="60547-197">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="60547-197">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="60547-198">Si, por razones técnicas o de negocios, prefiere no usar PowerShell o la línea de comandos para crear el esquema y el tipo de información confidencial de EDM Patter (paquete de reglas), puede usar el [Asistente de tipo de información confidencial y esquema de coincidencia de datos](sit-edm-wizard.md) para crearlos.</span><span class="sxs-lookup"><span data-stu-id="60547-198">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type patter (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="60547-199">Cuando termine de crear el esquema y el patrón de tipo de información confidencial de EDM, vuelva a completar todos los pasos necesarios para que su tipo de información confidencial basado en EDM esté disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="60547-199">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="60547-200">El esquema de coincidencia exacta de datos y el Asistente para tipos de información confidencial solo están disponibles para las nubes en todo el mundo y GCC.</span><span class="sxs-lookup"><span data-stu-id="60547-200">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="60547-201">Defina el esquema de la base de datos de información confidencial en formato XML (similar al siguiente ejemplo).</span><span class="sxs-lookup"><span data-stu-id="60547-201">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="60547-202">Dé un nombre a este archivo de esquema **edm.xml** y configúrelo para que por cada columna de la base de datos haya una línea que use la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="60547-202">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="60547-203">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="60547-203">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="60547-204">Use nombres de columna para los valores *Nombre de campo*.</span><span class="sxs-lookup"><span data-stu-id="60547-204">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="60547-205">Use *searchable="true"* para los campos que quiere que se puedan buscar, hasta un máximo de 5 campos.</span><span class="sxs-lookup"><span data-stu-id="60547-205">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="60547-206">Al menos un campo se debe poder utilizar en búsquedas.</span><span class="sxs-lookup"><span data-stu-id="60547-206">At least one field must be searchable.</span></span>

      <span data-ttu-id="60547-207">Por ejemplo, el siguiente archivo XML define el esquema para una base de datos de registros de pacientes, con cinco campos especificados para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="60547-207">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="60547-208">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="60547-208">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
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

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="60547-209">Coincidencia configurable con los campos caseInsensitive y ignoredDelimiters</span><span class="sxs-lookup"><span data-stu-id="60547-209">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="60547-210">En el ejemplo de XML anterior se usan los campos `caseInsensitive` y `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="60547-210">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="60547-211">Al incluir el campo \***caseInsensitive** _ establecido en el valor de `true` en la definición del esquema, EDM no excluirá un elemento basado en diferencias entre mayúsculas y minúsculas para el campo `PatientID`.</span><span class="sxs-lookup"><span data-stu-id="60547-211">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="60547-212">Por lo tanto, EDM verá `PatientID` _ *FOO-1234*\* y **fOo-1234** como iguales.</span><span class="sxs-lookup"><span data-stu-id="60547-212">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="60547-213">Al incluir el campo **_ignoredDelimiters_*_ con caracteres compatibles, EDM pasará por alto estos caracteres en `PatientID`. Por lo tanto, el EDM verá `PatientID` _\* FOO-1234*\* y `PatientID` **FOO#1234** como iguales.</span><span class="sxs-lookup"><span data-stu-id="60547-213">When you include the **_ignoredDelimiters_*_ field with supported characters,  EDM will ignore those characters in the `PatientID`. So EDM will see, `PatientID` _\* FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="60547-214">El indicador `ignoredDelimiters` admite cualquier carácter no alfanumérico. Aquí se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="60547-214">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="60547-215">\.</span><span class="sxs-lookup"><span data-stu-id="60547-215">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \; 

- <span data-ttu-id="60547-216">El indicador `ignoredDelimiters` no es compatible con:</span><span class="sxs-lookup"><span data-stu-id="60547-216">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="60547-217">caracteres 0-9</span><span class="sxs-lookup"><span data-stu-id="60547-217">characters 0-9</span></span>
- <span data-ttu-id="60547-218">A-Z</span><span class="sxs-lookup"><span data-stu-id="60547-218">A-Z</span></span>
- <span data-ttu-id="60547-219">a-z</span><span class="sxs-lookup"><span data-stu-id="60547-219">a-z</span></span>
- \"
- \,

<span data-ttu-id="60547-220">En este ejemplo, donde se usan tanto `caseInsensitive` como `ignoredDelimiters`, EDM vería **FOO-1234** y **fOo#1234** como iguales y clasificaría al elemento como el tipo de información confidencial para el registro del paciente.</span><span class="sxs-lookup"><span data-stu-id="60547-220">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="60547-221">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="60547-221">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="60547-222">Para cargar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="60547-222">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="60547-223">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-223">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="60547-224">Confirmar</span><span class="sxs-lookup"><span data-stu-id="60547-224">Confirm</span></span>
      >
      > <span data-ttu-id="60547-225">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="60547-225">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="60547-226">Se importará el nuevo esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="60547-226">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="60547-227">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="60547-227">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="60547-228">Si quiere que los cambios se realicen sin confirmación, en el paso 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="60547-228">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="60547-229">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="60547-229">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="60547-230">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="60547-230">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="60547-231">Configuración de un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="60547-231">Set up a rule package</span></span>

1. <span data-ttu-id="60547-232">Cree un paquete de reglas en formato XML (con codificación Unicode), similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60547-232">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="60547-233">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="60547-233">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="60547-234">Cuando configure el paquete de reglas, asegúrese de hacer referencia correctamente al archivo .csv y al archivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="60547-234">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="60547-235">Puede copiar, modificar y usar nuestro ejemplo.</span><span class="sxs-lookup"><span data-stu-id="60547-235">You can copy, modify, and use our example.</span></span> <span data-ttu-id="60547-236">En este XML de ejemplo, debe personalizar los siguientes campos para crear el tipo confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="60547-236">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="60547-237">**RulePack id y ExactMatch id**: use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) para generar un GUID.</span><span class="sxs-lookup"><span data-stu-id="60547-237">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="60547-238">**Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="60547-238">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="60547-239">Debe proporcionar un nombre de origen de datos de un esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="60547-239">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="60547-240">**idMatch**: este campo señala al elemento principal para EDM.</span><span class="sxs-lookup"><span data-stu-id="60547-240">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="60547-241">Matches: especifica el campo que se usará en la búsqueda exacta.</span><span class="sxs-lookup"><span data-stu-id="60547-241">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="60547-242">Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="60547-242">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="60547-243">Classification: este campo especifica la coincidencia de tipo confidencial que desencadena la búsqueda de EDM.</span><span class="sxs-lookup"><span data-stu-id="60547-243">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="60547-244">Puede especificar el nombre o el GUID de una clasificación personalizada o integrada existente.</span><span class="sxs-lookup"><span data-stu-id="60547-244">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="60547-245">**Match:** este campo señala a la evidencia adicional que se encuentra cerca de idMatch.</span><span class="sxs-lookup"><span data-stu-id="60547-245">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="60547-246">Matches: se proporciona un nombre de campo en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="60547-246">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="60547-247">**Resource:** esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="60547-247">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="60547-248">idRef: se proporciona un GUID para Id. de ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="60547-248">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="60547-249">Nombres y descripciones: personalice según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="60547-249">Name & descriptions: customize as required.</span></span>

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

2. <span data-ttu-id="60547-250">Cargue el paquete de reglas ejecutando, uno a la vez, los siguientes cmdlets de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60547-250">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="60547-251">Ya tiene configurada la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="60547-251">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="60547-252">El siguiente paso es crear un hash para los datos confidenciales y luego cargarlo para indexarlo.</span><span class="sxs-lookup"><span data-stu-id="60547-252">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="60547-253">Recuerde del procedimiento anterior que nuestro esquema RegistrosPacientes define cinco campos para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="60547-253">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="60547-254">Nuestro paquete de reglas de ejemplo incluye esos campos y hace referencia al archivo de esquema de la base de datos (**edm.xml**), con un elemento *ExactMatch* por campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="60547-254">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="60547-255">Considere el siguiente elemento ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="60547-255">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="60547-256">En este ejemplo, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-256">In this example, note that:</span></span>

- <span data-ttu-id="60547-257">El nombre de dataStore hace referencia al archivo .csv que hemos creado anteriormente: **dataStore = "RegistrosPacientes"**.</span><span class="sxs-lookup"><span data-stu-id="60547-257">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="60547-258">El valor de idMatch hace referencia a un campo para la búsqueda que aparece en el archivo de esquema de la base de datos: **idMatch matches = "NSS"**.</span><span class="sxs-lookup"><span data-stu-id="60547-258">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="60547-259">El valor classification hace referencia a un tipo de información confidencial existente o personalizada: **classification = "Número de seguridad social de Estados Unidos (NSS)"**.</span><span class="sxs-lookup"><span data-stu-id="60547-259">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="60547-260">(En este caso, usamos el tipo de información confidencial existente del número de la seguridad social de Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="60547-260">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="60547-261">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="60547-261">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="60547-262">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="60547-262">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="60547-263">Editar el esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="60547-263">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="60547-264">Si quiere realizar cambios en el archivo **edm.xml**, como cambiar los campos que se usan para la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="60547-264">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="60547-265">Puede cambiar el esquema EDM y el archivo de datos para aprovechar la **coincidencia configurable**.</span><span class="sxs-lookup"><span data-stu-id="60547-265">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="60547-266">Cuando se configura, EDM omite las diferencias entre mayúsculas y minúsculas y otros delimitadores cuando evalúa un elemento.</span><span class="sxs-lookup"><span data-stu-id="60547-266">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="60547-267">Esto facilita la definición del esquema XML y los archivos de datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="60547-267">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="60547-268">Para obtener más información, consulte [Modificar el esquema de coincidencia de datos exacta para usar la coincidencia configurable](sit-modify-edm-schema-configurable-match.md).</span><span class="sxs-lookup"><span data-stu-id="60547-268">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="60547-269">Edite el archivo **edm.xml** (este es el archivo tratado en la sección [Definir el esquema](#define-the-schema-for-your-database-of-sensitive-information) de este artículo).</span><span class="sxs-lookup"><span data-stu-id="60547-269">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="60547-270">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="60547-270">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="60547-271">Para actualizar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="60547-271">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="60547-272">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-272">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="60547-273">Confirmar</span><span class="sxs-lookup"><span data-stu-id="60547-273">Confirm</span></span>
      >
      > <span data-ttu-id="60547-274">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="60547-274">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="60547-275">Se actualizará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="60547-275">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="60547-276">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="60547-276">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="60547-277">Si quiere que los cambios se realicen sin confirmación, en el paso 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="60547-277">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="60547-278">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="60547-278">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="60547-279">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="60547-279">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="60547-280">Eliminación del esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="60547-280">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="60547-281">(Según sea necesario) Si quiere quitar el esquema que está usando de la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="60547-281">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="60547-282">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="60547-282">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="60547-283">Ejecute los siguientes cmdlets de PowerShell y sustituya el nombre del almacén de datos "registros de pacientes" por el que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="60547-283">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="60547-284">Se le pedirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="60547-284">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="60547-285">Confirmar</span><span class="sxs-lookup"><span data-stu-id="60547-285">Confirm</span></span>
      >
      > <span data-ttu-id="60547-286">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="60547-286">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="60547-287">Se quitará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="60547-287">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="60547-288">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="60547-288">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="60547-289">Si quiere que los cambios se realicen sin confirmación, en el paso 2, use este cmdlet: Remove-DlpEdmSchema -Identity registrospacientes -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="60547-289">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="60547-290">Parte 2: Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="60547-290">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="60547-291">En esta fase, configurará una cuenta de usuario y un grupo de seguridad personalizado y configurará la herramienta de agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="60547-291">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="60547-292">Luego, usará la herramienta para aplicar el algoritmo hash con valor de sal a los datos confidenciales y, después, los cargará.</span><span class="sxs-lookup"><span data-stu-id="60547-292">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="60547-293">El algoritmo hash y la carga se pueden realizar con un equipo o puede separar el paso de hash del paso de carga para mayor seguridad.</span><span class="sxs-lookup"><span data-stu-id="60547-293">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="60547-294">Si desea aplicar un algoritmo hash y cargar desde un equipo, tendrá que hacerlo desde un equipo que pueda conectarse directamente a su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60547-294">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="60547-295">Esto requiere que los archivos de datos confidenciales de texto no cifrado se encuentren en el equipo para la aplicación del algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="60547-295">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="60547-296">Si no desea que se muestre el archivo de datos confidenciales de texto no cifrado, puede aplicar un algoritmo hash en un equipo en una ubicación segura y, a continuación, copiar el archivo hash y el archivo de sal en un equipo que pueda conectarse directamente a su espacio empresarial de Microsoft 365 para cargarlo.</span><span class="sxs-lookup"><span data-stu-id="60547-296">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="60547-297">En este escenario, necesitará el EDMUploadAgent en ambos equipos.</span><span class="sxs-lookup"><span data-stu-id="60547-297">In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60547-298">Si usó el esquema de coincidencia exacta de datos y el Asistente para el tipo de información confidencial con el fin de crear los archivos de esquema y de patrón, \**_debe_* descargar el esquema para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="60547-298">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you \**_must_* download the schema for this procedure.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="60547-299">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="60547-299">Prerequisites</span></span>

- <span data-ttu-id="60547-300">una cuenta profesional o educativa de Microsoft 365 que se agregará al grupo de seguridad de **EDM\_DataUploaders**</span><span class="sxs-lookup"><span data-stu-id="60547-300">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="60547-301">un equipo con Windows 10 o Windows Server 2016 con .NET versión 4.6.2 para ejecutar el EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="60547-301">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="60547-302">un directorio en el equipo de carga para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-302">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="60547-303">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="60547-303">EDMUploadAgent</span></span>
    - <span data-ttu-id="60547-304">el archivo de elementos confidenciales en formato CSV **RegistrosPacientes.csv** en nuestros ejemplos</span><span class="sxs-lookup"><span data-stu-id="60547-304">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="60547-305">los archivos hash y de sal de salida</span><span class="sxs-lookup"><span data-stu-id="60547-305">and the output hash and salt files</span></span>
    - <span data-ttu-id="60547-306">el nombre del almacén de datos del archivo **edm.xml** que para este ejemplo es `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="60547-306">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="60547-307">Si ha usado el [esquema de coincidencia exacta de datos y el Asistente para el tipo de información confidencial](sit-edm-wizard.md) entonces \**_debe_* _ descargarlo</span><span class="sxs-lookup"><span data-stu-id="60547-307">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you \**_must_* _ download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="60547-308">Configuración de la cuenta de usuario y del grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="60547-308">Set up the security group and user account</span></span>

1. <span data-ttu-id="60547-309">Como administrador global, vaya al Centro de administración mediante el [vínculo apropiado para su suscripción](#portal-links-for-your-subscription) y [cree un grupo de seguridad](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) llamado _\*EDM\_DataUploaders\*\*.</span><span class="sxs-lookup"><span data-stu-id="60547-309">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called _\*EDM\_DataUploaders\*\*.</span></span>

2. <span data-ttu-id="60547-310">Agregue uno o más usuarios al grupo de seguridad **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="60547-310">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="60547-311">(Estos usuarios administrarán la base de datos de información confidencial).</span><span class="sxs-lookup"><span data-stu-id="60547-311">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="60547-312">Crear un hash y cargar desde un equipo</span><span class="sxs-lookup"><span data-stu-id="60547-312">Hash and upload from one computer</span></span>

<span data-ttu-id="60547-313">Este equipo debe tener acceso directo a su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60547-313">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="60547-314">Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="60547-314">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="60547-315">De forma opcional, puede ejecutar una validación en el archivo CSV antes de cargarlo ejecutando lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60547-315">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="60547-316">Para más información sobre todos los parámetros admitidos de EdmUploadAgent.exe >, ejecute</span><span class="sxs-lookup"><span data-stu-id="60547-316">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="60547-317">Vínculos al agente de carga de EDM por tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="60547-317">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="60547-318">[Comercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): la mayoría de los clientes comerciales deben usarlo</span><span class="sxs-lookup"><span data-stu-id="60547-318">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="60547-319">[GCC alto](https://go.microsoft.com/fwlink/?linkid=2137521): está específicamente diseñado para los suscriptores de nube de administración pública de alta seguridad</span><span class="sxs-lookup"><span data-stu-id="60547-319">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="60547-320">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) : está específicamente diseñado para los clientes de la nube del Departamento de defensa de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="60547-320">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="60547-321">Cree un directorio de trabajo para EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="60547-321">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="60547-322">Por ejemplo: **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="60547-322">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="60547-323">Coloque el archivo **RegistrosPacientes.csv** dentro.</span><span class="sxs-lookup"><span data-stu-id="60547-323">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="60547-324">Descargue e instale el [Agente de carga de EDM](#links-to-edm-upload-agent-by-subscription-type) adecuado para su suscripción en el directorio que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="60547-324">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="60547-325">El EDMUploadAgent de los vínculos anteriores se ha actualizado para agregar automáticamente un valor de sal a los datos hash.</span><span class="sxs-lookup"><span data-stu-id="60547-325">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="60547-326">De forma alternativa, puede brindar su propio valor de sal.</span><span class="sxs-lookup"><span data-stu-id="60547-326">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="60547-327">Una vez que haya usado esta versión, no podrá usar la versión anterior de EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="60547-327">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="60547-328">Puede cargar datos con EDMUploadAgent en cualquier almacén de datos determinado solo dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="60547-328">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="60547-329">Para obtener una lista de los parámetros de comando compatibles, ejecute el agente sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="60547-329">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="60547-330">Por ejemplo, 'EdmUploadAgent.exe'.</span><span class="sxs-lookup"><span data-stu-id="60547-330">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="60547-331">Autorice el agente de carga de EDM, abra la ventana del Símbolo del sistema (como administrador), cambie al directorio **C:\EDM\Data** y, después, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="60547-331">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="60547-332">Inicie sesión con su cuenta profesional o educativa de Microsoft 365 que se ha agregado al grupo de seguridad de EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="60547-332">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="60547-333">La información de inquilino se extrae de la cuenta de usuario para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="60547-333">Your tenant information is extracted from the user account to make the connection.</span></span>

<span data-ttu-id="60547-334">OPCIONAL: Si usó el esquema de coincidencia exacta de datos y el Asistente para el tipo de información confidencial con el fin de crear los archivos de esquema y de patrón, ejecute el siguiente comando en una ventana de símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="60547-334">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="60547-335">Para crear un hash y cargar los datos confidenciales, ejecute el siguiente comando en la ventana del Símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="60547-335">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file]`

<span data-ttu-id="60547-336">Por ejemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="60547-336">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

<span data-ttu-id="60547-337">Esto agregará automáticamente un valor de sal generado de manera aleatoria al hash para una mayor seguridad.</span><span class="sxs-lookup"><span data-stu-id="60547-337">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="60547-338">De forma opcional, si quiere usar su propio valor de sal, agregue **/Salt <saltvalue>** al comando.</span><span class="sxs-lookup"><span data-stu-id="60547-338">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="60547-339">Este valor debe tener 64 caracteres de longitud y solo puede contener los caracteres a-z y 0-9.</span><span class="sxs-lookup"><span data-stu-id="60547-339">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="60547-340">Compruebe el estado de la carga al ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="60547-340">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="60547-341">Ejemplo: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="60547-341">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="60547-342">Verifique que el estado se encuentre en **ProcesamientoEnCurso**.</span><span class="sxs-lookup"><span data-stu-id="60547-342">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="60547-343">Verifique nuevamente cada pocos minutos hasta que el estado cambie a **Completado**.</span><span class="sxs-lookup"><span data-stu-id="60547-343">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="60547-344">Una vez que el estado se muestre como completado, los datos de EDM ya están listos para su uso.</span><span class="sxs-lookup"><span data-stu-id="60547-344">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="60547-345">Separe el hash y cargue</span><span class="sxs-lookup"><span data-stu-id="60547-345">Separate Hash and upload</span></span>

<span data-ttu-id="60547-346">Aplique el algoritmo hash en un equipo en un entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="60547-346">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="60547-347">OPCIONAL: Si usó el esquema de coincidencia exacta de datos y el Asistente para el tipo de información confidencial con el fin de crear los archivos de esquema y de patrón, ejecute el siguiente comando en una ventana de símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="60547-347">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="60547-348">Ejecute el siguiente comando en la ventana del Símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="60547-348">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

<span data-ttu-id="60547-349">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60547-349">For example:</span></span>

> <span data-ttu-id="60547-350">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="60547-350">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

<span data-ttu-id="60547-351">De este forma, se obtendrá un archivo con hash y un archivo de sal con estas extensiones si no ha especificado la opción **/Salt <saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="60547-351">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="60547-352">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="60547-352">.EdmHash</span></span>
- <span data-ttu-id="60547-353">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="60547-353">.EdmSalt</span></span>

2. <span data-ttu-id="60547-354">Copie estos archivos de forma segura al equipo que usará para cargar el archivo CSV de elementos confidenciales (RegistrosPacientes) en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="60547-354">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="60547-355">Para cargar los datos con hash, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="60547-355">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="60547-356">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60547-356">For example:</span></span>

> <span data-ttu-id="60547-357">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="60547-357">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="60547-358">Para comprobar que se hayan cargado los datos confidenciales, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="60547-358">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="60547-359">Verá una lista de almacenes de datos y la última vez que se actualizaron.</span><span class="sxs-lookup"><span data-stu-id="60547-359">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="60547-360">Si desea ver todos los datos cargados en una determinada tienda, ejecute el comando siguiente en un símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="60547-360">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="60547-361">Continúe con el proceso de configuración y programación para [actualizar la base de datos de información confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="60547-361">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="60547-362">En este momento, está listo para usar la clasificación basada en EDM con los servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="60547-362">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="60547-363">Por ejemplo, puede [configurar una directiva DLP con clasificación basada en EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="60547-363">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="60547-364">Actualizar la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="60547-364">Refreshing your sensitive information database</span></span>

<span data-ttu-id="60547-365">Puede actualizar la base de datos de información confidencial diariamente y la herramienta de carga de EDM puede volver a indexar los datos confidenciales y cargar de nuevo los datos indexados.</span><span class="sxs-lookup"><span data-stu-id="60547-365">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="60547-366">Determine el proceso y la frecuencia (diaria o semanal) para actualizar la base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="60547-366">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="60547-367">Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="60547-367">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="60547-368">Mantenga el mismo nombre de archivo y ubicación que usó cuando siguió los pasos descritos en [Crear un hash y cargar los datos confidenciales](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="60547-368">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="60547-369">Si no hay ningún cambio en la estructura (nombres de campo) del archivo .csv, no necesita realizar cambios en el archivo de esquema de la base de datos al actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="60547-369">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="60547-370">Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente.</span><span class="sxs-lookup"><span data-stu-id="60547-370">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="60547-371">Use el [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar los pasos 2 y 3 en el procedimiento [Hash y carga de los datos confidenciales](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="60547-371">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="60547-372">Puede programar tareas con varios métodos:</span><span class="sxs-lookup"><span data-stu-id="60547-372">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="60547-373">Método</span><span class="sxs-lookup"><span data-stu-id="60547-373">Method</span></span>             | <span data-ttu-id="60547-374">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="60547-374">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="60547-375">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60547-375">Windows PowerShell</span></span>     | <span data-ttu-id="60547-376">Consulte la documentación [TareasProgramadas](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo</span><span class="sxs-lookup"><span data-stu-id="60547-376">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="60547-377">API del Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="60547-377">Task Scheduler API</span></span>     | <span data-ttu-id="60547-378">Consulte la documentación del [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="60547-378">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="60547-379">Interfaz de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="60547-379">Windows user interface</span></span> | <span data-ttu-id="60547-380">En Windows, haga clic en **Inicio** y escriba Programador de tareas.</span><span class="sxs-lookup"><span data-stu-id="60547-380">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="60547-381">A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="60547-381">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="60547-382">Script de PowerShell de ejemplo para el Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="60547-382">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="60547-383">Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de creación de hash para los datos y cargar los datos con hash:</span><span class="sxs-lookup"><span data-stu-id="60547-383">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="60547-384">Para programar la creación del hash y cargar en un paso combinado</span><span class="sxs-lookup"><span data-stu-id="60547-384">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="60547-385">Para programar la creación del hash y cargar en pasos separados</span><span class="sxs-lookup"><span data-stu-id="60547-385">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="60547-386">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="60547-386">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="60547-387">Estas ubicaciones son compatibles con los tipos de información confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="60547-387">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="60547-388">DLP para Exchange Online (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="60547-388">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="60547-389">OneDrive para la Empresa (archivos)</span><span class="sxs-lookup"><span data-stu-id="60547-389">OneDrive for Business (files)</span></span>
- <span data-ttu-id="60547-390">Microsoft Teams (conversaciones)</span><span class="sxs-lookup"><span data-stu-id="60547-390">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="60547-391">DLP para SharePoint (archivos)</span><span class="sxs-lookup"><span data-stu-id="60547-391">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="60547-392">Directivas DLP para la seguridad de las aplicaciones en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="60547-392">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="60547-393">Los tipos de información confidencial de EDM para las siguientes situaciones están actualmente en desarrollo, pero todavía no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="60547-393">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="60547-394">Clasificación automática de las etiquetas de sensibilidad y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="60547-394">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="60547-395">Para crear una directiva DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="60547-395">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="60547-396">Vaya al Centro de seguridad y cumplimiento con el [vínculo adecuado para su suscripción](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="60547-396">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="60547-397">Seleccione **Directiva de prevención de pérdida de datos** \> **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="60547-397">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="60547-398">Elija **Crear una directiva** \> **Personalizado** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-398">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="60547-399">En la pestaña **Nombre de la directiva**, especifique un nombre y una descripción y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-399">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="60547-400">En la pestaña **Elegir ubicaciones**, haga clic en **Permitir elegir ubicaciones concretas** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-400">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="60547-401">En la columna **Estado**, seleccione **correo electrónico de Exchange, cuentas de OneDrive, conversación de equipos y mensaje de canal**, y después elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-401">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="60547-402">En la pestaña **Configuración de directiva**, elija **Usar la configuración avanzada** y luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-402">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="60547-403">Elija **+ Nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="60547-403">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="60547-404">En la sección **Nombre**, especifique un nombre y una descripción para la regla.</span><span class="sxs-lookup"><span data-stu-id="60547-404">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="60547-405">En la sección **Condiciones** en la lista **+ Agregar una condición**, elija **El contenido incluye tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="60547-405">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![El contenido incluye tipos de información confidencial](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="60547-407">Busque el tipo de información confidencial que creó al configurar el paquete de reglas y elija **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="60547-407">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="60547-408">Elija **Hecho**.</span><span class="sxs-lookup"><span data-stu-id="60547-408">Then choose **Done**.</span></span>

12. <span data-ttu-id="60547-409">Termine de seleccionar las opciones para la regla, como **Notificaciones de usuario**, **Invalidaciones de usuario**, **Informes de incidentes**, etc. y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="60547-409">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="60547-410">En la pestaña **Configuración de directiva**, revise las reglas y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-410">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="60547-411">Especifique si quiere activar la directiva inmediatamente, probarla o dejarla desactivada.</span><span class="sxs-lookup"><span data-stu-id="60547-411">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="60547-412">A continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60547-412">Then choose **Next**.</span></span>

15. <span data-ttu-id="60547-413">En la pestaña **Revisar la configuración**, revise la directiva.</span><span class="sxs-lookup"><span data-stu-id="60547-413">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="60547-414">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="60547-414">Make any needed changes.</span></span> <span data-ttu-id="60547-415">Cuando haya terminado, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="60547-415">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="60547-416">Espere aproximadamente una hora para que la nueva directiva DLP pase por el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="60547-416">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="60547-417">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="60547-417">Related articles</span></span>

- [<span data-ttu-id="60547-418">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="60547-418">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="60547-419">Tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="60547-419">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="60547-420">Información general de directivas DLP</span><span class="sxs-lookup"><span data-stu-id="60547-420">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="60547-421">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="60547-421">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="60547-422">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="60547-422">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="60547-423">Modificar esquema de coincidencia de datos exacto para usar la coincidencia configurable</span><span class="sxs-lookup"><span data-stu-id="60547-423">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)

