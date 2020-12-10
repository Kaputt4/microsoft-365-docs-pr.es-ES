---
title: Barreras de la información en Microsoft 365
description: Obtenga información sobre cómo configurar las barreras de la información en Microsoft 365.
keywords: Microsoft 365, riesgo para Insider, cumplimiento
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
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613848"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="4f9ad-104">Barreras de la información en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f9ad-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="4f9ad-105">Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, y admite formas de restringir la comunicación y la colaboración entre grupos de usuarios específicos cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="4f9ad-106">Esto puede incluir situaciones o escenarios en los que desee restringir la comunicación y la colaboración entre dos grupos para evitar que se produzca un conflicto de intereses en la organización.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="4f9ad-107">Esto también puede incluir situaciones en las que es necesario restringir la comunicación y la colaboración entre determinadas personas dentro de la organización para salvaguardar la información interna.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="4f9ad-108">Las barreras de información son compatibles con Microsoft Teams, SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="4f9ad-109">Un administrador o las barreras de la información del administrador de cumplimiento pueden definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="4f9ad-110">Las directivas de barrera de información se pueden usar para situaciones como estas:</span><span class="sxs-lookup"><span data-stu-id="4f9ad-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="4f9ad-111">El usuario del grupo comercial del día no debe comunicarse ni compartir archivos con el equipo de marketing</span><span class="sxs-lookup"><span data-stu-id="4f9ad-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="4f9ad-112">El personal de finanzas que trabaja en la información confidencial de la compañía no debe comunicar ni compartir archivos con determinados grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="4f9ad-113">Un equipo interno con material de secreto comercial no debe llamar ni chatear en línea con los usuarios de determinados grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="4f9ad-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="4f9ad-114">Un equipo de investigación solo debe llamar o chatear en línea con un equipo de desarrollo del producto</span><span class="sxs-lookup"><span data-stu-id="4f9ad-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="4f9ad-115">Configurar barreras de la información para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f9ad-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="4f9ad-116">Siga estos pasos para configurar las barreras de información para su organización:</span><span class="sxs-lookup"><span data-stu-id="4f9ad-116">Use the following steps to configure information barriers for your organization:</span></span>

![Pasos para la solución de riesgos de Insider](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="4f9ad-118">Obtenga información sobre las barreras de la [información](information-barriers.md) en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f9ad-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="4f9ad-119">Configuración [de requisitos previos y permisos](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="4f9ad-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="4f9ad-120">Segmentación [de usuarios de la organización](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="4f9ad-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="4f9ad-121">Creación y configuración de [directivas de barrera de información](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="4f9ad-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="4f9ad-122">Aplicar [directivas de barrera de información](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="4f9ad-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="4f9ad-123">Más información acerca de las barreras de información</span><span class="sxs-lookup"><span data-stu-id="4f9ad-123">More information about information barriers</span></span>

- [<span data-ttu-id="4f9ad-124">Atributos para las directivas de barreras de información</span><span class="sxs-lookup"><span data-stu-id="4f9ad-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="4f9ad-125">Editar o quitar directivas de barrera de información</span><span class="sxs-lookup"><span data-stu-id="4f9ad-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)