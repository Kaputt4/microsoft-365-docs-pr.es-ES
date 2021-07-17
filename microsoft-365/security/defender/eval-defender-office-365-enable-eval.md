---
title: Habilitar el entorno de evaluación de Microsoft Defender para Office 365 en el entorno de producción, activar la evaluación, la activación
description: Pasos para activar la evaluación de Microsoft Defender para Office365, con licencias de prueba, control de registros MX, & auditoría de dominios aceptados y conexiones entrantes.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, laboratorio de evaluación de Microsoft 365 Defender Microsoft 365 Defender, piloto, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458772"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="a7061-104">Habilitar el entorno de evaluación</span><span class="sxs-lookup"><span data-stu-id="a7061-104">Enable the evaluation environment</span></span>

<span data-ttu-id="a7061-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a7061-105">**Applies to:**</span></span>
- <span data-ttu-id="a7061-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7061-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a7061-107">Este artículo es [el paso 2 de 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7061-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a7061-108">Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-office-365-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7061-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="a7061-109">Siga estos pasos para habilitar la evaluación de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7061-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![Pasos para habilitar Microsoft Defender para Office 365 en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="a7061-111">Paso 1: Activar licencias de prueba</span><span class="sxs-lookup"><span data-stu-id="a7061-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="a7061-112">Paso 2: Auditar y comprobar el registro MX público</span><span class="sxs-lookup"><span data-stu-id="a7061-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="a7061-113">Paso 3: Auditar dominios aceptados</span><span class="sxs-lookup"><span data-stu-id="a7061-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="a7061-114">Paso 4: Auditar conectores entrantes</span><span class="sxs-lookup"><span data-stu-id="a7061-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="a7061-115">Paso 5: Activar la evaluación</span><span class="sxs-lookup"><span data-stu-id="a7061-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="a7061-116">Paso 1: Activar licencias de prueba</span><span class="sxs-lookup"><span data-stu-id="a7061-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="a7061-117">Inicie sesión en su microsoft defender existente para Office 365 entorno o portal de administración de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="a7061-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="a7061-118">Vaya al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="a7061-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="a7061-119">Selecciona Servicios de compra en el inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="a7061-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Haga clic en Comprar servicios en el panel de navegación de Office 365.":::

3.  <span data-ttu-id="a7061-121">Desplácese hacia abajo hasta la Add-On (o busque "Defender") para buscar microsoft defender para Office 365 planes.</span><span class="sxs-lookup"><span data-stu-id="a7061-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="a7061-122">Haga clic en Detalles a continuación del plan que desea evaluar.</span><span class="sxs-lookup"><span data-stu-id="a7061-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Haga clic en el botón Detalles, a continuación.":::

5. <span data-ttu-id="a7061-124">Haga clic en *el vínculo Iniciar prueba gratuita.*</span><span class="sxs-lookup"><span data-stu-id="a7061-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Haga clic en el inicio de prueba gratuita *hyperlink* en este panel.":::

6. <span data-ttu-id="a7061-126">Confirme su solicitud y haga clic en *el botón Probar* ahora.</span><span class="sxs-lookup"><span data-stu-id="a7061-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Ahora haga clic en el botón Probar ahora **.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="a7061-128">Paso 2: Auditar y comprobar el registro MX público</span><span class="sxs-lookup"><span data-stu-id="a7061-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="a7061-129">Para evaluar de forma eficaz microsoft defender para Office 365, es importante que el correo electrónico externo entrante se retransmita a través de la instancia de Exchange Online Protection (EOP) asociada con el inquilino.</span><span class="sxs-lookup"><span data-stu-id="a7061-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="a7061-130">Inicie sesión en M365 Admin Portal, expanda Configuración y seleccione Dominios.</span><span class="sxs-lookup"><span data-stu-id="a7061-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="a7061-131">Seleccione el dominio de correo electrónico comprobado y haga clic en Administrar DNS.</span><span class="sxs-lookup"><span data-stu-id="a7061-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="a7061-132">Anote el registro MX generado y asignado al inquilino de EOP.</span><span class="sxs-lookup"><span data-stu-id="a7061-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="a7061-133">Obtenga acceso a la zona DNS externa (pública) y compruebe el registro MX principal asociado con el dominio de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7061-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="a7061-134">Si el registro MX público coincide actualmente con la dirección EOP asignada *(por ejemplo, tenant-com.mail.protection.outlook.com), no* es necesario realizar más cambios de enrutamiento .</span><span class="sxs-lookup"><span data-stu-id="a7061-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="a7061-135">Si el registro MX público se resuelve actualmente en una puerta de enlace SMTP local o de terceros, es posible que se requieran configuraciones de enrutamiento adicionales.</span><span class="sxs-lookup"><span data-stu-id="a7061-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="a7061-136">Si el registro MX público se resuelve actualmente en un Exchange local, es posible que aún esté en un modelo híbrido en el que algún buzón de destinatario aún no se haya migrado a EXO.</span><span class="sxs-lookup"><span data-stu-id="a7061-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="a7061-137">Paso 3: Auditar dominios aceptados</span><span class="sxs-lookup"><span data-stu-id="a7061-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="a7061-138">Inicie sesión en el portal Exchange Online administración, seleccione Correo Flow y, a continuación, haga clic en Dominios aceptados.</span><span class="sxs-lookup"><span data-stu-id="a7061-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="a7061-139">En la lista de dominios aceptados que se han agregado y comprobado en el espacio empresarial, anote el tipo de dominio **para** el dominio de correo electrónico principal.</span><span class="sxs-lookup"><span data-stu-id="a7061-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="a7061-140">Si el tipo de  dominio está establecido en Autoritativo, se supone que todos los buzones de destinatarios de la organización residen actualmente en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a7061-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="a7061-141">Si el tipo de dominio se establece en ***Retransmisión*** interna, es posible que aún esté en un modelo híbrido donde algunos buzones de destinatarios aún residen localmente.</span><span class="sxs-lookup"><span data-stu-id="a7061-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="a7061-142">Paso 4: Auditar conectores entrantes</span><span class="sxs-lookup"><span data-stu-id="a7061-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="a7061-143">Inicie sesión en el portal Exchange Online administración, seleccione Correo Flow y, a continuación, haga clic en Conectores.</span><span class="sxs-lookup"><span data-stu-id="a7061-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="a7061-144">En la lista de conectores configurados, anote  las entradas que sean de la organización de partners y que se puedan correlacionar con una puerta de enlace SMTP de terceros.</span><span class="sxs-lookup"><span data-stu-id="a7061-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="a7061-145">En la lista de conectores configurados, tome  nota de las entradas etiquetadas Desde el servidor de correo electrónico de su organización que puedan indicar que todavía está en un escenario híbrido.</span><span class="sxs-lookup"><span data-stu-id="a7061-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="a7061-146">Paso 5: Activar la evaluación</span><span class="sxs-lookup"><span data-stu-id="a7061-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="a7061-147">Use las instrucciones aquí para activar microsoft defender para Office 365 evaluación desde el portal Microsoft 365 Defender web.</span><span class="sxs-lookup"><span data-stu-id="a7061-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="a7061-148">Inicie sesión en el espacio empresarial con una cuenta que tenga acceso al portal Microsoft 365 Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="a7061-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="a7061-149">Elige si quieres que el portal de **Microsoft 365 Defender** sea la interfaz predeterminada de Microsoft Defender para Office 365 administración (recomendado).</span><span class="sxs-lookup"><span data-stu-id="a7061-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Haga clic en el botón Activar configuración para usar el portal de administración centralizado y mejorado Microsoft 365 Defender administración.":::

3. <span data-ttu-id="a7061-151">En el menú de navegación, seleccione **Directivas & reglas en** Correo & *colaboración*.</span><span class="sxs-lookup"><span data-stu-id="a7061-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Esta es una imagen del menú Colaboración & correo electrónico que apunta a Directivas & reglas. Haga clic en eso.":::

4. <span data-ttu-id="a7061-153">En el *panel Reglas de &,* haga clic en **Directivas de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="a7061-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Imagen del panel Reglas & directivas y una flecha que apunta a directivas de amenazas. Haga clic en el siguiente!":::

5. <span data-ttu-id="a7061-155">Desplácese hacia abajo *hasta Directivas adicionales* y seleccione el icono **Evaluar defender para Office 365** usuario.</span><span class="sxs-lookup"><span data-stu-id="a7061-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="El icono de Eval Defender para Office 365 que dice que es una prueba de 30 días en todos los vectores de colaboración & correo electrónico. Haga clic en.":::

6. <span data-ttu-id="a7061-157">Ahora elija si el correo electrónico externo se Exchange Online directamente o a una puerta de enlace o servicio de terceros y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7061-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 evaluará el envío de correo a los buzones Exchange Online correo. Dar los detalles de cómo se enruta el correo ahora, incluido el nombre del conector saliente que enruta el correo. Si solo usa Exchange Online Protection (EOP) no tendrá un conector. Elija uno de los que estoy usando un proveedor local o de terceros, o solo uso EOP.":::

7. <span data-ttu-id="a7061-159">Si usa una puerta de enlace de terceros, seleccione el nombre del proveedor en la lista desplegable junto con el conector de entrada asociado a esa solución.</span><span class="sxs-lookup"><span data-stu-id="a7061-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="a7061-160">Cuando haya enumerado sus respuestas, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7061-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="En este cuadro de diálogo, elija el servicio de proveedor de terceros que usa su organización o seleccione *Other*. En el siguiente cuadro de diálogo hacia abajo, seleccione el conector de entrada. A continuación, haga clic en Siguiente.":::

8. <span data-ttu-id="a7061-162">Revise la configuración y haga clic en **el botón Crear** evaluación.</span><span class="sxs-lookup"><span data-stu-id="a7061-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Este panel tiene una lista desplegable para revisar la configuración. También tiene un vínculo que permite hacer clic en Editar el tipo de enrutamiento si es necesario. Cuando esté listo, haga clic en el botón azul grande Crear evaluación.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Y ahora la configuración se ha completado. El botón azul de esta página dice &quot;Ir a evaluación&quot;.":::      |

## <a name="next-steps"></a><span data-ttu-id="a7061-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a7061-165">Next steps</span></span>

<span data-ttu-id="a7061-166">Paso 3 de 3: Configurar el piloto de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a7061-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a7061-167">Vuelva a la introducción a [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a7061-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="a7061-168">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a7061-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>