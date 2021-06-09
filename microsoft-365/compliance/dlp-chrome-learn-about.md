---
title: Obtenga información sobre el Centro de cumplimiento de Microsoft
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: La extensión de cumplimiento de Microsoft extiende la supervisión y el control de las actividades de archivo y acciones protectoras al explorador Google Chrome
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843811"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="9ca40-103">Obtenga información sobre el Centro de cumplimiento de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ca40-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="9ca40-104">[La prevención de pérdida de datos en punto de conexión (Endpoint DLP)](endpoint-dlp-learn-about.md) amplía la supervisión de la actividad y las capacidades de protección de la [Prevención de pérdida de datos (DLP) de Microsoft 365](dlp-learn-about-dlp.md) a elementos confidenciales que estén en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9ca40-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="9ca40-105">Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="9ca40-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="9ca40-106">Una vez instalada la extensión de cumplimiento de Microsoft en un dispositivo con Windows 10, las organizaciones podrán detectar si un usuario intenta acceder o cargar un elemento confidencial a un servicio en la nube mediante Google Chrome, y podrán aplicar acciones de protección mediante la DLP.</span><span class="sxs-lookup"><span data-stu-id="9ca40-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="9ca40-107">Actividades que puede supervisar y sobre las que puede tomar medidas</span><span class="sxs-lookup"><span data-stu-id="9ca40-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="9ca40-108">La extensión de cumplimiento de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9ca40-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="9ca40-109">actividad</span><span class="sxs-lookup"><span data-stu-id="9ca40-109">activity</span></span> |<span data-ttu-id="9ca40-110">description</span><span class="sxs-lookup"><span data-stu-id="9ca40-110">description</span></span>  | <span data-ttu-id="9ca40-111">acciones compatibles de directiva</span><span class="sxs-lookup"><span data-stu-id="9ca40-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="9ca40-112">archivo copiado en la nube</span><span class="sxs-lookup"><span data-stu-id="9ca40-112">file copied to cloud</span></span>  | <span data-ttu-id="9ca40-113">Detecta si un usuario intenta cargar un elemento confidencial en un dominio de servicio restringido con el explorador Chrome.</span><span class="sxs-lookup"><span data-stu-id="9ca40-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="9ca40-114">auditar, bloquear</span><span class="sxs-lookup"><span data-stu-id="9ca40-114">audit, block</span></span>|
|<span data-ttu-id="9ca40-115">archivo impreso</span><span class="sxs-lookup"><span data-stu-id="9ca40-115">file printed</span></span>  |<span data-ttu-id="9ca40-116">Detecta si un usuario trata de imprimir un elemento confidencial abierto en el explorador Chrome en una impresora local o de la red</span><span class="sxs-lookup"><span data-stu-id="9ca40-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="9ca40-117">auditar, bloquear con invalidación, bloquear</span><span class="sxs-lookup"><span data-stu-id="9ca40-117">audit, block with override, block</span></span>|
|<span data-ttu-id="9ca40-118">archivo copiado en el portapapeles</span><span class="sxs-lookup"><span data-stu-id="9ca40-118">file copied to clipboard</span></span> |<span data-ttu-id="9ca40-119">Se detecta cuando un usuario intenta copiar información de un elemento confidencial que se está viendo en el explorador Chrome y, a continuación, lo pega en otra aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="9ca40-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="9ca40-120">auditar, bloquear con invalidación, bloquear</span><span class="sxs-lookup"><span data-stu-id="9ca40-120">audit, block with override, block</span></span>|
|<span data-ttu-id="9ca40-121">archivo copiado en un almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="9ca40-121">file copied to removable storage</span></span>    | <span data-ttu-id="9ca40-122">Detecta si un usuario intenta copiar un elemento o información confidencial de un elemento confidencial abierto en el explorador Chrome en un medio extraíble o dispositivo USB</span><span class="sxs-lookup"><span data-stu-id="9ca40-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="9ca40-123">auditar, bloquear con invalidación, bloquear</span><span class="sxs-lookup"><span data-stu-id="9ca40-123">audit, block with override, block</span></span>|
|<span data-ttu-id="9ca40-124">archivo copiado en el recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="9ca40-124">file copied to network share</span></span>  |<span data-ttu-id="9ca40-125">Detecta si un usuario intenta copiar un elemento o información confidencial de un elemento confidencial abierto en el explorador Chrome en un recurso compartido de red o unidad de red asignada.</span><span class="sxs-lookup"><span data-stu-id="9ca40-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="9ca40-126">auditar, bloquear con invalidación, bloquear</span><span class="sxs-lookup"><span data-stu-id="9ca40-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="9ca40-127">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="9ca40-127">Deployment process</span></span>
1. [<span data-ttu-id="9ca40-128">Introducción a la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9ca40-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="9ca40-129">Herramientas y métodos de incorporación para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ca40-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="9ca40-130">Instalar la extensión en los dispositivos de Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ca40-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="9ca40-131">[Cree o edite directivas de DLP](create-test-tune-dlp-policy.md) que limiten la carga a servicios en la nube, o el acceso por parte de acciones de exploradores no permitidos y aplíquelas a sus dispositivos de Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ca40-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ca40-132">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="9ca40-132">Next steps</span></span>

<span data-ttu-id="9ca40-133">Consulte [Introducción a la extensión de cumplimiento de Microsoft](dlp-chrome-get-started.md) para ver procedimientos y escenarios completos de implementación.</span><span class="sxs-lookup"><span data-stu-id="9ca40-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ca40-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ca40-134">See also</span></span>

- [<span data-ttu-id="9ca40-135">Introducción a la extensión de cumplimiento de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ca40-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="9ca40-136">Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9ca40-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="9ca40-137">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ca40-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="9ca40-138">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ca40-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="9ca40-139">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="9ca40-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="9ca40-140">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="9ca40-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="9ca40-141">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="9ca40-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="9ca40-142">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9ca40-142">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="9ca40-143">Administración de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="9ca40-143">Insider Risk management</span></span>](insider-risk-management.md)
