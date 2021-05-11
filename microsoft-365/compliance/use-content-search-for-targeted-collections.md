---
title: Usar la búsqueda de contenido para colecciones dirigidas
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
description: Use la búsqueda de contenido en el centro Microsoft 365 cumplimiento para realizar una colección de destino, que busca elementos en un buzón o carpeta de sitio específico.
ms.openlocfilehash: cf0364d39a78e1bbbc062d85ce750d190fbbda5a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311905"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="f01d5-103">Usar la búsqueda de contenido para colecciones dirigidas</span><span class="sxs-lookup"><span data-stu-id="f01d5-103">Use Content search for targeted collections</span></span>

<span data-ttu-id="f01d5-104">La herramienta de búsqueda de contenido en el centro de cumplimiento de Microsoft 365 no proporciona una forma directa en la interfaz de usuario de buscar carpetas específicas en buzones de Exchange o sitios SharePoint y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="f01d5-104">The Content search tool in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="f01d5-105">Sin embargo, es posible buscar carpetas específicas (denominadas colección de *destino)* especificando la propiedad id. de carpeta para el correo electrónico o la propiedad path (DocumentLink) para los sitios de la sintaxis de consulta de búsqueda real.</span><span class="sxs-lookup"><span data-stu-id="f01d5-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="f01d5-106">Usar la búsqueda de contenido para realizar una colección de destino es útil cuando está seguro de que los elementos que responden a un caso o elementos con privilegios se encuentran en un buzón o carpeta de sitio específico.</span><span class="sxs-lookup"><span data-stu-id="f01d5-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="f01d5-107">Puede usar el script de este artículo para obtener el identificador de carpeta de carpetas de buzones de correo o la ruta de acceso (DocumentLink) para las carpetas de SharePoint y OneDrive para la Empresa sitio.</span><span class="sxs-lookup"><span data-stu-id="f01d5-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="f01d5-108">A continuación, puede usar el identificador de carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos ubicados en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="f01d5-109">Para devolver contenido ubicado en una carpeta de un sitio SharePoint o OneDrive para la Empresa, el script de este tema usa la propiedad administrada DocumentLink en lugar de la propiedad Path.</span><span class="sxs-lookup"><span data-stu-id="f01d5-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="f01d5-110">La propiedad DocumentLink es más sólida que la propiedad Path porque devolverá todo el contenido de una carpeta, mientras que la propiedad Path no devolverá algunos archivos multimedia.</span><span class="sxs-lookup"><span data-stu-id="f01d5-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="f01d5-111">Antes de ejecutar una colección de destino</span><span class="sxs-lookup"><span data-stu-id="f01d5-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="f01d5-112">Debe ser miembro del grupo de roles Administrador de exhibición de documentos electrónicos en el Centro de seguridad y & cumplimiento para ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f01d5-112">You have to be a member of the eDiscovery Manager role group in Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="f01d5-113">Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f01d5-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f01d5-114">También debe tener asignado el rol Destinatarios de correo en su Exchange Online organización.</span><span class="sxs-lookup"><span data-stu-id="f01d5-114">You also have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="f01d5-115">Esto es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics,** que se incluye en el script.</span><span class="sxs-lookup"><span data-stu-id="f01d5-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="f01d5-116">De forma predeterminada, el rol Destinatarios de correo se asigna a los grupos de roles Administración de la organización y Administración de destinatarios en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f01d5-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="f01d5-117">Para obtener más información acerca de cómo asignar permisos en Exchange Online, vea [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="f01d5-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help).</span></span> <span data-ttu-id="f01d5-118">También puede crear un grupo de roles personalizado, asignarle el rol Destinatarios de correo y, a continuación, agregar los miembros que necesitan ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f01d5-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="f01d5-119">Para obtener más información, consulte [Administrar grupos de roles](/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="f01d5-119">For more information, see [Manage role groups](/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="f01d5-120">El script de este artículo admite la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="f01d5-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="f01d5-121">Puede usar el script tal como está si es un Microsoft 365 o una Microsoft 365 GCC organización.</span><span class="sxs-lookup"><span data-stu-id="f01d5-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="f01d5-122">Si es una organización de Office 365 Alemania, una organización de Microsoft 365 GCC High o una organización de Microsoft 365 DoD, tendrá que editar el script para ejecutarlo correctamente.</span><span class="sxs-lookup"><span data-stu-id="f01d5-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="f01d5-123">En concreto, debe editar la línea y usar el parámetro `Connect-ExchangeOnline` *ExchangeEnvironmentName* (y el valor adecuado para el tipo de organización) para conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f01d5-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="f01d5-124">Además, debe editar la línea y usar los parámetros ConnectionUri y `Connect-IPPSSession` *AzureADAuthorizationEndpointUri* (y los valores adecuados para el tipo de organización) para conectarse a *PowerShell* del Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f01d5-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="f01d5-125">Para obtener más información, vea los ejemplos de Conectar para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) y Conectar a PowerShell del Centro de [& de seguridad.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="f01d5-125">For more information, see the examples in [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="f01d5-126">Cada vez que ejecuta el script, se crea una nueva sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f01d5-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="f01d5-127">Esto significa que puede usar todas las sesiones remotas de PowerShell disponibles.</span><span class="sxs-lookup"><span data-stu-id="f01d5-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="f01d5-128">Para evitar que esto suceda, ejecute el siguiente comando para desconectar las sesiones de PowerShell remotas activas.</span><span class="sxs-lookup"><span data-stu-id="f01d5-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="f01d5-129">Para obtener más información, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f01d5-129">For more information, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f01d5-130">El script incluye un control de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="f01d5-130">The script includes minimal error handling.</span></span> <span data-ttu-id="f01d5-131">El propósito principal del script es mostrar rápidamente una lista de los IDs de carpeta de buzones o rutas de acceso de sitio que se pueden usar en la sintaxis de consulta de búsqueda de una búsqueda de contenido para realizar una colección de destino.</span><span class="sxs-lookup"><span data-stu-id="f01d5-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="f01d5-132">El script de ejemplo proporcionado en este tema no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f01d5-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="f01d5-133">El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="f01d5-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="f01d5-134">Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito.</span><span class="sxs-lookup"><span data-stu-id="f01d5-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="f01d5-135">Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya.</span><span class="sxs-lookup"><span data-stu-id="f01d5-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="f01d5-136">En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.</span><span class="sxs-lookup"><span data-stu-id="f01d5-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="f01d5-137">Paso 1: Ejecutar el script para obtener una lista de carpetas para un buzón o sitio</span><span class="sxs-lookup"><span data-stu-id="f01d5-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="f01d5-138">El script que ejecute en este primer paso devolverá una lista de carpetas de buzones de correo o carpetas SharePoint y OneDrive para la Empresa carpetas, y el identificador de carpeta o ruta de acceso correspondiente para cada carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="f01d5-139">Al ejecutar este script, se le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="f01d5-139">When you run this script, it will prompt you for the following information.</span></span>

- <span data-ttu-id="f01d5-140">**Dirección de correo electrónico o dirección URL** del sitio: escriba una dirección de correo electrónico del custodio para devolver una lista de Exchange carpetas de buzones de correo e IDs de carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="f01d5-141">O escriba la dirección URL de un SharePoint o un sitio OneDrive para la Empresa para devolver una lista de rutas de acceso para el sitio especificado.</span><span class="sxs-lookup"><span data-stu-id="f01d5-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="f01d5-142">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="f01d5-142">Here are some examples:</span></span>

  - <span data-ttu-id="f01d5-143">**Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com</span><span class="sxs-lookup"><span data-stu-id="f01d5-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="f01d5-144">**SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="f01d5-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span>

  - <span data-ttu-id="f01d5-145">**OneDrive para la Empresa**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="f01d5-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span>

- <span data-ttu-id="f01d5-146">**Sus credenciales de usuario:** el script usará sus credenciales para conectarse Exchange Online PowerShell o Security & Compliance Center PowerShell mediante la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="f01d5-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="f01d5-147">Como se explicó anteriormente, debe tener asignados los permisos adecuados para ejecutar correctamente este script.</span><span class="sxs-lookup"><span data-stu-id="f01d5-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="f01d5-148">Para mostrar una lista de carpetas de buzones o nombres de vínculo de documento de sitio (ruta de acceso):</span><span class="sxs-lookup"><span data-stu-id="f01d5-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>

1. <span data-ttu-id="f01d5-149">Guarde el texto siguiente en un archivo Windows PowerShell script mediante un sufijo de nombre de archivo de .ps1; por ejemplo, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="f01d5-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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

2. <span data-ttu-id="f01d5-150">En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="f01d5-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="f01d5-151">Ejecute el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f01d5-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="f01d5-152">Escriba la información que el script le pida.</span><span class="sxs-lookup"><span data-stu-id="f01d5-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="f01d5-153">El script muestra una lista de carpetas de buzones o carpetas de sitio para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="f01d5-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="f01d5-154">Deje esta ventana abierta para poder copiar un identificador de carpeta o un nombre de vínculo de documento y pegarlo en una consulta de búsqueda en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f01d5-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="f01d5-155">En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede volver a dirigir el resultado del script a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f01d5-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="f01d5-156">Este archivo se guardará en la carpeta donde se encuentra el script.</span><span class="sxs-lookup"><span data-stu-id="f01d5-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="f01d5-157">Por ejemplo, para redirigir el resultado del script a un archivo de texto, ejecute el siguiente comando en Paso 3: A continuación, puede copiar un identificador de carpeta o un vínculo de documento del archivo para usarlo en una consulta de  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f01d5-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>

### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="f01d5-158">Salida de script para carpetas de buzones</span><span class="sxs-lookup"><span data-stu-id="f01d5-158">Script output for mailbox folders</span></span>

<span data-ttu-id="f01d5-159">Si va a obtener id. de carpeta de buzón, el script se conecta Exchange Online PowerShell, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de carpetas del buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="f01d5-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="f01d5-160">Para cada carpeta del buzón, el script muestra el nombre de la carpeta en la columna **FolderPath** y el identificador de carpeta en la **columna FolderQuery.**</span><span class="sxs-lookup"><span data-stu-id="f01d5-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="f01d5-161">Además, el script agrega el prefijo **de folderId** (que es el nombre de la propiedad mailbox) al identificador de carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="f01d5-162">Dado que **la propiedad folderid** es una propiedad que se puede buscar, usará en una consulta de búsqueda del paso  `folderid:<folderid>` 2 para buscar en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="f01d5-163">El script muestra un máximo de 100 carpetas de buzones.</span><span class="sxs-lookup"><span data-stu-id="f01d5-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f01d5-164">El script de este artículo incluye lógica de codificación que convierte los valores de id. de carpeta de 64 caracteres devueltos por **Get-MailboxFolderStatistics** al mismo formato de 48 caracteres que se indiza para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f01d5-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="f01d5-165">Si acaba de ejecutar el cmdlet **Get-MailboxFolderStatistics** en PowerShell para obtener un identificador de carpeta (en lugar de ejecutar el script en este artículo), se producirá un error en una consulta de búsqueda que use ese valor id de carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="f01d5-166">Debe ejecutar el script para obtener los identificadores de carpeta con el formato correcto que se pueden usar en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f01d5-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>

<span data-ttu-id="f01d5-167">Este es un ejemplo de la salida devuelta por el script para carpetas de buzones.</span><span class="sxs-lookup"><span data-stu-id="f01d5-167">Here's an example of the output returned by the script for mailbox folders.</span></span>

![Ejemplo de la lista de carpetas de buzones e IDs de carpetas devueltos por el script](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

<span data-ttu-id="f01d5-169">El ejemplo del paso 2 muestra la consulta usada para buscar en la subcarpeta Purgas de la carpeta Elementos recuperables del usuario.</span><span class="sxs-lookup"><span data-stu-id="f01d5-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>

### <a name="script-output-for-site-folders"></a><span data-ttu-id="f01d5-170">Salida de script para carpetas de sitio</span><span class="sxs-lookup"><span data-stu-id="f01d5-170">Script output for site folders</span></span>

<span data-ttu-id="f01d5-171">Si está obteniendo la ruta de acceso de la propiedad **documentlink** de sitios de SharePoint o OneDrive para la Empresa, el script se conecta a PowerShell de cumplimiento de seguridad &, crea una nueva búsqueda de contenido que busca carpetas en el sitio y, a continuación, muestra una lista de las carpetas ubicadas en el sitio especificado.</span><span class="sxs-lookup"><span data-stu-id="f01d5-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="f01d5-172">El script muestra el nombre de cada carpeta y agrega el prefijo **de documentlink** a la dirección URL de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="f01d5-173">Dado que **la propiedad documentlink** es una propiedad que se puede buscar, usará el par property:value en una consulta de búsqueda en el paso `documentlink:<path>` 2 para buscar en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="f01d5-174">El script muestra un máximo de 200 carpetas de sitio.</span><span class="sxs-lookup"><span data-stu-id="f01d5-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="f01d5-175">Si hay más de 200 carpetas de sitio, se muestran las más nuevas.</span><span class="sxs-lookup"><span data-stu-id="f01d5-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>

<span data-ttu-id="f01d5-176">Este es un ejemplo de la salida devuelta por el script para las carpetas del sitio.</span><span class="sxs-lookup"><span data-stu-id="f01d5-176">Here's an example of the output returned by the script for site folders.</span></span>

![Ejemplo de la lista de nombres de vínculo de documento para carpetas de sitio devueltas por el script](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="f01d5-178">Paso 2: Usar un identificador de carpeta o un vínculo de documento para realizar una colección de destino</span><span class="sxs-lookup"><span data-stu-id="f01d5-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="f01d5-179">Después de ejecutar el script para recopilar una lista de id. de carpeta o vínculos de documentos para un usuario específico, el siguiente paso para ir al Centro de cumplimiento de Microsoft 365 y crear una nueva búsqueda de contenido para buscar en una carpeta específica.</span><span class="sxs-lookup"><span data-stu-id="f01d5-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="f01d5-180">Usará el par or property:value en la consulta de búsqueda que configure en el cuadro de palabra clave Búsqueda de contenido (o como el valor del parámetro ContentMatchQuery si usa el `folderid:<folderid>` `documentlink:<path>` cmdlet **New-ComplianceSearch).** </span><span class="sxs-lookup"><span data-stu-id="f01d5-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="f01d5-181">Puede combinar la  `folderid` propiedad or con otros parámetros de búsqueda o condiciones de  `documentlink` búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f01d5-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="f01d5-182">Si solo incluye la propiedad or en la consulta, la búsqueda devolverá todos los  `folderid`  `documentlink` elementos ubicados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="f01d5-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>

1. <span data-ttu-id="f01d5-183">Vaya a e inicie sesión con la cuenta y las credenciales que <https://compliance.microsoft.com> usó para ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f01d5-183">Go to <https://compliance.microsoft.com> and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="f01d5-184">En el panel izquierdo del centro de cumplimiento, haga clic **en Mostrar toda** la búsqueda de contenido y, a continuación, haga clic en Nueva  >   **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="f01d5-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="f01d5-185">En el **cuadro Palabras clave,** pegue el `folderid:<folderid>` valor o devuelto por el script en el paso  `documentlink:<path>` 1.</span><span class="sxs-lookup"><span data-stu-id="f01d5-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="f01d5-186">Por ejemplo, la consulta de la siguiente captura de pantalla buscará cualquier elemento de la subcarpeta Purgas de la carpeta Elementos recuperables del usuario (el valor de la propiedad de la subcarpeta Purgas se muestra en la captura de pantalla del paso `folderid` 1):</span><span class="sxs-lookup"><span data-stu-id="f01d5-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Pegue el folderid o documentlink en el cuadro de palabra clave de la consulta de búsqueda](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="f01d5-188">En **Ubicaciones**, seleccione **Ubicaciones específicas y,** a continuación, haga clic **en Modificar**.</span><span class="sxs-lookup"><span data-stu-id="f01d5-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="f01d5-189">Realice una de las siguientes acciones, en función de si está buscando en una carpeta de buzón o en una carpeta de sitio:</span><span class="sxs-lookup"><span data-stu-id="f01d5-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="f01d5-190">Junto a Exchange correo electrónico, haga clic en Elegir usuarios, grupos o equipos **y,** **a** continuación, agregue el mismo buzón que especificó al ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f01d5-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="f01d5-191">O bien</span><span class="sxs-lookup"><span data-stu-id="f01d5-191">Or</span></span>

    - <span data-ttu-id="f01d5-192">Junto a **SharePoint,** haga  clic en Elegir sitios y, a continuación, agregue la misma dirección URL del sitio que especificó al ejecutar el script en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f01d5-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="f01d5-193">Después de guardar la ubicación de contenido para buscar, haga clic en Guardar  **& ejecutar**, escriba un nombre para la búsqueda de contenido y, a continuación, haga clic en Guardar para iniciar la búsqueda de colección de destino.</span><span class="sxs-lookup"><span data-stu-id="f01d5-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span>

### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="f01d5-194">Ejemplos de consultas de búsqueda para colecciones dirigidas</span><span class="sxs-lookup"><span data-stu-id="f01d5-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="f01d5-195">Estos son algunos ejemplos del uso de las  `folderid` propiedades y de una consulta de búsqueda para realizar una colección de  `documentlink` destino.</span><span class="sxs-lookup"><span data-stu-id="f01d5-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="f01d5-196">Los marcadores de posición se usan  `folderid:<folderid>` para y para ahorrar  `documentlink:<path>` espacio.</span><span class="sxs-lookup"><span data-stu-id="f01d5-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span>

- <span data-ttu-id="f01d5-197">En este ejemplo se buscan tres carpetas de buzones diferentes.</span><span class="sxs-lookup"><span data-stu-id="f01d5-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="f01d5-198">Puede usar una sintaxis de consulta similar para buscar en las carpetas ocultas de la carpeta Elementos recuperables de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f01d5-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="f01d5-199">En este ejemplo se busca en una carpeta de buzones los elementos que contienen una frase exacta.</span><span class="sxs-lookup"><span data-stu-id="f01d5-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="f01d5-200">En este ejemplo se busca en una carpeta de sitio (y en cualquier subcarpeta) documentos que contengan las letras "NDA" en el título.</span><span class="sxs-lookup"><span data-stu-id="f01d5-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="f01d5-201">En este ejemplo se busca en una carpeta de sitio (y en cualquier subcarpeta) los documentos que se modificaron dentro de un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="f01d5-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="f01d5-202">Más información</span><span class="sxs-lookup"><span data-stu-id="f01d5-202">More information</span></span>

<span data-ttu-id="f01d5-203">Tenga en cuenta lo siguiente al usar el script de este artículo para realizar colecciones dirigidas.</span><span class="sxs-lookup"><span data-stu-id="f01d5-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>

- <span data-ttu-id="f01d5-204">El script no quita ninguna carpeta de los resultados.</span><span class="sxs-lookup"><span data-stu-id="f01d5-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="f01d5-205">Por lo tanto, algunas carpetas enumeradas en los resultados pueden no ser aptos para la búsqueda (o devolver cero elementos) porque contienen contenido generado por el sistema o porque solo contienen subcarpetas y no elementos de buzón.</span><span class="sxs-lookup"><span data-stu-id="f01d5-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="f01d5-206">Este script solo devuelve información de carpeta para el buzón principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="f01d5-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="f01d5-207">No devuelve información sobre carpetas en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="f01d5-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="f01d5-208">Para devolver información acerca de las carpetas en el buzón de archivo del usuario, puede editar el script.</span><span class="sxs-lookup"><span data-stu-id="f01d5-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="f01d5-209">Para ello, cambie la línea a y, a `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` continuación, guarde y ejecute el script editado.</span><span class="sxs-lookup"><span data-stu-id="f01d5-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="f01d5-210">Este cambio devolverá los id. de carpeta para carpetas y subcarpetas en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="f01d5-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="f01d5-211">Para buscar en todo el buzón de archivo, puede conectar todos los pares property:value de id. de carpeta con un `OR` operador en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f01d5-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="f01d5-212">Al buscar carpetas de buzones de correo, solo se buscará la carpeta especificada (identificada por su propiedad); no se buscarán `folderid` subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="f01d5-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="f01d5-213">Para buscar subcarpetas, debe usar el identificador de carpeta para la subcarpeta que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="f01d5-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="f01d5-214">Al buscar carpetas de sitio, se buscará la carpeta (identificada por su propiedad) y todas `documentlink` las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="f01d5-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span>

- <span data-ttu-id="f01d5-215">Al exportar los resultados de una búsqueda en la que solo especificó la propiedad en la consulta de búsqueda, puede elegir la primera opción de exportación: "Todos los elementos, excepto los que tienen un formato no reconocido, están cifrados o no se indizaron por otros `folderid` motivos".</span><span class="sxs-lookup"><span data-stu-id="f01d5-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="f01d5-216">Todos los elementos de la carpeta siempre se exportarán independientemente de su estado de indización porque el identificador de carpeta siempre está indizado.</span><span class="sxs-lookup"><span data-stu-id="f01d5-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
