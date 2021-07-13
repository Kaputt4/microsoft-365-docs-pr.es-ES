---
title: Requisitos para Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para proveedores de servicios administrados (MSP), obtenga una lista de requisitos para usar Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395352"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="b5145-103">Requisitos para Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="b5145-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="b5145-104">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplan los requisitos enumerados en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5145-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="b5145-105">Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="b5145-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="b5145-106">Microsoft 365 Lighthouse es un portal de administración que ayuda a los proveedores de servicios administrados (MSP) a proteger y administrar dispositivos, datos y usuarios a escala para clientes de pequeñas y medianas empresas (SMB).</span><span class="sxs-lookup"><span data-stu-id="b5145-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="b5145-107">Los MSP deben estar inscritos en el programa Proveedor de soluciones en la nube (CSP) como revendedor indirecto o socio de factura directa para usar Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="b5145-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="b5145-108">Además, cada inquilino de cliente MSP debe cumplir los requisitos Microsoft 365 Lighthouse requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5145-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="b5145-109">Privilegios de administrador delegados (DAP) para msp</span><span class="sxs-lookup"><span data-stu-id="b5145-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="b5145-110">Al menos una Microsoft 365 Empresa Premium licencia</span><span class="sxs-lookup"><span data-stu-id="b5145-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="b5145-111">Menos de 500 usuarios con licencia</span><span class="sxs-lookup"><span data-stu-id="b5145-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="b5145-112">Requisitos para habilitar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b5145-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="b5145-113">Para ver los dispositivos de inquilino del cliente en las páginas de administración de dispositivos, un MSP debe:</span><span class="sxs-lookup"><span data-stu-id="b5145-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="b5145-114">Inscribir todos los dispositivos de cliente en Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="b5145-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="b5145-115">Para obtener más información, vea [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).</span><span class="sxs-lookup"><span data-stu-id="b5145-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="b5145-116">Asignar directivas de cumplimiento a todos los dispositivos de cliente.</span><span class="sxs-lookup"><span data-stu-id="b5145-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="b5145-117">Para obtener más información, vea [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="b5145-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="b5145-118">Requisitos para habilitar la administración de usuarios</span><span class="sxs-lookup"><span data-stu-id="b5145-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="b5145-119">Para que los datos de los clientes se muestren en informes en páginas de administración de usuarios, incluidos usuarios arriesgados, autenticación multifactor y restablecimiento de contraseña, los inquilinos de clientes deben tener licencias para Azure Active Directory Premium P1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b5145-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="b5145-120">Azure AD Premium P1 se incluye con Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="b5145-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="b5145-121">Requisitos para habilitar la administración de amenazas</span><span class="sxs-lookup"><span data-stu-id="b5145-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="b5145-122">Para ver los dispositivos de inquilino del cliente y las amenazas en las páginas de administración de amenazas, debe inscribir todos los dispositivos de inquilino del cliente en Microsoft Endpoint Manager (MEM) y protegerlos ejecutando Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b5145-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="b5145-123">Para obtener más información, vea [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).</span><span class="sxs-lookup"><span data-stu-id="b5145-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="b5145-124">Antivirus de Microsoft Defender forma parte del Windows operativo y está habilitado de forma predeterminada en dispositivos que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b5145-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="b5145-125">Si usa una solución antivirus que no es de Microsoft y no Antivirus de Microsoft Defender, Antivirus de Microsoft Defender se deshabilita automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b5145-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="b5145-126">Al desinstalar la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender se activa automáticamente para proteger los dispositivos Windows amenazas.</span><span class="sxs-lookup"><span data-stu-id="b5145-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="b5145-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="b5145-127">Related content</span></span>   

<span data-ttu-id="b5145-128">[Configurar Microsoft 365 Lighthouse seguridad del portal](m365-lighthouse-configure-portal-security.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5145-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="b5145-129">[Microsoft 365 Lighthouse de la página de cumplimiento de dispositivos](m365-lighthouse-device-compliance-page-overview.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5145-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="b5145-130">[Microsoft 365 Lighthouse de la página Usuarios](m365-lighthouse-users-page-overview.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5145-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="b5145-131">[Microsoft 365 Lighthouse de la página de administración de amenazas](m365-lighthouse-threat-management-page-overview.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5145-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="b5145-132">[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml)   (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5145-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

