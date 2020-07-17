---
title: Configurar usuarios y casos en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: Obtenga información sobre cómo configurar roles de usuario, crear casos y asignar usuarios a los casos en la exhibición avanzada de documentos electrónicos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e24354960b517815bef3cf498822d6ce9fd9dbe
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936747"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="3bee1-103">Configurar usuarios y casos en eDiscovery avanzado (Classic)</span><span class="sxs-lookup"><span data-stu-id="3bee1-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="3bee1-104">En este tema se describe cómo configurar usuarios y casos para la exhibición avanzada de documentos electrónicos (Classic).</span><span class="sxs-lookup"><span data-stu-id="3bee1-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3bee1-105">A medida que continuamos invirtiendo en nuevas versiones de eDiscovery avanzado, anunciamos la retirada de eDiscovery avanzado, también conocido como *eDiscovery avanzado (clásico)* o *eDiscovery avanzado v1.0*</span><span class="sxs-lookup"><span data-stu-id="3bee1-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="3bee1-106">Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="3bee1-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="3bee1-107">eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión.</span><span class="sxs-lookup"><span data-stu-id="3bee1-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="3bee1-108">Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="3bee1-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="requirements-to-set-up-users-and-cases"></a><span data-ttu-id="3bee1-109">Requisitos para configurar usuarios y casos</span><span class="sxs-lookup"><span data-stu-id="3bee1-109">Requirements to set up users and cases</span></span>

<span data-ttu-id="3bee1-110">Antes de configurar casos y usuarios en la exhibición avanzada de documentos electrónicos, se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3bee1-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="3bee1-111">Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3bee1-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="3bee1-112">Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3.</span><span class="sxs-lookup"><span data-stu-id="3bee1-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="3bee1-113">Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5.</span><span class="sxs-lookup"><span data-stu-id="3bee1-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="3bee1-114">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento para crear un caso de exhibición de documentos electrónicos y agregarle miembros.</span><span class="sxs-lookup"><span data-stu-id="3bee1-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="3bee1-115">Para agregarse al grupo de roles eDiscovery Manager en el &amp; centro de seguridad y cumplimiento, debe ser administrador global de la organización.</span><span class="sxs-lookup"><span data-stu-id="3bee1-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="3bee1-116">Si no es un administrador global, deberá solicitar a un administrador global que le agregue al grupo de roles eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="3bee1-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="3bee1-117">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="3bee1-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="3bee1-118">Permisos en el centro de seguridad y cumplimiento de 365 de Microsoft &amp;</span><span class="sxs-lookup"><span data-stu-id="3bee1-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="3bee1-119">Asignar permisos de eDiscovery en el centro de seguridad y cumplimiento de 365 de Microsoft &amp;</span><span class="sxs-lookup"><span data-stu-id="3bee1-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="3bee1-120">Paso 1: asignar permisos de eDiscovery para los usuarios</span><span class="sxs-lookup"><span data-stu-id="3bee1-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="3bee1-121">El primer paso consiste en asignar a los usuarios los permisos de requisitos en el centro de seguridad y &amp; cumplimiento para que puedan agregarse como miembro de un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3bee1-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="3bee1-122">Una vez que un usuario se ha agregado como miembro de un caso en el centro de seguridad &amp; y cumplimiento, podrá obtener acceso al caso en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3bee1-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="3bee1-123">Para asignar a un usuario los permisos necesarios para que se puedan agregar como miembro de un caso de exhibición de documentos electrónicos, vea el paso 1 en [casos de eDiscovery en el &amp; centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="3bee1-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="3bee1-124">Paso 2: crear un caso de exhibición de documentos electrónicos y agregar miembros</span><span class="sxs-lookup"><span data-stu-id="3bee1-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="3bee1-125">El siguiente paso consiste en crear un nuevo caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento y agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="3bee1-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="3bee1-126">Los miembros del caso podrán acceder al caso en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3bee1-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="3bee1-127">Para crear un nuevo caso de exhibición de documentos electrónicos, vea el paso 3 en Introducción [a la exhibición](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="3bee1-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="3bee1-128">Para agregar miembros a un caso de exhibición de documentos electrónicos, vea el paso 4 en Introducción [a la exhibición de](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case) documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="3bee1-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="3bee1-129">Paso 3: ir a un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="3bee1-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="3bee1-130">Después de crear un caso de exhibición de documentos electrónicos y agregar miembros, usted (o cualquier miembro del caso) puede tener acceso al caso correspondiente en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="3bee1-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="3bee1-131">Para obtener acceso a un caso en la exhibición avanzada de documentos electrónicos, vea [obtener acceso a un caso en eDiscovery avanzado](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="3bee1-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bee1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bee1-132">See also</span></span>

[<span data-ttu-id="3bee1-133">Advanced eDiscovery (clásico)</span><span class="sxs-lookup"><span data-stu-id="3bee1-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3bee1-134">Preparar los datos para la exhibición avanzada de documentos electrónicos (Classic)</span><span class="sxs-lookup"><span data-stu-id="3bee1-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 
