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
ms.openlocfilehash: 40d9473bcadfa636f6fd2b2c6c861c27dae8497c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685847"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="a8f35-103">Administración de dispositivos móviles para Contoso</span><span class="sxs-lookup"><span data-stu-id="a8f35-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="a8f35-104">Microsoft 365 para empresas incluye Intune y un conjunto de servicios de Azure para admitir la administración y seguridad de dispositivos móviles y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8f35-104">Microsoft 365 for enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="a8f35-p101">Contoso tiene muchos empleados con servicios móviles habilitados. Algunos de ellos tienen oficinas en ubicaciones y otros no tienen oficinas. Contoso necesitaba una forma de facilitar la productividad de los empleados y, a la vez, proteger los dispositivos, los datos de Contoso almacenados en esos dispositivos y el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8f35-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="a8f35-107">Plan</span><span class="sxs-lookup"><span data-stu-id="a8f35-107">Plan</span></span>

<span data-ttu-id="a8f35-108">En las primeras fases del análisis de la administración de dispositivos móviles para Microsoft 365 para empresas, contoso identificó los siguientes casos de uso de Intune:</span><span class="sxs-lookup"><span data-stu-id="a8f35-108">Early in the analysis of mobile device management for Microsoft 365 for enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="a8f35-109">Proteger los datos y el correo electrónico de Exchange Online para que se pueda acceder a los mismos de forma segura</span><span class="sxs-lookup"><span data-stu-id="a8f35-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="a8f35-110">Implementar un programa Bring your own device (BYOD) para los empleados de Contoso</span><span class="sxs-lookup"><span data-stu-id="a8f35-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="a8f35-111">Dar a los empleados de Contoso tabletas de uso compartido y limitado y teléfonos propiedad de la organización</span><span class="sxs-lookup"><span data-stu-id="a8f35-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="a8f35-112">Contoso no va a usar Intune para:</span><span class="sxs-lookup"><span data-stu-id="a8f35-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="a8f35-113">Permitir a los empleados el acceso seguro a Microsoft 365 desde un quiosco público no administrado</span><span class="sxs-lookup"><span data-stu-id="a8f35-113">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="a8f35-114">Proteger los datos y el correo electrónico locales para que se pueda acceder a los mismos desde dispositivos móviles, porque ya no hay servidores de Microsoft Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="a8f35-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="a8f35-115">Implementación</span><span class="sxs-lookup"><span data-stu-id="a8f35-115">Deploy</span></span>

<span data-ttu-id="a8f35-116">Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a8f35-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="a8f35-117">Configuró Intune como entidad de administración de dispositivos móviles (MDM) y está usando Intune en Azure para administrar el contenido y los dispositivos</span><span class="sxs-lookup"><span data-stu-id="a8f35-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="a8f35-118">Grupos de Azure AD creados para dispositivos para las configuraciones de inscripción e Intune y las directivas de acceso condicional basadas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="a8f35-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="a8f35-119">Vea las [Directivas de acceso condicional de Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a8f35-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="a8f35-120">Habilitó la plataforma de dispositivos de Apple para dar soporte a los empleados con iPads, iMacs, iPhones y teléfonos de propiedad corporativa basados en iPhone.</span><span class="sxs-lookup"><span data-stu-id="a8f35-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="a8f35-121">Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="a8f35-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="a8f35-122">Para los dispositivos que no están inscritos, un conjunto de directivas de administración de aplicaciones móviles (MAM) que requieren autenticación para obtener acceso a los servicios de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8f35-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="a8f35-123">Creó directivas de Intune que determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8f35-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="a8f35-124">Aplicaciones permitidas</span><span class="sxs-lookup"><span data-stu-id="a8f35-124">Allowed apps</span></span>
  - <span data-ttu-id="a8f35-125">Cifrado del dispositivo para ayudar a evitar accesos no autorizados</span><span class="sxs-lookup"><span data-stu-id="a8f35-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="a8f35-126">Una contraseña o un PIN de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="a8f35-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="a8f35-127">Un período de tiempo de espera de inactividad</span><span class="sxs-lookup"><span data-stu-id="a8f35-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="a8f35-128">Protección antivirus y contra malware, y actualizaciones de firma con Windows Defender en dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="a8f35-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="a8f35-129">Actualizaciones automáticas en dispositivos con Windows 10, en las que se incluyen las actualizaciones de seguridad más recientes</span><span class="sxs-lookup"><span data-stu-id="a8f35-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="a8f35-130">Inserción de certificados en los dispositivos administrados</span><span class="sxs-lookup"><span data-stu-id="a8f35-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="a8f35-p102">Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.</span><span class="sxs-lookup"><span data-stu-id="a8f35-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="a8f35-p103">Una vez realizada la implementación, Contoso inscribió equipos y dispositivos y tabletas propiedad de la empresa, agregándolos a los correspondientes grupos de dispositivos de Intune, y desarrolló un programa BYOD para que los empleados inscribieran sus dispositivos personales. Se aplicaron directivas de Intune a los dispositivos inscritos, con lo que se garantizó la administración y la protección de los dispositivos y sus aplicaciones. Los dispositivos no inscritos tienen directivas de administración de aplicaciones móviles (MAM) que establecen las aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="a8f35-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="a8f35-136">Esta es la arquitectura de implementación de la administración de dispositivos móviles de Contoso.</span><span class="sxs-lookup"><span data-stu-id="a8f35-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Infraestructura de implementación de la administración de dispositivos móviles de Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="a8f35-138">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="a8f35-138">Next step</span></span>

<span data-ttu-id="a8f35-139">[Obtenga información sobre](contoso-info-protect.md) cómo contoso usa las capacidades de protección de la información de Microsoft 365 para empresas para clasificar, identificar y proteger activos digitales fundamentales en toda su organización.</span><span class="sxs-lookup"><span data-stu-id="a8f35-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8f35-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8f35-140">See also</span></span>

[<span data-ttu-id="a8f35-141">Administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8f35-141">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="a8f35-142">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8f35-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a8f35-143">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="a8f35-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

