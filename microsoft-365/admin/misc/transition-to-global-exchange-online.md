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
ms.openlocfilehash: 93eab2c4e0ab2f841359061ebdca69967d8d7d33
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363876"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="ba7f5-103">Actualizar los registros MX para realizar la transición al servicio de Exchange Online global</span><span class="sxs-lookup"><span data-stu-id="ba7f5-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="ba7f5-104">Inicie sesión en [Centro de administración de Microsoft 365](https://admin.microsoft.com)y vaya a **Configuración**  >  **dominios**</span><span class="sxs-lookup"><span data-stu-id="ba7f5-104">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="ba7f5-105">El estado se mostrará en el lado derecho de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="ba7f5-106">Si los dominios de su organización apuntan a Microsoft Cloud Germany Exchange Online, deberá actualizar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="ba7f5-107">Haga clic en el dominio y, a continuación, en **Errores DNS detectados, haga clic aquí para ver**.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="ba7f5-108">Esta página tendrá instrucciones para mostrar cómo corregir el registro MX.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="ba7f5-109">Si el registrador de su dominio usa [dominio](../setup/add-domain.md#registrars-with-domain-connect)Conectar , puede hacer clic en "Corregir mis registros" en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="ba7f5-110">De lo contrario, puede seguir el vínculo del asistente para obtener instrucciones **paso a paso** para el registrador.</span><span class="sxs-lookup"><span data-stu-id="ba7f5-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>