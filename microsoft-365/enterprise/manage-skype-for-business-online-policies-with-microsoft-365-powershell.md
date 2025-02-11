---
title: Administrar las directivas de Skype Empresarial Online con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Resumen: use PowerShell para administrar las propiedades de la cuenta de usuario de Skype Empresarial Online con directivas.'
ms.openlocfilehash: 1ea469ec5477ea90fc6e8086360db724eddf3863
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185367"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Administrar las directivas de Skype Empresarial Online con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para administrar muchas propiedades de la cuenta de usuario para Skype Empresarial Online, debe especificarlas como propiedades de las directivas con PowerShell para Microsoft 365.
  
## <a name="before-you-begin"></a>Antes de empezar

Siga estas instrucciones para configurarse para ejecutar los comandos (omita los pasos que ya ha completado):

  > [!Note]
  > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.

1. Instale el [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-install).
    
2. Abra el símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   Cuando se le solicite, escriba el nombre y la contraseña de la cuenta de administrador de Skype Empresarial Online.
    
## <a name="manage-user-account-policies"></a>Administración de directivas de cuenta de usuario

Muchas propiedades de cuenta de usuario de Skype Empresarial Online se configuran mediante directivas. Las directivas son simplemente colecciones de configuraciones que se pueden aplicar a uno o varios usuarios. Para echar un vistazo a cómo se ha configurado una directiva, puede ejecutar este comando de ejemplo para la directiva FederationAndPICDefault:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

A su vez, debería recuperar algo similar a esto:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

En este ejemplo, los valores de esta directiva determinan lo que un uso puede o no puede hacer cuando se trata de comunicarse con usuarios federados. Por ejemplo, la propiedad EnableOutsideAccess debe establecerse en True para que un usuario pueda comunicarse con personas ajenas a la organización. Tenga en cuenta que esta propiedad no aparece en el Centro de administración de Microsoft 365. En su lugar, la propiedad se establece automáticamente en True o False en función de las demás selecciones que realice. Las otras dos propiedades de interés son:
  
- **EnableFederationAccess** indica si el usuario puede comunicarse con usuarios de dominios federados.
    
- **EnablePublicCloudAccess** indica si el usuario puede comunicarse con usuarios de Windows Live.
    
Por lo tanto, no cambia directamente las propiedades relacionadas con la federación en las cuentas de usuario (por ejemplo, **Set-CsUser -EnableFederationAccess $True**). En su lugar, asigne a una cuenta una directiva de acceso externo que tenga preconfigurados los valores de propiedad deseados. Si queremos que un usuario pueda comunicarse con usuarios federados y con usuarios de Windows Live, esa cuenta de usuario debe tener asignada una directiva que permita esos tipos de comunicación.
  
Si quiere saber si alguien puede comunicarse con usuarios de fuera de la organización, debe:
  
- Determinar qué directiva de acceso externo se ha asignado a dicho usuario.
    
- Determinar qué capacidades permite o no dicha directiva.
    
Por ejemplo, puede hacerlo mediante este comando:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Este comando busca la directiva asignada al usuario y, a continuación, busca las funcionalidades habilitadas o deshabilitadas dentro de esa directiva.
  
Para administrar las directivas de Skype Empresarial Online con PowerShell, consulte los cmdlets para:

- [Directiva de cliente](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Directiva de conferencia](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Directiva móvil](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Directiva de correo de voz en línea](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Directiva de enrutamiento de voz](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Un plan de marcado Skype Empresarial online es una directiva en todos los aspectos, excepto el nombre. El nombre "plan de marcado" se eligió en lugar de, por ejemplo, "directiva de marcado" para proporcionar compatibilidad con versiones anteriores con Office Communications Server y Con Exchange. 
  
Por ejemplo, para ver todas las directivas de voz disponibles para su uso, ejecute este comando:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Eso devuelve una lista de todas las directivas de voz disponibles para usted. Tenga en cuenta, sin embargo, que no todas las directivas se pueden asignar a todos los usuarios. Esto se debe a varias restricciones relacionadas con las licencias y la ubicación geográfica. (La llamada "[ubicación de uso](/previous-versions/azure/dn194136(v=azure.100))"). Si desea conocer las directivas de acceso externo y las directivas de conferencia que se pueden asignar a un usuario determinado, use comandos similares a estos: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies. 
  
En algunos casos, las propiedades de las directivas no se usan con Microsoft 365, mientras que otras solo pueden ser administradas por el personal de soporte técnico de Microsoft. 
  
Con Skype Empresarial Online, los usuarios deben administrarse mediante una directiva de algún tipo. Si una propiedad válida relacionada con la directiva está en blanco, esto significa que el usuario en cuestión está siendo administrado por una directiva global, que es una directiva que se aplica automáticamente a un usuario a menos que se le asigne específicamente una directiva por usuario. Dado que no se muestra una directiva de cliente para una cuenta de usuario, la directiva global la administra. Puede determinar la directiva de cliente global con este comando:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Vea también

[Administrar Skype Empresarial Online con PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)