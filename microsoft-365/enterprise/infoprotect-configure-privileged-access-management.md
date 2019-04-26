---
title: 'Paso 6: configurar la administración del acceso con privilegios para Office 365'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprenda y configure la administración del acceso con privilegios para Office 365
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304160"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="d4a9b-103">Paso 6: configurar la administración del acceso con privilegios para Office 365</span><span class="sxs-lookup"><span data-stu-id="d4a9b-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="d4a9b-104">*Este paso es opcional y solo es válido para las versiones E5 y de cumplimiento avanzado de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d4a9b-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d4a9b-p101">La administración del acceso con privilegios se habilita configurando directivas que especifiquen el acceso puntual para actividades basadas en tareas en el inquilino de Office 365. Permite proteger la organización ante infracciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración del acceso con privilegios que requiera una autorización explícita para acceder a la configuración del buzón de correo del inquilino de Office 365 y modificar la misma.</span><span class="sxs-lookup"><span data-stu-id="d4a9b-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="d4a9b-p102">En este paso, habilitará la administración del acceso con privilegios en el inquilino de Office 365 y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a los datos y las opciones de configuración de Office 365 de la organización. Para empezar con el acceso con privilegios en la organización de Office 365, debe seguir estos tres pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="d4a9b-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="d4a9b-110">Crear un grupo de aprobadores</span><span class="sxs-lookup"><span data-stu-id="d4a9b-110">Creating an approver's group</span></span>
- <span data-ttu-id="d4a9b-111">Habilitar el acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="d4a9b-111">Enabling privileged access</span></span>
- <span data-ttu-id="d4a9b-112">Crear directivas de aprobación</span><span class="sxs-lookup"><span data-stu-id="d4a9b-112">Creating approval policies</span></span>

<span data-ttu-id="d4a9b-p103">Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.</span><span class="sxs-lookup"><span data-stu-id="d4a9b-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="d4a9b-116">Para habilitar la administración del acceso con privilegios de Office 365, vea el tema [Configurar la administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="d4a9b-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="d4a9b-117">Para obtener más información, vea el tema [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="d4a9b-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="d4a9b-118">Resultados</span><span class="sxs-lookup"><span data-stu-id="d4a9b-118">Results</span></span>

<span data-ttu-id="d4a9b-119">El resultado de este paso es que ha incrementado la seguridad de Office 365 al habilitar el acceso puntual para datos clave y opciones de configuración de la organización.</span><span class="sxs-lookup"><span data-stu-id="d4a9b-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="d4a9b-120">Como control interno, consulte los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step6) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="d4a9b-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4a9b-121">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d4a9b-121">Next Step</span></span>

[<span data-ttu-id="d4a9b-122">Criterios de salida de infraestructura de protección de información</span><span class="sxs-lookup"><span data-stu-id="d4a9b-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)