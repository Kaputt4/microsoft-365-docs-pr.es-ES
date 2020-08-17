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
ms.openlocfilehash: 699cea6aec6f11462aed0c08db98ca4620df519a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686564"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="b5bee-103">Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos</span><span class="sxs-lookup"><span data-stu-id="b5bee-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="b5bee-104">Los [tipos de información confidencial](custom-sensitive-info-types.md) se usan para ayudar a evitar el uso compartido accidental o inadecuado de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="b5bee-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="b5bee-105">Como administrador, puede usar el Centro de seguridad y cumplimiento o PowerShell para definir un tipo de información confidencial basado en patrones, evidencia (palabras clave como  *empleado*,  *insignia*,  *ID*, etc.), proximidad de caracteres (la similitud de la evidencia y los caracteres en un patrón determinado) y niveles de confianza.</span><span class="sxs-lookup"><span data-stu-id="b5bee-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="b5bee-106">Estos tipos de información confidencial satisfacen las necesidades de negocio para muchas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="b5bee-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="b5bee-107">Pero, ¿qué pasa si quiere un tipo de información confidencial que use valores de datos exactos, en lugar de coincidir solo con patrones genéricos?</span><span class="sxs-lookup"><span data-stu-id="b5bee-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="b5bee-108">Con la clasificación basada en coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizado que está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="b5bee-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="b5bee-109">ser dinámico y actualizable;</span><span class="sxs-lookup"><span data-stu-id="b5bee-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="b5bee-110">ser más escalable;</span><span class="sxs-lookup"><span data-stu-id="b5bee-110">be more scalable;</span></span>
- <span data-ttu-id="b5bee-111">generar menos falsos positivos;</span><span class="sxs-lookup"><span data-stu-id="b5bee-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="b5bee-112">funcionar con datos confidenciales estructurados;</span><span class="sxs-lookup"><span data-stu-id="b5bee-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="b5bee-113">trabajar con información confidencial de forma más segura; y</span><span class="sxs-lookup"><span data-stu-id="b5bee-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="b5bee-114">usarse con varios servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5bee-114">be used with several Microsoft cloud services.</span></span>

![Clasificación basada en EDM](../media/EDMClassification.png)

