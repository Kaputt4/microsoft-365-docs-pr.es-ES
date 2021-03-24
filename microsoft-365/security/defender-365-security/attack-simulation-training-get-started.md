---
title: Introducción al uso de aprendizaje de simulación de ataques
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el aprendizaje de simulación de ataques para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073560"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="35abe-103">Introducción al uso de aprendizaje de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="35abe-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="35abe-104">Si su organización tiene Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación y respuesta de [amenazas,](office-365-ti.md)puede usar el aprendizaje de simulación de ataques en el Centro de seguridad de Microsoft para ejecutar escenarios de ataque realistas en su organización.</span><span class="sxs-lookup"><span data-stu-id="35abe-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="35abe-105">Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real impacte en la línea de fondo.</span><span class="sxs-lookup"><span data-stu-id="35abe-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="35abe-106">Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="35abe-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="35abe-107">El entrenamiento de simulación de ataque reemplaza la experiencia anterior de Attack Simulator v1 que se describe en [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="35abe-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="35abe-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="35abe-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="35abe-109">Para abrir el Centro de seguridad de Microsoft, vaya a <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="35abe-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="35abe-110">El aprendizaje de simulación de ataques está disponible en **Correo electrónico y colaboración** \> **Formación de simulación de ataque.**</span><span class="sxs-lookup"><span data-stu-id="35abe-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="35abe-111">Para ir directamente al aprendizaje de simulación de ataques, abra <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="35abe-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="35abe-112">Para obtener más información sobre la disponibilidad del aprendizaje de simulación de ataques en diferentes suscripciones de Microsoft 365, vea Descripción del servicio de [Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="35abe-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="35abe-113">Debe tener asignados permisos en el Centro de seguridad & cumplimiento o en Azure Active Directory para poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="35abe-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="35abe-114">En concreto, debe ser miembro de **administración** de la **organización,** administrador de seguridad o uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="35abe-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="35abe-115">**Administradores del simulador de ataque:** crea y administra todos los aspectos de las campañas de simulación de ataque.</span><span class="sxs-lookup"><span data-stu-id="35abe-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="35abe-116">**Autores de carga del simulador de** ataque: crea cargas de ataque que un administrador puede iniciar más adelante.</span><span class="sxs-lookup"><span data-stu-id="35abe-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="35abe-117">Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) o About admin [roles](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="35abe-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="35abe-118">No hay cmdlets de PowerShell correspondientes para el aprendizaje de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="35abe-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="35abe-119">Los datos relacionados con la simulación de ataques y el aprendizaje se almacenan con otros datos de clientes para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35abe-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="35abe-120">Para obtener más información, [vea Ubicaciones de datos de Microsoft 365](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="35abe-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="35abe-121">La simulación de ataques está disponible en las siguientes regiones: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN y KOR.</span><span class="sxs-lookup"><span data-stu-id="35abe-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="35abe-122">Simulaciones</span><span class="sxs-lookup"><span data-stu-id="35abe-122">Simulations</span></span>

<span data-ttu-id="35abe-123">*Phishing* es un término genérico para ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza.</span><span class="sxs-lookup"><span data-stu-id="35abe-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="35abe-124">*El phishing* forma parte de un subconjunto de técnicas que clasificamos como _ingeniería social._</span><span class="sxs-lookup"><span data-stu-id="35abe-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="35abe-125">En el aprendizaje de simulación de ataques, hay disponibles varios tipos de técnicas de ingeniería social:</span><span class="sxs-lookup"><span data-stu-id="35abe-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="35abe-126">**Recolección de credenciales:** un atacante envía al destinatario un mensaje que contiene una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="35abe-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="35abe-127">Cuando el destinatario hace clic en la dirección URL, se les traslada a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="35abe-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="35abe-128">Normalmente, la página de destino tiene un formato que representa un sitio web conocido para generar confianza en el usuario.</span><span class="sxs-lookup"><span data-stu-id="35abe-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="35abe-129">**Datos adjuntos de malware:** un atacante envía al destinatario un mensaje que contiene datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="35abe-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="35abe-130">Cuando el destinatario abre los datos adjuntos, el código arbitrario (por ejemplo, una macro) se ejecuta en el dispositivo del usuario para ayudar al atacante a instalar código adicional o atrincherarse aún más.</span><span class="sxs-lookup"><span data-stu-id="35abe-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="35abe-131">**Vínculo en datos adjuntos:** se trata de un híbrido de una recolección de credenciales.</span><span class="sxs-lookup"><span data-stu-id="35abe-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="35abe-132">Un atacante envía al destinatario un mensaje que contiene una dirección URL dentro de un archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="35abe-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="35abe-133">Cuando el destinatario abre los datos adjuntos y hace clic en la dirección URL, se les traslada a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="35abe-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="35abe-134">Normalmente, la página de destino tiene un formato que representa un sitio web conocido para generar confianza en el usuario.</span><span class="sxs-lookup"><span data-stu-id="35abe-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="35abe-135">**Vínculo a malware:** un atacante envía al destinatario un mensaje que contiene un vínculo a un archivo adjunto en un sitio de uso compartido de archivos conocido (por ejemplo, SharePoint Online o Dropbox).</span><span class="sxs-lookup"><span data-stu-id="35abe-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="35abe-136">Cuando el destinatario hace clic en la dirección URL, se abren los datos adjuntos y se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o reforzarse aún más.</span><span class="sxs-lookup"><span data-stu-id="35abe-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="35abe-137">**Drive-by-url:** un atacante envía al destinatario un mensaje que contiene una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="35abe-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="35abe-138">Cuando el destinatario hace clic en la dirección URL, se las traslada a un sitio web que intenta ejecutar código en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="35abe-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="35abe-139">Este código en segundo plano intenta recopilar información sobre el destinatario o implementar código arbitrario en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35abe-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="35abe-140">Normalmente, el sitio web de destino es un sitio web conocido que se ha visto comprometido o un clon de un sitio web conocido.</span><span class="sxs-lookup"><span data-stu-id="35abe-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="35abe-141">La familiaridad con el sitio web ayuda a convencer al usuario de que el vínculo es seguro para hacer clic.</span><span class="sxs-lookup"><span data-stu-id="35abe-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="35abe-142">Esta técnica también se conoce como ataque _de agujero de agua._</span><span class="sxs-lookup"><span data-stu-id="35abe-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="35abe-143">Compruebe la disponibilidad de la dirección URL de suplantación de identidad simulada en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="35abe-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="35abe-144">Aunque trabajamos con muchos proveedores de reputación de url para permitir siempre estas direcciones URL de simulación, no siempre tenemos cobertura completa (por ejemplo, Exploración segura de Google).</span><span class="sxs-lookup"><span data-stu-id="35abe-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="35abe-145">La mayoría de los proveedores proporcionan instrucciones que le permiten permitir siempre direcciones URL específicas (por ejemplo, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="35abe-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="35abe-146">Las direcciones URL usadas por el entrenamiento de simulación de ataque se describen en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="35abe-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="35abe-147">Crear una simulación</span><span class="sxs-lookup"><span data-stu-id="35abe-147">Create a simulation</span></span>

<span data-ttu-id="35abe-148">Para obtener instrucciones paso a paso sobre cómo crear y enviar una nueva simulación, consulte [Simulate a phishing attack](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="35abe-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="35abe-149">Crear una carga</span><span class="sxs-lookup"><span data-stu-id="35abe-149">Create a payload</span></span>

<span data-ttu-id="35abe-150">Para obtener instrucciones paso a paso sobre cómo crear una carga para su uso en una simulación, vea [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="35abe-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="35abe-151">Obtener información</span><span class="sxs-lookup"><span data-stu-id="35abe-151">Gaining insights</span></span>

<span data-ttu-id="35abe-152">Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulte Obtener información a través del aprendizaje [de simulación de ataques.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="35abe-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="35abe-153">Attack Simulator usa vínculos seguros en Defender para Office 365 para realizar un seguimiento seguro de los datos de clics de la dirección URL en el mensaje de carga que se envía a los destinatarios dirigidos de una campaña de suplantación de identidad( phishing), incluso si la configuración No realizar seguimiento de los clics del usuario en las directivas de **vínculos** seguros está activada.</span><span class="sxs-lookup"><span data-stu-id="35abe-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>