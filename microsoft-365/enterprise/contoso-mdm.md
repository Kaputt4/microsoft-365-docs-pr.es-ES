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
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso utiliza EMS en Microsoft 365 Enterprise para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: e6b6f822a8c0ea26b3d899e3531653b19e225d65
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871150"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="4aaf5-103">Administración de dispositivos móviles para Contoso</span><span class="sxs-lookup"><span data-stu-id="4aaf5-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="4aaf5-104">**Resumen:** Comprenda cómo Contoso utiliza EMS en Microsoft 365 Enterprise para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-104">**Summary:** Understand how Contoso uses EMS in Microsoft 365 Enterprise to manage its devices and the apps that run on them.</span></span>

<span data-ttu-id="4aaf5-105">Enterprise Mobility + Security (EMS) en Microsoft 365 Enterprise se compone de un conjunto de servicios de Azure y Microsoft Intune para facilitar la administración y la seguridad de dispositivos móviles y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-105">Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise consists of Microsoft Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="4aaf5-p101">Contoso tiene muchos empleados con servicios móviles habilitados. Algunos de ellos tienen oficinas en ubicaciones y otros no tienen oficinas. Contoso necesitaba una forma de facilitar la productividad de los empleados y, a la vez, proteger los dispositivos, los datos de Contoso almacenados en esos dispositivos y el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="4aaf5-108">Plan</span><span class="sxs-lookup"><span data-stu-id="4aaf5-108">Plan</span></span>

<span data-ttu-id="4aaf5-109">En las primeras fases del análisis de la administración de dispositivos móviles para Microsoft 365 Enterprise, Contoso identificó los siguientes casos de uso de Intune:</span><span class="sxs-lookup"><span data-stu-id="4aaf5-109">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="4aaf5-110">Proteger los datos y el correo electrónico de Exchange Online para que se pueda acceder a los mismos de forma segura</span><span class="sxs-lookup"><span data-stu-id="4aaf5-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="4aaf5-111">Implementar un programa Bring your own device (BYOD) para los empleados de Contoso</span><span class="sxs-lookup"><span data-stu-id="4aaf5-111">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="4aaf5-112">Dar a los empleados de Contoso tabletas de uso compartido y limitado y teléfonos propiedad de la organización</span><span class="sxs-lookup"><span data-stu-id="4aaf5-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="4aaf5-113">Contoso no va a usar Intune para:</span><span class="sxs-lookup"><span data-stu-id="4aaf5-113">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="4aaf5-114">Permitir a los empleados que accedan de forma segura a Office 365 desde un quiosco público no administrado</span><span class="sxs-lookup"><span data-stu-id="4aaf5-114">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="4aaf5-115">Proteger los datos y el correo electrónico locales para que se pueda acceder a los mismos desde dispositivos móviles, porque ya no hay servidores de Microsoft Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="4aaf5-116">Implementación</span><span class="sxs-lookup"><span data-stu-id="4aaf5-116">Deploy</span></span>

<span data-ttu-id="4aaf5-117">Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4aaf5-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="4aaf5-118">Configuró Intune como entidad de administración de dispositivos móviles (MDM) y está usando Intune en Azure para administrar el contenido y los dispositivos</span><span class="sxs-lookup"><span data-stu-id="4aaf5-118">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="4aaf5-119">Creó grupos de Azure AD para grupos de dispositivos para las configuraciones de inscripción e Intune y las directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="4aaf5-119">Created Azure AD groups for device groups for enrollment and Intune settings and conditional access policies</span></span>
- <span data-ttu-id="4aaf5-120">Habilitó la plataforma de dispositivos de Apple para dar soporte a los empleados con iPads, iMacs, iPhones y teléfonos de propiedad corporativa basados en iPhone</span><span class="sxs-lookup"><span data-stu-id="4aaf5-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="4aaf5-121">Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="4aaf5-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="4aaf5-122">Para los dispositivos que no están inscritos, un conjunto de directivas de administración de aplicaciones móviles (MAM) para exigir la autenticación para acceder a los servicios de Office 365</span><span class="sxs-lookup"><span data-stu-id="4aaf5-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="4aaf5-123">Creó directivas de Intune determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4aaf5-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="4aaf5-124">Aplicaciones permitidas</span><span class="sxs-lookup"><span data-stu-id="4aaf5-124">Allowed apps</span></span>
  - <span data-ttu-id="4aaf5-125">Cifrado del dispositivo para ayudar a evitar accesos no autorizados</span><span class="sxs-lookup"><span data-stu-id="4aaf5-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="4aaf5-126">Una contraseña o un PIN de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4aaf5-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="4aaf5-127">Un período de tiempo de espera de inactividad</span><span class="sxs-lookup"><span data-stu-id="4aaf5-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="4aaf5-128">Protección antivirus y contra malware, y actualizaciones de firma con Windows Defender en dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="4aaf5-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="4aaf5-129">Actualizaciones automáticas en dispositivos con Windows 10, en las que se incluyen las actualizaciones de seguridad más recientes</span><span class="sxs-lookup"><span data-stu-id="4aaf5-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="4aaf5-130">Inserción de certificados en los dispositivos administrados</span><span class="sxs-lookup"><span data-stu-id="4aaf5-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="4aaf5-p102">Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="4aaf5-p103">Una vez realizada la implementación, Contoso inscribió equipos y dispositivos y tabletas propiedad de la empresa, agregándolos a los correspondientes grupos de dispositivos de Intune, y desarrolló un programa BYOD para que los empleados inscribieran sus dispositivos personales. Se aplicaron directivas de Intune a los dispositivos inscritos, con lo que se garantizó la administración y la protección de los dispositivos y sus aplicaciones. Los dispositivos no inscritos tienen directivas de administración de aplicaciones móviles (MAM) que establecen las aplicaciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

## <a name="next-step"></a><span data-ttu-id="4aaf5-136">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="4aaf5-136">Next step</span></span>

<span data-ttu-id="4aaf5-137">[Obtenga más información](contoso-info-protect.md) sobre cómo usa Contoso las funcionalidades de protección de la información de Microsoft 365 Enterprise para clasificar, identificar y proteger activos digitales cruciales en su organización.</span><span class="sxs-lookup"><span data-stu-id="4aaf5-137">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="4aaf5-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aaf5-138">See also</span></span>

[<span data-ttu-id="4aaf5-139">Administración de dispositivos móviles para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4aaf5-139">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="4aaf5-140">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="4aaf5-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4aaf5-141">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="4aaf5-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

