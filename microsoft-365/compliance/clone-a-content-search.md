---
title: Clonar una búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Use el script de PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente en el portal de cumplimiento de Microsoft Purview en Microsoft 365.
ms.openlocfilehash: f5ec0433e445256865033b71082c92889972f827
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66017452"
---
# <a name="clone-a-content-search"></a>Clonar una búsqueda de contenido

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La creación de una búsqueda de contenido en el portal de cumplimiento de Microsoft Purview en Microsoft 365 que busca en muchos buzones o SharePoint y OneDrive para la Empresa sitios puede tardar un tiempo. Especificar los sitios que se van a buscar también puede ser propenso a errores si escribe mal una dirección URL. Para evitar estos problemas, puede usar el script Windows PowerShell de este artículo para clonar rápidamente una búsqueda de contenido existente. Al clonar una búsqueda, se crea una nueva búsqueda (con un nombre diferente) que contiene las mismas propiedades (como las ubicaciones de contenido y la consulta de búsqueda) que la búsqueda original. A continuación, puede editar la nueva búsqueda cambiando la consulta de palabras clave o el intervalo de fechas y ejecútela.

¿Por qué clonar búsquedas de contenido?

- Para comparar los resultados de diferentes consultas de búsqueda de palabras clave, ejecute en las mismas ubicaciones de contenido.

- Para evitar que tenga que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda.

- Para reducir el tamaño de los resultados de la búsqueda. Por ejemplo, si tiene una búsqueda que devuelve demasiados resultados para exportar, puede clonar la búsqueda y, a continuación, agregar una condición de búsqueda basada en un intervalo de fechas para reducir el número de resultados de búsqueda.

## <a name="script-information"></a>Información de script

- Debe instalar el módulo Exchange Online V2. Para obtener instrucciones, consulte [Instalar y mantener el módulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

- Debe ser miembro del grupo de roles administrador de eDiscovery en el portal de cumplimiento de Microsoft Purview para ejecutar el script descrito en este tema.

- El script incluye un control mínimo de errores. El propósito principal del script es clonar rápidamente una búsqueda de contenido.

- El script crea una nueva búsqueda de contenido, pero no la inicia.

- Este script tiene en cuenta si la búsqueda de contenido que está clonando está asociada a un caso de exhibición de documentos electrónicos. Si la búsqueda está asociada a un caso, la nueva búsqueda también se asociará con el mismo caso. Si la búsqueda existente no está asociada a un caso, la nueva búsqueda se mostrará en la página Búsqueda de **contenido** del portal de cumplimiento de Microsoft Purview.

- El script de ejemplo proporcionado en este tema no se admite en ningún programa o servicio de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-run-the-script-to-clone-a-search"></a>Paso 1: Ejecutar el script para clonar una búsqueda

El script de este paso creará una nueva búsqueda de contenido mediante la clonación de una existente. Al ejecutar este script, se le pedirá la siguiente información:

- **Credenciales de usuario** : el script usará sus credenciales para conectarse a PowerShell de cumplimiento de seguridad &. Como se indicó anteriormente, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview para ejecutar el script.

- **Nombre de la búsqueda existente** : se trata de la búsqueda de contenido que desea clonar.

- **Nombre de la nueva búsqueda que se creará** : si deja este valor en blanco, el script creará un nombre para la nueva búsqueda que se basa en el nombre de la búsqueda que va a clonar.

Para clonar una búsqueda:

1. Guarde el texto siguiente en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1; por ejemplo, `CloneSearch.ps1`.

   ```powershell
   # This PowerShell script clones an existing content search in Microsoft Purview compliance.

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

2. [Conectar a PowerShell de cumplimiento de & de seguridad](/powershell/exchange/connect-to-scc-powershell). En la misma ventana de PowerShell, vaya a la carpeta donde guardó el script.

3. Ejecute el script; por ejemplo:

     ```powershell
     .\CloneSearch.ps1
     ```

4. Escriba la siguiente información cuando el script le solicite. Escriba cada fragmento de información y, a continuación, presione **Entrar**.

     - Nombre de la búsqueda existente.
     - Nombre de la nueva búsqueda.

     El script crea la nueva búsqueda de contenido, pero no la inicia. Esto le da la oportunidad de editar y ejecutar la búsqueda en el paso siguiente. Para ver las propiedades de la nueva búsqueda, ejecute el cmdlet **Get-ComplianceSearch** o vaya a la página **Búsqueda de contenido** o **exhibición de documentos electrónicos** en el portal de cumplimiento de Microsoft Purview, en función de si la nueva búsqueda está asociada a un caso.

## <a name="step-2-edit-and-run-the-cloned-search-in-the-microsoft-purview-compliance-portal"></a>Paso 2: Editar y ejecutar la búsqueda clonada en el portal de cumplimiento de Microsoft Purview

Después de ejecutar el script para clonar una búsqueda de contenido existente, el siguiente paso es ir al portal de cumplimiento de Microsoft Purview para editar y ejecutar la nueva búsqueda. Como se indicó anteriormente, puede editar una búsqueda cambiando la consulta de búsqueda de palabras clave y agregando o quitando condiciones de búsqueda. Para más información, vea:

- [Búsqueda de contenido de Office 365](content-search.md)

- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).

- [Casos de eDiscovery](./get-started-core-ediscovery.md)
