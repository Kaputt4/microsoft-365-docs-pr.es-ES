---
title: Administrar las directivas de Skype Empresarial Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Resumen: use PowerShell para administrar las propiedades de la cuenta de usuario de Skype Empresarial Online con directivas.'
ms.openlocfilehash: ca945bc05e76525b4b2df6fb0b982a8468d87810
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515057"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Administrar las directivas de Skype Empresarial Online con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para administrar muchas propiedades de cuenta de usuario para Skype Empresarial Online, debe especificarlas como propiedades de directivas con PowerShell para Microsoft 365.
  
## <a name="before-you-begin"></a>Antes de empezar

Use estas instrucciones para configurarse para ejecutar los comandos (omita los pasos que ya ha completado):

  > [!Note]
  > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.

1. Instale el [módulo de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   Cuando se le pida, escriba el nombre y la contraseña de la cuenta de administrador de Skype Empresarial Online.
    
## <a name="manage-user-account-policies"></a>Administrar directivas de cuenta de usuario

Muchas propiedades de cuenta de usuario de Skype Empresarial Online se configuran mediante directivas. Las directivas son simplemente colecciones de configuraciones que se pueden aplicar a uno o varios usuarios. Para echar un vistazo a cómo se ha configurado una directiva, puede ejecutar este comando de ejemplo para la directiva FederationAndPICDefault:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

A su vez, debes recuperar algo similar a esto:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

En este ejemplo, los valores de esta directiva determinan lo que un uso puede o no puede hacer cuando se trata de comunicarse con usuarios federados. Por ejemplo, la propiedad EnableOutsideAccess debe establecerse en True para que un usuario pueda comunicarse con personas fuera de la organización. Tenga en cuenta que esta propiedad no aparece en el Centro de administración de Microsoft 365. En su lugar, la propiedad se establece automáticamente en True o False en función de las demás selecciones que realice. Las otras dos propiedades de interés son:
  
- **EnableFederationAccess** indica si el usuario puede comunicarse con usuarios de dominios federados.
    
- **EnablePublicCloudAccess** indica si el usuario puede comunicarse con usuarios de Windows Live.
    
Por lo tanto, no cambia directamente las propiedades relacionadas con la federación en cuentas de usuario (por ejemplo, **Set-CsUser -EnableFederationAccess $True**). En su lugar, asigne a una cuenta una directiva de acceso externo que tenga preconfigurados los valores de propiedad deseados. Si queremos que un usuario pueda comunicarse con usuarios federados y con usuarios Windows Live, esa cuenta de usuario debe tener asignada una directiva que permita esos tipos de comunicación.
  
Si desea saber si alguien puede comunicarse o no con usuarios de fuera de la organización, debe:
  
- Determinar qué directiva de acceso externo se ha asignado a dicho usuario.
    
- Determinar qué capacidades permite o no dicha directiva.
    
Por ejemplo, puede hacerlo con este comando:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Este comando busca la directiva asignada al usuario y, a continuación, busca las capacidades habilitadas o deshabilitadas dentro de esa directiva.
  
Para administrar directivas de Skype Empresarial Online con PowerShell, vea los cmdlets para:

- [Directiva de cliente](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Directiva de conferencia](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Directiva móvil](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Directiva de correo de voz en línea](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Directiva de enrutamiento de voz](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Un plan de marcado de Skype Empresarial Online es una directiva en todos los aspectos excepto el nombre. El nombre "plan de marcado" se eligió en lugar de, por ejemplo, "directiva de marcado" para proporcionar compatibilidad con versiones anteriores con Office Communications Server y con Exchange. 
  
Por ejemplo, para ver todas las directivas de voz disponibles para su uso, ejecute este comando:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Eso devuelve una lista de todas las directivas de voz disponibles para usted. Sin embargo, tenga en cuenta que no todas las directivas se pueden asignar a todos los usuarios. Esto se debe a varias restricciones relacionadas con las licencias y la ubicación geográfica. (La llamada "[ubicación de uso](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Si desea conocer las directivas de acceso externo y las directivas de conferencia que se pueden asignar a un usuario determinado, use comandos similares a estos: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

El parámetro ApplicableTo limita los datos devueltos a las directivas que se pueden asignar al usuario especificado (por ejemplo, Alex Darrow). Según las licencias y las restricciones de ubicación de uso, eso puede representar un subconjunto de todas las directivas disponibles. 
  
En algunos casos, las propiedades de las directivas no se usan con Microsoft 365, mientras que otras solo las puede administrar el personal de soporte técnico de Microsoft. 
  
Con Skype Empresarial Online, los usuarios deben administrarse mediante una directiva de algún tipo. Si una propiedad válida relacionada con la directiva está en blanco, significa que el usuario en cuestión está administrado por una directiva global, que es una directiva que se aplica automáticamente a un usuario a menos que se le asigne específicamente una directiva por usuario. Dado que no vemos una directiva de cliente enumerada para una cuenta de usuario, se administra mediante la directiva global. Puede determinar la directiva de cliente global con este comando:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Consulta también

[Administrar Skype Empresarial Online con PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)

