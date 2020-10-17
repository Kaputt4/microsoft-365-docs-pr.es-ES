---
title: Administrar Skype Empresarial Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Use PowerShell para Microsoft 365 para administrar las directivas de Skype Empresarial Online, directivas por usuario y opciones de reunión.
ms.openlocfilehash: ff35463dc0c2e16106432c393b10e31e6bf0a5d2
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477106"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Administrar Skype Empresarial Online con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Los administradores de Skype Empresarial Online son los responsables de la administración de directivas. Si bien puede realizar algunas de estas tareas en el Centro de administración de Microsoft 365, otras se pueden hacer con mayor facilidad en PowerShell.

## <a name="before-you-start"></a>Antes de comenzar

  > [!Note]
   > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
   
Instale el [Módulo de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).


## <a name="connect-using-admin-credentials"></a>Conectarse con sus credenciales de administrador

1. Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre y la contraseña de su cuenta de administrador y, a continuación, seleccione **Aceptar**.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Conectarse mediante una cuenta de administrador con autenticación multifactor

1. Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Cuando aparezca el comando **New-CsOnlineSession**, escriba el nombre de su cuenta de administrador de Skype Empresarial Online.

3. En el cuadro de diálogo **Iniciar sesión en su cuenta**, escriba la contraseña de administrador de Skype Empresarial Online y seleccione **Iniciar sesión**.

4. En el cuadro de diálogo **Iniciar sesión en su cuenta** siga las instrucciones para añadir información de autenticación, como el código de verificación, y luego seleccione **Verificar**.

Para más información, consulte:
  
- [Administrar las directivas de Skype Empresarial Online con PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Asignar directivas a cada usuario de Skype Empresarial Online con PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Consulte también

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Referencias de cmdlet de PowerShell de Skype Empresarial](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
