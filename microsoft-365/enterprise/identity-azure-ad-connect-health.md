---
title: 'Paso 8: Supervisar el estado de sincronización'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871581"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="e489c-103">Paso 8: Supervisar el estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="e489c-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="e489c-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e489c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="e489c-p101">En este paso, instalará un agente de Azure AD Connect Health en todos los servidores de identidades locales para supervisar la infraestructura de identidades y los servicios de sincronización proporcionados por Azure AD Connect. La información de supervisión estará disponible en un portal de Azure AD Connect Health, donde puede ver alertas, supervisión de rendimiento, análisis de uso y otra información.</span><span class="sxs-lookup"><span data-stu-id="e489c-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Componentes de Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="e489c-108">La decisión de diseño clave sobre cómo usar Azure AD Connect Health se basa en la forma en que use Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="e489c-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="e489c-109">Si usa la opción de **autenticación administrada**, vea primero [Usar Azure AD Connect Health con sincronización](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para comprender y configurar Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="e489c-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="e489c-110">Si solo sincroniza los nombres de las cuentas y los grupos mediante la **autenticación federada** con Servicios de federación de Active Directory (AD FS), empiece con [Usar Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para comprender y configurar Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="e489c-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="e489c-111">Cuando complete este paso, tendrá:</span><span class="sxs-lookup"><span data-stu-id="e489c-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="e489c-112">El agente de Azure AD Connect Health instalado en los servidores de proveedor de identidades locales.</span><span class="sxs-lookup"><span data-stu-id="e489c-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="e489c-113">En el portal de Azure AD Connect Health, se mostrará el estado actual de la infraestructura local y las actividades de sincronización con el espacio empresarial de Azure AD para sus suscripciones de Office 365 y EMS.</span><span class="sxs-lookup"><span data-stu-id="e489c-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="e489c-114">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-sync-health) de este paso.</span><span class="sxs-lookup"><span data-stu-id="e489c-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="e489c-115">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e489c-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="e489c-116">Simplificar las actualizaciones de contraseña</span><span class="sxs-lookup"><span data-stu-id="e489c-116">Simplify password updates</span></span>](identity-password-writeback.md) |

