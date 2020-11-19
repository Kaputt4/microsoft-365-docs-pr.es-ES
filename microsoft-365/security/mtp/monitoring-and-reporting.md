---
title: Supervisión y visualización de informes-centro de seguridad
description: Describe cómo el centro de seguridad 365 de Microsoft proporciona un resumen de la protección y el estado de la seguridad de un vistazo.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, estado
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356888"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="7fd88-104">Supervisión y visualización de informes en el centro de seguridad 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7fd88-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="7fd88-105">¿Quiere experimentar Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="7fd88-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7fd88-106">Puede [evaluarlo en un entorno de laboratorio](https://aka.ms/mtp-trial-lab) o [ejecutar el proyecto piloto en producción](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="7fd88-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="7fd88-107">El centro de seguridad 365 de Microsoft proporciona un resumen de los Estados de protección y seguridad en todo el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fd88-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="7fd88-108">El centro de seguridad incluye una sección de **informes** que presenta un host de tarjetas que abarcan una amplia variedad de áreas.</span><span class="sxs-lookup"><span data-stu-id="7fd88-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="7fd88-109">Los analistas de seguridad y los administradores pueden realizar un seguimiento de las tarjetas como parte de sus operaciones cotidianas.</span><span class="sxs-lookup"><span data-stu-id="7fd88-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="7fd88-110">En la obtención de detalles, las tarjetas proporcionan informes detallados y, en algunos casos, opciones de administración.</span><span class="sxs-lookup"><span data-stu-id="7fd88-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="7fd88-111">Personalización de vistas</span><span class="sxs-lookup"><span data-stu-id="7fd88-111">Customize views</span></span>

<span data-ttu-id="7fd88-112">De forma predeterminada, las tarjetas se agrupan en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="7fd88-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="7fd88-113">[Identidades](monitor-and-report-identities.md) : cuentas de usuario y credenciales</span><span class="sxs-lookup"><span data-stu-id="7fd88-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="7fd88-114">[Datos](monitor-data.md) : correo electrónico y contenido de documentos</span><span class="sxs-lookup"><span data-stu-id="7fd88-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="7fd88-115">[Dispositivos](monitor-devices.md) : equipos, teléfonos móviles y otros dispositivos</span><span class="sxs-lookup"><span data-stu-id="7fd88-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="7fd88-116">[Aplicaciones](monitor-apps.md) : programas y servicios en línea adjuntos</span><span class="sxs-lookup"><span data-stu-id="7fd88-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="7fd88-117">Cambie a **Agrupar por tema** para reorganizar las tarjetas y agruparlas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7fd88-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="7fd88-118">Las tarjetas de **riesgo** que resaltan las entidades, como las cuentas y los dispositivos, que pueden estar en peligro.</span><span class="sxs-lookup"><span data-stu-id="7fd88-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="7fd88-119">Estas tarjetas también resaltan posibles orígenes de riesgo, como nuevas campañas de amenazas y aplicaciones en la nube privilegiadas</span><span class="sxs-lookup"><span data-stu-id="7fd88-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="7fd88-120">**Tendencias de detección** : tarjetas que resaltan nuevas detecciones de amenazas, anomalías e infracciones de directivas</span><span class="sxs-lookup"><span data-stu-id="7fd88-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="7fd88-121">**Configuración y** tarjetas de mantenimiento que cubren la configuración y la implementación de los controles de seguridad, incluidos los Estados de incorporación de dispositivos a los servicios de administración</span><span class="sxs-lookup"><span data-stu-id="7fd88-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="7fd88-122">**Otras** : todas las demás que no se hayan clasificado en otros temas</span><span class="sxs-lookup"><span data-stu-id="7fd88-122">**Other** - all other cards not categorized under other topics</span></span>
