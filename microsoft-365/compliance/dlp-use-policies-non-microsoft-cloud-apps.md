---
title: Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Aprende a usar directivas de dlp para aplicaciones en la nube que no son de Microsoft.
ms.openlocfilehash: 6787add3ef8b2d6ded22bd05c0ff9658c4b7fbfc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922086"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="d4169-103">Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d4169-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="d4169-104">Las directivas de prevención de pérdida de datos (DLP) para aplicaciones en la nube que no son de Microsoft forman parte del conjunto de características DLP de Microsoft 365; con estas características, puede detectar y proteger elementos confidenciales en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4169-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="d4169-105">Para obtener más información acerca de todas las ofertas de DLP de Microsoft, vea [Overview of data loss prevention](./data-loss-prevention-policies.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d4169-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](./data-loss-prevention-policies.md?view=o365-worldwide).</span></span>

<span data-ttu-id="d4169-106">Puedes usar directivas DLP en aplicaciones en la nube que no son de Microsoft para supervisar y detectar cuándo se usan y comparten elementos confidenciales a través de aplicaciones en la nube que no son de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4169-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="d4169-107">El uso de estas directivas le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, y ayuda a evitar comportamientos de riesgo que puedan ponerlas en peligro.</span><span class="sxs-lookup"><span data-stu-id="d4169-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d4169-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="d4169-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="d4169-109">Licencias de SKU/suscripciones</span><span class="sxs-lookup"><span data-stu-id="d4169-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="d4169-110">Antes de empezar a usar directivas DLP en aplicaciones en la nube que no son de Microsoft, confirme la suscripción a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y los complementos.</span><span class="sxs-lookup"><span data-stu-id="d4169-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="d4169-111">Para acceder y usar esta funcionalidad, debe tener una de estas suscripciones o complementos:</span><span class="sxs-lookup"><span data-stu-id="d4169-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="d4169-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d4169-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="d4169-113">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d4169-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="d4169-114">Seguridad de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d4169-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="d4169-115">Preparar el entorno de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d4169-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="d4169-116">Las directivas DLP para aplicaciones en la nube que no son de Microsoft usan funcionalidades DLP de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d4169-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="d4169-117">Para usarlo, debes preparar el entorno de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d4169-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="d4169-118">Para obtener instrucciones, consulta [Establecer acciones de visibilidad instantánea, protección](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)y gobierno para tus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d4169-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="d4169-119">Conectar una aplicación en la nube que no es de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4169-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="d4169-120">Para usar la directiva DLP en una aplicación en la nube específica que no sea de Microsoft, la aplicación debe estar conectada a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d4169-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="d4169-121">Para obtener información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d4169-121">For information, see:</span></span>

- [<span data-ttu-id="d4169-122">Cuadro Conectar</span><span class="sxs-lookup"><span data-stu-id="d4169-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d4169-123">Conectar Dropbox</span><span class="sxs-lookup"><span data-stu-id="d4169-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d4169-124">Conectar G-Suite</span><span class="sxs-lookup"><span data-stu-id="d4169-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d4169-125">Conectar Salesforce</span><span class="sxs-lookup"><span data-stu-id="d4169-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d4169-126">Conectar Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="d4169-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="d4169-127">Después de conectar las aplicaciones en la nube a Cloud App Security, puedes crear directivas dlp de Microsoft 365 para ellas.</span><span class="sxs-lookup"><span data-stu-id="d4169-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="d4169-128">También es posible usar Microsoft Cloud App Security para crear directivas DLP en aplicaciones en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4169-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="d4169-129">Sin embargo, se recomienda usar Microsoft 365 para crear y administrar directivas DLP en aplicaciones en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4169-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="d4169-130">Crear una directiva DLP en una aplicación en la nube que no es de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4169-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="d4169-131">Cuando seleccione una ubicación para la directiva DLP, active la ubicación de **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="d4169-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="d4169-132">Para seleccionar una aplicación o instancia específica, seleccione **Elegir instancia**.</span><span class="sxs-lookup"><span data-stu-id="d4169-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="d4169-133">Si no selecciona una instancia, la directiva usa todas las aplicaciones conectadas en el inquilino de Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d4169-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Ubicaciones para aplicar la directiva](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US y Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="d4169-136">Puedes elegir varias acciones para cada aplicación en la nube compatible que no es de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4169-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="d4169-137">Para cada aplicación, hay diferentes acciones posibles (depende de la API de la aplicación en la nube).</span><span class="sxs-lookup"><span data-stu-id="d4169-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Crear regla](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="d4169-139">Al crear una regla en la directiva DLP, puedes seleccionar una acción para aplicaciones en la nube que no son de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4169-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="d4169-140">Para restringir aplicaciones de terceros, selecciona **Restringir aplicaciones de terceros.**</span><span class="sxs-lookup"><span data-stu-id="d4169-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Restringir aplicaciones de terceros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="d4169-142">Para obtener información sobre cómo crear y configurar directivas DLP, vea [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d4169-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4169-143">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d4169-143">See Also</span></span>

- [<span data-ttu-id="d4169-144">Crear pruebas y ajustar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="d4169-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="d4169-145">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="d4169-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="d4169-146">Crear una directiva DLP desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="d4169-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)