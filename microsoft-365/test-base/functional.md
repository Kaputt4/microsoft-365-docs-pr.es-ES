---
title: Pruebas funcionales en Test Base
description: Detalles sobre cómo probar la aplicación con las pruebas funcionales automatizadas existentes
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
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323228"
---
# <a name="functional-testing"></a><span data-ttu-id="ed231-103">Pruebas de funcionamiento</span><span class="sxs-lookup"><span data-stu-id="ed231-103">Functional testing</span></span>

<span data-ttu-id="ed231-104">Como proveedor de software, ahora puede realizar pruebas funcionales personalizadas con el marco de prueba que prefiera: a través del portal auto-serve Test Base for M365.</span><span class="sxs-lookup"><span data-stu-id="ed231-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="ed231-105">Cuando iniciamos el servicio inicialmente, ofrecemos las pruebas de lista de pruebas, que es un conjunto predefinido de pruebas controladas a través de scripts estandarizados.</span><span class="sxs-lookup"><span data-stu-id="ed231-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="ed231-106">Sin embargo, esto no pudo lograr la cobertura completa de pruebas para muchos proveedores de software independientes (ISV).</span><span class="sxs-lookup"><span data-stu-id="ed231-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="ed231-107">Por lo tanto, en respuesta a sus comentarios, estamos proporcionando a nuestros ISV la capacidad de cargar pruebas funcionales automatizadas.</span><span class="sxs-lookup"><span data-stu-id="ed231-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="ed231-108">Para usar esta característica, siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed231-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="ed231-109">Upload archivos (archivos binarios, dependencias y scripts) como un único .zip paquete.</span><span class="sxs-lookup"><span data-stu-id="ed231-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="ed231-110">Elija si desea reiniciar las máquinas virtuales (VM) de prueba en varios puntos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed231-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="ed231-111">Administrar las opciones disponibles para los scripts.</span><span class="sxs-lookup"><span data-stu-id="ed231-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="ed231-112">Elija cuándo aplicar la actualización Windows la máquina virtual durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed231-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="ed231-113">A continuación se resaltan las descripciones detalladas de los pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="ed231-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="ed231-114">**Upload un paquete de prueba funcional**</span><span class="sxs-lookup"><span data-stu-id="ed231-114">**Upload a functional test package**</span></span>

<span data-ttu-id="ed231-115">Para empezar, vaya Upload la página Upload, seleccione una nueva aplicación en Catálogo de aplicaciones en el menú de navegación del lado izquierdo del portal Test Base for M365 en Azure.</span><span class="sxs-lookup"><span data-stu-id="ed231-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="ed231-116">Desde allí:</span><span class="sxs-lookup"><span data-stu-id="ed231-116">From there:</span></span>

<span data-ttu-id="ed231-117">Ficha 1: escriba información básica.</span><span class="sxs-lookup"><span data-stu-id="ed231-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="ed231-118">Proporcione el nombre y la versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed231-118">Provide the name and version of your application.</span></span> <span data-ttu-id="ed231-119">En la opción Tipo de prueba, seleccione ```Functional tests``` .</span><span class="sxs-lookup"><span data-stu-id="ed231-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="ed231-120">*Tenga en cuenta que la opción De fábrica (OOB) es obligatoria de forma predeterminada.*</span><span class="sxs-lookup"><span data-stu-id="ed231-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![Seleccionar la pestaña de pruebas funcionales](Media/functional_testing_tab1.png)

