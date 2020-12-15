---
title: Crear una carga para la formación de simulación de ataques
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre cómo crear cargas personalizadas para la formación de simulación de ataques en Microsoft defender para Office 365.
ms.openlocfilehash: c42090634f6fa9500ae4c3e781b49b607ee928f5
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667548"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="a06f2-103">Crear una carga personalizada para la simulación de ataques formación</span><span class="sxs-lookup"><span data-stu-id="a06f2-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="a06f2-104">Microsoft ofrece un catálogo de carga sólida para diversas técnicas de ingeniería social que se deben emparejar con la formación de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="a06f2-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="a06f2-105">Sin embargo, es posible que desee crear cargas personalizadas que funcionen mejor para su organización.</span><span class="sxs-lookup"><span data-stu-id="a06f2-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="a06f2-106">En este artículo se describe cómo crear una carga en el aprendizaje de simulación de ataques en Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a06f2-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a06f2-107">Puede crear una carga haciendo clic en **crear una carga** , en la [ficha **cargas** dedicadas](https://security.microsoft.com/attacksimulator?viewid=payload) o en el [Asistente para la creación de simulación](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="a06f2-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="a06f2-108">El primer paso del asistente tendrá que seleccionar un tipo de carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="a06f2-109">**Actualmente, solo está disponible el correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="a06f2-110">A continuación, seleccione una técnica asociada.</span><span class="sxs-lookup"><span data-stu-id="a06f2-110">Next, select an associated technique.</span></span> <span data-ttu-id="a06f2-111">Consulte más detalles sobre las técnicas de [selección de una técnica de ingeniería social](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="a06f2-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="a06f2-112">En el siguiente paso, asigne un nombre a su carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-112">In the next step name your payload.</span></span> <span data-ttu-id="a06f2-113">Opcionalmente, puede darle una descripción.</span><span class="sxs-lookup"><span data-stu-id="a06f2-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="a06f2-114">Configurar carga</span><span class="sxs-lookup"><span data-stu-id="a06f2-114">Configure payload</span></span>

<span data-ttu-id="a06f2-115">Ahora es el momento de crear su carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-115">Now it's time to build your payload.</span></span> <span data-ttu-id="a06f2-116">Escriba el nombre del remitente, la dirección de correo electrónico y el asunto del correo electrónico en la sección **detalles del remitente** .</span><span class="sxs-lookup"><span data-stu-id="a06f2-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="a06f2-117">Seleccione una dirección URL de suplantación de identidad en la lista proporcionado.</span><span class="sxs-lookup"><span data-stu-id="a06f2-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="a06f2-118">Esta dirección URL se incrustará más adelante en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a06f2-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="a06f2-119">Puede elegir un correo electrónico interno para el remitente de la carga, lo que hará que la carga aparezca como procedente de otro empleado de la compañía.</span><span class="sxs-lookup"><span data-stu-id="a06f2-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="a06f2-120">Esto aumentará la susceptibilidad a la carga útil y contribuirá al aprendizaje de los empleados en el riesgo de amenazas internas.</span><span class="sxs-lookup"><span data-stu-id="a06f2-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="a06f2-121">Hay un editor de texto enriquecido disponible para crear su carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="a06f2-122">También puede importar un correo electrónico que haya creado previamente.</span><span class="sxs-lookup"><span data-stu-id="a06f2-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="a06f2-123">Al crear el cuerpo del correo electrónico, aprovéchese de las **etiquetas dinámicas** para personalizar el correo electrónico en sus objetivos.</span><span class="sxs-lookup"><span data-stu-id="a06f2-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="a06f2-124">Haga clic en **vínculo de suplantación de identidad** para agregar la dirección URL de suplantación de identidad seleccionada previamente en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a06f2-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Vínculo de suplantación de identidad y etiquetas dinámicas resaltadas en creación de carga para Microsoft defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="a06f2-126">Para ahorrar tiempo, active la opción para **reemplazar todos los vínculos del mensaje de correo electrónico con el vínculo suplantación de identidad (phishing)**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="a06f2-127">Una vez que haya terminado de crear la carga, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="a06f2-128">Adición de indicadores</span><span class="sxs-lookup"><span data-stu-id="a06f2-128">Adding indicators</span></span>

<span data-ttu-id="a06f2-129">Los indicadores ayudarán a los empleados que se redirigen a través de la simulación de ataque a comprender la pista que pueden buscar en futuros ataques.</span><span class="sxs-lookup"><span data-stu-id="a06f2-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="a06f2-130">Para empezar, haga clic en **Agregar indicador**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="a06f2-131">Seleccione un indicador que le gustaría usar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a06f2-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="a06f2-132">Esta lista es creados para contener las pistas más comunes que aparecen en los mensajes de correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a06f2-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="a06f2-133">Una vez seleccionado, asegúrese de que la ubicación del indicador esté configurada en **el cuerpo del correo electrónico** y haga clic en **Seleccionar texto**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="a06f2-134">Resalte la parte de su carga donde aparece este indicador y haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Texto resaltado en el cuerpo del mensaje para agregar a un indicador en la simulación de ataques](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="a06f2-136">Agregue una descripción personalizada para describir el indicador y haga clic en el marco de vista previa del indicador para ver una vista previa del indicador.</span><span class="sxs-lookup"><span data-stu-id="a06f2-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="a06f2-137">Una vez hecho, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-137">Once done, click **Add**.</span></span> <span data-ttu-id="a06f2-138">Repita estos pasos hasta que haya cubierto todos los indicadores de la carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="a06f2-139">Revisión de la carga</span><span class="sxs-lookup"><span data-stu-id="a06f2-139">Review payload</span></span>

<span data-ttu-id="a06f2-140">Ya ha terminado de crear la carga útil.</span><span class="sxs-lookup"><span data-stu-id="a06f2-140">You're done building your payload.</span></span> <span data-ttu-id="a06f2-141">Ahora es el momento de revisar los detalles y ver una vista previa de su carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="a06f2-142">La vista previa incluirá todos los indicadores que haya creado.</span><span class="sxs-lookup"><span data-stu-id="a06f2-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="a06f2-143">Puede editar cada parte de la carga de este paso.</span><span class="sxs-lookup"><span data-stu-id="a06f2-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="a06f2-144">Una vez que se haya satisfecho, **envíe** la carga.</span><span class="sxs-lookup"><span data-stu-id="a06f2-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a06f2-145">Las cargas que ha creado tendrán **tenant** como origen.</span><span class="sxs-lookup"><span data-stu-id="a06f2-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="a06f2-146">Al seleccionar cargas, asegúrese de no filtrar el **espacio empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a06f2-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>
