---
title: Supervisar y ver informes- Centro de seguridad
description: Describe cómo el Centro de seguridad de Microsoft 365 proporciona un resumen resumido de la protección y el estado de seguridad.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, estado
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930407"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="282e7-104">Supervisar y ver informes en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="282e7-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="282e7-105">¿Desea experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="282e7-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="282e7-106">Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="282e7-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="282e7-107">El Centro de seguridad de Microsoft 365 proporciona un resumen de los estados de protección y seguridad en su entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="282e7-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="282e7-108">El centro de seguridad incluye una **sección de** informes que incluye un gran número de tarjetas que cubren una variedad de áreas.</span><span class="sxs-lookup"><span data-stu-id="282e7-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="282e7-109">Los analistas y administradores de seguridad pueden realizar un seguimiento de las tarjetas como parte de sus operaciones diarias.</span><span class="sxs-lookup"><span data-stu-id="282e7-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="282e7-110">En la exploración en profundidad, las tarjetas proporcionan informes detallados y, en algunos casos, opciones de administración.</span><span class="sxs-lookup"><span data-stu-id="282e7-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="282e7-111">Personalizar vistas</span><span class="sxs-lookup"><span data-stu-id="282e7-111">Customize views</span></span>

<span data-ttu-id="282e7-112">De forma predeterminada, las tarjetas se agrupan en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="282e7-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="282e7-113">[Identidades:](monitor-and-report-identities.md) cuentas de usuario y credenciales</span><span class="sxs-lookup"><span data-stu-id="282e7-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="282e7-114">[Datos:](monitor-data.md) contenido del correo electrónico y del documento</span><span class="sxs-lookup"><span data-stu-id="282e7-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="282e7-115">[Dispositivos:](monitor-devices.md) equipos, teléfonos móviles y otros dispositivos</span><span class="sxs-lookup"><span data-stu-id="282e7-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="282e7-116">[Aplicaciones:](monitor-apps.md) programas y servicios en línea adjuntos</span><span class="sxs-lookup"><span data-stu-id="282e7-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="282e7-117">Cambie a **Agrupar por tema** para reorganizar las tarjetas y agruparlas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="282e7-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="282e7-118">**Riesgo:** tarjetas que resaltan entidades, como cuentas y dispositivos, que podrían estar en riesgo.</span><span class="sxs-lookup"><span data-stu-id="282e7-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="282e7-119">Estas tarjetas también resaltan posibles orígenes de riesgo, como nuevas campañas de amenazas y aplicaciones en la nube con privilegios</span><span class="sxs-lookup"><span data-stu-id="282e7-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="282e7-120">**Tendencias de detección:** tarjetas que resaltan nuevas detecciones de amenazas, anomalías e infracciones de directivas</span><span class="sxs-lookup"><span data-stu-id="282e7-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="282e7-121">**Configuración y estado:** tarjetas que cubren la configuración y la implementación de controles de seguridad, incluidos los estados de incorporación de dispositivos a los servicios de administración</span><span class="sxs-lookup"><span data-stu-id="282e7-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="282e7-122">**Otras** tarjetas no clasificadas en otros temas</span><span class="sxs-lookup"><span data-stu-id="282e7-122">**Other** - all other cards not categorized under other topics</span></span>
