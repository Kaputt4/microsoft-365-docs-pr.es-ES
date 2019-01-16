---
title: Criterios de salida de infraestructura de administración de dispositivos móviles
description: Microsoft 365 Enterprise incluye administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configurar Intune con su recurso de Azure Active Directory, inscribirse iOS, Mac OS, Android y Windows dispositivos, implementar aplicaciones, crear un perfil de configuración, use una directiva de cumplimiento de normas y habilitar el acceso condicional para mobile administración de dispositivos con Microsoft 365 Enterprise.
keywords: Documentación de Microsoft 365 365 de Microsoft, Microsoft 365 Enterprise, administración de dispositivos móviles, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871330"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="a2919-105">Criterios de salida de infraestructura de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="a2919-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="a2919-106">*Esto se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a2919-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a2919-107">Antes de pasar a la siguiente fase del proceso de implementación, asegúrese de que la configuración cumple los siguientes requisitos de infraestructura de administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="a2919-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="a2919-108">Intune está configurado y se han creado los usuarios y los grupos de Azure AD para aplicar las reglas de la organización para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a2919-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="a2919-109">Ha inscrito los dispositivos en Intune para que puedan recibir las directivas que cree.</span><span class="sxs-lookup"><span data-stu-id="a2919-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="a2919-110">Se agregaron las aplicaciones a los dispositivos para que los usuarios obtengan acceso a los servicios en la nube de Microsoft 365 de su organización, como Exchange Online y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a2919-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="a2919-111">Las características y ajustes se configuraron y aplicaron en los dispositivos con los usuarios y grupos de Azure AD que creó (por ejemplo, habilitar la protección antivirus y restringir aplicaciones específicas).</span><span class="sxs-lookup"><span data-stu-id="a2919-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="a2919-p102">Las directivas de cumplimiento se aplicaron para exigir un firewall o una longitud de contraseña en un dispositivo. Si los dispositivos no cumplen estas normas, el acceso condicional bloquea el acceso a los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="a2919-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="a2919-114">Fase siguiente</span><span class="sxs-lookup"><span data-stu-id="a2919-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="a2919-115">La siguiente fase del proceso de implementación de extremo a extremo para Microsoft 365 Enterprise es la [protección de la información](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="a2919-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
