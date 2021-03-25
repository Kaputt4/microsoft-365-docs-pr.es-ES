---
title: Crear una carga para el entrenamiento de simulación de ataques
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a crear cargas personalizadas para el aprendizaje de simulación de ataques en Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205190"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="eb5ae-103">Crear una carga personalizada para la simulación de ataques formación</span><span class="sxs-lookup"><span data-stu-id="eb5ae-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="eb5ae-104">Microsoft ofrece un sólido catálogo de cargas útiles para diversas técnicas de ingeniería social que se emparejan con el entrenamiento de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="eb5ae-105">Sin embargo, es posible que desee crear cargas personalizadas que funcionen mejor para su organización.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="eb5ae-106">En este artículo se describe cómo crear una carga en el aprendizaje de simulación de ataques en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="eb5ae-107">Puede crear una carga haciendo clic en **Crear una** carga en la pestaña [Cargas **dedicadas**](https://security.microsoft.com/attacksimulator?viewid=payload) o en el asistente para la creación [de simulación.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="eb5ae-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="eb5ae-108">El primer paso del asistente le hará seleccionar un tipo de carga.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="eb5ae-109">**Actualmente, solo el correo electrónico está disponible.**</span><span class="sxs-lookup"><span data-stu-id="eb5ae-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="eb5ae-110">A continuación, seleccione una técnica asociada.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-110">Next, select an associated technique.</span></span> <span data-ttu-id="eb5ae-111">Vea más detalles sobre técnicas en [Seleccionar una técnica de ingeniería social](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="eb5ae-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="eb5ae-112">En el siguiente paso, asigne un nombre a la carga.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-112">In the next step name your payload.</span></span> <span data-ttu-id="eb5ae-113">Opcionalmente, puede darle una descripción.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="eb5ae-114">Configurar carga</span><span class="sxs-lookup"><span data-stu-id="eb5ae-114">Configure payload</span></span>

<span data-ttu-id="eb5ae-115">Ahora es el momento de crear la carga útil.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-115">Now it's time to build your payload.</span></span> <span data-ttu-id="eb5ae-116">Introduzca el nombre del remitente, la dirección de correo electrónico y el asunto del correo electrónico en la **sección Detalles del** remitente.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="eb5ae-117">Elija una dirección URL de suplantación de identidad de la lista proporcionada.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="eb5ae-118">Esta dirección URL se incrustará más adelante en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="eb5ae-119">Puede elegir un correo electrónico interno para el remitente de la carga, lo que hará que la carga aparezca como procedente de otro empleado de la compañía.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="eb5ae-120">Esto aumentará la susceptibilidad a la carga útil y ayudará a educar a los empleados sobre el riesgo de amenazas internas.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="eb5ae-121">Hay disponible un editor de texto enriquecido para crear la carga.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="eb5ae-122">También puedes importar un correo electrónico que hayas creado previamente.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="eb5ae-123">A medida que cree el cuerpo del correo electrónico, aproveche las etiquetas **dinámicas** para personalizar el correo electrónico a sus destinos.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="eb5ae-124">Haga clic en El vínculo Suplantación de identidad **(phishing)** para agregar la dirección URL de suplantación de identidad seleccionada anteriormente en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Vínculo de phishing y etiquetas dinámicas resaltadas en la creación de cargas para Microsoft Defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="eb5ae-126">Para ahorrar tiempo, active la opción para reemplazar todos los vínculos del mensaje **de correo electrónico por el vínculo de suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="eb5ae-127">Una vez que haya terminado de compilar la carga a su gusto, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="eb5ae-128">Agregar indicadores</span><span class="sxs-lookup"><span data-stu-id="eb5ae-128">Adding indicators</span></span>

<span data-ttu-id="eb5ae-129">Los indicadores ayudarán a los empleados que pasan por la simulación de ataque a comprender la pista que pueden buscar en ataques futuros.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="eb5ae-130">Para empezar, haga clic **en Agregar indicador**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="eb5ae-131">Selecciona un indicador que quieras usar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="eb5ae-132">Esta lista está curada para contener las pistas más comunes que aparecen en los mensajes de correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="eb5ae-133">Una vez seleccionado, asegúrese de que la ubicación del indicador está establecida en **Desde el cuerpo** del correo electrónico y haga clic en Seleccionar **texto**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="eb5ae-134">Resalte la parte de la carga donde aparece este indicador y haga clic **en Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Texto resaltado en el cuerpo del mensaje para agregarlo a un indicador en el entrenamiento de simulación de ataques](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="eb5ae-136">Agregue una descripción personalizada para describir el indicador y haga clic en el marco de vista previa del indicador para ver una vista previa del indicador.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="eb5ae-137">Una vez hecho esto, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-137">Once done, click **Add**.</span></span> <span data-ttu-id="eb5ae-138">Repita estos pasos hasta que haya cubierto todos los indicadores de la carga.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="eb5ae-139">Revisar carga</span><span class="sxs-lookup"><span data-stu-id="eb5ae-139">Review payload</span></span>

<span data-ttu-id="eb5ae-140">Ya ha terminado de compilar la carga útil.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-140">You're done building your payload.</span></span> <span data-ttu-id="eb5ae-141">Ahora es el momento de revisar los detalles y ver una vista previa de la carga.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="eb5ae-142">La vista previa incluirá todos los indicadores que haya creado.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="eb5ae-143">Puede editar cada parte de la carga desde este paso.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="eb5ae-144">Una vez satisfecho, puede **enviar la** carga.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb5ae-145">Las cargas que haya creado tendrán **Tenant** como origen.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="eb5ae-146">Al seleccionar cargas, asegúrese de que no filtra **tenant**.</span><span class="sxs-lookup"><span data-stu-id="eb5ae-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="eb5ae-147">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="eb5ae-147">Related links</span></span>

[<span data-ttu-id="eb5ae-148">Introducción al uso de aprendizaje de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="eb5ae-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="eb5ae-149">Crear una simulación de ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="eb5ae-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="eb5ae-150">Obtenga información a través de la formación de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="eb5ae-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
