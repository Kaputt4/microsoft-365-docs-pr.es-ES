---
title: Actualizar los registros MX para pasar al servicio global de Exchange Online
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo realizar la transición desde Microsoft Cloud Germany Exchange Online al servicio global de Exchange Online
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644860"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="f3741-103">Actualizar los registros MX para pasar al servicio global de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f3741-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="f3741-104">Inicie sesión en el [portal de administración de Microsoft 365](https://admin.microsoft.com)y vaya a **Settings**  >  **dominios** de configuración</span><span class="sxs-lookup"><span data-stu-id="f3741-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="f3741-105">El estado se mostrará en el lado derecho de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="f3741-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="f3741-106">Si los dominios de su organización señalan a Microsoft Cloud Germany Exchange Online, deberá actualizar su registro MX.</span><span class="sxs-lookup"><span data-stu-id="f3741-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="f3741-107">Haga clic en el dominio y, a continuación, haga clic en **errores de DNS detectados; haga clic aquí para verlo**.</span><span class="sxs-lookup"><span data-stu-id="f3741-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="f3741-108">Esta página tendrá instrucciones para mostrar cómo corregir el registro MX.</span><span class="sxs-lookup"><span data-stu-id="f3741-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="f3741-109">Si el registrador de dominios usa [conexión de dominio](../setup/add-domain.md#registrars-with-domain-connect), puede hacer clic en "reparar mis registros" en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="f3741-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="f3741-110">De lo contrario, puede seguir el vínculo del Asistente para obtener **instrucciones paso a paso** para su registrador.</span><span class="sxs-lookup"><span data-stu-id="f3741-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>