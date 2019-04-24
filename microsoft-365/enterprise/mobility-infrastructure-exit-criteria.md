---
title: Criterios de salida de la infraestructura de administración de dispositivos móviles
description: Microsoft 365 Enterprise incluye la administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configure Intune con el recurso de Azure Active Directory, inscriba dispositivos iOS, macOS, Android y Windows, implemente aplicaciones, cree un perfil de configuración, use una directiva de cumplimiento y habilite el acceso condicional para dispositivos móviles Administración de dispositivos con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291237"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="57d40-105">Criterios de salida de la infraestructura de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="57d40-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="57d40-106">*Esto se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="57d40-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="57d40-107">Asegúrese de que la configuración cumple los siguientes requisitos para la infraestructura de administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="57d40-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="57d40-108">Intune está configurado y se han creado los usuarios y los grupos de Azure AD para aplicar las reglas de la organización para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="57d40-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="57d40-109">Ha inscrito los dispositivos en Intune para que puedan recibir las directivas que cree.</span><span class="sxs-lookup"><span data-stu-id="57d40-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="57d40-110">Se agregaron las aplicaciones a los dispositivos para que los usuarios obtengan acceso a los servicios en la nube de Microsoft 365 de su organización, como Exchange Online y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="57d40-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="57d40-111">Las características y ajustes se configuraron y aplicaron en los dispositivos con los usuarios y grupos de Azure AD que creó (por ejemplo, habilitar la protección antivirus y restringir aplicaciones específicas).</span><span class="sxs-lookup"><span data-stu-id="57d40-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="57d40-p102">Las directivas de cumplimiento se aplicaron para exigir un firewall o una longitud de contraseña en un dispositivo. Si los dispositivos no cumplen estas normas, el acceso condicional bloquea el acceso a los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="57d40-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="57d40-114">Resultados y pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="57d40-114">Results and next steps</span></span>

<span data-ttu-id="57d40-115">Los dispositivos se inscriben en Intune y se configuran con las directivas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="57d40-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="57d40-116">Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es la protección de la [información](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="57d40-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
