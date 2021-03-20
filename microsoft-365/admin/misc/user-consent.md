---
title: Administración del consentimiento del usuario para aplicaciones en Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Obtenga información sobre el consentimiento de los usuarios a las aplicaciones y cómo activarlas para permitir que las aplicaciones de terceros accedan a la información de Microsoft 365 de los usuarios.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914563"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="4304d-103">Administración del consentimiento del usuario para aplicaciones en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4304d-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="4304d-104">Esta configuración controla si los usuarios pueden dar ese consentimiento a las aplicaciones que usan OpenID Connect y OAuth 2.0 para el inicio de sesión y las solicitudes de acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="4304d-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="4304d-105">Una aplicación se puede crear desde su propia organización, o puede venir de otra organización de Office 365 o de un tercero.</span><span class="sxs-lookup"><span data-stu-id="4304d-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="4304d-106">Si activas esta configuración, esas aplicaciones pedirán a los usuarios permiso para acceder a los datos de la organización y los usuarios pueden elegir si se permiten.</span><span class="sxs-lookup"><span data-stu-id="4304d-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="4304d-107">Si desactivas esta configuración, los administradores deben dar su consentimiento a dichas aplicaciones antes de que los usuarios puedan usarlas.</span><span class="sxs-lookup"><span data-stu-id="4304d-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="4304d-108">En este caso, considere la posibilidad de configurar un flujo de trabajo de consentimiento de administrador en Azure Portal para que los usuarios puedan enviar una solicitud de aprobación de administrador para usar cualquier aplicación bloqueada.</span><span class="sxs-lookup"><span data-stu-id="4304d-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="4304d-109">Un usuario puede dar acceso sólo a las aplicaciones que acceden a su información Office 365.</span><span class="sxs-lookup"><span data-stu-id="4304d-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="4304d-110">No se puede dar acceso a una aplicación a otra información del usuario.</span><span class="sxs-lookup"><span data-stu-id="4304d-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="4304d-111">Activar o desactivar el consentimiento del usuario</span><span class="sxs-lookup"><span data-stu-id="4304d-111">Turning user consent on or off</span></span>
<span data-ttu-id="4304d-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="4304d-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="4304d-113">Este es el modo de activar o desactivar el consentimiento del usuario para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4304d-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="4304d-114">En el Centro de administración, vaya a la página **Configuración** de los Servicios de configuración de la organización y, a \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) continuación, seleccione **Consentimiento del usuario para aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="4304d-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="4304d-115">En la **página Consentimiento de usuario para aplicaciones,** seleccione la opción para activar o desactivar el consentimiento del usuario.</span><span class="sxs-lookup"><span data-stu-id="4304d-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="4304d-116">Más información</span><span class="sxs-lookup"><span data-stu-id="4304d-116">More info</span></span>
<span data-ttu-id="4304d-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="4304d-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="4304d-118">Para obtener información sobre cómo configurar las opciones de consentimiento en Azure Active Directory, lea [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="4304d-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="4304d-119">Para obtener información sobre cómo administrar el consentimiento de usuario a las aplicaciones, lea [Managing consent to applications y assessing consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="4304d-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span></span>