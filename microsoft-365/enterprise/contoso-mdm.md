---
title: Administración de dispositivos móviles para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso usa Microsoft Intune en Microsoft 365 empresa para administrar sus dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754002"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="ae166-103">Administración de dispositivos móviles para Contoso</span><span class="sxs-lookup"><span data-stu-id="ae166-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="ae166-104">Microsoft 365 para empresas incluye Intune y un conjunto de servicios de Azure que admiten la seguridad y la administración de aplicaciones y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="ae166-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="ae166-105">Contoso tiene muchos empleados habilitados para móviles.</span><span class="sxs-lookup"><span data-stu-id="ae166-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="ae166-106">Algunas tienen oficinas en ubicaciones de Contoso y otras no tienen oficinas.</span><span class="sxs-lookup"><span data-stu-id="ae166-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="ae166-107">Contoso necesitaba una forma de habilitar la productividad de los empleados, pero mantener los dispositivos, los datos de Contoso almacenados en esos dispositivos y el comportamiento de la aplicación seguros.</span><span class="sxs-lookup"><span data-stu-id="ae166-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="ae166-108">Plan</span><span class="sxs-lookup"><span data-stu-id="ae166-108">Plan</span></span>

<span data-ttu-id="ae166-109">Contoso identificó los siguientes casos de uso de Intune de administración de dispositivos móviles para Microsoft 365 empresa:</span><span class="sxs-lookup"><span data-stu-id="ae166-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="ae166-110">Proteja Exchange Online correo electrónico y datos para que los dispositivos móviles puedan acceder a él de forma segura.</span><span class="sxs-lookup"><span data-stu-id="ae166-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="ae166-111">Implemente un programa bring-your-own-device (BYOD) para los empleados de Contoso.</span><span class="sxs-lookup"><span data-stu-id="ae166-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="ae166-112">Emitir teléfonos propiedad de la organización y tabletas compartidas de uso limitado para los empleados de Contoso.</span><span class="sxs-lookup"><span data-stu-id="ae166-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="ae166-113">Contoso no usa Intune para:</span><span class="sxs-lookup"><span data-stu-id="ae166-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="ae166-114">Permitir que los empleados accedan de forma Microsoft 365 desde un quiosco público no administrado.</span><span class="sxs-lookup"><span data-stu-id="ae166-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="ae166-115">Proteja el correo electrónico y los datos locales para que los dispositivos móviles puedan acceder a él de forma segura, ya que no hay servidores de Microsoft Exchange local.</span><span class="sxs-lookup"><span data-stu-id="ae166-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="ae166-116">Implementación</span><span class="sxs-lookup"><span data-stu-id="ae166-116">Deploy</span></span>

<span data-ttu-id="ae166-117">Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ae166-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="ae166-118">Establece Intune como entidad de administración de dispositivos móviles (MDM) y usa Intune en Azure para administrar contenido y administrar los dispositivos</span><span class="sxs-lookup"><span data-stu-id="ae166-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="ae166-119">Grupos Azure Active Directory (Azure AD) para dispositivos para la inscripción y la configuración de Intune y directivas de acceso condicional basadas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="ae166-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="ae166-120">Para obtener más información, vea [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="ae166-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="ae166-121">Se ha habilitado la plataforma de dispositivos Apple para admitir a los empleados con iPads, iMacs y iPhones y iPhones de propiedad corporativa</span><span class="sxs-lookup"><span data-stu-id="ae166-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="ae166-122">Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="ae166-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="ae166-123">Para dispositivos que no están inscritos, implementó un conjunto de directivas de administración de aplicaciones móviles (MAM) para requerir autenticación para el acceso a Microsoft 365 servicios</span><span class="sxs-lookup"><span data-stu-id="ae166-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="ae166-124">Creó directivas de Intune que determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae166-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="ae166-125">Aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="ae166-125">Allowed apps.</span></span>
  - <span data-ttu-id="ae166-126">Cifrado de dispositivos para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="ae166-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="ae166-127">Un PIN o contraseña de seis dígitos.</span><span class="sxs-lookup"><span data-stu-id="ae166-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="ae166-128">Un período de tiempo de espera de inactividad.</span><span class="sxs-lookup"><span data-stu-id="ae166-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="ae166-129">Protección contra antivirus y malware, y actualizaciones de firmas con Windows Defender en Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ae166-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="ae166-130">Actualizaciones automáticas en Windows 10 dispositivos que incluyen las actualizaciones de seguridad más recientes.</span><span class="sxs-lookup"><span data-stu-id="ae166-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="ae166-131">Insertar certificados en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="ae166-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="ae166-p102">Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.</span><span class="sxs-lookup"><span data-stu-id="ae166-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="ae166-134">Contoso inscribió equipos implementados y smartphones y tabletas de propiedad de la empresa agregándolos a los grupos de dispositivos de Intune adecuados.</span><span class="sxs-lookup"><span data-stu-id="ae166-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="ae166-135">También establecieron un programa BYOD para que los empleados inscriban sus dispositivos personales.</span><span class="sxs-lookup"><span data-stu-id="ae166-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="ae166-136">Los dispositivos inscritos reciben directivas de Intune, lo que da como resultado dispositivos administrados y protegidos y sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ae166-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="ae166-137">Los dispositivos que no están inscritos tienen directivas de administración de aplicaciones móviles (MAM) que especifican aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="ae166-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="ae166-138">Esta es la arquitectura de implementación de administración de dispositivos móviles contoso.</span><span class="sxs-lookup"><span data-stu-id="ae166-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Infraestructura de implementación de administración de dispositivos móviles contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="ae166-140">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="ae166-140">Next step</span></span>

<span data-ttu-id="ae166-141">Obtenga información sobre cómo Contoso usa las [capacidades](contoso-info-protect.md) de protección de la información de Microsoft 365 empresa para clasificar, identificar y proteger activos digitales cruciales en toda su organización.</span><span class="sxs-lookup"><span data-stu-id="ae166-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae166-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae166-142">See also</span></span>

[<span data-ttu-id="ae166-143">Administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae166-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="ae166-144">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae166-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ae166-145">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="ae166-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

