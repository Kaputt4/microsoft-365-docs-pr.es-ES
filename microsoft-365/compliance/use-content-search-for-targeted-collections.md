---
title: Usar búsqueda de contenido para colecciones específicas
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Use la búsqueda de contenido en el centro de cumplimiento de Microsoft 365 para realizar colecciones de destino, que garantizan que los elementos se encuentran en un buzón o carpeta de sitio específicos.
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376597"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="0e9a4-103">Usar búsqueda de contenido para colecciones específicas</span><span class="sxs-lookup"><span data-stu-id="0e9a4-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="0e9a4-104">La característica de búsqueda de contenido en el centro de cumplimiento de Microsoft 365 no ofrece una forma directa en la interfaz de usuario para buscar en carpetas específicas de los buzones de Exchange o de los sitios de SharePoint y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-104">The Content Search feature in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="0e9a4-105">Sin embargo, es posible buscar carpetas específicas (denominadas *colección de destino*) especificando la propiedad ID de la carpeta para la propiedad email o path (DocumentLink) de los sitios de la sintaxis de la consulta de búsqueda real.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="0e9a4-106">Usar la búsqueda de contenido para realizar una colección de destino es útil cuando tiene la certeza de que los elementos que responden a un caso o los elementos con privilegios están ubicados en un buzón o carpeta de sitio específicos.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="0e9a4-107">Puede usar el script de este artículo para obtener el identificador de carpeta para las carpetas de buzón o la ruta de acceso (DocumentLink) para las carpetas de un sitio de SharePoint y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="0e9a4-108">A continuación, puede usar el identificador de carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos que se encuentran en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="0e9a4-109">Para devolver contenido que se encuentra en una carpeta de un sitio de SharePoint o de OneDrive para la empresa, el script de este tema usa la propiedad administrada DocumentLink en lugar de la propiedad path.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="0e9a4-110">La propiedad DocumentLink es más robusta que la propiedad path porque devolverá todo el contenido de una carpeta, mientras que la propiedad path no devolverá algunos archivos multimedia.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="0e9a4-111">Antes de ejecutar una colección de destino</span><span class="sxs-lookup"><span data-stu-id="0e9a4-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="0e9a4-112">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento para ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="0e9a4-113">Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0e9a4-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="0e9a4-114">Además, debe tener asignado el rol destinatarios de correo en su organización de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="0e9a4-115">Esto es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics** , que se incluye en el script.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="0e9a4-116">De forma predeterminada, la función destinatarios de correo se asigna a los grupos de funciones administración de la organización y administración de destinatarios en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="0e9a4-117">Para obtener más información acerca de la asignación de permisos en Exchange Online, consulte [Manage role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span><span class="sxs-lookup"><span data-stu-id="0e9a4-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="0e9a4-118">También puede crear un grupo de funciones personalizado, asignarle el rol destinatarios de correo y, a continuación, agregar los miembros que necesitan ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="0e9a4-119">Para obtener más información, consulte [Administrar grupos de roles](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="0e9a4-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="0e9a4-120">La secuencia de comandos de este artículo admite la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="0e9a4-121">Puede usar el script tal cual si es Microsoft 365 o una organización de Microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="0e9a4-122">Si es una organización de Office 365 Germany, una organización de Microsoft 365 GCC o una organización DoD de Microsoft 365, tendrá que editar el script para que se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="0e9a4-123">Concretamente, tiene que editar la línea `Connect-ExchangeOnline` y usar el parámetro *ExchangeEnvironmentName* (y el valor adecuado para el tipo de organización) para conectarse a PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="0e9a4-124">Además, tiene que editar la línea `Connect-IPPSSession` y usar los parámetros *ConnectionUri* y *AzureADAuthorizationEndpointUri* (y los valores apropiados para el tipo de organización) para conectarse a PowerShell del centro de cumplimiento de & de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="0e9a4-125">Para obtener más información, vea los ejemplos de [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) y [conectarse al centro de seguridad & cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="0e9a4-125">For more information, see the examples in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="0e9a4-126">Cada vez que se ejecuta el script, se crea una nueva sesión de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="0e9a4-127">Esto significa que puede usar todas las sesiones de PowerShell remoto disponibles.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="0e9a4-128">Para evitar que esto suceda, ejecute el siguiente comando para desconectar las sesiones remotas de PowerShell activas.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="0e9a4-129">Para obtener más información, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="0e9a4-129">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="0e9a4-130">El script incluye un tratamiento de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-130">The script includes minimal error handling.</span></span> <span data-ttu-id="0e9a4-131">El objetivo principal de la secuencia de comandos es mostrar rápidamente una lista de identificadores de carpetas de buzones o rutas de sitios que se pueden usar en la sintaxis de la consulta de búsqueda de una búsqueda de contenido para realizar una colección de destino.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="0e9a4-132">La secuencia de comandos de ejemplo proporcionada en este tema no es compatible con ningún servicio o programa de soporte estándar de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="0e9a4-133">El script de ejemplo se proporciona tal cual sin garantías de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="0e9a4-134">Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="0e9a4-135">Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="0e9a4-136">En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="0e9a4-137">Paso 1: ejecutar el script para obtener una lista de las carpetas de un buzón de correo o sitio</span><span class="sxs-lookup"><span data-stu-id="0e9a4-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="0e9a4-138">El script que se ejecuta en el primer paso devolverá una lista de carpetas de buzones o de carpetas de SharePoint y OneDrive para la empresa, así como el identificador de carpeta o la ruta de acceso correspondientes para cada carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="0e9a4-139">Al ejecutar este script, se le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-139">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="0e9a4-140">Dirección de **correo electrónico o dirección URL del sitio**: escriba una dirección de correo electrónico del custodio para devolver una lista de las carpetas de buzones y los identificadores de carpetas de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="0e9a4-141">O bien, escriba la dirección URL de un sitio de SharePoint o un sitio de OneDrive para la empresa para devolver una lista de rutas de la ubicación del sitio especificado.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="0e9a4-142">Aquí le mostramos otros ejemplos:</span><span class="sxs-lookup"><span data-stu-id="0e9a4-142">Here are some examples:</span></span>

  - <span data-ttu-id="0e9a4-143">**Exchange**: stacig@contoso. en Microsoft <spam> <spam> . com</span><span class="sxs-lookup"><span data-stu-id="0e9a4-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="0e9a4-144">**SharePoint**: https <span>://</span>contoso.SharePoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="0e9a4-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="0e9a4-145">**OneDrive para la empresa**: https <span>://</span>contoso-My.SharePoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="0e9a4-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="0e9a4-146">**Sus credenciales de usuario**: el script usará sus credenciales para conectarse a PowerShell de Exchange Online PowerShell o el PowerShell del centro de cumplimiento de & de seguridad usando la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="0e9a4-147">Como se ha explicado anteriormente, debe tener asignados los permisos adecuados para ejecutar correctamente este script.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="0e9a4-148">Para mostrar una lista de las carpetas del buzón o los nombres de documentlink (ruta de acceso) del sitio:</span><span class="sxs-lookup"><span data-stu-id="0e9a4-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="0e9a4-149">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="0e9a4-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. <span data-ttu-id="0e9a4-150">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="0e9a4-151">Ejecutar el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e9a4-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="0e9a4-152">Escriba la información que el script le pide.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="0e9a4-153">El script muestra una lista de carpetas de buzón de correo o carpetas del sitio para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="0e9a4-154">Deje esta ventana abierta para que pueda copiar un identificador de carpeta o nombre de documentlink y pegarlo en una consulta de búsqueda en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="0e9a4-155">En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede redirigir el resultado del script a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="0e9a4-156">Este archivo se guardará en la carpeta en la que se encuentra el script.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="0e9a4-157">Por ejemplo, para redirigir la salida del script a un archivo de texto, ejecute el siguiente comando en el paso 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` a continuación, puede copiar un identificador de carpeta o documentlink del archivo para usarlo en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="0e9a4-158">Salida de script para carpetas de buzón</span><span class="sxs-lookup"><span data-stu-id="0e9a4-158">Script output for mailbox folders</span></span>

<span data-ttu-id="0e9a4-159">Si está obteniendo identificadores de carpeta de buzón de correo, el script se conecta a Exchange Online PowerShell, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de las carpetas del buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="0e9a4-160">Para cada carpeta del buzón, el script muestra el nombre de la carpeta en la columna **folderPath** y el identificador de la carpeta en la columna **FolderQuery** .</span><span class="sxs-lookup"><span data-stu-id="0e9a4-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="0e9a4-161">Además, el script agrega el prefijo de **folderId** (que es el nombre de la propiedad Mailbox) al identificador de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="0e9a4-162">Dado que la propiedad **folderId** es una propiedad que se puede buscar, usará  `folderid:<folderid>` en una consulta de búsqueda en el paso 2 para buscar en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="0e9a4-163">El script muestra un máximo de 100 carpetas de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e9a4-164">El script de este artículo incluye la lógica de codificación que convierte los valores de identificador de carpeta de 64 caracteres devueltos por **Get-MailboxFolderStatistics** en el mismo formato de 48 caracteres que se indexa para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="0e9a4-165">Si solo ejecuta el cmdlet **Get-MailboxFolderStatistics** en PowerShell para obtener un identificador de carpeta (en lugar de ejecutar el script de este artículo), se producirá un error en una consulta de búsqueda que use ese valor de ID de carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="0e9a4-166">Tiene que ejecutar el script para obtener los identificadores de carpeta con formato correcto que se pueden usar en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="0e9a4-167">A continuación, se muestra un ejemplo del resultado devuelto por el script para las carpetas de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-167">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Ejemplo de la lista de carpetas de buzones y de identificadores de carpetas devueltos por el script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="0e9a4-169">El ejemplo del paso 2 muestra la consulta utilizada para buscar en la subcarpeta Purges de la carpeta elementos recuperables del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="0e9a4-170">Salida de script para carpetas de sitio</span><span class="sxs-lookup"><span data-stu-id="0e9a4-170">Script output for site folders</span></span>

<span data-ttu-id="0e9a4-171">Si va a obtener la ruta de acceso de la propiedad **documentlink** de los sitios de SharePoint o de OneDrive para la empresa, el script se conecta a seguridad & cumplimiento de las normas de seguridad, crea una nueva búsqueda de contenido que busca carpetas en el sitio y, a continuación, muestra una lista de las carpetas que se encuentran en el sitio especificado.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="0e9a4-172">El script muestra el nombre de cada carpeta y agrega el prefijo de **documentlink** a la dirección URL de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="0e9a4-173">Como la propiedad **documentlink** es una propiedad que se puede buscar, use el `documentlink:<path>` par Property: value en una consulta de búsqueda en el paso 2 para buscar en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="0e9a4-174">El script muestra un máximo de 200 carpetas del sitio.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="0e9a4-175">Si hay más de 200 carpetas de sitio, se muestran las más recientes.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="0e9a4-176">A continuación, se muestra un ejemplo de los resultados devueltos por el script para las carpetas del sitio.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-176">Here's an example of the output returned by the script for site folders.</span></span>
  
![Ejemplo de la lista de nombres de documentlink para las carpetas de sitio devueltas por el script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="0e9a4-178">Paso 2: usar un identificador de carpeta o documentlink para realizar una colección de destino</span><span class="sxs-lookup"><span data-stu-id="0e9a4-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="0e9a4-179">Una vez que haya ejecutado el script para recopilar una lista de identificadores de carpeta o vínculos de documentos para un usuario específico, siga el paso siguiente para ir al centro de cumplimiento de Microsoft 365 y crear una nueva búsqueda de contenido para buscar en una carpeta específica.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="0e9a4-180">Use el  `folderid:<folderid>`  `documentlink:<path>` par propiedad o: valor de la consulta de búsqueda que configure en el cuadro palabra clave de búsqueda de contenido (o como el valor para el parámetro  *ContentMatchQuery*  si usa el cmdlet **New-ComplianceSearch** ).</span><span class="sxs-lookup"><span data-stu-id="0e9a4-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="0e9a4-181">Puede combinar la  `folderid` propiedad o  `documentlink` con otros parámetros de búsqueda o condiciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="0e9a4-182">Si solo incluye la  `folderid` propiedad o  `documentlink` en la consulta, la búsqueda devolverá todos los elementos que se encuentran en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="0e9a4-183">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con la cuenta y las credenciales que usó para ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-183">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="0e9a4-184">En el panel izquierdo del centro de cumplimiento, haga clic en **Mostrar**  >  **búsqueda de contenido** y, a continuación, haga clic en **nueva búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="0e9a4-185">En el cuadro **palabras clave** , pegue `folderid:<folderid>` el  `documentlink:<path>` valor o devuelto por el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="0e9a4-186">Por ejemplo, en la siguiente captura de pantalla se buscará cualquier elemento de la subcarpeta depuraciones en la carpeta elementos recuperables del usuario (el valor de la `folderid` propiedad de la subcarpeta purgas se muestra en la captura de pantalla del paso 1):</span><span class="sxs-lookup"><span data-stu-id="0e9a4-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Pegue el folderId o documentlink en el cuadro de palabras clave de la consulta de búsqueda](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="0e9a4-188">En **ubicaciones**, seleccione **ubicaciones específicas** y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="0e9a4-189">Realice una de las siguientes acciones, en función de si está buscando en una carpeta de buzón de correo o en una carpeta de sitio:</span><span class="sxs-lookup"><span data-stu-id="0e9a4-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="0e9a4-190">Junto a **correo electrónico de Exchange**, haga clic en **elegir usuarios, grupos o equipos** y, a continuación, agregue el mismo buzón que especificó cuando ejecutó el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="0e9a4-191">O bien</span><span class="sxs-lookup"><span data-stu-id="0e9a4-191">Or</span></span>

    - <span data-ttu-id="0e9a4-192">Junto a **sitios de SharePoint**, haga clic en **elegir sitios** y, a continuación, agregue la dirección URL del sitio que especificó al ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="0e9a4-193">Una vez guardada la ubicación de contenido para realizar la búsqueda, haga clic en **guardar & ejecutar**, escriba un nombre para la búsqueda de contenido y, a continuación, haga clic en **Guardar** para iniciar la búsqueda de colección de destino.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="0e9a4-194">Ejemplos de consultas de búsqueda para colecciones dirigidas</span><span class="sxs-lookup"><span data-stu-id="0e9a4-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="0e9a4-195">A continuación se muestran algunos ejemplos de cómo usar las  `folderid`  `documentlink` propiedades y en una consulta de búsqueda para realizar una colección de destino.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="0e9a4-196">Los marcadores de posición se usan para  `folderid:<folderid>` y  `documentlink:<path>` para ahorrar espacio.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="0e9a4-197">En este ejemplo se buscan tres carpetas de buzón diferentes.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="0e9a4-198">Puede usar sintaxis de consulta similar para buscar en las carpetas ocultas de la carpeta elementos recuperables de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="0e9a4-199">En este ejemplo se busca en una carpeta de buzón los elementos que contienen una frase exacta.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="0e9a4-200">En este ejemplo se busca en una carpeta del sitio (y en cualquier subcarpeta) documentos que contengan las letras "NDA" en el título.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="0e9a4-201">En este ejemplo se busca en una carpeta del sitio (y en cualquier subcarpeta) los documentos que se han modificado en un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="0e9a4-202">Más información</span><span class="sxs-lookup"><span data-stu-id="0e9a4-202">More information</span></span>

<span data-ttu-id="0e9a4-203">Tenga en cuenta lo siguiente cuando use el script de este artículo para realizar colecciones de destino.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="0e9a4-204">El script no quita ninguna carpeta de los resultados.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="0e9a4-205">Por lo tanto, algunas carpetas que aparecen en los resultados podrían no ser buscadas (o devolver cero elementos) porque contienen contenido generado por el sistema o porque solo contienen subcarpetas y no elementos del buzón.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="0e9a4-206">Este script solo devuelve información de la carpeta del buzón de correo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="0e9a4-207">No devuelve información sobre las carpetas en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="0e9a4-208">Para devolver información sobre las carpetas en el buzón de archivo del usuario, puede editar el script.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="0e9a4-209">Para ello, cambie la línea `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` a `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` y, a continuación, guarde y ejecute el script editado.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="0e9a4-210">Este cambio devolverá los identificadores de carpeta de las carpetas y subcarpetas del buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="0e9a4-211">Para buscar en todo el buzón de archivo, puede conectar todos los pares de propiedad ID de carpeta: valor con un `OR` operador en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="0e9a4-212">Al buscar carpetas de buzones de correo, solo se buscará en la carpeta especificada (identificada por su `folderid` propiedad); no se buscará en las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="0e9a4-213">Para buscar en subcarpetas, debe usar el identificador de carpeta de la subcarpeta que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="0e9a4-214">Al buscar carpetas de sitio, se buscará en la carpeta (identificada por su `documentlink` propiedad) y en todas las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="0e9a4-215">Al exportar los resultados de una búsqueda en la que solo especificó la `folderid` propiedad en la consulta de búsqueda, puede elegir la primera opción de exportación: "todos los elementos, excluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos".</span><span class="sxs-lookup"><span data-stu-id="0e9a4-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="0e9a4-216">Todos los elementos de la carpeta siempre se exportarán independientemente de su estado de indización, ya que el identificador de carpeta siempre está indizado.</span><span class="sxs-lookup"><span data-stu-id="0e9a4-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
