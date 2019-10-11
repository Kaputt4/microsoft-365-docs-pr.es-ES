---
title: Configurar la autenticación multifactor
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Configurar multi-factor Authentication para Microsoft 365 Business.
ms.openlocfilehash: f015463d3fecbfe88bae90ddea7d98cf11cad693
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2019
ms.locfileid: "37454034"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="a8f51-103">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="a8f51-103">Multi-factor authentication</span></span>

<span data-ttu-id="a8f51-104">La autenticación multifactor (MFA) requiere que los usuarios inicien sesión con un segundo método para comprobar su identidad con una llamada telefónica o con una aplicación autenticadora.</span><span class="sxs-lookup"><span data-stu-id="a8f51-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a8f51-105">Configurar MFA en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8f51-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a8f51-106">[![Etiqueta para que sepa que el centro de administración está cambiando y puede encontrar más información en aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="a8f51-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="a8f51-107">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a8f51-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="a8f51-108">En el panel de navegación izquierdo, elija **instalar**.</span><span class="sxs-lookup"><span data-stu-id="a8f51-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="a8f51-109">En la página Configuración, elija **Ver** en la tarjeta **activar la autenticación multifactor (MFA)** .</span><span class="sxs-lookup"><span data-stu-id="a8f51-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="a8f51-110">En la página **activar la MFA** , elija **Introducción**o **administrar** si ya ha configurado la MFA y desea realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="a8f51-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  <span data-ttu-id="a8f51-111">:::image type="content" source="media/turnonmfa.png" alt-text="Captura de pantalla de la página activar MFA.":::</span><span class="sxs-lookup"><span data-stu-id="a8f51-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot of turn on MFA page.":::</span></span>

5. <span data-ttu-id="a8f51-112">En el panel **seguridad de inicio de sesión de strenghen** , marque la opción **requerir una autenticación multifactor para administradores**y, después, elija **crear Directiva**.</span><span class="sxs-lookup"><span data-stu-id="a8f51-112">On the **Strenghen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
