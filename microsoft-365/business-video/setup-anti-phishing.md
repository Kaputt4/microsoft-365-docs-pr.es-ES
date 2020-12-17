---
title: Configurar la protección contra suplantación de identidad
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo configurar la protección contra la suplantación de identidad.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702892"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="6d75a-103">Configurar la protección contra suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="6d75a-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="6d75a-104">La suplantación de identidad (phishing) es un ataque malintencionado en el que un mensaje de correo electrónico se ve como enviado desde un origen conocido, pero intenta recopilar información personal.</span><span class="sxs-lookup"><span data-stu-id="6d75a-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="6d75a-105">De forma predeterminada, Microsoft 365 incluye alguna protección contra la suplantación de identidad (phishing), pero puede aumentar dicha protección refinando la configuración.</span><span class="sxs-lookup"><span data-stu-id="6d75a-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="6d75a-106">Vamos a echar un vistazo.</span><span class="sxs-lookup"><span data-stu-id="6d75a-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="6d75a-107">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="6d75a-107">Try it!</span></span>

1. <span data-ttu-id="6d75a-108">En el centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) , **Seleccione seguridad**, administración de **amenazas**, **Directiva** y, a continuación, **protección contra phishing ATP**.</span><span class="sxs-lookup"><span data-stu-id="6d75a-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="6d75a-109">Seleccione **directiva predeterminada** para redefinirla.</span><span class="sxs-lookup"><span data-stu-id="6d75a-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="6d75a-110">En la sección **suplantación** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d75a-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="6d75a-111">Vaya a **Agregar dominios para proteger** y seleccione el botón de alternancia para incluir automáticamente los dominios que posee.</span><span class="sxs-lookup"><span data-stu-id="6d75a-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="6d75a-112">Vaya a **acciones**, abra el menú desplegable **si un usuario suplantado envía un correo electrónico** y elija la acción que desee.</span><span class="sxs-lookup"><span data-stu-id="6d75a-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="6d75a-113">Abra la lista desplegable **si el correo electrónico se envía por un dominio representado** y elija la acción que desee.</span><span class="sxs-lookup"><span data-stu-id="6d75a-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="6d75a-114">Seleccione **activar las sugerencias de seguridad de suplantación**.</span><span class="sxs-lookup"><span data-stu-id="6d75a-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="6d75a-115">Elija si se deben proporcionar sugerencias a los usuarios cuando el sistema detecte usuarios suplantados, dominios o caracteres inusuales.</span><span class="sxs-lookup"><span data-stu-id="6d75a-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="6d75a-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d75a-116">Select **Save**.</span></span>
1. <span data-ttu-id="6d75a-117">Seleccione **inteligencia de buzones de correo** y compruebe que está encendido.</span><span class="sxs-lookup"><span data-stu-id="6d75a-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="6d75a-118">Esto permite que el correo electrónico sea más eficaz mediante el aprendizaje de los patrones de uso.</span><span class="sxs-lookup"><span data-stu-id="6d75a-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="6d75a-119">Elija **Agregar remitentes y dominios de confianza**.</span><span class="sxs-lookup"><span data-stu-id="6d75a-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="6d75a-120">Aquí puede agregar direcciones de correo electrónico o dominios que no deben clasificarse como suplantación.</span><span class="sxs-lookup"><span data-stu-id="6d75a-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="6d75a-121">Elija **revisar la configuración**, asegúrese de que todo sea correcto, seleccione **Guardar** y, después, **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6d75a-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="6d75a-122">Su organización ahora tiene mejor protección frente a las amenazas de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6d75a-122">Your organization now has better protection from phishing threats.</span></span>