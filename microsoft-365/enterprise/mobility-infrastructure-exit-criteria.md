---
title: Criterios de salida de la infraestructura de administración de dispositivos móviles
description: Microsoft 365 Enterprise incluye la administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configure Intune con el recurso de Azure Active Directory, inscriba dispositivos iOS, macOS, Android y Windows, implemente aplicaciones, cree un perfil de configuración, use una directiva de cumplimiento y habilite el acceso condicional para dispositivos móviles Administración de dispositivos con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: daf7bcf6525f30b7b52065e4f6bf2ff335f4ea4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600887"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="87352-105">Criterios de salida de la infraestructura de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="87352-105">Mobile device management infrastructure exit criteria</span></span>

![Fase 5: Administración de dispositivos móviles](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="87352-107">*Esto se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="87352-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="87352-108">Asegúrese de que la configuración cumple los siguientes requisitos para la infraestructura de administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="87352-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="87352-109">Intune está configurado, incluida la creación de usuarios y grupos de Azure Active Directory (Azure AD) para aplicar las reglas de la organización a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="87352-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="87352-110">Ha inscrito los dispositivos en Intune para que puedan recibir las directivas que cree.</span><span class="sxs-lookup"><span data-stu-id="87352-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="87352-111">Se agregaron las aplicaciones a los dispositivos para que los usuarios obtengan acceso a los servicios en la nube de Microsoft 365 de su organización, como Exchange Online y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="87352-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="87352-112">Las características y ajustes se configuraron y aplicaron en los dispositivos con los usuarios y grupos de Azure AD que creó (por ejemplo, habilitar la protección antivirus y restringir aplicaciones específicas).</span><span class="sxs-lookup"><span data-stu-id="87352-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="87352-113">Las directivas de cumplimiento están en su ubicación para requerir un firewall o una longitud de contraseña en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87352-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="87352-114">Si los dispositivos no son compatibles, el acceso condicional bloquea el acceso a los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="87352-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="87352-115">Resultados y siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="87352-115">Results and next steps</span></span>

<span data-ttu-id="87352-116">Los dispositivos se inscriben en Intune y se configuran con las directivas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="87352-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="87352-118">Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es la protección de la [información](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="87352-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
