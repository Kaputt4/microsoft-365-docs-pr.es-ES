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
ms.openlocfilehash: 957bde2112d5a0cf0c20bb28a8341b6f04118fc8
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536325"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="435bc-103">Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos</span><span class="sxs-lookup"><span data-stu-id="435bc-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="435bc-104">Los [tipos de información confidencial](custom-sensitive-info-types.md) se usan para ayudar a evitar el uso compartido accidental o inadecuado de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="435bc-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="435bc-105">Como administrador, puede usar el Centro de seguridad y cumplimiento o PowerShell para definir un tipo de información confidencial basado en patrones, evidencia (palabras clave como  *empleado*,  *insignia*,  *ID*, etc.), proximidad de caracteres (la similitud de la evidencia y los caracteres en un patrón determinado) y niveles de confianza.</span><span class="sxs-lookup"><span data-stu-id="435bc-105">As an administrator, you can use the Security & Compliance Center or PowerShell to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="435bc-106">Estos tipos de información confidencial satisfacen las necesidades de negocio para muchas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="435bc-106">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="435bc-107">Pero, ¿qué pasa si quiere un tipo de información confidencial que use valores de datos exactos, en lugar de coincidir solo con patrones genéricos?</span><span class="sxs-lookup"><span data-stu-id="435bc-107">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="435bc-108">Con la clasificación basada en coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizado que está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="435bc-108">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="435bc-109">ser dinámico y actualizable;</span><span class="sxs-lookup"><span data-stu-id="435bc-109">be dynamic and refreshable;</span></span>
- <span data-ttu-id="435bc-110">ser más escalable;</span><span class="sxs-lookup"><span data-stu-id="435bc-110">be more scalable;</span></span>
- <span data-ttu-id="435bc-111">generar menos falsos positivos;</span><span class="sxs-lookup"><span data-stu-id="435bc-111">result in fewer false-positives;</span></span>
- <span data-ttu-id="435bc-112">funcionar con datos confidenciales estructurados;</span><span class="sxs-lookup"><span data-stu-id="435bc-112">work with structured sensitive data;</span></span>
- <span data-ttu-id="435bc-113">trabajar con información confidencial de forma más segura; y</span><span class="sxs-lookup"><span data-stu-id="435bc-113">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="435bc-114">usarse con varios servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="435bc-114">be used with several Microsoft cloud services.</span></span>

![Clasificación basada en EDM](../media/EDMClassification.png)

