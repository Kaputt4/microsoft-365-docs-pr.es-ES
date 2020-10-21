---
title: Administración de dispositivos móviles para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo contoso usa Microsoft Intune en Microsoft 365 para empresas para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: d3f973827a9b05a415efe9225a2bdb3d83ccaf38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649650"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="d3eb9-103">Administración de dispositivos móviles para Contoso</span><span class="sxs-lookup"><span data-stu-id="d3eb9-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="d3eb9-104">Microsoft 365 para empresas incluye Intune y un conjunto de servicios de Azure compatibles con la administración y seguridad de dispositivos móviles y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="d3eb9-p101">Contoso tiene muchos empleados con movilidad habilitada. Algunas tienen oficinas en las ubicaciones de Contoso y otras no tienen oficinas. Contoso necesitaba una forma de habilitar la productividad de los empleados y mantener seguros los dispositivos, los datos de Contoso almacenados en dichos dispositivos y el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="d3eb9-108">Plan</span><span class="sxs-lookup"><span data-stu-id="d3eb9-108">Plan</span></span>

<span data-ttu-id="d3eb9-109">Contoso identificó los siguientes casos de uso de Intune de la administración de dispositivos móviles para Microsoft 365 para empresas:</span><span class="sxs-lookup"><span data-stu-id="d3eb9-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="d3eb9-110">Proteger los datos y el correo electrónico de Exchange Online para que los dispositivos móviles puedan acceder a ellos de forma segura.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="d3eb9-111">Implemente un programa traer a su propio dispositivo (BYOD) para los empleados de contoso.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="d3eb9-112">Emitir teléfonos de propiedad de organización y tabletas compartidas de uso limitado a los empleados de contoso.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="d3eb9-113">Contoso no usa Intune para:</span><span class="sxs-lookup"><span data-stu-id="d3eb9-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="d3eb9-114">Permitir a los empleados tener acceso seguro a Microsoft 365 desde un quiosco público no administrado.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="d3eb9-115">Proteger el correo electrónico y los datos locales para que los dispositivos móviles puedan acceder a ellos de forma segura, ya que no hay servidores de Microsoft Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="d3eb9-116">Implementación</span><span class="sxs-lookup"><span data-stu-id="d3eb9-116">Deploy</span></span>

<span data-ttu-id="d3eb9-117">Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d3eb9-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="d3eb9-118">Establezca Intune como la entidad de administración de dispositivos móviles (MDM) y use Intune en Azure para administrar el contenido y administrar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="d3eb9-119">Grupos de Azure Active Directory (Azure AD) creados para dispositivos para la configuración de Intune e Intune y las directivas de acceso condicional basadas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="d3eb9-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="d3eb9-120">Para obtener más información, consulte [directivas de acceso condicional de Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="d3eb9-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="d3eb9-121">Se ha habilitado la plataforma de dispositivos de Apple para admitir empleados con iPad, iMacs y iPhone y iPhones de propiedad corporativa.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="d3eb9-122">Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="d3eb9-123">Para los dispositivos que no están inscritos, implementó un conjunto de directivas de administración de aplicaciones móviles (MAM) para exigir la autenticación para obtener acceso a los servicios de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3eb9-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="d3eb9-124">Creó directivas de Intune que determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3eb9-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="d3eb9-125">Aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-125">Allowed apps.</span></span>
  - <span data-ttu-id="d3eb9-126">Cifrado del dispositivo para ayudar a evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="d3eb9-127">Un PIN de seis dígitos o una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="d3eb9-128">Un período de tiempo de espera de inactividad.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="d3eb9-129">Protección antivirus y contra malware, y actualizaciones de firmas con Windows Defender en dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="d3eb9-130">Actualizaciones automáticas en dispositivos con Windows 10 que incluyen las actualizaciones de seguridad más recientes.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="d3eb9-131">Insertar certificados en los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="d3eb9-p102">Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="d3eb9-134">Contoso inscribió los equipos implementados y smartphones y tabletas de propiedad de la empresa agregándolos a los grupos de dispositivos de Intune adecuados.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="d3eb9-135">También establecieron un programa BYOD para que los empleados inscriban sus dispositivos personales.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="d3eb9-136">Los dispositivos inscritos reciben directivas de Intune, que tienen como resultado los dispositivos administrados y protegidos y sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="d3eb9-137">Los dispositivos que no están inscritos tienen directivas de administración de aplicaciones móviles (MAM) que especifican las aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="d3eb9-138">Esta es la arquitectura de implementación de administración de dispositivos móviles de contoso.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Infraestructura de implementación de administración de dispositivos móviles de Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="d3eb9-140">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d3eb9-140">Next step</span></span>

<span data-ttu-id="d3eb9-141">[Obtenga información sobre](contoso-info-protect.md) cómo contoso usa las capacidades de protección de la información de Microsoft 365 para empresas para clasificar, identificar y proteger activos digitales fundamentales en toda su organización.</span><span class="sxs-lookup"><span data-stu-id="d3eb9-141">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3eb9-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3eb9-142">See also</span></span>

[<span data-ttu-id="d3eb9-143">Administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d3eb9-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="d3eb9-144">Información general de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d3eb9-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d3eb9-145">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="d3eb9-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

