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
ms.openlocfilehash: 4477dadf0ea38a81ac0ae282da3f74fc12f3406f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916685"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="f8992-103">Administrar Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8992-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="f8992-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f8992-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f8992-105">Los administradores de Skype Empresarial Online son los responsables de la administración de directivas.</span><span class="sxs-lookup"><span data-stu-id="f8992-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="f8992-106">Si bien puede realizar algunas de estas tareas en el Centro de administración de Microsoft 365, otras se pueden hacer con mayor facilidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8992-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f8992-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f8992-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="f8992-108">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="f8992-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f8992-109">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="f8992-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="f8992-110">Instale el [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="f8992-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="f8992-111">Conectarse con sus credenciales de administrador</span><span class="sxs-lookup"><span data-stu-id="f8992-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="f8992-112">Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f8992-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="f8992-113">En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre y la contraseña de su cuenta de administrador y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8992-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="f8992-114">Conectarse mediante una cuenta de administrador con autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="f8992-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="f8992-115">Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f8992-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="f8992-116">Cuando se solicite, escriba el nombre de su cuenta de administrador de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f8992-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="f8992-117">En el cuadro de diálogo **Iniciar sesión en su cuenta**, escriba la contraseña de administrador de Skype Empresarial Online y seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="f8992-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="f8992-118">En el cuadro de diálogo **Iniciar sesión en su cuenta** siga las instrucciones para añadir información de autenticación, como el código de verificación, y luego seleccione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="f8992-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="f8992-119">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f8992-119">For more information, see:</span></span>
  
- [<span data-ttu-id="f8992-120">Administrar las directivas de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8992-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="f8992-121">Asignar directivas a cada usuario de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8992-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="f8992-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8992-122">See also</span></span>

[<span data-ttu-id="f8992-123">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8992-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f8992-124">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8992-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="f8992-125">Referencias de cmdlet de PowerShell de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f8992-125">Skype for Business PowerShell cmdlet references</span></span>](/powershell/module/skype/?view=skype-ps)