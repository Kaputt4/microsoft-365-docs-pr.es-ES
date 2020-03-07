---
title: Configurar usuarios y casos en la exhibición de documentos electrónicos avanzada de Office 365
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
description: 'Obtenga información sobre cómo configurar roles de usuario, crear casos y asignar usuarios a los casos en Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 76d5e6ab503cc053e31811cc06ac12545a9eeb7e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557760"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="9fe6e-103">Configurar usuarios y casos en eDiscovery avanzado (Classic)</span><span class="sxs-lookup"><span data-stu-id="9fe6e-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="9fe6e-104">En este tema se describe cómo configurar usuarios y casos para la exhibición avanzada de documentos electrónicos (Classic).</span><span class="sxs-lookup"><span data-stu-id="9fe6e-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9fe6e-105">A medida que seguimos invirtiendo en versiones más recientes de eDiscovery avanzado, anunciamos el retiro de Office 365 Advanced eDiscovery, conocido también como *Advanced eDiscovery (Classic)* o *Advanced eDiscovery v 1.0*.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="9fe6e-106">Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="9fe6e-107">eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="9fe6e-108">Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="9fe6e-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="9fe6e-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9fe6e-109">Prerequisites</span></span>

<span data-ttu-id="9fe6e-110">Antes de configurar casos y usuarios en la exhibición avanzada de documentos electrónicos, se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fe6e-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="9fe6e-111">Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="9fe6e-112">Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="9fe6e-113">Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="9fe6e-114">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento de Office 365 para crear un caso de exhibición de documentos electrónicos y agregarle miembros.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-114">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="9fe6e-115">Para agregarse al grupo de roles de eDiscovery Manager en &amp; el centro de seguridad y cumplimiento, debe ser administrador global de la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="9fe6e-116">Si no es un administrador global, deberá solicitar a un administrador global que le agregue al grupo de roles eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="9fe6e-117">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9fe6e-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="9fe6e-118">Permisos en el centro de seguridad &amp; y cumplimiento de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9fe6e-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="9fe6e-119">Asignar permisos de eDiscovery en el centro de &amp; seguridad y cumplimiento de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9fe6e-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="9fe6e-120">Paso 1: asignar permisos de eDiscovery para los usuarios</span><span class="sxs-lookup"><span data-stu-id="9fe6e-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="9fe6e-121">El primer paso consiste en asignar a los usuarios los permisos de requisitos &amp; en el centro de seguridad y cumplimiento para que puedan agregarse como miembro de un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="9fe6e-122">Una vez que un usuario se ha agregado como miembro de un caso en &amp; el centro de seguridad y cumplimiento, podrá obtener acceso al caso en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="9fe6e-123">Para asignar a un usuario los permisos necesarios para que se puedan agregar como miembro de un caso de exhibición de documentos electrónicos, vea el paso 1 en [casos de &amp; eDiscovery en el centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="9fe6e-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="9fe6e-124">Paso 2: crear un caso de exhibición de documentos electrónicos y agregar miembros</span><span class="sxs-lookup"><span data-stu-id="9fe6e-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="9fe6e-125">El siguiente paso es crear un nuevo caso de exhibición de documentos electrónicos &amp; en el centro de seguridad y cumplimiento y agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-125">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="9fe6e-126">Los miembros del caso podrán acceder al caso en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="9fe6e-127">Para crear un nuevo caso de eDiscovery, vea el paso 2 en [casos de eDiscovery en el &amp; centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="9fe6e-127">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="9fe6e-128">Para agregar miembros a un caso de eDiscovery, vea el paso 3 de [los casos de eDiscovery en &amp; el centro de seguridad y cumplimiento de 365 de Microsoft](ediscovery-cases.md#step-3-add-members-to-a-case) .</span><span class="sxs-lookup"><span data-stu-id="9fe6e-128">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="9fe6e-129">Paso 3: ir a un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="9fe6e-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="9fe6e-130">Después de crear un caso de exhibición de documentos electrónicos y agregar miembros, usted (o cualquier miembro del caso) puede tener acceso al caso correspondiente en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="9fe6e-131">Para obtener acceso a un caso en la exhibición avanzada de documentos electrónicos, vea el paso 8 en [los casos de eDiscovery en el centro de seguridad &amp; y cumplimiento de Microsoft 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="9fe6e-131">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fe6e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fe6e-132">See also</span></span>

[<span data-ttu-id="9fe6e-133">Exhibición avanzada de documentos electrónicos (Classic)</span><span class="sxs-lookup"><span data-stu-id="9fe6e-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9fe6e-134">Preparar datos</span><span class="sxs-lookup"><span data-stu-id="9fe6e-134">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
