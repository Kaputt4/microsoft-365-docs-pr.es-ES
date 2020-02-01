---
title: Conceptos básicos sobre la cobertura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Obtenga información sobre la nueva característica de cobertura.
ms.openlocfilehash: 22f7c35b1a5baf97fb72f541d57da28adeeffbe4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594691"
---
# <a name="allotment-basics"></a><span data-ttu-id="8fc38-103">Conceptos básicos sobre la cobertura</span><span class="sxs-lookup"><span data-stu-id="8fc38-103">Allotment basics</span></span>

<span data-ttu-id="8fc38-104">La cobertura de licencias le permite establecer límites de licencia y delegar la administración de la asignación de licencias solo a los productos y límites de licencia que seleccione.</span><span class="sxs-lookup"><span data-stu-id="8fc38-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="8fc38-105">Las coberturas usan licencias basadas en grupos para asignar licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8fc38-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="8fc38-106">Los límites de licencia proporcionan un control mayor sobre el número de licencias asignadas a los usuarios de los grupos.</span><span class="sxs-lookup"><span data-stu-id="8fc38-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="8fc38-107">Por lo tanto, aunque aumente el número de usuarios de los grupos, puede asegurarse de que se mantiene dentro del límite de licencia que ha establecido para su cobertura.</span><span class="sxs-lookup"><span data-stu-id="8fc38-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="8fc38-108">También puede delegar la administración de su cobertura.</span><span class="sxs-lookup"><span data-stu-id="8fc38-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="8fc38-109">Los propietarios de la cobertura delegada obtienen acceso al centro de administración, pero solo pueden ver y administrar las licencias en las coberturas que poseen.</span><span class="sxs-lookup"><span data-stu-id="8fc38-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="8fc38-110">Esto proporciona una delegación más granular de la administración de licencias dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="8fc38-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8fc38-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8fc38-111">Prerequisites</span></span>

<span data-ttu-id="8fc38-112">Debe cumplir con los requisitos de licencia para las [licencias basadas en grupos](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="8fc38-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="8fc38-113">Puede usar las coberturas con cualquier producto de Office 365 disponible para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8fc38-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="8fc38-114">Conjuntos de programas de Office y productos independientes</span><span class="sxs-lookup"><span data-stu-id="8fc38-114">Office suites and standalone products</span></span>
- <span data-ttu-id="8fc38-115">Productos de movilidad y empresa</span><span class="sxs-lookup"><span data-stu-id="8fc38-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="8fc38-116">Productos de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8fc38-116">Dynamics 365 products</span></span>

<span data-ttu-id="8fc38-117">Los siguientes productos no se pueden usar con coberturas:</span><span class="sxs-lookup"><span data-stu-id="8fc38-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="8fc38-118">Aplicaciones de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8fc38-118">Microsoft Store apps</span></span>
- <span data-ttu-id="8fc38-119">Software perpetuo o software que se asigna directamente a un usuario si no hay ninguna licencia implicada.</span><span class="sxs-lookup"><span data-stu-id="8fc38-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="8fc38-120">Recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="8fc38-120">Azure resources</span></span>

<span data-ttu-id="8fc38-121">Debe ser administrador global o de licencia para empezar con una cobertura.</span><span class="sxs-lookup"><span data-stu-id="8fc38-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="8fc38-122">Introducción</span><span class="sxs-lookup"><span data-stu-id="8fc38-122">Getting started</span></span>

<span data-ttu-id="8fc38-123">La característica coberturas está disponible en una versión preliminar privada sólo para un número reducido de clientes.</span><span class="sxs-lookup"><span data-stu-id="8fc38-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="8fc38-124">Si está interesado en unirse, rellene este formulario: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span><span class="sxs-lookup"><span data-stu-id="8fc38-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