<span data-ttu-id="b5bee-116">La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="b5bee-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="b5bee-117">La base de datos puede ser actualizada diaria o semanalmente, y puede contener hasta 100 millones de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="b5bee-118">Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables.</span><span class="sxs-lookup"><span data-stu-id="b5bee-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="b5bee-119">Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) o [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="b5bee-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="b5bee-120">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="b5bee-120">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="b5bee-121">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="b5bee-121">Chinese (simplified)</span></span>
> - <span data-ttu-id="b5bee-122">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="b5bee-122">Chinese (traditional)</span></span>
> - <span data-ttu-id="b5bee-123">Coreano</span><span class="sxs-lookup"><span data-stu-id="b5bee-123">Korean</span></span>
> - <span data-ttu-id="b5bee-124">Japonés</span><span class="sxs-lookup"><span data-stu-id="b5bee-124">Japanese</span></span>
> 
><span data-ttu-id="b5bee-125">Esta vista previa solo se encuentra en la nube comercial y la implementación está limitada a:</span><span class="sxs-lookup"><span data-stu-id="b5bee-125">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="b5bee-126">Japón</span><span class="sxs-lookup"><span data-stu-id="b5bee-126">Japan</span></span>
> - <span data-ttu-id="b5bee-127">Corea</span><span class="sxs-lookup"><span data-stu-id="b5bee-127">Korea</span></span>
> - <span data-ttu-id="b5bee-128">China</span><span class="sxs-lookup"><span data-stu-id="b5bee-128">China</span></span>
> - <span data-ttu-id="b5bee-129">RAE de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="b5bee-129">Hong Kong</span></span>
> - <span data-ttu-id="b5bee-130">RAE de Macao</span><span class="sxs-lookup"><span data-stu-id="b5bee-130">Macau</span></span>
> - <span data-ttu-id="b5bee-131">Taiwán</span><span class="sxs-lookup"><span data-stu-id="b5bee-131">Taiwan</span></span>
>
><span data-ttu-id="b5bee-132">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="b5bee-132">This support is available for sensitive information types.</span></span> <span data-ttu-id="b5bee-133">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="b5bee-133">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="b5bee-134">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="b5bee-134">Required licenses and permissions</span></span>

<span data-ttu-id="b5bee-135">Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5bee-135">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="b5bee-136">Para obtener más información acerca de los permisos de DLP, vea [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="b5bee-136">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="b5bee-137">La clasificación basada en EDM se incluye en estas suscripciones</span><span class="sxs-lookup"><span data-stu-id="b5bee-137">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="b5bee-138">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="b5bee-138">Office 365 E5</span></span>
- <span data-ttu-id="b5bee-139">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b5bee-139">Microsoft 365 E5</span></span>
- <span data-ttu-id="b5bee-140">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b5bee-140">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="b5bee-141">Gobierno y protección de información de Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="b5bee-141">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="b5bee-142">Vínculos del portal para la suscripción</span><span class="sxs-lookup"><span data-stu-id="b5bee-142">Portal links for your subscription</span></span>


|<span data-ttu-id="b5bee-143">Portal</span><span class="sxs-lookup"><span data-stu-id="b5bee-143">Portal</span></span>  |<span data-ttu-id="b5bee-144">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="b5bee-144">World Wide/GCC</span></span>  |<span data-ttu-id="b5bee-145">GCC-High</span><span class="sxs-lookup"><span data-stu-id="b5bee-145">GCC-High</span></span>  |<span data-ttu-id="b5bee-146">DOD</span><span class="sxs-lookup"><span data-stu-id="b5bee-146">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b5bee-147">Office SCC</span><span class="sxs-lookup"><span data-stu-id="b5bee-147">Office SCC</span></span>     |  <span data-ttu-id="b5bee-148">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="b5bee-148">protection.office.com</span></span>       |<span data-ttu-id="b5bee-149">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="b5bee-149">scc.office365.us</span></span>         |<span data-ttu-id="b5bee-150">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="b5bee-150">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="b5bee-151">Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5bee-151">Microsoft 365 Security center</span></span>     |<span data-ttu-id="b5bee-152">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b5bee-152">security.microsoft.com</span></span>         |<span data-ttu-id="b5bee-153">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="b5bee-153">security.microsoft.us</span></span>         |<span data-ttu-id="b5bee-154">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="b5bee-154">security.apps.mil</span></span>|
|<span data-ttu-id="b5bee-155">Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5bee-155">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="b5bee-156">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b5bee-156">compliance.microsoft.com</span></span>         |<span data-ttu-id="b5bee-157">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="b5bee-157">compliance.microsoft.us</span></span>         |<span data-ttu-id="b5bee-158">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="b5bee-158">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="b5bee-159">El flujo de trabajo de un vistazo</span><span class="sxs-lookup"><span data-stu-id="b5bee-159">The work flow at a glance</span></span>

|<span data-ttu-id="b5bee-160">Fase</span><span class="sxs-lookup"><span data-stu-id="b5bee-160">Phase</span></span>  |<span data-ttu-id="b5bee-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5bee-161">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="b5bee-162">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-162">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="b5bee-163">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="b5bee-163">(As needed)</span></span><br/><span data-ttu-id="b5bee-164">- [Editar el esquema de la base de datos](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="b5bee-164">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="b5bee-165">- [Quitar el esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="b5bee-165">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="b5bee-166">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="b5bee-166">- Read access to the sensitive data</span></span><br/><span data-ttu-id="b5bee-167">- Esquema de la base de datos en formato XML (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="b5bee-167">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="b5bee-168">- Paquete de reglas en formato XML (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="b5bee-168">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="b5bee-169">- Permisos de administrador para el Centro de seguridad y cumplimiento (con PowerShell)</span><span class="sxs-lookup"><span data-stu-id="b5bee-169">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="b5bee-170">Parte 2: Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="b5bee-170">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="b5bee-171">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="b5bee-171">(As needed)</span></span><br/>[<span data-ttu-id="b5bee-172">Actualizar los datos</span><span class="sxs-lookup"><span data-stu-id="b5bee-172">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="b5bee-173">- Cuenta de usuario y de grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="b5bee-173">- Custom security group and user account</span></span><br/><span data-ttu-id="b5bee-174">- Acceso de administrador local en el equipo con el agente de carga EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-174">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="b5bee-175">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="b5bee-175">- Read access to the sensitive data</span></span><br/><span data-ttu-id="b5bee-176">- Procesar y programar la actualización de los datos</span><span class="sxs-lookup"><span data-stu-id="b5bee-176">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="b5bee-177">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5bee-177">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="b5bee-178">- Suscripción a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="b5bee-178">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="b5bee-179">- Característica de clasificación basada en EDM habilitada</span><span class="sxs-lookup"><span data-stu-id="b5bee-179">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="b5bee-180">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-180">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="b5bee-181">La configuración de la clasificación basada en EDM implica guardar los datos confidenciales en formato .csv, definir un esquema para la base de datos de información confidencial, crear un paquete de reglas y cargar el paquete de reglas y el esquema.</span><span class="sxs-lookup"><span data-stu-id="b5bee-181">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="b5bee-182">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="b5bee-182">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="b5bee-183">Identifique la información confidencial que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="b5bee-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="b5bee-184">Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="b5bee-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="b5bee-185">El archivo de datos puede incluir un máximo de:</span><span class="sxs-lookup"><span data-stu-id="b5bee-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="b5bee-186">Hasta 100 millones de filas de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="b5bee-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="b5bee-187">Hasta 32 columnas (campos) por origen de datos</span><span class="sxs-lookup"><span data-stu-id="b5bee-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="b5bee-188">Hasta 5 columnas (campos) marcadas como utilizables en búsquedas</span><span class="sxs-lookup"><span data-stu-id="b5bee-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="b5bee-189">Estructure los datos confidenciales en el archivo .csv de forma que la primera fila incluya los nombres de los campos que se usan para la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="b5bee-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="b5bee-190">En el archivo .csv, puede que tenga nombres de campo, como "NSS", "FechaNacimiento", "Nombre", "Apellido", etc.</span><span class="sxs-lookup"><span data-stu-id="b5bee-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="b5bee-191">Tenga en cuenta que los encabezados de columna no pueden incluir espacios o guiones bajos en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="b5bee-191">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="b5bee-192">Por ejemplo, nuestro archivo .csv se llama  *RegistrosPacientes.csv* e incluye las columnas  *IdPaciente*,  *NEM*,  *Apellidos*,  *Nombre*,  *NSS*, etc.</span><span class="sxs-lookup"><span data-stu-id="b5bee-192">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="b5bee-193">Defina el esquema de la base de datos de información confidencial en formato XML (similar al siguiente ejemplo).</span><span class="sxs-lookup"><span data-stu-id="b5bee-193">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="b5bee-194">Nombre este archivo de esquema  **edm.xml** y configúrelo para que por cada columna de la base de datos haya una línea que use la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b5bee-194">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="b5bee-195">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="b5bee-195">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="b5bee-196">Use nombres de columna para los valores *Nombre de campo* .</span><span class="sxs-lookup"><span data-stu-id="b5bee-196">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="b5bee-197">Use *searchable="true"* para los campos que quiere que se puedan buscar, hasta un máximo de 5 campos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-197">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="b5bee-198">Debe designar un mínimo de un campo como utilizable para búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b5bee-198">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="b5bee-199">Por ejemplo, el siguiente archivo XML define el esquema para una base de datos de registros de pacientes con cinco campos especificados para la búsqueda: *PatientID*, *MRN*,  *SSN*, *Phone* y *DOB*.</span><span class="sxs-lookup"><span data-stu-id="b5bee-199">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="b5bee-200">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="b5bee-200">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="b5bee-201">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b5bee-201">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="b5bee-202">Para cargar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b5bee-202">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="b5bee-203">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5bee-203">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="b5bee-204">Confirmar</span><span class="sxs-lookup"><span data-stu-id="b5bee-204">Confirm</span></span>
      >
      > <span data-ttu-id="b5bee-205">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="b5bee-205">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="b5bee-206">Se importará el nuevo esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="b5bee-206">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="b5bee-207">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="b5bee-207">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="b5bee-208">Si quiere que los cambios se realicen sin confirmación, en el paso 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="b5bee-208">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="b5bee-209">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-209">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="b5bee-210">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="b5bee-210">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="b5bee-211">Ahora que se ha definido el esquema de la base de datos de información confidencial, el siguiente paso es configurar un paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="b5bee-211">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="b5bee-212">Vaya a la sección [Configurar un paquete de reglas](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="b5bee-212">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="b5bee-213">Editar el esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-213">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="b5bee-214">Si quiere realizar cambios en el archivo **edm.xml**, como cambiar los campos que se usan para la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b5bee-214">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="b5bee-215">Edite el archivo **edm.xml** (este es el archivo tratado en la sección  [Definir el esquema](#define-the-schema-for-your-database-of-sensitive-information)  de este artículo).</span><span class="sxs-lookup"><span data-stu-id="b5bee-215">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="b5bee-216">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b5bee-216">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="b5bee-217">Para actualizar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b5bee-217">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="b5bee-218">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5bee-218">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="b5bee-219">Confirmar</span><span class="sxs-lookup"><span data-stu-id="b5bee-219">Confirm</span></span>
      >
      > <span data-ttu-id="b5bee-220">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="b5bee-220">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="b5bee-221">Se actualizará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="b5bee-221">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="b5bee-222">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="b5bee-222">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="b5bee-223">Si quiere que los cambios se realicen sin confirmación, en el paso 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="b5bee-223">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="b5bee-224">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-224">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="b5bee-225">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="b5bee-225">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="b5bee-226">Eliminación del esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-226">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="b5bee-227">(Según sea necesario) Si quiere quitar el esquema que está usando de la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b5bee-227">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="b5bee-228">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b5bee-228">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="b5bee-229">Ejecute los siguientes cmdlets de PowerShell y sustituya el nombre del almacén de datos "registrospacientes" por el que quiere quitar:</span><span class="sxs-lookup"><span data-stu-id="b5bee-229">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="b5bee-230">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5bee-230">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="b5bee-231">Confirmar</span><span class="sxs-lookup"><span data-stu-id="b5bee-231">Confirm</span></span>
      >
      > <span data-ttu-id="b5bee-232">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="b5bee-232">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="b5bee-233">Se quitará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="b5bee-233">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="b5bee-234">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="b5bee-234">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="b5bee-235">Si quiere que los cambios se realicen sin confirmación, en el paso 2, use este cmdlet: Remove-DlpEdmSchema -Identity registrospacientes -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="b5bee-235">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="b5bee-236">Configuración de un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="b5bee-236">Set up a rule package</span></span>

1. <span data-ttu-id="b5bee-237">Cree un paquete de reglas en formato XML (con codificación Unicode), similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5bee-237">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="b5bee-238">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="b5bee-238">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="b5bee-239">Cuando configure el paquete de reglas, asegúrese de hacer referencia correctamente al archivo .csv y al archivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-239">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="b5bee-240">Puede copiar, modificar y usar nuestro ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b5bee-240">You can copy, modify, and use our example.</span></span> <span data-ttu-id="b5bee-241">En este XML de ejemplo, debe personalizar los siguientes campos para crear el tipo confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="b5bee-241">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="b5bee-242">**RulePack id y ExactMatch id**: use  [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  para generar un GUID.</span><span class="sxs-lookup"><span data-stu-id="b5bee-242">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="b5bee-243">**Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b5bee-243">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="b5bee-244">Debe proporcionar un nombre de origen de datos de un esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="b5bee-244">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="b5bee-245">**idMatch**: este campo señala al elemento principal para EDM.</span><span class="sxs-lookup"><span data-stu-id="b5bee-245">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="b5bee-246">Matches: especifica el campo que se usará en la búsqueda exacta.</span><span class="sxs-lookup"><span data-stu-id="b5bee-246">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="b5bee-247">Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="b5bee-247">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="b5bee-248">Classification: este campo especifica la coincidencia de tipo confidencial que desencadena la búsqueda de EDM.</span><span class="sxs-lookup"><span data-stu-id="b5bee-248">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="b5bee-249">Puede especificar el nombre o el GUID de una clasificación personalizada o integrada existente.</span><span class="sxs-lookup"><span data-stu-id="b5bee-249">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="b5bee-250">**Match:** este campo señala a la evidencia adicional que se encuentra cerca de idMatch.</span><span class="sxs-lookup"><span data-stu-id="b5bee-250">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="b5bee-251">Matches: se proporciona un nombre de campo en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="b5bee-251">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="b5bee-252">**Resource:** esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="b5bee-252">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="b5bee-253">idRef: se proporciona un GUID para Id. de ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="b5bee-253">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="b5bee-254">Nombres y descripciones: personalice según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b5bee-254">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="b5bee-255">Cargue el paquete de reglas ejecutando, uno a la vez, los siguientes cmdlets de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b5bee-255">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="b5bee-256">Ya tiene configurada la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="b5bee-256">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="b5bee-257">El siguiente paso es crear un hash para los datos confidenciales y luego cargarlo para indexarlo.</span><span class="sxs-lookup"><span data-stu-id="b5bee-257">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="b5bee-258">Recuerde del procedimiento anterior que nuestro esquema RegistrosPacientes define cinco campos para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="b5bee-258">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="b5bee-259">Nuestro paquete de reglas de ejemplo incluye esos campos y hace referencia al archivo de esquema de la base de datos (**edm.xml**), con un elemento  *ExactMatch*  por campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b5bee-259">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="b5bee-260">Considere el siguiente elemento ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="b5bee-260">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="b5bee-261">En este ejemplo, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5bee-261">In this example, note the following:</span></span>

- <span data-ttu-id="b5bee-262">El nombre de dataStore hace referencia al archivo .csv que hemos creado anteriormente: **dataStore = "RegistrosPacientes"**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-262">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="b5bee-263">El valor de idMatch hace referencia a un campo para la búsqueda que aparece en el archivo de esquema de la base de datos: **idMatch matches = "NSS"**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-263">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="b5bee-264">El valor classification hace referencia a un tipo de información confidencial existente o personalizada: **classification = "Número de seguridad social de Estados Unidos (NSS)"**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-264">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="b5bee-265">(En este caso, usamos el tipo de información confidencial existente del número de la seguridad social de Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="b5bee-265">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="b5bee-266">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-266">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="b5bee-267">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="b5bee-267">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="b5bee-268">Parte 2: Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="b5bee-268">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="b5bee-269">Durante esta fase, configurará una cuenta de usuario y un grupo de seguridad personalizado y configurará la herramienta de agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="b5bee-269">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="b5bee-270">Luego, use la herramienta para crear un hash de los datos confidenciales y cargar los datos con hash para que puedan ser indexados.</span><span class="sxs-lookup"><span data-stu-id="b5bee-270">Then, you use the tool to hash the sensitive data, and upload the hashed data so it can be indexed.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="b5bee-271">Configuración de la cuenta de usuario y del grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="b5bee-271">Set up the security group and user account</span></span>

1. <span data-ttu-id="b5bee-272">Como administrador global, vaya al centro de administración mediante el [vínculo apropiado para su suscripción](#portal-links-for-your-subscription) y  [cree un grupo de seguridad](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) llamado **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-272">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="b5bee-273">Agregue uno o más usuarios al grupo de seguridad **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="b5bee-273">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="b5bee-274">(Estos usuarios administrarán la base de datos de información confidencial).</span><span class="sxs-lookup"><span data-stu-id="b5bee-274">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="b5bee-275">Asegúrese de que cada usuario que administra la información confidencial es un administrador local en el equipo que usa para el agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="b5bee-275">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="b5bee-276">Configuración del agente de carga de EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-276">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="b5bee-277">Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad **EDM\_DataUploaders** y un administrador local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b5bee-277">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="b5bee-278">Vínculos al agente de carga de EDM por tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="b5bee-278">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="b5bee-279">Comercial + GCC</span><span class="sxs-lookup"><span data-stu-id="b5bee-279">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="b5bee-280">GCC-High</span><span class="sxs-lookup"><span data-stu-id="b5bee-280">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="b5bee-281">DoD</span><span class="sxs-lookup"><span data-stu-id="b5bee-281">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="b5bee-282">Descargue e instale el [agente de carga del EDM adecuado](#links-to-edm-upload-agent-by-subscription-type) para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b5bee-282">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="b5bee-283">De forma predeterminada, la ubicación de la instalación debe ser  **C:\\Archivos de programa\\Microsoft\\EdmUploadAgent**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-283">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

   > [!TIP]
   > <span data-ttu-id="b5bee-284">Para obtener una lista de los parámetros de comando compatibles, ejecute el agente sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-284">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="b5bee-285">Por ejemplo, 'EdmUploadAgent.exe'.</span><span class="sxs-lookup"><span data-stu-id="b5bee-285">For example 'EdmUploadAgent.exe'.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b5bee-286">Puede cargar los datos con EDMUploadAgent en cualquier almacén de datos determinado dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="b5bee-286">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="b5bee-287">Para autorizar al agente de carga de EDM, abra el símbolo de sistema de Windows (como administrador) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b5bee-287">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="b5bee-288">Inicie sesión con su cuenta profesional o educativa de Office 365 que se ha agregado al grupo de seguridad EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="b5bee-288">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="b5bee-289">El siguiente paso es usar el Agente de carga EDM para crear un hash para los datos confidenciales y luego cargar los datos con hash.</span><span class="sxs-lookup"><span data-stu-id="b5bee-289">The next step is to use the EDM Upload Agent to hash the sensitive data, and then upload the hashed data.</span></span>

#### <a name="hash-and-upload-the-sensitive-data"></a><span data-ttu-id="b5bee-290">Crear un hash y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="b5bee-290">Hash and upload the sensitive data</span></span>

<span data-ttu-id="b5bee-291">Guarde el archivo de datos confidenciales (recuerde que nuestro ejemplo es **RegistrosPacientes.csv**) en la unidad local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b5bee-291">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="b5bee-292">(Hemos guardado nuestro archivo  **RegistrosPacientes.csv**  de ejemplo en  **C:\\Edm\\Data**).</span><span class="sxs-lookup"><span data-stu-id="b5bee-292">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="b5bee-293">Para crear un hash y cargar los datos confidenciales, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="b5bee-293">To hash and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="b5bee-294">Ejemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\RegistrosPacientes.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="b5bee-294">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="b5bee-295">Para separar y ejecutar el hash para los datos confidenciales en un entorno aislado, ejecute el algoritmo de hash y cargue los pasos por separado.</span><span class="sxs-lookup"><span data-stu-id="b5bee-295">To separate and execute the hashing of sensitive data in an isolated environment, execute the hashing and upload steps separately.</span></span>

<span data-ttu-id="b5bee-296">Para crear un hash para los datos confidenciales, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="b5bee-296">To hash the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="b5bee-297">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5bee-297">For example:</span></span>

> <span data-ttu-id="b5bee-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="b5bee-298">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="b5bee-299">Para cargar los datos con hash, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="b5bee-299">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="b5bee-300">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5bee-300">For example:</span></span>

> <span data-ttu-id="b5bee-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="b5bee-301">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="b5bee-302">Para comprobar que se hayan cargado los datos confidenciales, ejecute el siguiente comando en el Símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="b5bee-302">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="b5bee-303">Verá una lista de almacenes de datos y la última vez que se actualizaron.</span><span class="sxs-lookup"><span data-stu-id="b5bee-303">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="b5bee-304">Si desea ver todos los datos cargados en una determinada tienda, ejecute el comando siguiente en un símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="b5bee-304">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="b5bee-305">Continúe con el proceso de configuración y programación para  [Actualizar la base de datos de información confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="b5bee-305">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="b5bee-306">En este momento, está listo para usar la clasificación basada en EDM con los servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5bee-306">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="b5bee-307">Por ejemplo, puede [configurar una directiva DLP con clasificación basada en EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="b5bee-307">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="b5bee-308">Actualizar la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="b5bee-308">Refreshing your sensitive information database</span></span>

<span data-ttu-id="b5bee-309">Puede actualizar su base de datos de información confidencial de forma diaria o semanal, y la Herramienta de carga EDM puede volver a crear un hash para los datos confidenciales y luego volver a cargar los datos con hash.</span><span class="sxs-lookup"><span data-stu-id="b5bee-309">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can re-hash the sensitive data and then reupload the hashed data.</span></span>

1. <span data-ttu-id="b5bee-310">Determine el proceso y la frecuencia (diaria o semanal) para actualizar la base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="b5bee-310">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="b5bee-311">Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="b5bee-311">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="b5bee-312">Mantenga el mismo nombre de archivo y ubicación que usó cuando siguió los pasos descritos en  [Crear un hash y cargar los datos confidenciales](#hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="b5bee-312">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="b5bee-313">Si no hay ningún cambio en la estructura (nombres de campo) del archivo .csv, no necesita realizar cambios en el archivo de esquema de la base de datos al actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-313">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="b5bee-314">Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente.</span><span class="sxs-lookup"><span data-stu-id="b5bee-314">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="b5bee-315">Use el [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar los pasos 2 y 3 en el procedimiento [de](#hash-and-upload-the-sensitive-data)Crear un hash y cargar los datos confidenciales .</span><span class="sxs-lookup"><span data-stu-id="b5bee-315">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="b5bee-316">Puede programar tareas con varios métodos:</span><span class="sxs-lookup"><span data-stu-id="b5bee-316">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="b5bee-317">Método</span><span class="sxs-lookup"><span data-stu-id="b5bee-317">Method</span></span>             | <span data-ttu-id="b5bee-318">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="b5bee-318">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="b5bee-319">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5bee-319">Windows PowerShell</span></span>     | <span data-ttu-id="b5bee-320">Consulte la documentación [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo</span><span class="sxs-lookup"><span data-stu-id="b5bee-320">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="b5bee-321">API del Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="b5bee-321">Task Scheduler API</span></span>     | <span data-ttu-id="b5bee-322">Consulte la documentación del [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="b5bee-322">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="b5bee-323">Interfaz de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="b5bee-323">Windows user interface</span></span> | <span data-ttu-id="b5bee-324">En Windows, haga clic en **Inicio** y escriba programador de tareas.</span><span class="sxs-lookup"><span data-stu-id="b5bee-324">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="b5bee-325">A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-325">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="b5bee-326">Script de PowerShell de ejemplo para el Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="b5bee-326">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="b5bee-327">Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de creación de hash para los datos y cargar los datos con hash:</span><span class="sxs-lookup"><span data-stu-id="b5bee-327">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="b5bee-328">Para programar la creación del hash y cargar en un paso combinado</span><span class="sxs-lookup"><span data-stu-id="b5bee-328">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="b5bee-329">Para programar la creación del hash y cargar en pasos separados</span><span class="sxs-lookup"><span data-stu-id="b5bee-329">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="b5bee-330">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5bee-330">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="b5bee-331">Estas ubicaciones son compatibles con los tipos de información confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="b5bee-331">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="b5bee-332">DLP para Exchange Online (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="b5bee-332">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="b5bee-333">OneDrive para la Empresa (archivos)</span><span class="sxs-lookup"><span data-stu-id="b5bee-333">OneDrive for Business (files)</span></span>
- <span data-ttu-id="b5bee-334">Microsoft Teams (conversaciones)</span><span class="sxs-lookup"><span data-stu-id="b5bee-334">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="b5bee-335">DLP para SharePoint (archivos)</span><span class="sxs-lookup"><span data-stu-id="b5bee-335">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="b5bee-336">Directivas DLP para la seguridad de las aplicaciones en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5bee-336">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="b5bee-337">Los tipos de información confidencial de EDM para las siguientes situaciones están actualmente en desarrollo, pero todavía no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="b5bee-337">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="b5bee-338">Clasificación automática de las etiquetas de sensibilidad y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="b5bee-338">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="b5bee-339">Para crear una directiva DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="b5bee-339">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="b5bee-340">Vaya al Centro de seguridad y cumplimiento con el [vínculo adecuado para su suscripción](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="b5bee-340">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="b5bee-341">Haga clic en **Prevención de pérdida de datos** \> **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-341">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="b5bee-342">Elija **Crear una directiva** \> **Personalizada** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-342">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="b5bee-343">En la pestaña **Nombre de la directiva** , especifique un nombre y una descripción y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-343">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="b5bee-344">En la pestaña **Elegir ubicaciones** , haga clic en **Permitir elegir ubicaciones concretas** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-344">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="b5bee-345">En la columna **Estado** , seleccione **correo electrónico de Exchange, cuentas de OneDrive, conversación de equipos y mensaje de canal** , y después elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-345">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="b5bee-346">En la pestaña **Configuración de directiva** , elija **Usar la configuración avanzada** y luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-346">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="b5bee-347">Elija **+ Nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-347">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="b5bee-348">En la sección **Nombre** , especifique un nombre y una descripción para la regla.</span><span class="sxs-lookup"><span data-stu-id="b5bee-348">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="b5bee-349">En la sección **Condiciones** en la lista **+ Agregar una condición,** elija **El contenido incluye tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-349">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![El contenido incluye tipos de información confidencial](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="b5bee-351">Busque el tipo de información confidencial que creó al configurar el paquete de reglas y elija **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-351">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="b5bee-352">Luego elija **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-352">Then choose **Done**.</span></span>

12. <span data-ttu-id="b5bee-353">Termine de seleccionar las opciones para la regla, como **Notificaciones de usuario**, **Invalidaciones de usuario**, **Informes de incidentes**, etc. y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-353">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="b5bee-354">En la pestaña **Configuración de directiva,** revise las reglas y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-354">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="b5bee-355">Especifique si quiere activar la directiva inmediatamente, probarla o dejarla desactivada.</span><span class="sxs-lookup"><span data-stu-id="b5bee-355">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="b5bee-356">Luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-356">Then choose **Next**.</span></span>

15. <span data-ttu-id="b5bee-357">En la pestaña **Revisar la configuración,** , revise la directiva.</span><span class="sxs-lookup"><span data-stu-id="b5bee-357">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="b5bee-358">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="b5bee-358">Make any needed changes.</span></span> <span data-ttu-id="b5bee-359">Cuando haya terminado, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b5bee-359">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="b5bee-360">Espere aproximadamente una hora para que la nueva directiva DLP pase por el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="b5bee-360">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b5bee-361">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="b5bee-361">Related articles</span></span>

- [<span data-ttu-id="b5bee-362">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="b5bee-362">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="b5bee-363">Tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="b5bee-363">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="b5bee-364">Información general de directivas DLP</span><span class="sxs-lookup"><span data-stu-id="b5bee-364">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="b5bee-365">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b5bee-365">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="b5bee-366">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="b5bee-366">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)

