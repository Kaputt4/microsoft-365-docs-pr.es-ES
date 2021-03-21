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
description: Use la búsqueda de contenido y el script de este artículo para buscar en los buzones y los sitios de OneDrive para la Empresa un grupo de usuarios.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922472"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Usar búsqueda de contenido para buscar una lista de usuarios en el buzón y el sitio de OneDrive para la Empresa

El Centro de & seguridad proporciona una serie de cmdlets Windows PowerShell que le permiten automatizar tareas relacionadas con la exhibición de documentos electrónicos que requieren mucho tiempo. Actualmente, la creación de una búsqueda de contenido en el Centro de seguridad & cumplimiento para buscar un gran número de ubicaciones de contenido de custodia lleva tiempo y preparación. Antes de crear una búsqueda, debe recopilar la dirección URL de cada sitio de OneDrive para la Empresa y, a continuación, agregar cada buzón y sitio de OneDrive para la Empresa a la búsqueda. En versiones futuras, esto será más fácil de hacer en el Centro de seguridad & cumplimiento. Hasta entonces, puede usar el script de este artículo para automatizar este proceso. Este script solicita el nombre del dominio MySite de la organización (por ejemplo, **contoso** en la dirección URL), una lista de direcciones de correo electrónico de usuario, el nombre de la nueva búsqueda de contenido y la consulta de búsqueda que se va `https://contoso-my.sharepoint.com` a usar. El script obtiene la dirección URL de OneDrive para la Empresa para cada usuario de la lista y, a continuación, crea e inicia una búsqueda de contenido que busca en el buzón y en el sitio de OneDrive para la Empresa para cada usuario de la lista, mediante la consulta de búsqueda que proporcione.
  
## <a name="permissions-and-script-information"></a>Permisos e información de script

- Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & y un administrador global de SharePoint Online para ejecutar el script en el paso 3.

- Asegúrese de guardar la lista de usuarios que cree en el paso 2 y el script del paso 3 en la misma carpeta. Esto facilitará la ejecución del script.

- El script incluye un control de errores mínimo. Su objetivo principal es buscar de forma rápida y sencilla el buzón y el sitio de OneDrive para la Empresa de cada usuario.

- Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Paso 1: Instalar el Shell de administración de SharePoint Online

El primer paso es instalar el Shell de administración de SharePoint Online. No es necesario usar el shell en este procedimiento, pero debe instalarlo porque contiene los requisitos previos requeridos por el script que ejecuta en el paso 3. Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la Empresa.
  
Vaya a Configurar el entorno del Shell de administración de [SharePoint Online Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y realice los pasos 1 y 2 para instalar el Shell de administración de SharePoint Online.
  
## <a name="step-2-generate-a-list-of-users"></a>Paso 2: Generar una lista de usuarios

El script del paso 3 creará una búsqueda de contenido para buscar en los buzones y cuentas de OneDrive una lista de usuarios. Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).
  
Este es un comando de [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) de Exchange Online que puede ejecutar para obtener una lista de direcciones de correo electrónico para todos los usuarios de su organización y guardarlo en un archivo de texto denominado `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Después de ejecutar este comando, asegúrese de abrir el archivo y quitar el encabezado que contiene el nombre de la propiedad,  `PrimarySmtpAddress` . El archivo de texto solo debe contener una lista de direcciones de correo electrónico y nada más. Asegúrese de que no hay filas en blanco antes o después de la lista de direcciones de correo electrónico.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Paso 3: Ejecutar el script para crear e iniciar la búsqueda

Al ejecutar el script en este paso, se le pedirá la siguiente información. Asegúrese de tener esta información lista antes de ejecutar el script.
  
- **Sus credenciales de** usuario: el script usará sus credenciales para obtener acceso a SharePoint Online para obtener las direcciones URL de OneDrive para la Empresa y para conectarse al Centro de seguridad & cumplimiento con PowerShell remoto. 
    
- **Nombre del dominio de MySite:** el dominio MySite es el dominio que contiene todos los sitios de OneDrive para la Empresa de la organización. Por ejemplo, si la dirección URL del dominio de MySite es , escribiría cuando el script le pida el nombre del **https://contoso-my.sharepoint.com**  `contoso` dominio de MySite. 
    
- **Pathname del archivo de texto del paso 2:** el nombre de ruta del archivo de texto que creó en el paso 2. Si el archivo de texto y el script se encuentran en la misma carpeta, escriba el nombre del archivo de texto. De lo contrario, escriba el nombre de ruta de acceso completo para el archivo de texto. 
    
- **Nombre de la búsqueda de contenido:** el nombre de la búsqueda de contenido que creará el script. 
    
- **Consulta de búsqueda:** se crea y se ejecuta la consulta de búsqueda que se usará con la búsqueda de contenido. Para obtener más información acerca de las consultas de búsqueda, vea [Consultas de palabras clave y condiciones de búsqueda para Búsqueda de contenido](keyword-queries-and-search-conditions.md).


**Para ejecutar el script:**
    
1. Guarde el texto siguiente en un archivo Windows PowerShell script mediante un sufijo de nombre de archivo de .ps1; por ejemplo, `SearchEXOOD4B.ps1` . Guarde el archivo en la misma carpeta donde guardó la lista de usuarios en el paso 2.
    
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

2. Abra Windows PowerShell y vaya a la carpeta donde guardó el script y la lista de usuarios del paso 2.
    
3. Inicie el script; por ejemplo:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Cuando se le pidan sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar**. 
    
5. Escriba la siguiente información cuando se lo pida el script. Escriba cada fragmento de información y, a continuación, presione **ENTRAR**.
    
    - El nombre del dominio de MySite. 
    
    - Pathname del archivo de texto que contiene la lista de usuarios.
    
    - Un nombre para la búsqueda de contenido.
    
    - La consulta de búsqueda (deje esto en blanco para devolver todos los elementos de las ubicaciones de contenido).
    
    El script obtiene las direcciones URL de cada sitio de OneDrive para la Empresa y, a continuación, crea e inicia la búsqueda. Puede ejecutar el cmdlet **Get-ComplianceSearch** en PowerShell del Centro de seguridad & cumplimiento para mostrar las  estadísticas y los resultados de la búsqueda, o bien puede ir a la página Búsqueda de contenido en el Centro de seguridad & cumplimiento para ver información sobre la búsqueda.