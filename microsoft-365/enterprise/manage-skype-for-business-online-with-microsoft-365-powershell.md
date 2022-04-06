---
title: Administrar Skype Empresarial Online con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Use PowerShell para Microsoft 365 para administrar las directivas de Skype Empresarial Online, directivas por usuario y opciones de reunión.
ms.openlocfilehash: cb546a7e4130509d7acd0021b3cb78df23c1819f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474480"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Administrar Skype Empresarial Online con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Los administradores de Skype Empresarial Online son los responsables de la administración de directivas. Si bien puede realizar algunas de estas tareas en el Centro de administración de Microsoft 365, otras se pueden hacer con mayor facilidad en PowerShell.

## <a name="before-you-start"></a>Antes de comenzar

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de **PowerShell de Teams**, no es necesario que instale el conector de Skype Empresarial Online.

> [!NOTE]
> Los administradores de Skype Empresarial Online pueden administrar tanto las directivas de las aplicaciones de **Teams** y **Skype Empresarial Online** a través de PowerShell.

Instale el [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-install).

## <a name="connect-using-admin-credentials"></a>Conectarse con sus credenciales de administrador

1. Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre y la contraseña de su cuenta de administrador y, a continuación, seleccione **Aceptar**.

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Conectarse mediante una cuenta de administrador con autenticación multifactor

1. Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. Cuando se solicite, escriba el nombre de su cuenta de administrador de Skype Empresarial Online.

3. En el cuadro de diálogo **Iniciar sesión en su cuenta**, escriba la contraseña de administrador de Skype Empresarial Online y seleccione **Iniciar sesión**.

4. En el cuadro de diálogo **Iniciar sesión en su cuenta** siga las instrucciones para añadir información de autenticación, como el código de verificación, y luego seleccione **Verificar**.

Para más información, consulte:

- [Administrar las directivas de Skype Empresarial Online con PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [Asignar directivas a cada usuario de Skype Empresarial Online con PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a>Consulte también

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Referencias de cmdlet de PowerShell de Skype Empresarial](/powershell/module/skype/)
