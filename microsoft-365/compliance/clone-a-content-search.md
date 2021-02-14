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
description: Use el script de PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente en el Centro de cumplimiento de Office 365 o Microsoft 365.
ms.openlocfilehash: 9bc9329d31ae27736bdcd399c555f5d70bb9c761
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357908"
---
# <a name="clone-a-content-search"></a>Clonar una búsqueda de contenido

Crear una búsqueda de contenido en el Centro de cumplimiento en Office 365 o Microsoft 365 que busque en muchos buzones o sitios de SharePoint y OneDrive para la Empresa puede tardar un tiempo. Especificar los sitios en los que se va a buscar también puede ser propenso a errores si se escribir mal una dirección URL. Para evitar estos problemas, puede usar el script Windows PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente. Al clonar una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (como las ubicaciones de contenido y la consulta de búsqueda) que la búsqueda original. A continuación, puede editar la nueva búsqueda cambiando la consulta de palabra clave o el intervalo de fechas y ejecutarla.
  
¿Por qué clonar búsquedas de contenido?
  
- Para comparar los resultados de diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido.
    
- Para evitar tener que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda.
    
- Para reducir el tamaño de los resultados de la búsqueda. Por ejemplo, si tiene una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregar una condición de búsqueda basada en un intervalo de fechas para reducir el número de resultados de búsqueda.
  
## <a name="script-information"></a>Información de script

- Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento para ejecutar el script descrito en este tema.
    
- El script incluye un control de errores mínimo. El propósito principal del script es clonar rápidamente una búsqueda de contenido.
    
- El script crea una nueva búsqueda de contenido, pero no la inicia.
    
- Este script tiene en cuenta si la búsqueda de contenido que está clonando está asociada a un caso de exhibición de documentos electrónicos. Si la búsqueda está asociada a un caso, la nueva búsqueda también se asociará con el mismo caso. Si la búsqueda existente no está asociada a un caso,  la nueva búsqueda aparecerá en la página Búsqueda de contenido del centro de cumplimiento. 
    
- El script de ejemplo que se proporciona en este tema no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Paso 1: Ejecutar el script para clonar una búsqueda

El script de este paso creará una nueva búsqueda de contenido clonando una existente. Cuando ejecute este script, se le pedirá la siguiente información:
  
- **Sus credenciales de usuario:** el script usará sus credenciales para conectarse al Centro de seguridad & cumplimiento de su organización con Windows PowerShell. Como se indicó anteriormente, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de & compliance para ejecutar el script. 
    
- **Nombre de la búsqueda existente:** se trata de la búsqueda de contenido que desea clonar. 
    
- **El nombre** de la nueva búsqueda que se creará: si deja este valor en blanco, el script creará un nombre para la nueva búsqueda que se basa en el nombre de la búsqueda que está clonando. 
    
Para clonar una búsqueda:
  
1. Guarde el siguiente texto en un archivo Windows PowerShell de script con un sufijo de nombre de archivo de .ps1; por ejemplo, `CloneSearch.ps1` .
    
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

2. Abra Windows PowerShell y vaya a la carpeta donde guardó el script.
    
3. Ejecute el script; por ejemplo:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. Cuando se le soliciten sus credenciales, escriba su dirección de correo electrónico y contraseña y, a continuación, haga clic en **Aceptar.**
    
5. Escriba la siguiente información cuando se lo pida el script. Escriba cada fragmento de información y, a continuación, presione **Entrar**.
    
    - Nombre de la búsqueda existente.
    
    - Nombre de la nueva búsqueda.
    
    El script crea la nueva búsqueda de contenido, pero no la inicia. Esto le da la oportunidad de editar y ejecutar la búsqueda en el paso siguiente. Puede ver las propiedades de la nueva búsqueda ejecutando el cmdlet  **Get-ComplianceSearch** o yendo a la página Búsqueda de contenido o **exhibición** de documentos electrónicos en el centro de cumplimiento, dependiendo de si la nueva búsqueda está asociada a un caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Paso 2: Editar y ejecutar la búsqueda clonada en el Centro de cumplimiento

Después de ejecutar el script para clonar una búsqueda de contenido existente, el siguiente paso es ir al Centro de cumplimiento para editar y ejecutar la nueva búsqueda. Como se indicó anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabras clave y agregando o quitando condiciones de búsqueda. Para obtener más información, vea:
  
- [Búsqueda de contenido de Office 365](content-search.md)
    
- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
    
- [Casos de exhibición de documentos electrónicos](ediscovery-cases.md)
