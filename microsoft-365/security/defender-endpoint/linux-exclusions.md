---
title: Configurar y validar exclusiones para Microsoft Defender para Endpoint en Linux
description: Proporcionar y validar exclusiones para Microsoft Defender para Endpoint en Linux. Las exclusiones se pueden establecer para archivos, carpetas y procesos.
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, exclusiones, exámenes, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b55572509e9837f2858f96b01a13fbf259b2b770
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393792"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="ae7ad-105">Configurar y validar exclusiones para Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="ae7ad-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ae7ad-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ae7ad-106">**Applies to:**</span></span>

- [<span data-ttu-id="ae7ad-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ae7ad-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae7ad-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae7ad-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ae7ad-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ae7ad-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ae7ad-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ae7ad-111">En este artículo se proporciona información sobre cómo definir exclusiones que se aplican a los exámenes a petición y la protección y supervisión en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae7ad-112">Las exclusiones descritas en este artículo no se aplican a otras funcionalidades de Defender for Endpoint en Linux, incluidas detección y respuesta de puntos de conexión (EDR).</span><span class="sxs-lookup"><span data-stu-id="ae7ad-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="ae7ad-113">Los archivos que se excluyen mediante los métodos descritos en este artículo aún pueden desencadenar EDR alertas y otras detecciones.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="ae7ad-114">Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de los exámenes de Defender para endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="ae7ad-115">Las exclusiones pueden ser útiles para evitar detecciones incorrectas en archivos o software que son únicos o personalizados para su organización.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="ae7ad-116">También pueden ser útiles para mitigar los problemas de rendimiento causados por Defender para Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="ae7ad-117">La definición de exclusiones reduce la protección que ofrece Defender para Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="ae7ad-118">Siempre debe evaluar los riesgos asociados con la implementación de exclusiones y solo debe excluir los archivos que confía en que no son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="ae7ad-119">Tipos de exclusión admitidos</span><span class="sxs-lookup"><span data-stu-id="ae7ad-119">Supported exclusion types</span></span>

<span data-ttu-id="ae7ad-120">En la tabla siguiente se muestran los tipos de exclusión admitidos por Defender para Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="ae7ad-121">Exclusión</span><span class="sxs-lookup"><span data-stu-id="ae7ad-121">Exclusion</span></span> | <span data-ttu-id="ae7ad-122">Definición</span><span class="sxs-lookup"><span data-stu-id="ae7ad-122">Definition</span></span> | <span data-ttu-id="ae7ad-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ae7ad-123">Examples</span></span>
---|---|---
<span data-ttu-id="ae7ad-124">Extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="ae7ad-124">File extension</span></span> | <span data-ttu-id="ae7ad-125">Todos los archivos con la extensión, en cualquier lugar del dispositivo</span><span class="sxs-lookup"><span data-stu-id="ae7ad-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="ae7ad-126">Archivo</span><span class="sxs-lookup"><span data-stu-id="ae7ad-126">File</span></span> | <span data-ttu-id="ae7ad-127">Un archivo específico identificado por la ruta de acceso completa</span><span class="sxs-lookup"><span data-stu-id="ae7ad-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="ae7ad-128">Folder</span><span class="sxs-lookup"><span data-stu-id="ae7ad-128">Folder</span></span> | <span data-ttu-id="ae7ad-129">Todos los archivos de la carpeta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="ae7ad-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="ae7ad-130">Proceso</span><span class="sxs-lookup"><span data-stu-id="ae7ad-130">Process</span></span> | <span data-ttu-id="ae7ad-131">Un proceso específico (especificado por la ruta de acceso completa o el nombre de archivo) y todos los archivos abiertos por él</span><span class="sxs-lookup"><span data-stu-id="ae7ad-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="ae7ad-132">Las rutas anteriores deben ser vínculos duros, no vínculos simbólicos, para poder excluirse correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="ae7ad-133">Puede comprobar si una ruta de acceso es un vínculo simbólico ejecutando `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="ae7ad-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="ae7ad-134">Las exclusiones de archivos, carpetas y procesos admiten los siguientes caracteres comodín:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="ae7ad-135">Carácter comodín</span><span class="sxs-lookup"><span data-stu-id="ae7ad-135">Wildcard</span></span> | <span data-ttu-id="ae7ad-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae7ad-136">Description</span></span> | <span data-ttu-id="ae7ad-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae7ad-137">Example</span></span> | <span data-ttu-id="ae7ad-138">Coincidencias</span><span class="sxs-lookup"><span data-stu-id="ae7ad-138">Matches</span></span> | <span data-ttu-id="ae7ad-139">No coincide</span><span class="sxs-lookup"><span data-stu-id="ae7ad-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="ae7ad-140">Coincide con cualquier número de caracteres, incluido ninguno (tenga en cuenta que cuando se usa este comodín dentro de una ruta de acceso, solo sustituirá una carpeta)</span><span class="sxs-lookup"><span data-stu-id="ae7ad-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="ae7ad-141">?</span><span class="sxs-lookup"><span data-stu-id="ae7ad-141">?</span></span> | <span data-ttu-id="ae7ad-142">Coincide con cualquier carácter</span><span class="sxs-lookup"><span data-stu-id="ae7ad-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="ae7ad-143">Cómo configurar la lista de exclusiones</span><span class="sxs-lookup"><span data-stu-id="ae7ad-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="ae7ad-144">Desde la consola de administración</span><span class="sxs-lookup"><span data-stu-id="ae7ad-144">From the management console</span></span>

<span data-ttu-id="ae7ad-145">Para obtener más información sobre cómo configurar exclusiones de Puppet, Ansible u otra consola de administración, consulte [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="ae7ad-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="ae7ad-146">Desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="ae7ad-146">From the command line</span></span>

<span data-ttu-id="ae7ad-147">Ejecute el siguiente comando para ver los modificadores disponibles para administrar exclusiones:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="ae7ad-148">Al configurar exclusiones con caracteres comodín, escriba el parámetro entre comillas dobles para evitar el globbing.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="ae7ad-149">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-149">Examples:</span></span>

- <span data-ttu-id="ae7ad-150">Agregar una exclusión para una extensión de archivo:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="ae7ad-151">Agregar una exclusión para un archivo:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="ae7ad-152">Agregar una exclusión para una carpeta:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- <span data-ttu-id="ae7ad-153">Agregue una exclusión para una segunda carpeta:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-153">Add an exclusion for a second folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- <span data-ttu-id="ae7ad-154">Agregue una exclusión para una carpeta con un comodín en ella:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-154">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="ae7ad-155">Esto solo excluirá las rutas de acceso de un nivel por debajo *de /var/*, pero no las carpetas que están más anidadas; por ejemplo, */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-155">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="ae7ad-156">Esto excluirá todas las rutas de acceso cuyo elemento primario *es /var/*; por ejemplo, */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-156">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="ae7ad-157">Agregar una exclusión para un proceso:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-157">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```


- <span data-ttu-id="ae7ad-158">Agregar una exclusión para un segundo proceso:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-158">Add an exclusion for a second process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="ae7ad-159">Validar listas de exclusiones con el archivo de prueba EICAR</span><span class="sxs-lookup"><span data-stu-id="ae7ad-159">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="ae7ad-160">Puede validar que las listas de exclusión funcionan mediante `curl` la descarga de un archivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-160">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="ae7ad-161">En el siguiente fragmento de código Bash, reemplace `test.txt` por un archivo que cumpla las reglas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-161">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="ae7ad-162">Por ejemplo, si ha excluido la `.testing` extensión, reemplace `test.txt` por `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="ae7ad-162">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="ae7ad-163">Si está probando una ruta de acceso, asegúrese de ejecutar el comando dentro de esa ruta.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-163">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="ae7ad-164">Si Defender para Endpoint en Linux informa de malware, la regla no funciona.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-164">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="ae7ad-165">Si no hay ningún informe de malware y existe el archivo descargado, la exclusión funciona.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-165">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="ae7ad-166">Puede abrir el archivo para confirmar que el contenido es el mismo que el descrito en el sitio web del archivo [de prueba EICAR](http://2016.eicar.org/86-0-Intended-use.html).</span><span class="sxs-lookup"><span data-stu-id="ae7ad-166">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="ae7ad-167">Si no tiene acceso a Internet, puede crear su propio archivo de prueba EICAR.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-167">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="ae7ad-168">Escriba la cadena EICAR en un nuevo archivo de texto con el siguiente comando Bash:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-168">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="ae7ad-169">También puede copiar la cadena en un archivo de texto en blanco e intentar guardarla con el nombre de archivo o en la carpeta que está intentando excluir.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-169">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="ae7ad-170">Permitir amenazas</span><span class="sxs-lookup"><span data-stu-id="ae7ad-170">Allow threats</span></span>

<span data-ttu-id="ae7ad-171">Además de excluir cierto contenido para que no se digitalizara, también puede configurar el producto para que no detecte algunas clases de amenazas (identificadas por el nombre de la amenaza).</span><span class="sxs-lookup"><span data-stu-id="ae7ad-171">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="ae7ad-172">Debes tener cuidado al usar esta funcionalidad, ya que puede dejar el dispositivo desprotegido.</span><span class="sxs-lookup"><span data-stu-id="ae7ad-172">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="ae7ad-173">Para agregar un nombre de amenaza a la lista permitida, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-173">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="ae7ad-174">El nombre de la amenaza asociado a una detección en el dispositivo se puede obtener con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-174">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="ae7ad-175">Por ejemplo, para agregar (el nombre de amenaza asociado con la detección `EICAR-Test-File (not a virus)` eicar) a la lista permitida, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ae7ad-175">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
