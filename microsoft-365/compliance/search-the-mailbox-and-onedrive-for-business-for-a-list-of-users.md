---
title: Buscar en el buzón & sitio de OneDrive para la Empresa para obtener una lista de usuarios con búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Use la búsqueda de contenido y el script de este artículo para buscar un grupo de usuarios en los buzones y los sitios de OneDrive para la Empresa.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e3a10913cc4d8618e3d25bdf34e30c9d55a43324
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357802"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="f7b91-103">Usar búsqueda de contenido para buscar una lista de usuarios en el buzón y el sitio de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="f7b91-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="f7b91-104">El Centro de & cumplimiento proporciona una serie de cmdlets Windows PowerShell que le permiten automatizar tareas relacionadas con la exhibición de documentos electrónicos que requieren mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="f7b91-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="f7b91-105">Actualmente, la creación de una búsqueda de contenido en el Centro de seguridad & cumplimiento para buscar un gran número de ubicaciones de contenido de administrador requiere tiempo y preparación.</span><span class="sxs-lookup"><span data-stu-id="f7b91-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="f7b91-106">Antes de crear una búsqueda, debe recopilar la dirección URL de cada sitio de OneDrive para la Empresa y, a continuación, agregar cada buzón y el sitio de OneDrive para la Empresa a la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f7b91-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="f7b91-107">En futuras versiones, será más fácil hacerlo en el Centro de seguridad y & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f7b91-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="f7b91-108">Hasta entonces, puede usar el script de este artículo para automatizar este proceso.</span><span class="sxs-lookup"><span data-stu-id="f7b91-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="f7b91-109">Este script le solicita el nombre del dominio de MiSitio de su organización (por ejemplo, **contoso** en la dirección URL), una lista de direcciones de correo electrónico de usuario, el nombre de la nueva búsqueda de contenido y la consulta de búsqueda que se va `https://contoso-my.sharepoint.com` a usar.</span><span class="sxs-lookup"><span data-stu-id="f7b91-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="f7b91-110">El script obtiene la dirección URL de OneDrive para la Empresa para cada usuario de la lista y, a continuación, crea e inicia una búsqueda de contenido que busca en el buzón y en el sitio de OneDrive para la Empresa para cada usuario de la lista, mediante la consulta de búsqueda que proporcione.</span><span class="sxs-lookup"><span data-stu-id="f7b91-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="f7b91-111">Permisos e información de script</span><span class="sxs-lookup"><span data-stu-id="f7b91-111">Permissions and script information</span></span>

