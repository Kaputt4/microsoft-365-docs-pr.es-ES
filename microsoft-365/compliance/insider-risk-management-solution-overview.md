---
title: Administración de riesgos de Insider en Microsoft 365
description: Obtenga información sobre cómo configurar la administración de riesgos de insider en Microsoft 365.
keywords: Microsoft 365, riesgo interno, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: 0cca5c517bf72601b469411bf83bedbbd8e50cdc
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819752"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="973b5-104">Administración de riesgos de Insider en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="973b5-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="973b5-105">Cada vez más, los empleados tienen más acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios.</span><span class="sxs-lookup"><span data-stu-id="973b5-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="973b5-106">En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, al tiempo que cumplen los requisitos de cumplimiento y los estándares de privacidad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="973b5-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="973b5-107">Estos riesgos pueden incluir el robo de datos al salir de los empleados y las pérdidas de datos de información fuera de la organización por sobresharing accidental o intenciones malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="973b5-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="973b5-108">La administración de riesgos de Insider en Microsoft 365 usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, recortar y actuar rápidamente en la actividad de usuario de riesgo.</span><span class="sxs-lookup"><span data-stu-id="973b5-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="973b5-109">Al usar registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de insider permite definir directivas específicas para identificar indicadores de riesgo y tomar medidas para mitigar estos riesgos.</span><span class="sxs-lookup"><span data-stu-id="973b5-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="973b5-110">Configurar la administración de riesgos de insider para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="973b5-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="973b5-111">Siga estos pasos para configurar la administración de riesgos de insider para su organización:</span><span class="sxs-lookup"><span data-stu-id="973b5-111">Use the following steps to configure insider risk management for your organization:</span></span>

![Pasos de administración de riesgos de insider risk solution insider](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="973b5-113">Información sobre [la administración de riesgos de insider](insider-risk-management.md) en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="973b5-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="973b5-114">Planear la administración [de riesgos de insider y comprobar licencias](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="973b5-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="973b5-115">Configurar [la configuración de administración de riesgos de insider](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="973b5-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="973b5-116">Configurar [permisos y requisitos](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) [previos de directivas & conectores](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span><span class="sxs-lookup"><span data-stu-id="973b5-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span></span>
5. <span data-ttu-id="973b5-117">Crear y configurar directivas [de administración de riesgos internas](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="973b5-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="973b5-118">Más información sobre la administración de riesgos de insider</span><span class="sxs-lookup"><span data-stu-id="973b5-118">More information about insider risk management</span></span>

- [<span data-ttu-id="973b5-119">Administrar directivas de riesgo de insider</span><span class="sxs-lookup"><span data-stu-id="973b5-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="973b5-120">Investigar alertas de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="973b5-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="973b5-121">Actuar en casos de riesgo de información interna</span><span class="sxs-lookup"><span data-stu-id="973b5-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)