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
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Configurar multi-factor Authentication para Microsoft 365 Business.
ms.openlocfilehash: 59a3ff7a9494ccfc44fa701c6f605a9bd9eeafcf
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715062"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="1f0cc-103">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="1f0cc-103">Multi-factor authentication</span></span>

<span data-ttu-id="1f0cc-104">La autenticación multifactor (MFA) requiere que los usuarios inicien sesión con un segundo método para comprobar su identidad con una llamada telefónica o con una aplicación autenticadora.</span><span class="sxs-lookup"><span data-stu-id="1f0cc-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1f0cc-105">Configurar MFA en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f0cc-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1f0cc-106">[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="1f0cc-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="1f0cc-107">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1f0cc-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="1f0cc-108">En el panel de navegación izquierdo, elija **instalar**.</span><span class="sxs-lookup"><span data-stu-id="1f0cc-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="1f0cc-109">En la página Configuración, elija **Ver** en la tarjeta **activar la autenticación multifactor (MFA)** .</span><span class="sxs-lookup"><span data-stu-id="1f0cc-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="1f0cc-110">En la página **activar la MFA** , elija **Introducción**o **administrar** si ya ha configurado la MFA y desea realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="1f0cc-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  <span data-ttu-id="1f0cc-111">:::image type="content" source="media/turnonmfa.png" alt-text="Captura de pantalla de la página activar MFA.":::</span><span class="sxs-lookup"><span data-stu-id="1f0cc-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot of turn on MFA page.":::</span></span>

5. <span data-ttu-id="1f0cc-112">En el panel **reforzar la seguridad de inicio de sesión** , seleccione una de las dos opciones de **requerir multi-factor Authentication para administradores**y, después, elija **crear Directiva**.</span><span class="sxs-lookup"><span data-stu-id="1f0cc-112">On the **Strengthen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
