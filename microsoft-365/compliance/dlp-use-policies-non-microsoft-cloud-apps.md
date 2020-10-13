---
title: Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no sean de Microsoft (versión preliminar)
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
description: Obtenga información sobre cómo usar directivas de DLP para aplicaciones en la nube que no son de Microsoft.
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422762"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="2ef00-103">Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no sean de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="2ef00-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="2ef00-104">Las directivas de prevención de pérdida de datos (DLP) de aplicaciones en la nube que no son de Microsoft forman parte del conjunto de características de Microsoft 365 DLP; con estas características, puede detectar y proteger los elementos confidenciales en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ef00-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="2ef00-105">Para obtener más información sobre todas las ofertas de DLP de Microsoft, vea [información general sobre prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2ef00-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="2ef00-106">Puede usar directivas de DLP para las aplicaciones en la nube que no son de Microsoft para supervisar y detectar los elementos confidenciales que se usan y comparten a través de aplicaciones en la nube que no son de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef00-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="2ef00-107">El uso de estas directivas le proporciona la visibilidad y el control necesarios para garantizar que se usan y protegen correctamente, y ayuda a evitar un comportamiento arriesgado que pueda poner en peligro.</span><span class="sxs-lookup"><span data-stu-id="2ef00-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2ef00-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2ef00-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="2ef00-109">Licencias de SKU/suscripciones</span><span class="sxs-lookup"><span data-stu-id="2ef00-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="2ef00-110">Antes de empezar a usar directivas de DLP en aplicaciones en la nube que no sean de Microsoft, confirme la [suscripción a microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y los complementos.</span><span class="sxs-lookup"><span data-stu-id="2ef00-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="2ef00-111">Para tener acceso a esta funcionalidad y usarla, debe tener una de estas suscripciones o complementos:</span><span class="sxs-lookup"><span data-stu-id="2ef00-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="2ef00-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2ef00-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="2ef00-113">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2ef00-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="2ef00-114">Seguridad de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2ef00-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="2ef00-115">Preparar el entorno de seguridad de aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="2ef00-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="2ef00-116">Las directivas DLP en las aplicaciones en la nube que no son de Microsoft usan capacidades DLP de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="2ef00-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="2ef00-117">Para usarlo, debe preparar el entorno de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="2ef00-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="2ef00-118">Para obtener instrucciones, vea [establecer la visibilidad, la protección y las acciones de gobierno de isntant para las aplicaciones](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span><span class="sxs-lookup"><span data-stu-id="2ef00-118">For instructions, see [Set isntant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="2ef00-119">Conectar una aplicación en la nube que no es de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ef00-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="2ef00-120">Para usar la Directiva DLP en una aplicación en la nube específica que no es de Microsoft, la aplicación debe estar conectada a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="2ef00-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="2ef00-121">Para obtener información, consulte:</span><span class="sxs-lookup"><span data-stu-id="2ef00-121">For information, see:</span></span>

- [<span data-ttu-id="2ef00-122">Cuadro conectar</span><span class="sxs-lookup"><span data-stu-id="2ef00-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="2ef00-123">Conectar con Dropbox</span><span class="sxs-lookup"><span data-stu-id="2ef00-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="2ef00-124">Conexión G-Suite</span><span class="sxs-lookup"><span data-stu-id="2ef00-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="2ef00-125">Conexión de Salesforce</span><span class="sxs-lookup"><span data-stu-id="2ef00-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="2ef00-126">Conectar Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="2ef00-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="2ef00-127">Después de conectar las aplicaciones en la nube a Cloud App Security, puede crear directivas de Microsoft 365 DLP para ellas.</span><span class="sxs-lookup"><span data-stu-id="2ef00-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="2ef00-128">También es posible usar Microsoft Cloud App Security para crear directivas DLP para las aplicaciones en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef00-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="2ef00-129">Sin embargo, se recomienda usar Microsoft 365 para crear y administrar directivas de DLP para las aplicaciones en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef00-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="2ef00-130">Crear una directiva DLP para una aplicación en la nube que no es de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ef00-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="2ef00-131">Cuando seleccione una ubicación para la Directiva DLP, active la ubicación de **seguridad** de la aplicación en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef00-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="2ef00-132">Para seleccionar una aplicación o instancia específica, seleccione **elegir instancia**.</span><span class="sxs-lookup"><span data-stu-id="2ef00-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="2ef00-133">Si no selecciona una instancia, la Directiva usará todas las aplicaciones conectadas en el inquilino de seguridad de la aplicación en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef00-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Ubicaciones para aplicar la Directiva](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US y Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="2ef00-136">Puede elegir varias acciones para cada aplicación en la nube que no sea de Microsoft compatible.</span><span class="sxs-lookup"><span data-stu-id="2ef00-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="2ef00-137">Para cada aplicación, hay diferentes acciones posibles (depende de la API de la aplicación de nube).</span><span class="sxs-lookup"><span data-stu-id="2ef00-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Crear regla](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="2ef00-139">Al crear una regla en la Directiva DLP, puede seleccionar una acción para las aplicaciones en la nube que no sean de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ef00-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="2ef00-140">Para restringir aplicaciones de terceros, seleccione **restringir aplicaciones de terceros**.</span><span class="sxs-lookup"><span data-stu-id="2ef00-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Restringir aplicaciones de terceros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="2ef00-142">Para obtener información acerca de la creación y configuración de directivas de DLP, consulte [Create Test and Tune a DLP Policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2ef00-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef00-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ef00-143">See Also</span></span>

- [<span data-ttu-id="2ef00-144">Crear prueba y ajustar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="2ef00-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="2ef00-145">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="2ef00-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="2ef00-146">Crear una directiva DLP desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="2ef00-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
