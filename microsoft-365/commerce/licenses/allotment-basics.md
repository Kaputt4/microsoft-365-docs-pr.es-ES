---
title: Conceptos básicos de asignación
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: ''
ms.custom:
- commerce_licensing
description: Obtenga información sobre la nueva característica de asignación.
ms.date: 03/17/2021
ms.openlocfilehash: 949e06d4bf54405e0045f8c7512a04b1b5cc22c0
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327135"
---
# <a name="allotment-basics"></a><span data-ttu-id="281af-103">Conceptos básicos de asignación</span><span class="sxs-lookup"><span data-stu-id="281af-103">Allotment basics</span></span>

<span data-ttu-id="281af-104">Las asignaciones de licencias le permiten establecer límites de licencia y delegar la administración de la asignación de licencias solo en los productos y límites de licencia que seleccione.</span><span class="sxs-lookup"><span data-stu-id="281af-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="281af-105">Las asignaciones usan licencias basadas en grupos para asignar licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="281af-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="281af-106">Los límites de licencia proporcionan un control agregado sobre cuántas licencias se asignan a los usuarios de los grupos.</span><span class="sxs-lookup"><span data-stu-id="281af-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="281af-107">Por lo tanto, incluso a medida que aumenta el número de usuarios de los grupos, puede asegurarse de que se mantiene dentro del límite de licencia que ha establecido para la asignación.</span><span class="sxs-lookup"><span data-stu-id="281af-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="281af-108">También puede delegar la administración de las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="281af-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="281af-109">Los propietarios delegados de asignación obtienen acceso al centro de administración, pero solo pueden ver y administrar las licencias en las asignaciones que poseen.</span><span class="sxs-lookup"><span data-stu-id="281af-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="281af-110">Esto proporciona una delegación más granular de la administración de licencias dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="281af-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="281af-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="281af-111">Prerequisites</span></span>

<span data-ttu-id="281af-112">Debe cumplir los requisitos de licencias para [licencias basadas en grupos.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="281af-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="281af-113">Puede usar las asignaciones con cualquier producto disponible para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="281af-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="281af-114">Conjuntos de aplicaciones de Office y productos independientes</span><span class="sxs-lookup"><span data-stu-id="281af-114">Office suites and standalone products</span></span>
- <span data-ttu-id="281af-115">Productos de movilidad y empresa</span><span class="sxs-lookup"><span data-stu-id="281af-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="281af-116">Productos de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="281af-116">Dynamics 365 products</span></span>

<span data-ttu-id="281af-117">Los siguientes productos no se pueden usar con asignaciones:</span><span class="sxs-lookup"><span data-stu-id="281af-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="281af-118">Aplicaciones de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="281af-118">Microsoft Store apps</span></span>
- <span data-ttu-id="281af-119">Software perpetuo o software que se asigna directamente a un usuario si no hay ninguna licencia implicada.</span><span class="sxs-lookup"><span data-stu-id="281af-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="281af-120">Recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="281af-120">Azure resources</span></span>

<span data-ttu-id="281af-121">Debe ser un administrador global o de licencia para empezar con una asignación.</span><span class="sxs-lookup"><span data-stu-id="281af-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="281af-122">Introducción</span><span class="sxs-lookup"><span data-stu-id="281af-122">Getting started</span></span>

<span data-ttu-id="281af-123">La característica de asignación está disponible en una vista previa privada solo para un pequeño número de clientes.</span><span class="sxs-lookup"><span data-stu-id="281af-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="281af-124">Si está interesado en unirse, rellene este formulario: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="281af-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>