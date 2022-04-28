---
title: Uso de la búsqueda de contenido para colecciones de destino
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Use búsqueda de contenido en el portal de cumplimiento de Microsoft Purview para realizar una colección de destino, que busca elementos en un buzón o carpeta de sitio específico.
ms.openlocfilehash: 396c42183667e59e738779f618ca077d909db419
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094932"
---
# <a name="use-content-search-for-targeted-collections"></a>Uso de la búsqueda de contenido para colecciones de destino

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La herramienta de búsqueda de contenido del portal de cumplimiento de Microsoft Purview no proporciona una forma directa en la interfaz de usuario de buscar carpetas específicas en buzones de Exchange o SharePoint y sitios de OneDrive para la Empresa. Sin embargo, es posible buscar carpetas específicas ( *denominadas colección de destino*) especificando la propiedad id. de carpeta para el correo electrónico o la propiedad path (DocumentLink) para los sitios en la sintaxis de consulta de búsqueda real. El uso de búsqueda de contenido para realizar una colección de destino es útil cuando está seguro de que los elementos que responden a un caso o elementos con privilegios se encuentran en un buzón de correo o carpeta de sitio específico. Puede usar el script de este artículo para obtener el identificador de carpeta de las carpetas de buzón o la ruta de acceso (DocumentLink) para las carpetas de un sitio SharePoint y OneDrive para la Empresa. A continuación, puede usar el identificador de carpeta o la ruta de acceso en una consulta de búsqueda para devolver los elementos ubicados en la carpeta.

> [!NOTE]
> Para devolver contenido ubicado en una carpeta de un sitio SharePoint o OneDrive para la Empresa, el script de este tema usa la propiedad administrada DocumentLink en lugar de la propiedad Path. La propiedad DocumentLink es más sólida que la propiedad Path porque devolverá todo el contenido de una carpeta, mientras que la propiedad Path no devolverá algunos archivos multimedia.

## <a name="before-you-run-a-targeted-collection"></a>Antes de ejecutar una colección de destino

- Debe ser miembro del grupo de roles administrador de eDiscovery en el portal de cumplimiento para ejecutar el script en el paso 1. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md).

- También tiene que tener asignado el rol Destinatarios de correo en la organización de Exchange Online. Esto es necesario para ejecutar el cmdlet **Get-MailboxFolderStatistics** , que se incluye en el script. De forma predeterminada, el rol Destinatarios de correo se asigna a los grupos de roles Administración de la organización y Administración de destinatarios en Exchange Online. Para obtener más información sobre cómo asignar permisos en Exchange Online, vea [Administrar miembros del grupo de roles](/exchange/manage-role-group-members-exchange-2013-help). También puede crear un grupo de roles personalizado, asignarle el rol Destinatarios de correo y, a continuación, agregar los miembros que necesitan ejecutar el script en el paso 1. Para obtener más información, consulte [Administrar grupos de roles](/Exchange/permissions-exo/role-groups).

- El script de este artículo admite la autenticación moderna. Puede usar el script tal como está si es un Microsoft 365 o una organización Microsoft 365 GCC. Si es una organización Office 365 Alemania, una organización Microsoft 365 GCC High o una organización Microsoft 365 DoD, tendrá que editar el script para ejecutarlo correctamente. En concreto, tiene que editar la línea `Connect-ExchangeOnline` y usar el parámetro *ExchangeEnvironmentName* (y el valor adecuado para el tipo de organización) para conectarse a Exchange Online PowerShell.  Además, tiene que editar la línea `Connect-IPPSSession` y usar los parámetros *ConnectionUri* y *AzureADAuthorizationEndpointUri* (y los valores adecuados para el tipo de organización) para conectarse a PowerShell security & Compliance Center. Para obtener más información, consulte los ejemplos de [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) y [Conectar a PowerShell del Centro de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).

