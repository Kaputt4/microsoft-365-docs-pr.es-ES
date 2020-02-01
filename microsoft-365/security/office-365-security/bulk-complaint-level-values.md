---
title: Valores de nivel de queja masiva, correo masivo, niveles de BCL, cómo funciona BCL, clasificaciones BCL, antispam, encabezado contra correo electrónico no deseado, filtrado de correo masivo, detener correo masivo
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Obtenga información sobre los valores de nivel de queja masiva (BCL) en Office 365.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599727"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="79166-103">Valores de nivel de queja de correo masivo</span><span class="sxs-lookup"><span data-stu-id="79166-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="79166-104">Los troyanos de envío masivo de correo electrónico varían en sus patrones de envío, la creación de contenido y las prácticas de adquisición de listas.</span><span class="sxs-lookup"><span data-stu-id="79166-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="79166-105">Algunos son buenos troyanos de envío de correo electrónico que envían mensajes deseados con contenido relevante a sus suscriptores.</span><span class="sxs-lookup"><span data-stu-id="79166-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="79166-106">Estos mensajes generan pocas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="79166-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="79166-107">Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="79166-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="79166-108">Para distinguir estos tipos de troyanos de envío masivo de correo, se asigna una clasificación de nivel de queja de correo masivo (BCL) a los troyanos de envío masivo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="79166-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="79166-109">Las clasificaciones de BCL oscilan entre 1 y 9, según la probabilidad con la que el troyano de envío masivo de correo electrónico generará quejas.</span><span class="sxs-lookup"><span data-stu-id="79166-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="79166-110">Es probable que un remitente que tiene una clasificación 9 de BCL genere muchas quejas por parte de los destinatarios, mientras que es poco probable que una clasificación 3 de BCL genere muchas quejas.</span><span class="sxs-lookup"><span data-stu-id="79166-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="79166-111">Microsoft usa fuentes internas y de terceros para identificar el correo masivo y determinar el BCL adecuado.</span><span class="sxs-lookup"><span data-stu-id="79166-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="79166-112">Para obtener más información sobre este encabezado de mensaje, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="79166-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="79166-113">Dado que es probable que un correo masivo con una clasificación de 9 genere quejas, la BCL predeterminada es 7.</span><span class="sxs-lookup"><span data-stu-id="79166-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="79166-114">Esto significa que los mensajes de correo masivo se aceptarán hasta que no se acepte el nivel de queja de 7 y el correo a partir de ese momento.</span><span class="sxs-lookup"><span data-stu-id="79166-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="79166-115">Cuanto menor sea la clasificación, se aceptará el correo menos masivo.</span><span class="sxs-lookup"><span data-stu-id="79166-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="79166-116">Si los usuarios son, y su trabajo es, sensible al correo masivo y su BCL está establecido en 4, se aceptará correo masivo con una BCL superior a 4.</span><span class="sxs-lookup"><span data-stu-id="79166-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="79166-117">Para usar los valores de BCL a fin de establecer el nivel deseado de filtrado de correo masivo que requiere su organización, siga estos pasos en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="79166-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="79166-118">En la tabla siguiente se describen los valores de BCL que están actualmente en uso.</span><span class="sxs-lookup"><span data-stu-id="79166-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="79166-119">**Valor de BCL**</span><span class="sxs-lookup"><span data-stu-id="79166-119">**BCL Value**</span></span>|<span data-ttu-id="79166-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="79166-120">**Description**</span></span>|
|<span data-ttu-id="79166-121">comprendi</span><span class="sxs-lookup"><span data-stu-id="79166-121">0</span></span>|<span data-ttu-id="79166-122">El mensaje no es de un remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="79166-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="79166-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="79166-123">1, 2, 3</span></span>|<span data-ttu-id="79166-124">El mensaje proviene de un remitente de correo masivo que genera pocas quejas.</span><span class="sxs-lookup"><span data-stu-id="79166-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="79166-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="79166-125">4, 5, 6, 7</span></span>|<span data-ttu-id="79166-126">El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.</span><span class="sxs-lookup"><span data-stu-id="79166-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="79166-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="79166-127">8, 9</span></span>|<span data-ttu-id="79166-128">El mensaje proviene de un remitente masivo que genera un gran número de quejas.</span><span class="sxs-lookup"><span data-stu-id="79166-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
