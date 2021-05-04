---
title: Modificar el esquema de coincidencia de datos exactos para usar la coincidencia configurable
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
description: Obtenga información acerca de cómo modificar un esquema de EDM para usar la coincidencia configurable.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114198"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="c1b7b-103">Modificar el esquema de coincidencia de datos exactos para usar la coincidencia configurable</span><span class="sxs-lookup"><span data-stu-id="c1b7b-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="c1b7b-104">La clasificación basada en la coincidencia de datos exactos le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="c1b7b-105">Cuando necesite permitir el uso de variantes de una cadena exacta, puede usar la *coincidencia configurable* para indicar a Microsoft 365 que omita mayúsculas y minúsculas y otros delimitadores.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c1b7b-106">Use este procedimiento para modificar un esquema EDM y un archivo de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="c1b7b-107">Desinstale **EdmUploadAgent.exe** del equipo que usa para conectarse a Microsoft 365 para propósitos de esquema de EDM y carga de archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="c1b7b-108">Descargue el archivo **EdmUploadAgent.exe** apropiado para su suscripción mediante los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="c1b7b-109">[Comercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639): la mayoría de los clientes comerciales deben usarlo</span><span class="sxs-lookup"><span data-stu-id="c1b7b-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="c1b7b-110">[GCC alto](https://go.microsoft.com/fwlink/?linkid=2137521): está específicamente diseñado para los suscriptores de nube de administración pública de alta seguridad</span><span class="sxs-lookup"><span data-stu-id="c1b7b-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="c1b7b-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) : está específicamente diseñado para los clientes de la nube del Departamento de Defensa de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="c1b7b-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="c1b7b-112">Autorice al agente de carga de EDM, abra la ventana del símbolo del sistema (como administrador) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="c1b7b-113">Si no tiene una copia actual del esquema existente, debe descargar una copia del esquema existente y ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="c1b7b-114">Personalice el esquema para que todas las columnas usen “caseInsensitive” y/o “ignoredDelimiters”.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="c1b7b-115">El valor predeterminado de "caseInsensitive" es "false" y de "ignoredDelimiters" es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="c1b7b-116">El tipo de información confidencial personalizado subyacente o el tipo de información confidencial integrado que se usa para detectar el patrón de regex general debe admitir la detección de las entradas de variantes que aparecen en ignoredDelimiters.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="c1b7b-117">Por ejemplo, el tipo de información confidencial integrado del número de la seguridad social de Estados Unidos (SSN) puede detectar variaciones en los datos que incluyen guiones, espacios o la falta de espacios entre los números agrupados que componen el SSN.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="c1b7b-118">Como resultado, solo los delimitadores que son relevantes para incluir en ignoredDelimiters de EDM para los datos SSN son: guion y espacio.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="c1b7b-119">Este es un esquema de ejemplo en el que se simula la coincidencia que no distingue mayúsculas de minúsculas creando las columnas adicionales necesarias para reconocer las variaciones de mayúsculas y minúsculas en los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="c1b7b-120">En el ejemplo anterior, las variantes de la columna `PolicyNumber` original ya no serán necesarias si se agregan tanto `caseInsensitive` como `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="c1b7b-121">Para actualizar este esquema para que EDM use la coincidencia configurable, utilice las marcas `caseInsensitive` y `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="c1b7b-122">Este es el aspecto que tiene:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="c1b7b-123">El indicador `ignoredDelimiters` admite cualquier carácter no alfanumérico. Aquí se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="c1b7b-124">\.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-124">\.</span></span>
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

<span data-ttu-id="c1b7b-125">El indicador `ignoredDelimiters` no es compatible con:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="c1b7b-126">caracteres 0-9</span><span class="sxs-lookup"><span data-stu-id="c1b7b-126">characters 0-9</span></span>
- <span data-ttu-id="c1b7b-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="c1b7b-127">A-Z</span></span>
- <span data-ttu-id="c1b7b-128">a-z</span><span class="sxs-lookup"><span data-stu-id="c1b7b-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="c1b7b-129">Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c1b7b-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="c1b7b-130">Si su organización ha configurado una [Clave de cliente de para Microsoft 365 en el nivel de inquilino (versión preliminar pública)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), la coincidencia de datos exacta hará que se use automáticamente su funcionalidad de cifrado.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="c1b7b-131">Esto solo está disponible para los inquilinos con licencia E5 en la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="c1b7b-132">Actualice el esquema ejecutando estos cmdlets uno por vez:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="c1b7b-133">Si es necesario, actualice el archivo de datos para que coincida con la nueva versión de esquema.</span><span class="sxs-lookup"><span data-stu-id="c1b7b-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="c1b7b-134">De forma opcional, puede ejecutar una validación en el archivo CSV antes de cargarlo ejecutando lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="c1b7b-135">Para más información sobre todos los parámetros admitidos de EdmUploadAgent.exe >, ejecute</span><span class="sxs-lookup"><span data-stu-id="c1b7b-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="c1b7b-136">Abra la ventana del símbolo del sistema (como administrador) y ejecute el siguiente comando para obtener el hash y cargar los datos confidenciales:</span><span class="sxs-lookup"><span data-stu-id="c1b7b-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="c1b7b-137">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1b7b-137">Related articles</span></span>

- <span data-ttu-id="c1b7b-138">[Crear un tipo de información confidencial personalizado con una clasificación basada en la coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="c1b7b-138">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="c1b7b-139">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="c1b7b-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="c1b7b-140">Tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="c1b7b-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="c1b7b-141">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="c1b7b-141">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="c1b7b-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c1b7b-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="c1b7b-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="c1b7b-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)