- Cada vez que se ejecuta el script, se crea una nueva sesión remota de PowerShell. Esto significa que puede usar todas las sesiones remotas de PowerShell disponibles. Para evitar que esto suceda, ejecute el siguiente comando para desconectar las sesiones de PowerShell remotas activas.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Para obtener más información, vea [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- El script incluye un control mínimo de errores. El propósito principal del script es mostrar rápidamente una lista de identificadores de carpeta de buzón o rutas de acceso de sitio que se pueden usar en la sintaxis de consulta de búsqueda de una búsqueda de contenido para realizar una colección de destino.

- El script de ejemplo proporcionado en este tema no se admite en ningún programa o servicio de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Paso 1: Ejecutar el script para obtener una lista de carpetas para un buzón o sitio

El script que ejecute en este primer paso devolverá una lista de carpetas de buzón de correo o SharePoint y OneDrive para la Empresa carpetas, así como el identificador de carpeta o la ruta de acceso correspondientes para cada carpeta. Al ejecutar este script, se le pedirá la siguiente información.

- **Dirección de correo electrónico o dirección URL del sitio**: escriba una dirección de correo electrónico del custodio para devolver una lista de carpetas y identificadores de carpeta de Exchange buzón. O bien, escriba la dirección URL de un sitio de SharePoint o un sitio de OneDrive para la Empresa para devolver una lista de rutas de acceso para el sitio especificado. Estos son algunos ejemplos:

  - **Exchange**:`stacig@contoso.onmicrosoft.com`

  - **SharePoint**:`https://contoso.sharepoint.com/sites/marketing`

  - **OneDrive para la Empresa**:`https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com`

- **Credenciales de usuario**: el script usará sus credenciales para conectarse a Exchange Online PowerShell o PowerShell del Centro de cumplimiento de seguridad & mediante la autenticación moderna. Como se explicó anteriormente, debe tener asignados los permisos adecuados para ejecutar correctamente este script.

Para mostrar una lista de carpetas de buzón o nombres de vínculo de documento de sitio (ruta de acceso):

1. Guarde el texto siguiente en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1; por ejemplo, `GetFolderSearchParameters.ps1`.

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the compliance portal.            #
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
   # Authenticate with Exchange Online and the compliance portal (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline -ShowBanner:$false -CommandName Get-MailboxFolderStatistics
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

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.

3. Ejecute el script; por ejemplo:

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. Escriba la información que le pide el script.

    El script muestra una lista de carpetas de buzón o carpetas de sitio para el usuario especificado. Deje esta ventana abierta para que pueda copiar un identificador de carpeta o un nombre de vínculo de documento y pegarlo en una consulta de búsqueda en el paso 2.

    > [!TIP]
    > En lugar de mostrar una lista de carpetas en la pantalla del equipo, puede volver a dirigir la salida del script a un archivo de texto. Este archivo se guardará en la carpeta donde se encuentra el script. Por ejemplo, para redirigir la salida del script a un archivo de texto, ejecute el siguiente comando en Paso 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` A continuación, puede copiar un identificador de carpeta o un vínculo de documento del archivo para usarlo en una consulta de búsqueda.

### <a name="script-output-for-mailbox-folders"></a>Salida de script para carpetas de buzón

Si va a obtener identificadores de carpeta de buzón, el script se conecta a Exchange Online PowerShell, ejecuta el cmdlet **Get-MailboxFolderStatisics** y, a continuación, muestra la lista de carpetas del buzón especificado. Para cada carpeta del buzón de correo, el script muestra el nombre de la carpeta en la columna **FolderPath** y el identificador de carpeta en la columna **FolderQuery** . Además, el script agrega el prefijo **folderId** (que es el nombre de la propiedad mailbox) al identificador de carpeta. Dado que la propiedad **folderid** es una propiedad que permite búsquedas, usará  `folderid:<folderid>` en una consulta de búsqueda en el paso 2 para buscar en esa carpeta. 

> [!IMPORTANT]
> El script de este artículo incluye lógica de codificación que convierte los valores de id. de carpeta de 64 caracteres **devueltos por Get-MailboxFolderStatistics** al mismo formato de 48 caracteres que se indexa para la búsqueda. Si acaba de ejecutar el cmdlet **Get-MailboxFolderStatistics** en PowerShell para obtener un identificador de carpeta (en lugar de ejecutar el script en este artículo), se producirá un error en una consulta de búsqueda que usa ese valor de id. de carpeta. Tiene que ejecutar el script para obtener los identificadores de carpeta con formato correcto que se pueden usar en una búsqueda de contenido.

Este es un ejemplo de la salida devuelta por el script para las carpetas de buzón.

![Ejemplo de la lista de carpetas de buzón de correo e identificadores de carpeta devueltos por el script.](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

En el ejemplo del paso 2 se muestra la consulta usada para buscar en la subcarpeta Purgas de la carpeta Elementos recuperables del usuario.

### <a name="script-output-for-site-folders"></a>Salida de script para carpetas de sitio

Si obtiene la ruta de acceso de la propiedad **documentlink** de SharePoint o OneDrive para la Empresa sitios, el script se conecta a PowerShell de cumplimiento de seguridad &, crea una nueva búsqueda de contenido que busca carpetas en el sitio y, a continuación, muestra una lista de las carpetas ubicadas en el sitio especificado. El script muestra el nombre de cada carpeta y agrega el prefijo de **vínculo de documento** a la dirección URL de la carpeta. Dado que la propiedad **documentlink** es una propiedad que permite búsquedas, usará `documentlink:<path>` el par property:value en una consulta de búsqueda en el paso 2 para buscar en esa carpeta. El script muestra un máximo de 100 carpetas de sitio. Si hay más de 100 carpetas de sitio, se muestran las más recientes.

Este es un ejemplo de la salida devuelta por el script para las carpetas de sitio.

![Ejemplo de la lista de nombres de vínculo de documento para las carpetas de sitio devueltas por el script.](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Paso 2: Usar un identificador de carpeta o un vínculo de documento para realizar una colección de destino

Después de ejecutar el script para recopilar una lista de identificadores de carpeta o vínculos de documentos para un usuario específico, el siguiente paso es ir al portal de cumplimiento y crear una nueva búsqueda de contenido para buscar en una carpeta específica. Usará el  `folderid:<folderid>` par o  `documentlink:<path>` property:value en la consulta de búsqueda que configure en el cuadro palabra clave Búsqueda de contenido (o como el valor del parámetro  *ContentMatchQuery*  si usa el cmdlet **New-ComplianceSearch** ). Puede combinar la  `folderid` propiedad o  `documentlink` con otros parámetros de búsqueda o condiciones de búsqueda. Si solo incluye la  `folderid` propiedad o  `documentlink` en la consulta, la búsqueda devolverá todos los elementos ubicados en la carpeta especificada.

1. Vaya a <https://compliance.microsoft.com> e inicie sesión con la cuenta y las credenciales que usó para ejecutar el script en el paso 1.

2. En el panel izquierdo del centro de cumplimiento, haga clic en **Mostrar todo** >  **Búsqueda de contenido** y, a continuación, haga clic en **Nueva búsqueda**.

3. En el cuadro **Palabras clave** , pegue el `folderid:<folderid>` valor o  `documentlink:<path>/*` devuelto por el script en el paso 1.

    Por ejemplo, la consulta de la captura de pantalla siguiente buscará cualquier elemento de la subcarpeta Purgas de la carpeta Elementos recuperables del usuario (el valor de la `folderid` propiedad para la subcarpeta Purgas se muestra en la captura de pantalla del paso 1):

    ![Pegue el folderid o documentlink en el cuadro de palabra clave de la consulta de búsqueda.](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > Las búsquedas de vínculos de documento requieren el uso de un elemento final  `asterisk '/*'`.  

4. En **Ubicaciones**, seleccione **Ubicaciones específicas** y, a continuación, haga clic en **Modificar**.

5. Realice una de las siguientes acciones, en función de si está buscando en una carpeta de buzón o en una carpeta de sitio:

    - Junto a **Exchange correo electrónico**, haga clic en **Elegir usuarios, grupos o equipos y agregue** el mismo buzón que especificó al ejecutar el script en el paso 1.

      O bien

    - Junto a **SharePoint sitios**, haga clic en **Elegir sitios** y agregue la misma dirección URL de sitio que especificó al ejecutar el script en el paso 1.

6. Después de guardar la ubicación de contenido para buscar, haga clic en **Guardar & ejecutar**, escriba un nombre para búsqueda de contenido y, a continuación, haga clic en **Guardar** para iniciar la búsqueda de recopilación de destino.

### <a name="examples-of-search-queries-for-targeted-collections"></a>Ejemplos de consultas de búsqueda para colecciones de destino

Estos son algunos ejemplos de uso de las  `folderid` propiedades y  `documentlink` en una consulta de búsqueda para realizar una colección de destino. Los marcadores de posición se usan para  `folderid:<folderid>` y  `documentlink:<path>` para ahorrar espacio.

- En este ejemplo se buscan tres carpetas de buzón diferentes. Puede usar una sintaxis de consulta similar para buscar en las carpetas ocultas en la carpeta Elementos recuperables de un usuario.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- En este ejemplo se busca en una carpeta de buzón los elementos que contienen una frase exacta.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- En este ejemplo se busca en una carpeta de sitio (y en cualquier subcarpeta) documentos que contengan las letras "NDA" en el título.

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- En este ejemplo se busca en una carpeta de sitio (y en cualquier subcarpeta) los documentos que se cambiaron dentro de un intervalo de fechas.

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Más información

Tenga en cuenta lo siguiente al usar el script de este artículo para realizar colecciones de destino.

- El script no quita ninguna carpeta de los resultados. Por lo tanto, es posible que algunas carpetas enumeradas en los resultados no puedan buscarse (o devolver cero elementos) porque contienen contenido generado por el sistema o porque solo contienen subcarpetas y no elementos de buzón.

- Este script solo devuelve información de carpeta para el buzón principal del usuario. No devuelve información sobre las carpetas del buzón de archivo del usuario. Para devolver información sobre las carpetas en el buzón de archivo del usuario, puede editar el script. Para ello, cambie la línea `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` a y, a `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` continuación, guarde y ejecute el script editado. Este cambio devolverá los identificadores de carpeta de carpetas y subcarpetas en el buzón de archivo del usuario. Para buscar en todo el buzón de archivo, puede conectar todos los pares property:value del identificador de carpeta con un `OR` operador en una consulta de búsqueda.

- Al buscar carpetas de buzón, solo se buscará la carpeta especificada (identificada por su `folderid` propiedad). No se buscarán subcarpetas. Para buscar subcarpetas, debe usar el identificador de carpeta de la subcarpeta que desea buscar.

- Al buscar carpetas de sitio, se buscará la carpeta (identificada por su `documentlink` propiedad) y todas las subcarpetas.

- Al exportar los resultados de una búsqueda en la que solo especificó la `folderid` propiedad en la consulta de búsqueda, puede elegir la primera opción de exportación: "Todos los elementos, excepto los que tienen un formato no reconocido, se cifran o no se indexan por otros motivos". Todos los elementos de la carpeta siempre se exportarán independientemente de su estado de indexación porque el identificador de carpeta siempre está indexado.
