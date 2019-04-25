---
title: Administración de dispositivos móviles para Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso utiliza EMS en Microsoft 365 Enterprise para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: f47d6a1ee608d33802f1c523d3b954af3771f212
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278047"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="8618a-103">Administración de dispositivos móviles para Contoso</span><span class="sxs-lookup"><span data-stu-id="8618a-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="8618a-104">**Resumen:** Comprenda cómo Contoso utiliza EMS en Microsoft 365 Enterprise para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.</span><span class="sxs-lookup"><span data-stu-id="8618a-104">**Summary:** Understand how Contoso uses EMS in Microsoft 365 Enterprise to manage its devices and the apps that run on them.</span></span>

<span data-ttu-id="8618a-105">Enterprise Mobility + Security (EMS) en Microsoft 365 Enterprise se compone de un conjunto de servicios de Azure y Microsoft Intune para facilitar la administración y la seguridad de dispositivos móviles y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8618a-105">Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise consists of Microsoft Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="8618a-p101">Contoso tiene muchos empleados con servicios móviles habilitados. Algunos de ellos tienen oficinas en ubicaciones y otros no tienen oficinas. Contoso necesitaba una forma de facilitar la productividad de los empleados y, a la vez, proteger los dispositivos, los datos de Contoso almacenados en esos dispositivos y el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8618a-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="8618a-108">Plan</span><span class="sxs-lookup"><span data-stu-id="8618a-108">Plan</span></span>

<span data-ttu-id="8618a-109">En las primeras fases del análisis de la administración de dispositivos móviles para Microsoft 365 Enterprise, Contoso identificó los siguientes casos de uso de Intune:</span><span class="sxs-lookup"><span data-stu-id="8618a-109">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="8618a-110">Proteger los datos y el correo electrónico de Exchange Online para que se pueda acceder a los mismos de forma segura</span><span class="sxs-lookup"><span data-stu-id="8618a-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="8618a-111">Implementar un programa Bring your own device (BYOD) para los empleados de Contoso</span><span class="sxs-lookup"><span data-stu-id="8618a-111">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="8618a-112">Dar a los empleados de Contoso tabletas de uso compartido y limitado y teléfonos propiedad de la organización</span><span class="sxs-lookup"><span data-stu-id="8618a-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="8618a-113">Contoso no va a usar Intune para:</span><span class="sxs-lookup"><span data-stu-id="8618a-113">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="8618a-114">Permitir a los empleados que accedan de forma segura a Office 365 desde un quiosco público no administrado</span><span class="sxs-lookup"><span data-stu-id="8618a-114">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="8618a-115">Proteger los datos y el correo electrónico locales para que se pueda acceder a los mismos desde dispositivos móviles, porque ya no hay servidores de Microsoft Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="8618a-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="8618a-116">Implementación</span><span class="sxs-lookup"><span data-stu-id="8618a-116">Deploy</span></span>

<span data-ttu-id="8618a-117">Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8618a-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="8618a-118">Configuró Intune como entidad de administración de dispositivos móviles (MDM) y está usando Intune en Azure para administrar el contenido y los dispositivos</span><span class="sxs-lookup"><span data-stu-id="8618a-118">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="8618a-119">Grupos de Azure AD creados para dispositivos para las configuraciones de inscripción e Intune y las directivas de acceso condicional basadas en dispositivos</span><span class="sxs-lookup"><span data-stu-id="8618a-119">Created Azure AD groups for device groups for enrollment and Intune settings and conditional access policies</span></span>

  <span data-ttu-id="8618a-120">Ve las [directivas de acceso condicional de Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8618a-120">See [Contoso's conditional access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="8618a-121">Habilitó la plataforma de dispositivos de Apple para dar soporte a los empleados con iPads, iMacs, iPhones y teléfonos de propiedad corporativa basados en iPhone</span><span class="sxs-lookup"><span data-stu-id="8618a-121">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="8618a-122">Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="8618a-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="8618a-123">Para los dispositivos que no están inscritos, un conjunto de directivas de administración de aplicaciones móviles (MAM) para exigir la autenticación para acceder a los servicios de Office 365</span><span class="sxs-lookup"><span data-stu-id="8618a-123">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="8618a-124">Creó directivas de Intune determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8618a-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="8618a-125">Aplicaciones permitidas</span><span class="sxs-lookup"><span data-stu-id="8618a-125">Allowed apps</span></span>
  - <span data-ttu-id="8618a-126">Cifrado del dispositivo para ayudar a evitar accesos no autorizados</span><span class="sxs-lookup"><span data-stu-id="8618a-126">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="8618a-127">Una contraseña o un PIN de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="8618a-127">A six-digit PIN or password</span></span>
  - <span data-ttu-id="8618a-128">Un período de tiempo de espera de inactividad</span><span class="sxs-lookup"><span data-stu-id="8618a-128">An inactivity timeout period</span></span>
  - <span data-ttu-id="8618a-129">Protección antivirus y contra malware, y actualizaciones de firma con Windows Defender en dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="8618a-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="8618a-130">Actualizaciones automáticas en dispositivos con Windows 10, en las que se incluyen las actualizaciones de seguridad más recientes</span><span class="sxs-lookup"><span data-stu-id="8618a-130">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="8618a-131">Inserción de certificados en los dispositivos administrados</span><span class="sxs-lookup"><span data-stu-id="8618a-131">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="8618a-p102">Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.</span><span class="sxs-lookup"><span data-stu-id="8618a-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="8618a-p103">Una vez realizada la implementación, Contoso inscribió equipos y dispositivos y tabletas propiedad de la empresa, agregándolos a los correspondientes grupos de dispositivos de Intune, y desarrolló un programa BYOD para que los empleados inscribieran sus dispositivos personales. Se aplicaron directivas de Intune a los dispositivos inscritos, con lo que se garantizó la administración y la protección de los dispositivos y sus aplicaciones. Los dispositivos no inscritos tienen directivas de administración de aplicaciones móviles (MAM) que establecen las aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="8618a-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

## <a name="next-step"></a><span data-ttu-id="8618a-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="8618a-137">Next step</span></span>

<span data-ttu-id="8618a-138">[Obtenga más información](contoso-info-protect.md) sobre cómo usa Contoso las funcionalidades de protección de la información de Microsoft 365 Enterprise para clasificar, identificar y proteger activos digitales cruciales en su organización.</span><span class="sxs-lookup"><span data-stu-id="8618a-138">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8618a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="8618a-139">See also</span></span>

[<span data-ttu-id="8618a-140">Administración de dispositivos móviles para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8618a-140">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="8618a-141">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="8618a-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8618a-142">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="8618a-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

