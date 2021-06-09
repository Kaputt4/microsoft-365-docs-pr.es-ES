---
title: Actualizar los registros MX para realizar la transición al servicio de Exchange Online global
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
description: Obtenga información sobre cómo realizar la transición de Microsoft Cloud Germany Exchange Online al servicio de Exchange Online global
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644860"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="7e78d-103">Actualizar los registros MX para realizar la transición al servicio de Exchange Online global</span><span class="sxs-lookup"><span data-stu-id="7e78d-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="7e78d-104">Inicie sesión en [Microsoft 365 de administración y](https://admin.microsoft.com)vaya a **Configuración**  >  **dominios**</span><span class="sxs-lookup"><span data-stu-id="7e78d-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="7e78d-105">El estado se mostrará en el lado derecho de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="7e78d-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="7e78d-106">Si los dominios de su organización apuntan a Microsoft Cloud Germany Exchange Online, deberá actualizar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="7e78d-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="7e78d-107">Haga clic en el dominio y, a continuación, en **Errores DNS detectados, haga clic aquí para ver**.</span><span class="sxs-lookup"><span data-stu-id="7e78d-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="7e78d-108">Esta página tendrá instrucciones para mostrar cómo corregir el registro MX.</span><span class="sxs-lookup"><span data-stu-id="7e78d-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="7e78d-109">Si el registrador de su dominio usa [dominio](../setup/add-domain.md#registrars-with-domain-connect)Conectar , puede hacer clic en "Corregir mis registros" en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="7e78d-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="7e78d-110">De lo contrario, puede seguir el vínculo del asistente para obtener instrucciones **paso a paso** para el registrador.</span><span class="sxs-lookup"><span data-stu-id="7e78d-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>