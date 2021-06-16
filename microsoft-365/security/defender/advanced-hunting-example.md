---
title: Ejemplo de búsqueda avanzada para Microsoft Defender para Office 365
description: Introducción a la búsqueda de amenazas de correo electrónico mediante la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965153"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="cb1ef-104">Ejemplo de búsqueda avanzada para Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cb1ef-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cb1ef-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cb1ef-105">**Applies to:**</span></span>
- <span data-ttu-id="cb1ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb1ef-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cb1ef-107">¿Quiere empezar a buscar amenazas para correos electrónicos mediante la búsqueda avanzada de amenazas?</span><span class="sxs-lookup"><span data-stu-id="cb1ef-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="cb1ef-108">Pruebe esto:</span><span class="sxs-lookup"><span data-stu-id="cb1ef-108">Try this:</span></span>

<span data-ttu-id="cb1ef-109">La sección [Introducción](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) del [artículo de Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) tiene fragmentos lógicos de configuración temprana que tienen este aspecto:</span><span class="sxs-lookup"><span data-stu-id="cb1ef-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="cb1ef-110">Configure todo con 'Anti' en el nombre.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="cb1ef-111">Antimalware</span><span class="sxs-lookup"><span data-stu-id="cb1ef-111">Anti-malware</span></span>
   - <span data-ttu-id="cb1ef-112">Anti-phishing</span><span class="sxs-lookup"><span data-stu-id="cb1ef-112">Anti-phishing</span></span>
   - <span data-ttu-id="cb1ef-113">Contra correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="cb1ef-113">Anti-spam</span></span>
2. <span data-ttu-id="cb1ef-114">Configure todo con "Caja fuerte" en el nombre.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="cb1ef-115">Vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="cb1ef-115">Safe Links</span></span>
   - <span data-ttu-id="cb1ef-116">Archivos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="cb1ef-116">Safe Attachments</span></span>
3. <span data-ttu-id="cb1ef-117">Defender las cargas de trabajo (ej.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-117">Defend the workloads (ex.</span></span> <span data-ttu-id="cb1ef-118">SharePoint Online, OneDrive y Teams).</span><span class="sxs-lookup"><span data-stu-id="cb1ef-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="cb1ef-119">Proteger con purga automática de cero horas.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="cb1ef-120">Junto con un [vínculo](../office-365-security/protect-against-threats.md) para entrar directamente y establecer la configuración el primer día.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="cb1ef-121">El último paso de la **Introducción** es proteger a los usuarios con la **Purga automática**, también conocida como ZAP.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="cb1ef-122">Puede ser muy importante saber si sus esfuerzos para purgar de manera automática correos electrónicos sospechosos o malintencionados, tras el envío, han tenido éxito.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="cb1ef-123">Poder ir rápidamente al lenguaje de consulta Kusto para buscar problemas es una ventaja de unificar estos dos centros de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="cb1ef-124">Los equipos de seguridad pueden supervisar las pérdidas de ZAP si toman sus siguientes pasos [aquí](https://security.microsoft.com/advanced-hunting), en **Hunting** \> **Advanced Hunting**.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="cb1ef-125">En la página Búsqueda avanzada, haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="cb1ef-126">Copie la consulta siguiente en la ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="cb1ef-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="cb1ef-127">Seleccione **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="La página Búsqueda avanzada (en Búsqueda) con Consulta seleccionada en la parte superior del panel de consulta y ejecutando una consulta kusto para capturar acciones de ZAP en los últimos 7 días.":::

<span data-ttu-id="cb1ef-129">Los datos de esta consulta aparecerán en el panel de resultados bajo la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="cb1ef-130">Los resultados incluyen información como "DeviceName", "AccountDisplayName" y "ZapTime" en un conjunto de resultados que se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="cb1ef-131">Los resultados también se pueden exportar para sus registros.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-131">Results can also be exported for your records.</span></span> <span data-ttu-id="cb1ef-132">Si se trata de una consulta que volverá a necesitar, seleccione **Guardar** > **Guardar como** y agregue la consulta a su lista de consultadas, compartidas o consultas de comunidad.</span><span class="sxs-lookup"><span data-stu-id="cb1ef-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="cb1ef-133">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="cb1ef-133">Related information</span></span>
- [<span data-ttu-id="cb1ef-134">Procedimientos recomendados de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="cb1ef-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="cb1ef-135">Información general: búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="cb1ef-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
