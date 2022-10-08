---
title: Asignación de directivas por usuario Skype Empresarial en línea con PowerShell para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Resumen: use PowerShell para Microsoft 365 para asignar la configuración de comunicación por usuario con directivas de Skype Empresarial Online.'
ms.openlocfilehash: db23a3d4a16355a6bf1d9e0f8a8c1daffda7eb63
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178963"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Asignación de directivas por usuario Skype Empresarial en línea con PowerShell para Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

El uso de PowerShell para Microsoft 365 es una manera eficaz de asignar la configuración de comunicación por usuario con directivas de Skype Empresarial Online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Preparación para ejecutar los comandos de PowerShell

Siga estas instrucciones para configurarse para ejecutar los comandos (omita los pasos que ya ha completado):
  
  > [!Note]
   > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.

1. Instale el [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-install).
    
2. Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   Cuando se le solicite, escriba el nombre y la contraseña de la cuenta de administrador de Skype Empresarial Online.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Actualización de la configuración de comunicación externa para una cuenta de usuario

Supongamos que desea cambiar la configuración de comunicación externa en una cuenta de usuario. Por ejemplo, quiere permitir que Alex se comunique con los usuarios federados (EnableFederationAccess es igual a True), pero no con los usuarios de Windows Live (EnablePublicCloudAccess es igual a False). Para ello, debe hacer dos cosas:
  
1. Buscar una directiva de acceso externo que cumpla nuestros criterios.
    
2. Asignar esa directiva de acceso externo a Alex.
    
¿Cómo se determina qué directiva de acceso externo se va a asignar a Alex? El siguiente comando devuelve todas las directivas de acceso externo donde EnableFederationAccess se establece en True y EnablePublicCloudAccess se establece en False:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

A menos que haya creado instancias personalizadas de ExternalAccessPolicy, ese comando devuelve una directiva que cumple nuestros criterios (FederationOnly). A continuación le mostramos un ejemplo:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Ahora que sabe qué directiva asignar a Alex, podemos asignarla mediante el cmdlet [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) . A continuación le mostramos un ejemplo:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Asignar una directiva es bastante sencillo: basta con especificar la identidad del usuario y el nombre de la directiva que se va a asignar. 
  
Y cuando se trata de directivas y asignaciones de directivas, no se limita a trabajar con cuentas de usuario de una en una. Por ejemplo, supongamos que necesita una lista de todos los usuarios que tienen permiso para comunicarse con los socios federados y los usuarios de Windows Live. Ya sabemos que a esos usuarios se les ha asignado la directiva de acceso de usuario externo FederationAndPICDefault. Como sabemos eso, puede mostrar una lista de todos esos usuarios ejecutando un comando simple. Este es el comando:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

En otras palabras, veremos a todos los usuarios donde la propiedad ExternalAccessPolicy se establece en FederationAndPICDefault. (Y, para limitar la cantidad de información que aparece en pantalla, use el cmdlet Select-Object para mostrar solo el nombre para mostrar de cada usuario). 
  
Para configurar todas nuestras cuentas de usuario para que usen esa misma directiva, use este comando:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Este comando usa Get-CsOnlineUser para devolver una colección de todos los usuarios que se han habilitado para Lync y, a continuación, envía toda esa información a Grant-CsExternalAccessPolicy, que asigna la directiva FederationAndPICDefault a todos y cada uno de los usuarios de la colección.
  
Como ejemplo adicional, supongamos que ha asignado anteriormente a Alex la directiva FederationAndPICDefault y ahora ha cambiado de opinión y desea que lo administre la directiva de acceso externo global. No se puede asignar explícitamente la directiva global a nadie. En su lugar, la directiva global se usa para un usuario determinado si no se asigna ninguna directiva por usuario a ese usuario. Por lo tanto, si queremos que Alex se administre mediante la directiva global, debe  *anular la asignación*  de cualquier directiva por usuario que se le haya asignado anteriormente. A continuación se muestra un ejemplo:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Este comando establece el nombre de la directiva de acceso externo asignada a Alex en un valor null ($Null). Null significa "nothing". En otras palabras, no se asigna ninguna directiva de acceso externo a Alex. Cuando no se asigna ninguna directiva de acceso externo a un usuario, la directiva global administra ese usuario.

## <a name="managing-large-numbers-of-users"></a>Administración de un gran número de usuarios

Para administrar un gran número de usuarios (1000 o más), debe procesar por lotes los comandos a través de un bloque de script mediante el cmdlet [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) .  En ejemplos anteriores, cada vez que se ejecuta un cmdlet, debe configurar la llamada y, a continuación, esperar el resultado antes de enviarlo de vuelta.  Cuando se usa un bloque de script, esto permite que los cmdlets se ejecuten de forma remota y, una vez completados, vuelvan a enviar los datos.

```powershell
$s = Get-PSSession | Where-Object { ($.ComputerName -like '*.online.lync.com' -or $.Computername -eq 'api.interfaces.records.teams.microsoft.com') -and $.State -eq 'Opened' -and $.Availability -eq 'Available' }

$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

Esto encontrará 500 usuarios a la vez que no tienen una directiva de cliente. Les concederá la directiva de cliente "ClientPolicyNoIMURL" y la directiva de acceso externo "FederationAndPicDefault". Los resultados se procesan por lotes en grupos de 50 y cada lote de 50 se envía a la máquina remota.
  
## <a name="see-also"></a>Vea también

[Administrar Skype Empresarial Online con PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