- <span data-ttu-id="f7b91-112">Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & y un administrador global de SharePoint Online para ejecutar el script en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f7b91-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="f7b91-113">Asegúrese de guardar la lista de usuarios que crea en el paso 2 y el script del paso 3 en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="f7b91-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="f7b91-114">Esto facilitará la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="f7b91-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="f7b91-115">El script incluye un control de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="f7b91-115">The script includes minimal error handling.</span></span> <span data-ttu-id="f7b91-116">Su propósito principal es buscar rápida y fácilmente el buzón de correo y el sitio de OneDrive para la Empresa de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="f7b91-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="f7b91-p104">Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.</span><span class="sxs-lookup"><span data-stu-id="f7b91-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="f7b91-122">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7b91-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="f7b91-123">El primer paso es instalar el Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f7b91-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="f7b91-124">No es necesario usar el shell en este procedimiento, pero tiene que instalarlo porque contiene los requisitos previos requeridos por el script que se ejecuta en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f7b91-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="f7b91-125">Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="f7b91-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="f7b91-126">Vaya a Configurar el entorno del Shell de administración de [SharePoint Online Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice los pasos 1 y 2 para instalar el Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f7b91-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="f7b91-127">Paso 2: Generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="f7b91-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="f7b91-128">El script del paso 3 creará una búsqueda de contenido para buscar en los buzones y cuentas de OneDrive una lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f7b91-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="f7b91-129">Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="f7b91-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="f7b91-130">Este es un comando de [PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) de Exchange Online que puede ejecutar para obtener una lista de direcciones de correo electrónico para todos los usuarios de su organización y guardarlo en un archivo de texto denominado `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="f7b91-130">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="f7b91-131">Después de ejecutar este comando, asegúrese de abrir el archivo y quitar el encabezado que contiene el nombre de  `PrimarySmtpAddress` propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7b91-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="f7b91-132">El archivo de texto solo debe contener una lista de direcciones de correo electrónico y nada más.</span><span class="sxs-lookup"><span data-stu-id="f7b91-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="f7b91-133">Asegúrese de que no hay filas en blanco antes o después de la lista de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f7b91-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="f7b91-134">Paso 3: Ejecutar el script para crear e iniciar la búsqueda</span><span class="sxs-lookup"><span data-stu-id="f7b91-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="f7b91-135">Cuando ejecute el script en este paso, se le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="f7b91-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="f7b91-136">Asegúrese de tener esta información lista antes de ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="f7b91-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="f7b91-137">**Sus credenciales de** usuario: el script usará sus credenciales para obtener acceso a SharePoint Online para obtener las direcciones URL de OneDrive para la Empresa y conectarse al Centro de seguridad & Cumplimiento con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="f7b91-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="f7b91-138">**Nombre de su dominio de MiSitio:** el dominio de MiSitio es el dominio que contiene todos los sitios de OneDrive para la Empresa de su organización.</span><span class="sxs-lookup"><span data-stu-id="f7b91-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="f7b91-139">Por ejemplo, si la dirección URL del dominio de MiSitio es , escribiría cuando el script le pida el nombre del **https://contoso-my.sharepoint.com**  `contoso` dominio de MiSitio.</span><span class="sxs-lookup"><span data-stu-id="f7b91-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="f7b91-140">Nombre de la ruta de acceso del archivo de **texto del paso 2:** el nombre de la ruta de acceso del archivo de texto que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f7b91-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="f7b91-141">Si el archivo de texto y el script se encuentran en la misma carpeta, escriba el nombre del archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f7b91-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="f7b91-142">De lo contrario, escriba el nombre de ruta de acceso completo para el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f7b91-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="f7b91-143">**Nombre de la búsqueda de contenido:** nombre de la búsqueda de contenido que creará el script.</span><span class="sxs-lookup"><span data-stu-id="f7b91-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="f7b91-144">**Consulta de búsqueda:** se crea y ejecuta la consulta de búsqueda que se usará con la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f7b91-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="f7b91-145">Para obtener más información acerca de las consultas de búsqueda, vea Consultas de palabras clave y [condiciones de búsqueda para búsqueda de contenido.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="f7b91-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="f7b91-146">**Para ejecutar el script:**</span><span class="sxs-lookup"><span data-stu-id="f7b91-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="f7b91-147">Guarde el siguiente texto en un archivo de script Windows PowerShell nombre de archivo con el sufijo de nombre de archivo .ps1; por ejemplo, `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="f7b91-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="f7b91-148">Guarde el archivo en la misma carpeta donde guardó la lista de usuarios en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f7b91-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="f7b91-149">Abra Windows PowerShell y vaya a la carpeta donde guardó el script y la lista de usuarios del paso 2.</span><span class="sxs-lookup"><span data-stu-id="f7b91-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="f7b91-150">Inicie el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7b91-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="f7b91-151">Cuando se le soliciten sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="f7b91-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="f7b91-152">Escriba la siguiente información cuando se lo pida el script.</span><span class="sxs-lookup"><span data-stu-id="f7b91-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="f7b91-153">Escriba cada información y, a continuación, presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="f7b91-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="f7b91-154">El nombre del dominio de MiSitio.</span><span class="sxs-lookup"><span data-stu-id="f7b91-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="f7b91-155">Nombre de ruta de acceso del archivo de texto que contiene la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f7b91-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="f7b91-156">Un nombre para la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="f7b91-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="f7b91-157">La consulta de búsqueda (deje esto en blanco para devolver todos los elementos de las ubicaciones de contenido).</span><span class="sxs-lookup"><span data-stu-id="f7b91-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="f7b91-158">El script obtiene las direcciones URL de cada sitio de OneDrive para la Empresa y, a continuación, crea e inicia la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f7b91-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="f7b91-159">Puede ejecutar el cmdlet **Get-ComplianceSearch** en PowerShell del Centro de seguridad & Cumplimiento para mostrar las  estadísticas y los resultados de la búsqueda, o puede ir a la página Búsqueda de contenido en el Centro de seguridad y cumplimiento de & para ver información sobre la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f7b91-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span> 
