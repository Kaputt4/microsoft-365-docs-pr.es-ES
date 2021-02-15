---
title: Usar la protección de identidades, dispositivos y amenazas para la regulación de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Evitar infracciones de datos personales con los servicios de protección de identidades, dispositivos y amenazas de Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847183"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="2b86e-103">Usar la protección de identidades, dispositivos y amenazas para la regulación de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="2b86e-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="2b86e-104">Microsoft 365 proporciona una serie de funcionalidades de protección de identidades, dispositivos y amenazas que las organizaciones pueden emplear para ayudar a cumplir con las normativas de cumplimiento relacionadas con la privacidad de los datos.</span><span class="sxs-lookup"><span data-stu-id="2b86e-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="2b86e-105">En este artículo se describe lo que las normativas de privacidad de datos requieren en estas áreas y se proporciona una lista de características y servicios relacionados de Microsoft 365 con vínculos a más información para ayudarle a cumplir los requisitos de implementación.</span><span class="sxs-lookup"><span data-stu-id="2b86e-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="2b86e-106">Modo en que la protección de identidades, dispositivos y amenazas se relaciona con la regulación de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="2b86e-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="2b86e-107">Aunque las normativas de privacidad de datos varían en su especificidad, la esencia de lo que llaman se incluye en el artículo 5(1) (f) del RGPD, que indica que:</span><span class="sxs-lookup"><span data-stu-id="2b86e-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="2b86e-108">Los datos personales se procesarán de manera que garanticen la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida, destrucción o daños accidentales, mediante las medidas técnicas u organizativas adecuadas ("integridad y confidencialidad").</span><span class="sxs-lookup"><span data-stu-id="2b86e-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="2b86e-109">Dado que las infracciones de datos personales suelen deberse a la amenaza de la cuenta administrativa o del usuario final y al acceso malintencionado al sistema.</span><span class="sxs-lookup"><span data-stu-id="2b86e-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="2b86e-110">Por ejemplo, un pirateo de la cuenta de administrador puede provocar la filtración de los números de tarjeta de crédito del cliente u otra información personal.</span><span class="sxs-lookup"><span data-stu-id="2b86e-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="2b86e-111">Todas las identidades, dispositivos y protección contra amenazas generalmente recomendables disponibles con Microsoft 365 potencialmente deben implementarse, lo que se reflejará en la puntuación de cumplimiento, que se encuentra en el Administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2b86e-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="2b86e-112">Uso de los resultados del trabajo de evaluación y el Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2b86e-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="2b86e-113">El Administrador de cumplimiento incluye protección contra amenazas, dispositivos y identidades mediante estas categorías:</span><span class="sxs-lookup"><span data-stu-id="2b86e-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="2b86e-114">La identidad corresponde a la categoría **Acceso de** control</span><span class="sxs-lookup"><span data-stu-id="2b86e-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="2b86e-115">El dispositivo corresponde a la categoría **Administrar dispositivos**</span><span class="sxs-lookup"><span data-stu-id="2b86e-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="2b86e-116">La protección contra amenazas corresponde a la categoría **Proteger contra amenazas**</span><span class="sxs-lookup"><span data-stu-id="2b86e-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="2b86e-117">Si se seleccionan en nuestro conjunto de ejemplo de cuatro normativas principales de privacidad de datos, el Administrador de cumplimiento especifica 90 acciones de mejora, la mayoría de las cuales se marcan como "27".</span><span class="sxs-lookup"><span data-stu-id="2b86e-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="2b86e-118">Dado que el Administrador de cumplimiento llama a un número tan grande para estas categorías, algunos de los más comunes se enumeran aquí, como referencia.</span><span class="sxs-lookup"><span data-stu-id="2b86e-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="2b86e-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para la identidad y la categoría De acceso de **control,** con la que puede:</span><span class="sxs-lookup"><span data-stu-id="2b86e-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="2b86e-120">Implementar la autenticación resistente a la reproducción (para evitar ataques "Man in the middle")</span><span class="sxs-lookup"><span data-stu-id="2b86e-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="2b86e-121">Bloquear la autenticación heredada.</span><span class="sxs-lookup"><span data-stu-id="2b86e-121">Block legacy authentication.</span></span>
- <span data-ttu-id="2b86e-122">Configurar directivas de riesgo de usuario y riesgo de inicio de sesión de usuario.</span><span class="sxs-lookup"><span data-stu-id="2b86e-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="2b86e-123">Habilite el acceso condicional y la autenticación multifactor (MFA) para administradores y no administradores.</span><span class="sxs-lookup"><span data-stu-id="2b86e-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="2b86e-124">Configurar y aplicar directivas de contraseña.</span><span class="sxs-lookup"><span data-stu-id="2b86e-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="2b86e-125">Restrinja el acceso a cuentas con privilegios con Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="2b86e-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="2b86e-126">Deshabilitar el acceso al finalizar.</span><span class="sxs-lookup"><span data-stu-id="2b86e-126">Disable access upon termination.</span></span>
- <span data-ttu-id="2b86e-127">Auditar cuentas de usuario y cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="2b86e-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="2b86e-128">Revise los cambios administrativos y del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="2b86e-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="2b86e-129">Usa [Microsoft Endpoint Manager para](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) dispositivos y la categoría Administrar **dispositivos,** con la que puedes:</span><span class="sxs-lookup"><span data-stu-id="2b86e-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="2b86e-130">Bloquear los dispositivos móviles rotos y con raíz de la celda.</span><span class="sxs-lookup"><span data-stu-id="2b86e-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="2b86e-131">Configurar Intune para la administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="2b86e-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="2b86e-132">Crear directivas de cumplimiento para dispositivos Android, iOS, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="2b86e-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="2b86e-133">Cree un perfil de configuración de dispositivos para dispositivos Android, iOS, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="2b86e-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="2b86e-134">Crear directivas de protección de aplicaciones para iOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="2b86e-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="2b86e-135">Ocultar información con la pantalla de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2b86e-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="2b86e-136">Implementar directivas de contraseña para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="2b86e-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="2b86e-137">Requerir que los dispositivos móviles se bloquee tras la inactividad.</span><span class="sxs-lookup"><span data-stu-id="2b86e-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="2b86e-138">Requerir que los dispositivos móviles borren varios errores de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="2b86e-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="2b86e-139">Use Exchange Online Protection y Microsoft Defender para  [Office 365](../security/office-365-security/office-365-atp.md) para la categoría Proteger contra amenazas, con la que puede:</span><span class="sxs-lookup"><span data-stu-id="2b86e-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="2b86e-140">Habilitar la autenticación del remitente (SPF, DMARC y DKIM).</span><span class="sxs-lookup"><span data-stu-id="2b86e-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="2b86e-141">Configurar Microsoft Defender para las directivas contra suplantación de identidad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b86e-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="2b86e-142">Implementar datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="2b86e-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="2b86e-143">Implementar vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="2b86e-143">Implement Safe Links.</span></span>
- <span data-ttu-id="2b86e-144">Implementar directivas de detección y respuesta de malware.</span><span class="sxs-lookup"><span data-stu-id="2b86e-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="2b86e-145">Implementar directivas de correo no deseado saliente y entrante.</span><span class="sxs-lookup"><span data-stu-id="2b86e-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="2b86e-146">Referencias:</span><span class="sxs-lookup"><span data-stu-id="2b86e-146">References:</span></span>

- [<span data-ttu-id="2b86e-147">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="2b86e-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="2b86e-148">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="2b86e-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="2b86e-149">Archivos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="2b86e-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="2b86e-150">Vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="2b86e-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="2b86e-151">Documentos seguros</span><span class="sxs-lookup"><span data-stu-id="2b86e-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