<span data-ttu-id="435bc-116">La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="435bc-116">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="435bc-117">La base de datos puede ser actualizada diaria o semanalmente, y puede contener hasta 100 millones de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="435bc-117">The database can be refreshed daily or weekly, and it can contain up to 100 million rows of data.</span></span> <span data-ttu-id="435bc-118">Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables.</span><span class="sxs-lookup"><span data-stu-id="435bc-118">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="435bc-119">Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) o [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="435bc-119">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="435bc-120">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="435bc-120">Required licenses and permissions</span></span>

<span data-ttu-id="435bc-121">Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="435bc-121">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="435bc-122">Para obtener más información acerca de los permisos de DLP, vea [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="435bc-122">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="435bc-123">La clasificación basada en EDM se incluye en estas suscripciones</span><span class="sxs-lookup"><span data-stu-id="435bc-123">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="435bc-124">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="435bc-124">Office 365 E5</span></span>
- <span data-ttu-id="435bc-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="435bc-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="435bc-126">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="435bc-126">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="435bc-127">Gobierno y protección de información de Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="435bc-127">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="435bc-128">Vínculos del portal para la suscripción</span><span class="sxs-lookup"><span data-stu-id="435bc-128">Portal links for your subscription</span></span>


|<span data-ttu-id="435bc-129">Portal</span><span class="sxs-lookup"><span data-stu-id="435bc-129">Portal</span></span>  |<span data-ttu-id="435bc-130">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="435bc-130">World Wide/GCC</span></span>  |<span data-ttu-id="435bc-131">GCC-High</span><span class="sxs-lookup"><span data-stu-id="435bc-131">GCC-High</span></span>  |<span data-ttu-id="435bc-132">DOD</span><span class="sxs-lookup"><span data-stu-id="435bc-132">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="435bc-133">Office SCC</span><span class="sxs-lookup"><span data-stu-id="435bc-133">Office SCC</span></span>     |  <span data-ttu-id="435bc-134">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="435bc-134">protection.office.com</span></span>       |<span data-ttu-id="435bc-135">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="435bc-135">scc.office365.us</span></span>         |<span data-ttu-id="435bc-136">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="435bc-136">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="435bc-137">Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="435bc-137">Microsoft 365 Security center</span></span>     |<span data-ttu-id="435bc-138">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="435bc-138">security.microsoft.com</span></span>         |<span data-ttu-id="435bc-139">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="435bc-139">security.microsoft.us</span></span>         |<span data-ttu-id="435bc-140">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="435bc-140">security.apps.mil</span></span>|
|<span data-ttu-id="435bc-141">Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="435bc-141">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="435bc-142">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="435bc-142">compliance.microsoft.com</span></span>         |<span data-ttu-id="435bc-143">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="435bc-143">compliance.microsoft.us</span></span>         |<span data-ttu-id="435bc-144">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="435bc-144">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="435bc-145">El flujo de trabajo de un vistazo</span><span class="sxs-lookup"><span data-stu-id="435bc-145">The work flow at a glance</span></span>

|<span data-ttu-id="435bc-146">Fase</span><span class="sxs-lookup"><span data-stu-id="435bc-146">Phase</span></span>  |<span data-ttu-id="435bc-147">Requisitos</span><span class="sxs-lookup"><span data-stu-id="435bc-147">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="435bc-148">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-148">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="435bc-149">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="435bc-149">(As needed)</span></span><br/><span data-ttu-id="435bc-150">- [Editar el esquema de la base de datos](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="435bc-150">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="435bc-151">- [Quitar el esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="435bc-151">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="435bc-152">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="435bc-152">- Read access to the sensitive data</span></span><br/><span data-ttu-id="435bc-153">- Esquema base de datos en formato .xml (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="435bc-153">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="435bc-154">- Paquete de reglas en formato .xml (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="435bc-154">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="435bc-155">- Permisos de administrador para el Centro de seguridad y cumplimiento (con PowerShell)</span><span class="sxs-lookup"><span data-stu-id="435bc-155">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="435bc-156">Parte 2: Indizar y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="435bc-156">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="435bc-157">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="435bc-157">(As needed)</span></span><br/>[<span data-ttu-id="435bc-158">Actualizar los datos</span><span class="sxs-lookup"><span data-stu-id="435bc-158">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="435bc-159">- Cuenta de usuario y de grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="435bc-159">- Custom security group and user account</span></span><br/><span data-ttu-id="435bc-160">- Acceso de administrador local en el equipo con el agente de carga EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-160">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="435bc-161">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="435bc-161">- Read access to the sensitive data</span></span><br/><span data-ttu-id="435bc-162">- Procesar y programar la actualización de los datos</span><span class="sxs-lookup"><span data-stu-id="435bc-162">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="435bc-163">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="435bc-163">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="435bc-164">- Suscripción a Microsoft 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="435bc-164">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="435bc-165">- Característica de clasificación basada en EDM habilitada</span><span class="sxs-lookup"><span data-stu-id="435bc-165">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="435bc-166">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-166">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="435bc-167">La configuración de la clasificación basada en EDM implica guardar los datos confidenciales en formato .csv, definir un esquema para la base de datos de información confidencial, crear un paquete de reglas y cargar el paquete de reglas y el esquema.</span><span class="sxs-lookup"><span data-stu-id="435bc-167">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="435bc-168">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="435bc-168">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="435bc-169">Identifique la información confidencial que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="435bc-169">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="435bc-170">Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="435bc-170">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="435bc-171">El archivo de datos puede incluir un máximo de:</span><span class="sxs-lookup"><span data-stu-id="435bc-171">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="435bc-172">Hasta 100 millones de filas de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="435bc-172">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="435bc-173">Hasta 32 columnas (campos) por origen de datos</span><span class="sxs-lookup"><span data-stu-id="435bc-173">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="435bc-174">Hasta 5 columnas (campos) marcadas como utilizables en búsquedas</span><span class="sxs-lookup"><span data-stu-id="435bc-174">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="435bc-175">Estructure los datos confidenciales en el archivo .csv de forma que la primera fila incluya los nombres de los campos que se usan para la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="435bc-175">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="435bc-176">En el archivo .csv, puede que tenga nombres de campo, como "NSS", "FechaNacimiento", "Nombre", "Apellido", etc.</span><span class="sxs-lookup"><span data-stu-id="435bc-176">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="435bc-177">Tenga en cuenta que los encabezados de columna no pueden incluir espacios o guiones bajos en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="435bc-177">Please note that column headers can't include spaces or underscores in their names.</span></span> <span data-ttu-id="435bc-178">Por ejemplo, nuestro archivo .csv se llama  *RegistrosPacientes.csv* e incluye las columnas  *IdPaciente*,  *NEM*,  *Apellidos*,  *Nombre*,  *NSS*, etc.</span><span class="sxs-lookup"><span data-stu-id="435bc-178">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="435bc-179">Defina el esquema de la base de datos de información confidencial en formato .xml (similar al ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="435bc-179">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="435bc-180">Nombre este archivo de esquema  **edm.xml** y configúrelo para que por cada columna de la base de datos haya una línea que use la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="435bc-180">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="435bc-181">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="435bc-181">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="435bc-182">Use nombres de columna para los valores *Nombre de campo* .</span><span class="sxs-lookup"><span data-stu-id="435bc-182">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="435bc-183">Use *searchable="true"* para los campos que quiere que se puedan buscar, hasta un máximo de 5 campos.</span><span class="sxs-lookup"><span data-stu-id="435bc-183">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="435bc-184">Debe designar un mínimo de un campo como utilizable para búsqueda.</span><span class="sxs-lookup"><span data-stu-id="435bc-184">You must designate a minimum of one field as searchable.</span></span>

      <span data-ttu-id="435bc-185">Por ejemplo, el siguiente archivo .xml define el esquema para una base de datos de registros de pacientes, con cinco campos especificados para la búsqueda: *IdPaciente*, *NEM*,  *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="435bc-185">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="435bc-186">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="435bc-186">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="435bc-187">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="435bc-187">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="435bc-188">Para cargar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="435bc-188">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="435bc-189">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="435bc-189">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="435bc-190">Confirmar</span><span class="sxs-lookup"><span data-stu-id="435bc-190">Confirm</span></span>
      >
      > <span data-ttu-id="435bc-191">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="435bc-191">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="435bc-192">Se importará el nuevo esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="435bc-192">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="435bc-193">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="435bc-193">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="435bc-194">Si quiere que los cambios se realicen sin confirmación, en el paso 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="435bc-194">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="435bc-195">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="435bc-195">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="435bc-196">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="435bc-196">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="435bc-197">Ahora que se ha definido el esquema de la base de datos de información confidencial, el siguiente paso es configurar un paquete de reglas.</span><span class="sxs-lookup"><span data-stu-id="435bc-197">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="435bc-198">Vaya a la sección [Configurar un paquete de reglas](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="435bc-198">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="435bc-199">Editar el esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-199">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="435bc-200">Si quiere realizar cambios en el archivo **edm.xml**, como cambiar los campos que se usan para la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="435bc-200">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="435bc-201">Edite el archivo **edm.xml** (este es el archivo tratado en la sección  [Definir el esquema](#define-the-schema-for-your-database-of-sensitive-information)  de este artículo).</span><span class="sxs-lookup"><span data-stu-id="435bc-201">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="435bc-202">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="435bc-202">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="435bc-203">Para actualizar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="435bc-203">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="435bc-204">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="435bc-204">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="435bc-205">Confirmar</span><span class="sxs-lookup"><span data-stu-id="435bc-205">Confirm</span></span>
      >
      > <span data-ttu-id="435bc-206">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="435bc-206">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="435bc-207">Se actualizará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="435bc-207">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="435bc-208">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="435bc-208">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="435bc-209">Si quiere que los cambios se realicen sin confirmación, en el paso 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="435bc-209">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="435bc-210">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="435bc-210">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="435bc-211">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="435bc-211">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="435bc-212">Eliminación del esquema de la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-212">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="435bc-213">(Según sea necesario) Si quiere quitar el esquema que está usando de la clasificación basada en EDM, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="435bc-213">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="435bc-214">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="435bc-214">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="435bc-215">Ejecute los siguientes cmdlets de PowerShell y sustituya el nombre del almacén de datos "registrospacientes" por el que quiere quitar:</span><span class="sxs-lookup"><span data-stu-id="435bc-215">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="435bc-216">Se le pedirá que confirme lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="435bc-216">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="435bc-217">Confirmar</span><span class="sxs-lookup"><span data-stu-id="435bc-217">Confirm</span></span>
      >
      > <span data-ttu-id="435bc-218">¿Está seguro de que desea realizar esta acción?</span><span class="sxs-lookup"><span data-stu-id="435bc-218">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="435bc-219">Se quitará el esquema EDM para el almacén de datos "registrospacientes".</span><span class="sxs-lookup"><span data-stu-id="435bc-219">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="435bc-220">¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):</span><span class="sxs-lookup"><span data-stu-id="435bc-220">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="435bc-221">Si quiere que los cambios se realicen sin confirmación, en el paso 2, use este cmdlet: Remove-DlpEdmSchema -Identity registrospacientes -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="435bc-221">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="435bc-222">Configuración de un paquete de reglas</span><span class="sxs-lookup"><span data-stu-id="435bc-222">Set up a rule package</span></span>

1. <span data-ttu-id="435bc-223">Cree un paquete de reglas en formato .xml (con codificación Unicode), similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="435bc-223">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="435bc-224">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="435bc-224">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="435bc-225">Cuando configure el paquete de reglas, asegúrese de hacer referencia correctamente al archivo .csv y al archivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="435bc-225">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="435bc-226">Puede copiar, modificar y usar nuestro ejemplo.</span><span class="sxs-lookup"><span data-stu-id="435bc-226">You can copy, modify, and use our example.</span></span> <span data-ttu-id="435bc-227">En este XML de ejemplo, debe personalizar los siguientes campos para crear el tipo confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="435bc-227">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="435bc-228">**RulePack id y ExactMatch id**: use  [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  para generar un GUID.</span><span class="sxs-lookup"><span data-stu-id="435bc-228">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="435bc-229">**Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="435bc-229">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="435bc-230">Debe proporcionar un nombre de origen de datos de un esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="435bc-230">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="435bc-231">**idMatch**: este campo señala al elemento principal para EDM.</span><span class="sxs-lookup"><span data-stu-id="435bc-231">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="435bc-232">Matches: especifica el campo que se usará en la búsqueda exacta.</span><span class="sxs-lookup"><span data-stu-id="435bc-232">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="435bc-233">Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="435bc-233">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="435bc-234">Classification: este campo especifica la coincidencia de tipo confidencial que desencadena la búsqueda de EDM.</span><span class="sxs-lookup"><span data-stu-id="435bc-234">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="435bc-235">Puede especificar el nombre o el GUID de una clasificación personalizada o integrada existente.</span><span class="sxs-lookup"><span data-stu-id="435bc-235">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="435bc-236">**Match:** este campo señala a la evidencia adicional que se encuentra cerca de idMatch.</span><span class="sxs-lookup"><span data-stu-id="435bc-236">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="435bc-237">Matches: se proporciona un nombre de campo en el esquema EDM para DataStore.</span><span class="sxs-lookup"><span data-stu-id="435bc-237">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="435bc-238">**Resource:** esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="435bc-238">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="435bc-239">idRef: se proporciona un GUID para Id. de ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="435bc-239">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="435bc-240">Nombres y descripciones: personalice según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="435bc-240">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="435bc-241">Cargue el paquete de reglas ejecutando, uno a la vez, los siguientes cmdlets de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="435bc-241">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="435bc-242">Ya tiene configurada la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="435bc-242">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="435bc-243">El siguiente paso es indexar los datos confidenciales y luego cargar los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="435bc-243">The next step is to index the sensitive data, and then upload the indexed data.</span></span>

<span data-ttu-id="435bc-244">Recuerde del procedimiento anterior que nuestro esquema RegistrosPacientes define cinco campos para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="435bc-244">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="435bc-245">Nuestro paquete de reglas de ejemplo incluye esos campos y hace referencia al archivo de esquema de la base de datos (**edm.xml**), con un elemento  *ExactMatch*  por campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="435bc-245">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="435bc-246">Considere el siguiente elemento ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="435bc-246">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="435bc-247">En este ejemplo, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="435bc-247">In this example, note the following:</span></span>

- <span data-ttu-id="435bc-248">El nombre de dataStore hace referencia al archivo .csv que hemos creado anteriormente: **dataStore = "RegistrosPacientes"**.</span><span class="sxs-lookup"><span data-stu-id="435bc-248">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="435bc-249">El valor de idMatch hace referencia a un campo para la búsqueda que aparece en el archivo de esquema de la base de datos: **idMatch matches = "NSS"**.</span><span class="sxs-lookup"><span data-stu-id="435bc-249">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="435bc-250">El valor classification hace referencia a un tipo de información confidencial existente o personalizada: **classification = "Número de seguridad social de Estados Unidos (NSS)"**.</span><span class="sxs-lookup"><span data-stu-id="435bc-250">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="435bc-251">(En este caso, usamos el tipo de información confidencial existente del número de la seguridad social de Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="435bc-251">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="435bc-252">La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="435bc-252">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="435bc-253">La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.</span><span class="sxs-lookup"><span data-stu-id="435bc-253">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="435bc-254">Parte 2: Indizar y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="435bc-254">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="435bc-255">Durante esta fase, configurará una cuenta de usuario y un grupo de seguridad personalizado y configurará la herramienta de agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="435bc-255">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="435bc-256">Después, usará la herramienta para indexar los datos confidenciales y luego cargar los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="435bc-256">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="435bc-257">Configuración de la cuenta de usuario y del grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="435bc-257">Set up the security group and user account</span></span>

1. <span data-ttu-id="435bc-258">Como administrador global, vaya al centro de administración mediante el [vínculo apropiado para su suscripción](#portal-links-for-your-subscription) y  [cree un grupo de seguridad](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) llamado **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="435bc-258">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="435bc-259">Agregue uno o más usuarios al grupo de seguridad **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="435bc-259">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="435bc-260">(Estos usuarios administrarán la base de datos de información confidencial).</span><span class="sxs-lookup"><span data-stu-id="435bc-260">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="435bc-261">Asegúrese de que cada usuario que administra la información confidencial es un administrador local en el equipo que usa para el agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="435bc-261">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="435bc-262">Configuración del agente de carga de EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-262">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="435bc-263">Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad **EDM\_DataUploaders** y un administrador local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="435bc-263">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="435bc-264">Vínculos al agente de carga de EDM por tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="435bc-264">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="435bc-265">Comercial + GCC</span><span class="sxs-lookup"><span data-stu-id="435bc-265">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="435bc-266">GCC-High</span><span class="sxs-lookup"><span data-stu-id="435bc-266">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="435bc-267">DoD</span><span class="sxs-lookup"><span data-stu-id="435bc-267">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="435bc-268">Descargue e instale el [agente de carga del EDM adecuado](#links-to-edm-upload-agent-by-subscription-type) para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="435bc-268">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription.</span></span> <span data-ttu-id="435bc-269">De forma predeterminada, la ubicación de la instalación debe ser  **C:\\Archivos de programa\\Microsoft\\EdmUploadAgent**.</span><span class="sxs-lookup"><span data-stu-id="435bc-269">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

> [!TIP]
> <span data-ttu-id="435bc-270">Para obtener una lista de los parámetros de comando compatibles, ejecute el agente sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="435bc-270">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="435bc-271">Por ejemplo, 'EdmUploadAgent.exe'.</span><span class="sxs-lookup"><span data-stu-id="435bc-271">For example 'EdmUploadAgent.exe'.</span></span>

> [!NOTE]
> <span data-ttu-id="435bc-272">Puede cargar los datos con EDMUploadAgent en cualquier almacén de datos determinado dos veces al día.</span><span class="sxs-lookup"><span data-stu-id="435bc-272">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

2. <span data-ttu-id="435bc-273">Para autorizar al agente de carga de EDM, abra el símbolo de sistema de Windows (como administrador) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="435bc-273">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="435bc-274">Inicie sesión con su cuenta profesional o educativa de Office 365 que se ha agregado al grupo de seguridad EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="435bc-274">Sign in with your work or school account for Office 365 that was added to the EDM_DataUploaders security group.</span></span>

<span data-ttu-id="435bc-275">El siguiente paso es usar el agente de carga de EDM para indexar los datos confidenciales y luego cargar los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="435bc-275">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

#### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="435bc-276">Indización y carga de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="435bc-276">Index and upload the sensitive data</span></span>

<span data-ttu-id="435bc-277">Guarde el archivo de datos confidenciales (recuerde que nuestro ejemplo es **RegistrosPacientes.csv**) en la unidad local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="435bc-277">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="435bc-278">(Hemos guardado nuestro archivo  **RegistrosPacientes.csv**  de ejemplo en  **C:\\Edm\\Data**).</span><span class="sxs-lookup"><span data-stu-id="435bc-278">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="435bc-279">Para indizar y cargar los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:</span><span class="sxs-lookup"><span data-stu-id="435bc-279">To index and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="435bc-280">Ejemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\RegistrosPacientes.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="435bc-280">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="435bc-281">Para separar y ejecutar el índice de datos confidenciales en un entorno aislado, ejecute el índice y cargue los pasos por separado.</span><span class="sxs-lookup"><span data-stu-id="435bc-281">To separate and execute index of sensitive data in an isolated environment, execute index and upload steps separately.</span></span>

<span data-ttu-id="435bc-282">Para indizar los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:</span><span class="sxs-lookup"><span data-stu-id="435bc-282">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="435bc-283">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="435bc-283">For example:</span></span>

> <span data-ttu-id="435bc-284">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="435bc-284">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="435bc-285">Para cargar los datos indizados, ejecute el siguiente comando en el símbolo de Windows:</span><span class="sxs-lookup"><span data-stu-id="435bc-285">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="435bc-286">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="435bc-286">For example:</span></span>

> <span data-ttu-id="435bc-287">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="435bc-287">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>

<span data-ttu-id="435bc-288">Para comprobar que se han cargado los datos confidenciales, ejecute el siguiente comando en el símbolo de sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="435bc-288">To verify that your sensitive data has been uploaded, run the following command in Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="435bc-289">Verá una lista de almacenes de datos y la última vez que se actualizaron.</span><span class="sxs-lookup"><span data-stu-id="435bc-289">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="435bc-290">Si desea ver todos los datos cargados en una determinada tienda, ejecute el comando siguiente en un símbolo del sistema de Windows:</span><span class="sxs-lookup"><span data-stu-id="435bc-290">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="435bc-291">Continúe con el proceso de configuración y programación para  [Actualizar la base de datos de información confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="435bc-291">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="435bc-292">En este momento, está listo para usar la clasificación basada en EDM con los servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="435bc-292">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="435bc-293">Por ejemplo, puede [configurar una directiva DLP con clasificación basada en EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="435bc-293">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="435bc-294">Actualizar la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="435bc-294">Refreshing your sensitive information database</span></span>

<span data-ttu-id="435bc-295">Puede actualizar la base de datos de información confidencial de forma diaria o semanal, la herramienta de carga de EDM puede volver a indizar los datos confidenciales y cargar de nuevo los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="435bc-295">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="435bc-296">Determine el proceso y la frecuencia (diaria o semanal) para actualizar la base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="435bc-296">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="435bc-297">Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="435bc-297">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="435bc-298">Mantenga el mismo nombre de archivo y la ubicación que usó cuando siguió los pasos descritos en [Indización y carga de datos confidenciales](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="435bc-298">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="435bc-299">Si no hay ningún cambio en la estructura (nombres de campo) del archivo .csv, no necesita realizar cambios en el archivo de esquema de la base de datos al actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="435bc-299">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="435bc-300">Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente.</span><span class="sxs-lookup"><span data-stu-id="435bc-300">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="435bc-301">Use el [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar los pasos 2 y 3 en el procedimiento [Indización y carga de datos confidenciales](#index-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="435bc-301">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="435bc-302">Puede programar tareas con varios métodos:</span><span class="sxs-lookup"><span data-stu-id="435bc-302">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="435bc-303">**Método**</span><span class="sxs-lookup"><span data-stu-id="435bc-303">**Method**</span></span>             | <span data-ttu-id="435bc-304">**Qué hacer**</span><span class="sxs-lookup"><span data-stu-id="435bc-304">**What to do**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                     |
      | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
      | <span data-ttu-id="435bc-305">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="435bc-305">Windows PowerShell</span></span>     | <span data-ttu-id="435bc-306">Consulte la documentación [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo</span><span class="sxs-lookup"><span data-stu-id="435bc-306">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="435bc-307">API del Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="435bc-307">Task Scheduler API</span></span>     | <span data-ttu-id="435bc-308">Consulte la documentación del [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="435bc-308">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="435bc-309">Interfaz de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="435bc-309">Windows user interface</span></span> | <span data-ttu-id="435bc-310">En Windows, haga clic en **Inicio** y escriba programador de tareas.</span><span class="sxs-lookup"><span data-stu-id="435bc-310">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="435bc-311">A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="435bc-311">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="435bc-312">Script de PowerShell de ejemplo para el Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="435bc-312">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="435bc-313">Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de indización de datos y carga de los datos indizados:</span><span class="sxs-lookup"><span data-stu-id="435bc-313">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a><span data-ttu-id="435bc-314">Para programar el índice y la carga en un paso combinado</span><span class="sxs-lookup"><span data-stu-id="435bc-314">To schedule index and upload in a combined step</span></span>

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

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a><span data-ttu-id="435bc-315">Para programar el índice y la carga en pasos separados</span><span class="sxs-lookup"><span data-stu-id="435bc-315">To schedule index and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="435bc-316">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="435bc-316">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="435bc-317">Estas ubicaciones son compatibles con los tipos de información confidencial de EDM:</span><span class="sxs-lookup"><span data-stu-id="435bc-317">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="435bc-318">DLP para Exchange Online (correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="435bc-318">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="435bc-319">OneDrive para la Empresa (archivos)</span><span class="sxs-lookup"><span data-stu-id="435bc-319">OneDrive for Business (files)</span></span>
- <span data-ttu-id="435bc-320">Microsoft Teams (conversaciones)</span><span class="sxs-lookup"><span data-stu-id="435bc-320">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="435bc-321">DLP para SharePoint (archivos)</span><span class="sxs-lookup"><span data-stu-id="435bc-321">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="435bc-322">Directivas DLP para la seguridad de las aplicaciones en la nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="435bc-322">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="435bc-323">Los tipos de información confidencial de EDM para las siguientes situaciones están actualmente en desarrollo, pero todavía no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="435bc-323">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="435bc-324">Clasificación automática de las etiquetas de sensibilidad y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="435bc-324">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="435bc-325">Para crear una directiva DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="435bc-325">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="435bc-326">Vaya al Centro de seguridad y cumplimiento con el [vínculo adecuado para su suscripción](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="435bc-326">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="435bc-327">Haga clic en **Prevención de pérdida de datos** \> **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="435bc-327">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="435bc-328">Elija **Crear una directiva** \> **Personalizada** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-328">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="435bc-329">En la pestaña **Nombre de la directiva** , especifique un nombre y una descripción y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-329">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="435bc-330">En la pestaña **Elegir ubicaciones** , haga clic en **Permitir elegir ubicaciones concretas** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-330">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="435bc-331">En la columna **Estado** , seleccione **correo electrónico de Exchange, cuentas de OneDrive, conversación de equipos y mensaje de canal** , y después elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-331">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="435bc-332">En la pestaña **Configuración de directiva** , elija **Usar la configuración avanzada** y luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-332">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="435bc-333">Elija **+ Nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="435bc-333">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="435bc-334">En la sección **Nombre** , especifique un nombre y una descripción para la regla.</span><span class="sxs-lookup"><span data-stu-id="435bc-334">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="435bc-335">En la sección **Condiciones** en la lista **+ Agregar una condición,** elija **El contenido incluye tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="435bc-335">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![El contenido incluye tipos de información confidencial](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="435bc-337">Busque el tipo de información confidencial que creó al configurar el paquete de reglas y elija **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="435bc-337">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="435bc-338">Luego elija **Listo**.</span><span class="sxs-lookup"><span data-stu-id="435bc-338">Then choose **Done**.</span></span>

12. <span data-ttu-id="435bc-339">Termine de seleccionar las opciones para la regla, como **Notificaciones de usuario**, **Invalidaciones de usuario**, **Informes de incidentes**, etc. y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="435bc-339">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="435bc-340">En la pestaña **Configuración de directiva,** revise las reglas y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-340">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="435bc-341">Especifique si quiere activar la directiva inmediatamente, probarla o dejarla desactivada.</span><span class="sxs-lookup"><span data-stu-id="435bc-341">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="435bc-342">Luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="435bc-342">Then choose **Next**.</span></span>

15. <span data-ttu-id="435bc-343">En la pestaña **Revisar la configuración,** , revise la directiva.</span><span class="sxs-lookup"><span data-stu-id="435bc-343">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="435bc-344">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="435bc-344">Make any needed changes.</span></span> <span data-ttu-id="435bc-345">Cuando haya terminado, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="435bc-345">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="435bc-346">Espere aproximadamente una hora para que la nueva directiva DLP pase por el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="435bc-346">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="435bc-347">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="435bc-347">Related articles</span></span>

- [<span data-ttu-id="435bc-348">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="435bc-348">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="435bc-349">Tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="435bc-349">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="435bc-350">Información general de directivas DLP</span><span class="sxs-lookup"><span data-stu-id="435bc-350">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="435bc-351">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="435bc-351">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="435bc-352">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="435bc-352">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema?view=exchange-ps)
- <span data-ttu-id="435bc-353">[Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="435bc-353">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
