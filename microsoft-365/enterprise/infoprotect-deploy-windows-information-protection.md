---
title: 'Paso 4: Configurar Windows Information Protection'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprender e implementar Windows Information Protection en Microsoft 365.
ms.openlocfilehash: b624db45c4fe3bd75b2158f225176b7a78ba30f8
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047273"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="568e0-103">Paso 4: Configurar Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="568e0-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="568e0-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="568e0-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="568e0-105">A medida que se utilizan más dispositivos personales para el trabajo, aumenta el riesgo de que aplicaciones y dispositivos sufran una pérdida de datos privados de la organización.</span><span class="sxs-lookup"><span data-stu-id="568e0-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="568e0-106">Por ejemplo, un empleado envía accidentalmente una imagen de un plan de marketing de un producto futuro a una red social o guarda un archivo que contiene información confidencial en su almacenamiento de nube público.</span><span class="sxs-lookup"><span data-stu-id="568e0-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="568e0-107">Windows Information Protection (WIP) le ayuda a protegerse contra estos tipos de filtrado de datos en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="568e0-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="568e0-108">Para obtener más información, vea [Proteger los datos empresariales con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="568e0-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="568e0-109">En Microsoft 365 Enterprise, WIP es una combinación de Windows 10 Enterprise y Microsoft Intune, que se incluye con su suscripción.</span><span class="sxs-lookup"><span data-stu-id="568e0-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="568e0-110">Para implementar WIP en su organización con Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="568e0-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="568e0-111">Inscriba los dispositivos de Windows en Intune.</span><span class="sxs-lookup"><span data-stu-id="568e0-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="568e0-112">Debería haberlo hecho en la [Fase 5: administración de dispositivos móviles](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="568e0-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="568e0-113">Cree una [directiva Intune para WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="568e0-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="568e0-114">Asegúrese de que se ha rellenado la lista de aplicaciones protegidas.</span><span class="sxs-lookup"><span data-stu-id="568e0-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="568e0-115">Elija el nivel de protección de WIP.</span><span class="sxs-lookup"><span data-stu-id="568e0-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="568e0-116">También puede usar WIP con [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="568e0-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="568e0-117">Vea [Procedimientos recomendados para WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="568e0-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="568e0-118">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="568e0-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="568e0-119">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="568e0-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="568e0-120">Configurar la Prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="568e0-120">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


