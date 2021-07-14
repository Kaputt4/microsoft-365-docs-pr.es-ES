---
title: Obtenga información sobre las directivas de aplicación
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre las directivas de aplicación.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420358"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="3737e-103">Obtenga información sobre las directivas de aplicación</span><span class="sxs-lookup"><span data-stu-id="3737e-103">Learn about app policies</span></span>

><span data-ttu-id="3737e-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="3737e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3737e-105">La gobernanza de aplicaciones de Microsoft detecta un comportamiento anómalo de la aplicación en el inquilino de Microsoft 365 y genera alertas que puede ver, investigar y resolver.</span><span class="sxs-lookup"><span data-stu-id="3737e-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="3737e-106">Más allá de esta funcionalidad de detección integrada, puede usar un conjunto de plantillas predeterminadas para crear sus propias directivas de aplicación que generen otras alertas.</span><span class="sxs-lookup"><span data-stu-id="3737e-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="3737e-107">Estas directivas para patrones y comportamientos de aplicaciones y usuarios pueden proteger a los usuarios contra el uso de aplicaciones no compatibles o malintencionadas y limitar el acceso de aplicaciones de riesgo a los datos del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="3737e-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="3737e-108">Esta es una revisión rápida de los roles de administrador necesarios para la administración de directivas de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3737e-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="3737e-109">Función</span><span class="sxs-lookup"><span data-stu-id="3737e-109">Role</span></span> | <span data-ttu-id="3737e-110">Leer directivas</span><span class="sxs-lookup"><span data-stu-id="3737e-110">Read policies</span></span> | <span data-ttu-id="3737e-111">Crear, actualizar o eliminar directivas</span><span class="sxs-lookup"><span data-stu-id="3737e-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="3737e-112">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3737e-112">Compliance Administrator</span></span> | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| <span data-ttu-id="3737e-115">Lector de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3737e-115">Compliance Reader</span></span> | ![Marca de verificación](..\media\checkmark.png) |  |
| <span data-ttu-id="3737e-117">Administrador global</span><span class="sxs-lookup"><span data-stu-id="3737e-117">Global Administrator</span></span> | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| <span data-ttu-id="3737e-120">Lector global</span><span class="sxs-lookup"><span data-stu-id="3737e-120">Global Reader</span></span>  | ![Marca de verificación](..\media\checkmark.png) |  |
| <span data-ttu-id="3737e-122">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="3737e-122">Security Administrator</span></span> | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| <span data-ttu-id="3737e-125">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="3737e-125">Security Reader</span></span>  | ![Marca de verificación](..\media\checkmark.png) |  |
| <span data-ttu-id="3737e-127">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="3737e-127">Security Operator</span></span> | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="3737e-130">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="3737e-130">Next step</span></span>

[<span data-ttu-id="3737e-131">Introducción a las directivas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3737e-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
