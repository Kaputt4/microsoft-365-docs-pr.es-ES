---
title: Plan for end-of-support software and software versions
description: Descubra y planee versiones de software y software que ya no son compatibles y no recibirán actualizaciones de seguridad.
keywords: Administración de amenazas y vulnerabilidades, recomendación de seguridad de Microsoft Defender para endpoint tvm, recomendación de ciberseguridad, recomendación de seguridad que se puede tomar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1800cfdabd402321c49b737eff7f9d67639eb300
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689006"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="dc3d8-104">Plan for end-of-support software and software versions with Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="dc3d8-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc3d8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="dc3d8-105">**Applies to:**</span></span>

- [<span data-ttu-id="dc3d8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="dc3d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="dc3d8-107">Amenaza y administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="dc3d8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="dc3d8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc3d8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="dc3d8-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="dc3d8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dc3d8-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="dc3d8-111">El fin de la compatibilidad (EOS), también conocido como fin de vida (EOL), para las versiones de software o software significa que ya no se admitirán ni se les dará servicio y no recibirán actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="dc3d8-112">Cuando usa versiones de software o software con soporte técnico finalizado, expone su organización a vulnerabilidades de seguridad, riesgos legales y financieros.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="dc3d8-113">Es fundamental que los administradores de SEGURIDAD y TI trabajen juntos y se aseguren de que el inventario de software de la organización esté configurado para obtener resultados óptimos, cumplimiento y un ecosistema de red en buen estado.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="dc3d8-114">Deben examinar las opciones para quitar o reemplazar aplicaciones que han alcanzado versiones de fin de soporte y actualización que ya no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="dc3d8-115">Es mejor crear e implementar un **plan** antes de que finalicen las fechas de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

>[!NOTE]
> <span data-ttu-id="dc3d8-116">Actualmente, la funcionalidad de fin de soporte técnico solo está disponible para Windows productos.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-116">End-of-support capability is currently available only for Windows products.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="dc3d8-117">Buscar versiones de software o software que ya no son compatibles</span><span class="sxs-lookup"><span data-stu-id="dc3d8-117">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="dc3d8-118">En el menú Administración de amenazas y vulnerabilidades, vaya a [**Recomendaciones de seguridad**](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="dc3d8-118">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="dc3d8-119">Vaya al panel **Filtros** y busque la sección etiquetas.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-119">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="dc3d8-120">Seleccione una o varias de las opciones de etiqueta de EOS.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-120">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="dc3d8-121">A **continuación, aplique**.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-121">Then **Apply**.</span></span>

    ![Etiquetas de captura de pantalla que dicen software de EOS, versiones de EOS y próximas versiones de EOS.](images/tvm-eos-tag.png)

3. <span data-ttu-id="dc3d8-123">Verá una lista de recomendaciones relacionadas con el software con soporte finalizado, las versiones de software que han finalizado el soporte técnico o las versiones con el próximo final de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-123">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="dc3d8-124">Estas etiquetas también están visibles en la [página de inventario de](tvm-software-inventory.md) software.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-124">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Recomendaciones con etiqueta EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="dc3d8-126">Lista de versiones y fechas</span><span class="sxs-lookup"><span data-stu-id="dc3d8-126">List of versions and dates</span></span>

<span data-ttu-id="dc3d8-127">Para ver una lista de versiones que han llegado al final de la compatibilidad, o finalizar o admitir pronto, y esas fechas, siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc3d8-127">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="dc3d8-128">Aparecerá un mensaje en el control de recomendación de seguridad para software con versiones que han llegado al final del soporte técnico, o llegará al final de la compatibilidad pronto.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-128">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Captura de pantalla del vínculo de distribución de versiones.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="dc3d8-130">Seleccione el **vínculo de distribución** de versiones para ir a la página de desglose de software.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-130">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="dc3d8-131">Allí, puede ver una lista filtrada de versiones con etiquetas que las identifican como el final de la compatibilidad o el próximo final de la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-131">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Captura de pantalla de la página de análisis de software con el software de fin de soporte técnico.](images/software-drilldown-eos.png)

3. <span data-ttu-id="dc3d8-133">Seleccione una de las versiones de la tabla que desea abrir.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-133">Select one of the versions in the table to open.</span></span> <span data-ttu-id="dc3d8-134">Por ejemplo, versión 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-134">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="dc3d8-135">Aparecerá un menú desplegable con la fecha de finalización del soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-135">A flyout will appear with the end of support date.</span></span>

    ![Captura de pantalla de la fecha de finalización del soporte técnico.](images/version-eos-date.png)

<span data-ttu-id="dc3d8-137">Una vez que identifique qué versiones de software y software son vulnerables debido a su estado de fin de soporte técnico, debe decidir si desea actualizarlas o quitarlas de su organización.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-137">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="dc3d8-138">Si lo hace, disminuirá la exposición de las organizaciones a vulnerabilidades y amenazas persistentes avanzadas.</span><span class="sxs-lookup"><span data-stu-id="dc3d8-138">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc3d8-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dc3d8-139">Related topics</span></span>

- [<span data-ttu-id="dc3d8-140">Información general sobre amenazas administración de vulnerabilidades amenazas</span><span class="sxs-lookup"><span data-stu-id="dc3d8-140">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="dc3d8-141">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="dc3d8-141">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="dc3d8-142">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="dc3d8-142">Software inventory</span></span>](tvm-software-inventory.md)
