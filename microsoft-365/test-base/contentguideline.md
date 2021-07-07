---
title: Directrices del paquete de prueba
description: Revisar las directrices sobre el paquete de prueba
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323048"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="ae925-103">Directrices del paquete de prueba</span><span class="sxs-lookup"><span data-stu-id="ae925-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="ae925-104">1. Referencia a scripts</span><span class="sxs-lookup"><span data-stu-id="ae925-104">1.   Script referencing</span></span>

<span data-ttu-id="ae925-105">Al cargar un archivo .zip en el portal, descomprimimos todo el contenido de ese archivo en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="ae925-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="ae925-106">No es necesario escribir ningún código para realizar esta operación inicial de descomprimir.</span><span class="sxs-lookup"><span data-stu-id="ae925-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="ae925-107">También puede hacer referencia a cualquier archivo dentro del .zip mediante la ruta de acceso relativa al archivo zip cargado.</span><span class="sxs-lookup"><span data-stu-id="ae925-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="ae925-108">En el ejemplo siguiente, se muestra cómo puede hacer referencia a los archivos binarios o scripts desde el campo de entrada en la pestaña Tareas. El texto en azul debe especificarse en el **campo Ruta** de acceso script sin **las comillas.**</span><span class="sxs-lookup"><span data-stu-id="ae925-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="ae925-109">Es importante que conozca el contenido del archivo zip antes de cargarlo.</span><span class="sxs-lookup"><span data-stu-id="ae925-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="ae925-110">A menudo, al comprimir una carpeta, el equipo local creará una carpeta principal debajo del archivo zip.</span><span class="sxs-lookup"><span data-stu-id="ae925-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="ae925-111">En este caso, la referencia será como se muestra en negrita **a** continuación:</span><span class="sxs-lookup"><span data-stu-id="ae925-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="ae925-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="ae925-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="ae925-113">ScriptX.ps1: **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ae925-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="ae925-114">Script.ps1: **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ae925-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="ae925-115">Otras veces, el archivo zip puede tener los archivos o el contenido justo debajo de él, es decir, no hay carpeta de 2nd level:</span><span class="sxs-lookup"><span data-stu-id="ae925-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="ae925-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="ae925-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="ae925-117">ScriptX.ps1: **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ae925-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="ae925-118">Script.ps1: **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="ae925-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="ae925-119">2. Ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="ae925-119">2.   Script execution</span></span>

<span data-ttu-id="ae925-120">**Pruebas de salida:** El paquete de aplicación debe contener al menos tres scripts de PowerShell que ejecuten la instalación, el inicio y el cierre desatendidos de la aplicación y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="ae925-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="ae925-121">Cada script debe controlar la comprobación de sus propios requisitos previos, validarlo correctamente y limpiar después de sí mismo (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="ae925-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="ae925-122">**Pruebas funcionales:** El paquete de aplicación debe contener al menos un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae925-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="ae925-123">Cuando se proporciona más de un script, los scripts se ejecutan en secuencia de carga y un error en un script determinado impedirá la ejecución de scripts posteriores.</span><span class="sxs-lookup"><span data-stu-id="ae925-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="ae925-124">Requisitos de script</span><span class="sxs-lookup"><span data-stu-id="ae925-124">Script requirements</span></span>

<span data-ttu-id="ae925-125">• PowerShell versión 5.1+</span><span class="sxs-lookup"><span data-stu-id="ae925-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="ae925-126">• Ejecución desatendida</span><span class="sxs-lookup"><span data-stu-id="ae925-126">•   Unattended execution</span></span>    

<span data-ttu-id="ae925-127">• Código de devolución de error</span><span class="sxs-lookup"><span data-stu-id="ae925-127">•   Error return code</span></span>               

<span data-ttu-id="ae925-128">• Validar el éxito</span><span class="sxs-lookup"><span data-stu-id="ae925-128">•   Validate success</span></span>            

<span data-ttu-id="ae925-129">• Registro en una carpeta de registro específica del script</span><span class="sxs-lookup"><span data-stu-id="ae925-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="ae925-130">Cada script debe ejecutarse completamente desatendido para ejecutarse correctamente en la canalización de prueba.</span><span class="sxs-lookup"><span data-stu-id="ae925-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="ae925-131">Los scripts deben devolver "0" al finalizar correctamente y un código de error distinto de cero si se produce algún error durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae925-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="ae925-132">Cada script debe validar que se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae925-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="ae925-133">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae925-133">E.g.</span></span> <span data-ttu-id="ae925-134">el script de instalación debe comprobar la existencia de determinados archivos binarios o claves del Registro en el sistema, después de que el binario del instalador termine de ejecutarse para garantizar con un grado razonable de confianza que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae925-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="ae925-135">Esto es necesario para diagnosticar correctamente dónde se producen errores durante una ejecución de prueba, por ejemplo, no se puede instalar la aplicación correctamente en lugar de no poder iniciarla.</span><span class="sxs-lookup"><span data-stu-id="ae925-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="ae925-136">**Evite lo siguiente:** Los scripts no deben reiniciar el equipo, si es necesario reiniciarlo, especifique esto durante la carga de los scripts.</span><span class="sxs-lookup"><span data-stu-id="ae925-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="ae925-137">3. Colección de registros</span><span class="sxs-lookup"><span data-stu-id="ae925-137">3.   Log collection</span></span>

<span data-ttu-id="ae925-138">Cada script debe generar los registros que genere en una carpeta denominada ```logs``` .</span><span class="sxs-lookup"><span data-stu-id="ae925-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="ae925-139">Todas las carpetas del directorio denominado ```logs``` se copiarán y se presentarán para su descarga en la ```Test Results``` página.</span><span class="sxs-lookup"><span data-stu-id="ae925-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="ae925-140">Por ejemplo, el script de instalación (que puede encontrarse en el directorio **App/scripts/install)** puede generar sus registros en: **logs/install.log**, de modo que el registro final esté en: **Apps/scripts/install/logs/install.log**</span><span class="sxs-lookup"><span data-stu-id="ae925-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="ae925-141">El sistema recogerá el archivo junto con otros archivos dentro de otras ```install.log``` ```logs``` carpetas y lo intercalará para su descarga.</span><span class="sxs-lookup"><span data-stu-id="ae925-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="ae925-142">4. Archivos binarios de aplicación</span><span class="sxs-lookup"><span data-stu-id="ae925-142">4.   Application binaries</span></span>

<span data-ttu-id="ae925-143">Los archivos binarios y las dependencias deben incluirse en el archivo zip único.</span><span class="sxs-lookup"><span data-stu-id="ae925-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="ae925-144">Estos deben incluir todo lo necesario para la instalación de la aplicación (por ejemplo, el instalador de la aplicación); si la aplicación tiene una dependencia en algún marco, como .NET Core/Standard o .NET Framework, estos deben incluirse en el archivo y hacer referencia correctamente en los scripts proporcionados.</span><span class="sxs-lookup"><span data-stu-id="ae925-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="ae925-145">El archivo zip cargado no puede tener espacios ni caracteres especiales en su nombre</span><span class="sxs-lookup"><span data-stu-id="ae925-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae925-146">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ae925-146">Next steps</span></span>

<span data-ttu-id="ae925-147">Avance al siguiente artículo para ver algunas **preguntas más frecuentes (PREGUNTAS FRECUENTES)**</span><span class="sxs-lookup"><span data-stu-id="ae925-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ae925-148">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="ae925-148">Next step</span></span>](faq.md)
