---
title: Prevención de la pérdida de datos
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo administrar la configuración de directivas de prevención de pérdida de datos.
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580443"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="53f8c-103">Evitar la pérdida de datos con DLP</span><span class="sxs-lookup"><span data-stu-id="53f8c-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="53f8c-104">Las directivas de prevención de pérdida de datos ayudan a identificar y proteger la información confidencial de su empresa, como números de seguridad social o registros médicos.</span><span class="sxs-lookup"><span data-stu-id="53f8c-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="53f8c-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="53f8c-105">Try it!</span></span>

1. <span data-ttu-id="53f8c-106">Para empezar, vaya al Centro [de administración](https://admin.microsoft.com)y seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="53f8c-107">Desplácese hacia abajo **hasta Configurar la prevención de pérdida de datos** y, a continuación, seleccione **Ver** y, a continuación, **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="53f8c-108">Para editar una directiva, selecciónelo, elija **Editar directiva** y, a continuación, seleccione qué cambiar.</span><span class="sxs-lookup"><span data-stu-id="53f8c-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="53f8c-109">Por ejemplo, seleccione **Ubicaciones** para cambiar lo que se examina.</span><span class="sxs-lookup"><span data-stu-id="53f8c-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="53f8c-110">Para habilitar el examen de contenido en Microsoft Teams, active el modificador de alternancia en la **posición On** y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="53f8c-111">Para editar la configuración de directiva, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="53f8c-112">Deberá establecer reglas independientes que se apliquen a pequeñas y grandes cantidades de contenido confidencial detectado.</span><span class="sxs-lookup"><span data-stu-id="53f8c-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="53f8c-113">Expanda la regla de bajo volumen.</span><span class="sxs-lookup"><span data-stu-id="53f8c-113">Expand your low volume rule.</span></span> <span data-ttu-id="53f8c-114">Elija **Editar regla**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="53f8c-115">Revisa la configuración y ajustala según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="53f8c-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="53f8c-116">Por ejemplo, puede elegir personalizar el **texto del correo electrónico** y personalizar el texto de sugerencia de **directiva**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="53f8c-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-117">Select **Save**.</span></span>
1. <span data-ttu-id="53f8c-118">Repita la regla de volumen alto.</span><span class="sxs-lookup"><span data-stu-id="53f8c-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="53f8c-119">Seleccione **Guardar** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="53f8c-120">Para crear una nueva directiva, seleccione **Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="53f8c-121">Puede crear una directiva personalizada o empezar con una plantilla.</span><span class="sxs-lookup"><span data-stu-id="53f8c-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="53f8c-122">Por ejemplo, para crear una directiva HIPAA, seleccione la **plantilla** Médica y de salud y, a continuación, seleccione Ley de seguros de salud **(HIPAA)** de Estados Unidos .</span><span class="sxs-lookup"><span data-stu-id="53f8c-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="53f8c-123">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-123">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-124">Escriba un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="53f8c-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="53f8c-125">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-125">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-126">Elija las ubicaciones que desea examinar.</span><span class="sxs-lookup"><span data-stu-id="53f8c-126">Choose the locations to scan.</span></span> <span data-ttu-id="53f8c-127">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-127">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-128">Elija el tipo de contenido que desea proteger.</span><span class="sxs-lookup"><span data-stu-id="53f8c-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="53f8c-129">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-129">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-130">Elija lo que desea que suceda si se detecta información confidencial.</span><span class="sxs-lookup"><span data-stu-id="53f8c-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="53f8c-131">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-131">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-132">Personalice los permisos de acceso e invalidación.</span><span class="sxs-lookup"><span data-stu-id="53f8c-132">Customize your access and override permissions.</span></span> <span data-ttu-id="53f8c-133">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-133">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-134">Elija cuándo desea que la directiva entre en vigor.</span><span class="sxs-lookup"><span data-stu-id="53f8c-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="53f8c-135">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-135">Select **Next**.</span></span>
1. <span data-ttu-id="53f8c-136">Revise la configuración y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="53f8c-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="53f8c-137">Una vez que la directiva entre en vigor, el correo electrónico que contiene la información confidencial descrita se bloqueará y el remitente que intentó enviar esa información verá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="53f8c-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>