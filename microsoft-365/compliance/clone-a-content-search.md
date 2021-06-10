---
title: Clonar una búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Use el script de PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente en el centro de cumplimiento en Office 365 o Microsoft 365.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918066"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="e6b02-103">Clonar una búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="e6b02-103">Clone a Content Search</span></span>

<span data-ttu-id="e6b02-104">Crear una búsqueda de contenido en el centro de cumplimiento en Office 365 o Microsoft 365 que busque muchos buzones o sitios SharePoint y OneDrive para la Empresa pueden tardar un tiempo.</span><span class="sxs-lookup"><span data-stu-id="e6b02-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="e6b02-105">La especificación de los sitios en los que se va a buscar también puede ser propenso a errores si se escribir mal una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="e6b02-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="e6b02-106">Para evitar estos problemas, puede usar el script Windows PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente.</span><span class="sxs-lookup"><span data-stu-id="e6b02-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="e6b02-107">Al clonar una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (como las ubicaciones de contenido y la consulta de búsqueda) que la búsqueda original.</span><span class="sxs-lookup"><span data-stu-id="e6b02-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="e6b02-108">A continuación, puede editar la nueva búsqueda cambiando la consulta de palabras clave o el intervalo de fechas y ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="e6b02-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="e6b02-109">¿Por qué clonar búsquedas de contenido?</span><span class="sxs-lookup"><span data-stu-id="e6b02-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="e6b02-110">Para comparar los resultados de diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido.</span><span class="sxs-lookup"><span data-stu-id="e6b02-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="e6b02-111">Para evitar que tenga que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6b02-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="e6b02-112">Para reducir el tamaño de los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6b02-112">To decrease the size of the search results.</span></span> <span data-ttu-id="e6b02-113">Por ejemplo, si tiene una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregar una condición de búsqueda basada en un intervalo de fechas para reducir el número de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6b02-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="e6b02-114">Información de script</span><span class="sxs-lookup"><span data-stu-id="e6b02-114">Script information</span></span>

- <span data-ttu-id="e6b02-115">Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento para ejecutar el script descrito en este tema.</span><span class="sxs-lookup"><span data-stu-id="e6b02-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="e6b02-116">El script incluye un control de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="e6b02-116">The script includes minimal error handling.</span></span> <span data-ttu-id="e6b02-117">El propósito principal del script es clonar rápidamente una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="e6b02-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="e6b02-118">El script crea una nueva búsqueda de contenido, pero no la inicia.</span><span class="sxs-lookup"><span data-stu-id="e6b02-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="e6b02-119">Este script tiene en cuenta si la búsqueda de contenido que está clonando está asociada con un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="e6b02-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="e6b02-120">Si la búsqueda está asociada a un caso, la nueva búsqueda también se asociará con el mismo caso.</span><span class="sxs-lookup"><span data-stu-id="e6b02-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="e6b02-121">Si la búsqueda existente no está asociada a un caso, la nueva búsqueda aparecerá en la página **Búsqueda** de contenido en el centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e6b02-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="e6b02-122">El script de ejemplo proporcionado en este tema no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6b02-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="e6b02-123">El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="e6b02-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="e6b02-124">Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito.</span><span class="sxs-lookup"><span data-stu-id="e6b02-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="e6b02-125">Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya.</span><span class="sxs-lookup"><span data-stu-id="e6b02-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="e6b02-126">En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.</span><span class="sxs-lookup"><span data-stu-id="e6b02-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="e6b02-127">Paso 1: Ejecutar el script para clonar una búsqueda</span><span class="sxs-lookup"><span data-stu-id="e6b02-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="e6b02-128">El script de este paso creará una nueva búsqueda de contenido clonando una existente.</span><span class="sxs-lookup"><span data-stu-id="e6b02-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="e6b02-129">Al ejecutar este script, se le pedirá la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e6b02-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="e6b02-130">**Sus credenciales de usuario:** el script usará sus credenciales para conectarse al Centro de seguridad y & cumplimiento para su organización con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6b02-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="e6b02-131">Como se ha indicado anteriormente, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de & de seguridad para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="e6b02-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="e6b02-132">**Nombre de la búsqueda existente:** se trata de la búsqueda de contenido que desea clonar.</span><span class="sxs-lookup"><span data-stu-id="e6b02-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="e6b02-133">**Nombre de** la nueva búsqueda que se creará: si deja este valor en blanco, el script creará un nombre para la nueva búsqueda basado en el nombre de la búsqueda que está clonando.</span><span class="sxs-lookup"><span data-stu-id="e6b02-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="e6b02-134">Para clonar una búsqueda:</span><span class="sxs-lookup"><span data-stu-id="e6b02-134">To clone a search:</span></span>
  
1. <span data-ttu-id="e6b02-135">Guarde el texto siguiente en un archivo Windows PowerShell script mediante un sufijo de nombre de archivo de .ps1; por ejemplo, `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e6b02-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="e6b02-136">Abra Windows PowerShell y vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="e6b02-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="e6b02-137">Ejecute el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6b02-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="e6b02-138">Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6b02-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e6b02-139">Escriba la siguiente información cuando se lo pida el script.</span><span class="sxs-lookup"><span data-stu-id="e6b02-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="e6b02-140">Escriba cada fragmento de información y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="e6b02-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="e6b02-141">Nombre de la búsqueda existente.</span><span class="sxs-lookup"><span data-stu-id="e6b02-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="e6b02-142">Nombre de la nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6b02-142">The name of the new search.</span></span>
    
    <span data-ttu-id="e6b02-143">El script crea la nueva búsqueda de contenido, pero no la inicia.</span><span class="sxs-lookup"><span data-stu-id="e6b02-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="e6b02-144">Esto le da la oportunidad de editar y ejecutar la búsqueda en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6b02-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="e6b02-145">Puede ver las propiedades de la nueva búsqueda ejecutando el cmdlet  **Get-ComplianceSearch** o yendo a la página Búsqueda de contenido o exhibición de documentos electrónicos en el centro de cumplimiento, en función de si la nueva búsqueda está asociada a un caso. </span><span class="sxs-lookup"><span data-stu-id="e6b02-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="e6b02-146">Paso 2: Editar y ejecutar la búsqueda clonada en el centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e6b02-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="e6b02-147">Después de ejecutar el script para clonar una búsqueda de contenido existente, el siguiente paso es ir al Centro de cumplimiento para editar y ejecutar la nueva búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6b02-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="e6b02-148">Como se ha indicado anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabras clave y agregando o eliminando condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e6b02-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="e6b02-149">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="e6b02-149">For more information, see:</span></span>
  
- [<span data-ttu-id="e6b02-150">Búsqueda de contenido de Office 365</span><span class="sxs-lookup"><span data-stu-id="e6b02-150">Content Search in Office 365</span></span>](content-search.md)
    
- <span data-ttu-id="e6b02-151">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="e6b02-151">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
    
- [<span data-ttu-id="e6b02-152">Casos de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="e6b02-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)