<span data-ttu-id="ed231-122">Ficha 2: Upload los componentes del paquete cargando un archivo zip con toda la prueba (archivos binarios, dependencias, scripts, etc.).</span><span class="sxs-lookup"><span data-stu-id="ed231-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="ed231-123">Vea aka.ms/usl-package-outline para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ed231-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="ed231-124">(Nota: Tanto los scripts de prueba de lista para usar como el contenido de la prueba funcional deben colocarse en el mismo archivo zip).</span><span class="sxs-lookup"><span data-stu-id="ed231-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="ed231-125">Actualmente, el tamaño del archivo está limitado a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="ed231-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="ed231-126">Ficha 3: Configurar las tareas de pruebas de lista de pruebas y funcionales.</span><span class="sxs-lookup"><span data-stu-id="ed231-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="ed231-127">Aquí, elija las rutas de acceso a los scripts de PowerShell que instalarán, iniciarán, cerrarán y desinstalarán la aplicación (para fuera de la caja), así como las rutas de acceso a todos los scripts personalizados para realizar la prueba funcional.</span><span class="sxs-lookup"><span data-stu-id="ed231-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="ed231-128">**(Nota: Un script para desinstalar la aplicación es opcional).**</span><span class="sxs-lookup"><span data-stu-id="ed231-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="ed231-129">Actualmente, puede cargar entre 1 y 8 scripts para las pruebas funcionales.</span><span class="sxs-lookup"><span data-stu-id="ed231-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="ed231-130">(Comentario amable en esta entrada si necesita más scripts!)</span><span class="sxs-lookup"><span data-stu-id="ed231-130">(Kindly comment on this post if you need more scripts!)</span></span>

![Upload hasta 8 scripts con pruebas funcionales](Media/functional_testing_tab3.png)

<span data-ttu-id="ed231-132">(Opcional) Configure un reinicio después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="ed231-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="ed231-133">Algunas aplicaciones requieren un reinicio después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="ed231-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="ed231-134">Seleccione el script específico en la pestaña Tareas si desea que se realice un reinicio ```Reboot After Execution``` después de la ejecución de ese script.</span><span class="sxs-lookup"><span data-stu-id="ed231-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="ed231-135">Ficha 4: elija cuándo se instala la actualización Windows: la aplicación de la revisión Windows Update se realiza antes de cualquier script de su elección.</span><span class="sxs-lookup"><span data-stu-id="ed231-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="ed231-136">Se recomienda instalar una actualización de Windows después de la instalación de la aplicación para imitar estrechamente los escenarios de uso de aplicaciones reales.</span><span class="sxs-lookup"><span data-stu-id="ed231-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![La actualización Windows puede instalarse después de un script específico](Media/functional_testing_tab4.png)

<span data-ttu-id="ed231-138">Ficha 5: revisar y crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="ed231-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="ed231-139">Una vez que haya completado los pasos enumerados anteriormente, seleccione ```Create``` para finalizar el proceso de carga.</span><span class="sxs-lookup"><span data-stu-id="ed231-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="ed231-140">Una vez creado el paquete, puede comprobar el estado de comprobación del paquete.</span><span class="sxs-lookup"><span data-stu-id="ed231-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="ed231-141">Ejecutamos una prueba inicial para instalar, iniciar, cerrar y desinstalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed231-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="ed231-142">Esto nos permite comprobar que el paquete se puede instalar en nuestro servicio sin errores.</span><span class="sxs-lookup"><span data-stu-id="ed231-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="ed231-143">El proceso de verificación podría tardar hasta 24 horas.</span><span class="sxs-lookup"><span data-stu-id="ed231-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="ed231-144">Una vez completada la comprobación, puede ver el estado en el ```Manage packages``` menú, que sería una de las dos entradas:</span><span class="sxs-lookup"><span data-stu-id="ed231-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="ed231-145">La comprobación se realiza correctamente: el paquete se probará automáticamente con las actualizaciones Windows versiones anteriores a las compilaciones del sistema operativo que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="ed231-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="ed231-146">o</span><span class="sxs-lookup"><span data-stu-id="ed231-146">or</span></span>
2. <span data-ttu-id="ed231-147">Error en la comprobación: deberá investigar los motivos del error, corregir el problema y volver a cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="ed231-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="ed231-148">También se le notificará de cualquiera de los resultados a través del icono de notificación en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="ed231-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
