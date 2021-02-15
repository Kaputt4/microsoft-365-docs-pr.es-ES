---
title: Configurar la protección contra la suplantación de identidad
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo configurar la protección contra la suplantación de identidad.
ms.openlocfilehash: bcb6b8bac316b4b74c505656cb9a93e7a87e0830
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927879"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="7a99b-103">Configurar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="7a99b-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="7a99b-104">La suplantación de identidad (phishing) es un ataque malintencionado en el que un correo electrónico parece enviado desde un origen conocido, pero intenta recopilar su información personal.</span><span class="sxs-lookup"><span data-stu-id="7a99b-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="7a99b-105">De forma predeterminada, Microsoft 365 incluye alguna protección contra la suplantación de identidad, pero puede aumentar esa protección refinando la configuración.</span><span class="sxs-lookup"><span data-stu-id="7a99b-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="7a99b-106">Echemos un vistazo.</span><span class="sxs-lookup"><span data-stu-id="7a99b-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="7a99b-107">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="7a99b-107">Try it!</span></span>

1. <span data-ttu-id="7a99b-108">En el centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) , seleccione **Seguridad**, Administración **de amenazas**, **Directiva** y, a continuación, **Protección contra suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="7a99b-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="7a99b-109">Seleccione **Directiva predeterminada para** refinarla.</span><span class="sxs-lookup"><span data-stu-id="7a99b-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="7a99b-110">En la **sección Suplantación,** seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7a99b-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="7a99b-111">Vaya a **Agregar dominios para proteger y** seleccione el botón de alternancia para incluir automáticamente los dominios de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="7a99b-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="7a99b-112">Vaya a **Acciones,** abra la lista desplegable Si un usuario suplantado envía el correo electrónico y elija la acción que desee.</span><span class="sxs-lookup"><span data-stu-id="7a99b-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="7a99b-113">Abra la lista desplegable Si un dominio **suplantado** envía correo electrónico y elige la acción que quieras.</span><span class="sxs-lookup"><span data-stu-id="7a99b-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="7a99b-114">Seleccione **Activar sugerencias de seguridad de suplantación.**</span><span class="sxs-lookup"><span data-stu-id="7a99b-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="7a99b-115">Elija si se deben proporcionar sugerencias a los usuarios cuando el sistema detecte usuarios suplantados, dominios o caracteres inusuales.</span><span class="sxs-lookup"><span data-stu-id="7a99b-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="7a99b-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7a99b-116">Select **Save**.</span></span>
1. <span data-ttu-id="7a99b-117">Seleccione **inteligencia de** buzones de correo y compruebe que está activada.</span><span class="sxs-lookup"><span data-stu-id="7a99b-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="7a99b-118">Esto permite que el correo electrónico sea más eficaz mediante el aprendizaje de patrones de uso.</span><span class="sxs-lookup"><span data-stu-id="7a99b-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="7a99b-119">Elija **Agregar remitentes y dominios de confianza.**</span><span class="sxs-lookup"><span data-stu-id="7a99b-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="7a99b-120">Aquí puede agregar direcciones de correo electrónico o dominios que no deben clasificarse como suplantación.</span><span class="sxs-lookup"><span data-stu-id="7a99b-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="7a99b-121">Elija **Revisar la configuración,** asegúrese de que todo sea correcto, seleccione **Guardar** y, a continuación, **cerrar.**</span><span class="sxs-lookup"><span data-stu-id="7a99b-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="7a99b-122">Su organización ahora tiene una mejor protección contra las amenazas de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="7a99b-122">Your organization now has better protection from phishing threats.</span></span>