---
title: 'Paso 7: configurar la administración del acceso con privilegios'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprenda y configure la administración del acceso con privilegios.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636993"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="77460-103">Paso 7: configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="77460-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="77460-104">*Este paso es opcional y solo es válido para las versiones E5 y de cumplimiento avanzado de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="77460-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Protección de la información](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="77460-106">La administración del acceso con privilegios está habilitada mediante la configuración de directivas que especifican el acceso Just-in-Time para actividades basadas en tareas en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="77460-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="77460-107">Puede ayudar a proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a la configuración crítica.</span><span class="sxs-lookup"><span data-stu-id="77460-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="77460-108">Por ejemplo, puede configurar una directiva de administración de acceso privilegiada que requiera la aprobación explícita para acceder y cambiar la configuración del buzón de la organización en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="77460-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="77460-109">En este paso, habilitará la administración del acceso con privilegios en su espacio empresarial y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a las opciones de configuración y datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="77460-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="77460-110">Hay tres pasos básicos para empezar a trabajar con privilegios de acceso en la organización:</span><span class="sxs-lookup"><span data-stu-id="77460-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="77460-111">Crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="77460-111">Creating an approver's group</span></span>
- <span data-ttu-id="77460-112">Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="77460-112">Enabling privileged access</span></span>
- <span data-ttu-id="77460-113">Crear directivas de aprobación</span><span class="sxs-lookup"><span data-stu-id="77460-113">Creating approval policies</span></span>

<span data-ttu-id="77460-p103">Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.</span><span class="sxs-lookup"><span data-stu-id="77460-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="77460-117">Para habilitar la administración del acceso privilegiado, consulte el tema [Configure privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .</span><span class="sxs-lookup"><span data-stu-id="77460-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="77460-118">Para obtener más información, vea el tema [Administración de acceso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .</span><span class="sxs-lookup"><span data-stu-id="77460-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="77460-120">Para poner en práctica esta configuración en un entorno de prueba, consulte [Guía de gestión de acceso privilegiado en un entorno de pruebas](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="77460-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="77460-121">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step7) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="77460-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="77460-122">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="77460-122">Next Step</span></span>

[<span data-ttu-id="77460-123">Criterios de salida de infraestructura de protección de información</span><span class="sxs-lookup"><span data-stu-id="77460-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
