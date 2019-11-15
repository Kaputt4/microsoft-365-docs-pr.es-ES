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
ms.openlocfilehash: 23c3298545a288b459fd3bb858bb7c1d1714ee75
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627386"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="82edd-103">Paso 4: Configurar Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="82edd-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="82edd-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="82edd-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="82edd-106">A medida que se utilizan más dispositivos personales para el trabajo, aumenta el riesgo de que aplicaciones y dispositivos sufran una pérdida de datos privados de la organización.</span><span class="sxs-lookup"><span data-stu-id="82edd-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="82edd-107">Por ejemplo, un empleado envía accidentalmente una imagen de un plan de marketing de un producto futuro a una red social o guarda un archivo que contiene información confidencial en su almacenamiento de nube público.</span><span class="sxs-lookup"><span data-stu-id="82edd-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="82edd-108">Windows Information Protection (WIP) le ayuda a protegerse contra estos tipos de filtrado de datos en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="82edd-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="82edd-109">Para obtener más información, vea [Proteger los datos empresariales con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="82edd-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="82edd-110">En Microsoft 365 Enterprise, WIP es una combinación de Windows 10 Enterprise y Microsoft Intune, que se incluye con su suscripción.</span><span class="sxs-lookup"><span data-stu-id="82edd-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="82edd-111">Para implementar WIP en su organización con Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="82edd-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="82edd-112">Inscriba los dispositivos de Windows en Intune.</span><span class="sxs-lookup"><span data-stu-id="82edd-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="82edd-113">Debería haberlo hecho en la [Fase 5: administración de dispositivos móviles](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="82edd-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="82edd-114">Cree una [directiva Intune para WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="82edd-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="82edd-115">Asegúrese de que se ha rellenado la lista de aplicaciones protegidas.</span><span class="sxs-lookup"><span data-stu-id="82edd-115">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="82edd-116">Elija el nivel de protección de WIP.</span><span class="sxs-lookup"><span data-stu-id="82edd-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="82edd-117">También puede usar el trabajo en curso con [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="82edd-117">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="82edd-118">Vea [Procedimientos recomendados para WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="82edd-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="82edd-119">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="82edd-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="82edd-120">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="82edd-120">Next step</span></span>

|||
|:-------|:-----|
|![Paso 5](./media/stepnumbers/Step5.png)|[<span data-ttu-id="82edd-122">Configurar la Prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="82edd-122">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


