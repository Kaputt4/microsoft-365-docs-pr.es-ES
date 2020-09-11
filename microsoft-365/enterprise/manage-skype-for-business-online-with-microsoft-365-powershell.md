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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430039"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="318d2-103">Administrar Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="318d2-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="318d2-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="318d2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="318d2-105">Los administradores de Skype Empresarial Online son los responsables de la administración de directivas.</span><span class="sxs-lookup"><span data-stu-id="318d2-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="318d2-106">Si bien puede realizar algunas de estas tareas en el Centro de administración de Microsoft 365, otras se pueden hacer con mayor facilidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="318d2-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="318d2-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="318d2-107">Before you start</span></span>

<span data-ttu-id="318d2-108">Descargue e instale el [módulo de Windows PowerShell de Skype Empresarial Online](https://www.microsoft.com/download/details.aspx?id=39366), y, a continuación, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="318d2-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="318d2-109">Conectarse mediante las credenciales de administrador de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="318d2-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="318d2-110">Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="318d2-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="318d2-111">En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre y la contraseña de su cuenta de administrador de Skype Empresarial Online y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="318d2-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="318d2-112">Conectarse mediante una cuenta de administrador con autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="318d2-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="318d2-113">Abra una ventana del símbolo del sistema de Windows PowerShell y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="318d2-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="318d2-114">Cuando aparezca el comando **New-CsOnlineSession**, escriba el nombre de su cuenta de administrador de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="318d2-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="318d2-115">En el cuadro de diálogo **Iniciar sesión en su cuenta**, escriba la contraseña de administrador de Skype Empresarial Online y seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="318d2-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="318d2-116">En el cuadro de diálogo **Iniciar sesión en su cuenta** siga las instrucciones para añadir información de autenticación, como el código de verificación, y luego seleccione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="318d2-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="318d2-117">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="318d2-117">For more information, see:</span></span>
  
- [<span data-ttu-id="318d2-118">Administrar las directivas de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="318d2-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="318d2-119">Asignar directivas a cada usuario de Skype Empresarial Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="318d2-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="318d2-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="318d2-120">See also</span></span>

[<span data-ttu-id="318d2-121">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="318d2-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="318d2-122">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="318d2-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="318d2-123">Referencias de cmdlet de PowerShell de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="318d2-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
