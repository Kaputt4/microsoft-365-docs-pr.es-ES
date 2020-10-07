---
title: Usar identidad, dispositivo y protección contra amenazas para la normativa de privacidad de datos
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
description: Evite las violaciones de datos personales con los servicios de identidad, dispositivos y protección contra amenazas de Microsoft 365.
ms.openlocfilehash: 681ff807b734430ae864334b409fe11397f3089e
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377062"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="b7404-103">Usar identidad, dispositivo y protección contra amenazas para la normativa de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="b7404-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="b7404-104">Microsoft 365 proporciona una serie de capacidades de identidad, dispositivo y protección contra amenazas que las organizaciones pueden emplear para ayudar a cumplir con las regulaciones de cumplimiento de datos relacionadas con la privacidad de datos.</span><span class="sxs-lookup"><span data-stu-id="b7404-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="b7404-105">En este artículo se describe lo que los reglamentos de privacidad de datos requieren en estas áreas y se proporciona una lista de características y servicios de Microsoft 365 con vínculos a información adicional que le ayudarán a abordar los requisitos de implementación.</span><span class="sxs-lookup"><span data-stu-id="b7404-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="b7404-106">Cómo se relacionan la protección de identidades, dispositivos y amenazas con la normativa de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="b7404-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="b7404-107">Aunque las regulaciones de privacidad de datos varían en su especificidad, la esencia de lo que llaman se expresa en el artículo 5 de RGPD (1) (f), que establece que:</span><span class="sxs-lookup"><span data-stu-id="b7404-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="b7404-108">Los datos personales se procesarán de manera que se garantice la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida, destrucción o daños accidentales, mediante las medidas técnicas o organizacionales adecuadas (integridad y confidencialidad).</span><span class="sxs-lookup"><span data-stu-id="b7404-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="b7404-109">Debido a que las infracciones de datos personales suelen deberse a la intromisión de cuentas de usuarios finales o administrativos y al acceso malintencionado al sistema.</span><span class="sxs-lookup"><span data-stu-id="b7404-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="b7404-110">Por ejemplo, una cuenta de administrador pirata puede dar como resultado la exfiltración de números de tarjeta de crédito de clientes u otra información personal.</span><span class="sxs-lookup"><span data-stu-id="b7404-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="b7404-111">Todos los requisitos generales de identidad, dispositivo y protección contra amenazas disponibles con Microsoft 365 potencialmente deben implementarse, lo que se reflejará en su puntuación de cumplimiento, que se encuentra en el administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b7404-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="b7404-112">Uso de los resultados del administrador de cumplimiento y trabajo de evaluación</span><span class="sxs-lookup"><span data-stu-id="b7404-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="b7404-113">El administrador de cumplimiento incluye la protección contra amenazas, dispositivos y identidades mediante estas categorías:</span><span class="sxs-lookup"><span data-stu-id="b7404-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="b7404-114">La identidad corresponde a la categoría de **acceso de control**</span><span class="sxs-lookup"><span data-stu-id="b7404-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="b7404-115">El dispositivo corresponde a la categoría **administrar dispositivos**</span><span class="sxs-lookup"><span data-stu-id="b7404-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="b7404-116">La protección contra amenazas corresponde a la categoría **protección contra amenazas**</span><span class="sxs-lookup"><span data-stu-id="b7404-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="b7404-117">Si se seleccionan en el conjunto de ejemplo de cuatro normativas de privacidad de datos principales, el administrador de cumplimiento especifica las acciones de mejora de 90, la mayoría de las cuales se puntuan como "27".</span><span class="sxs-lookup"><span data-stu-id="b7404-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="b7404-118">Dado que el administrador de cumplimiento llama a un número tan grande para estas categorías, algunos de los más comunes se enumeran aquí, como referencia.</span><span class="sxs-lookup"><span data-stu-id="b7404-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="b7404-119">Use [Azure Active Directory (Azure ad)](https://azure.microsoft.com/services/active-directory/) para la identidad y la categoría de **acceso de control** , con la que puede:</span><span class="sxs-lookup"><span data-stu-id="b7404-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="b7404-120">Implementación de la autenticación resistente a la reproducción (para evitar ataques "Man in the Middle")</span><span class="sxs-lookup"><span data-stu-id="b7404-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="b7404-121">Bloquear la autenticación heredada.</span><span class="sxs-lookup"><span data-stu-id="b7404-121">Block legacy authentication.</span></span>
- <span data-ttu-id="b7404-122">Configure los riesgos de usuario y las directivas de riesgo de inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="b7404-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="b7404-123">Habilitar el acceso condicional y la autenticación multifactor (MFA) para administradores y no administradores.</span><span class="sxs-lookup"><span data-stu-id="b7404-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="b7404-124">Configurar y aplicar directivas de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="b7404-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="b7404-125">Restrinja el acceso a las cuentas con privilegios con Azure AD privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="b7404-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="b7404-126">Deshabilitar el acceso al terminar.</span><span class="sxs-lookup"><span data-stu-id="b7404-126">Disable access upon termination.</span></span>
- <span data-ttu-id="b7404-127">Auditar las cuentas de usuario y los cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="b7404-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="b7404-128">Revise los cambios administrativos y de grupo de funciones.</span><span class="sxs-lookup"><span data-stu-id="b7404-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="b7404-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos y la categoría **administrar dispositivos** , con la que puede:</span><span class="sxs-lookup"><span data-stu-id="b7404-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="b7404-130">Bloquee los dispositivos móviles con jailbreak y Rooting.</span><span class="sxs-lookup"><span data-stu-id="b7404-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="b7404-131">Configurar Intune para la administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="b7404-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="b7404-132">Cree directivas de cumplimiento para dispositivos Android, iOS, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="b7404-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="b7404-133">Cree un perfil de configuración de dispositivo para dispositivos Android, iOS, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="b7404-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="b7404-134">Cree directivas de protección de aplicaciones para iOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="b7404-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="b7404-135">Ocultar información con la pantalla de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b7404-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="b7404-136">Implemente directivas de contraseñas para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="b7404-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="b7404-137">Requerir que los dispositivos móviles se bloqueen al inactividad.</span><span class="sxs-lookup"><span data-stu-id="b7404-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="b7404-138">Requerir que los dispositivos móviles se borren en varios errores de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b7404-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="b7404-139">Use [Exchange Online Protection y Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) para la categoría **proteger contra amenazas** , con la que puede:</span><span class="sxs-lookup"><span data-stu-id="b7404-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="b7404-140">Habilitar la autenticación de remitente (SPF, DMARC y DKIM).</span><span class="sxs-lookup"><span data-stu-id="b7404-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="b7404-141">Configurar las directivas de protección contra suplantación de identidad (ATP) de Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b7404-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="b7404-142">Implementar datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="b7404-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="b7404-143">Implementar vínculos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="b7404-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="b7404-144">Implementar directivas de detección y respuesta de malware.</span><span class="sxs-lookup"><span data-stu-id="b7404-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="b7404-145">Implemente directivas de correo no deseado salientes y entrantes.</span><span class="sxs-lookup"><span data-stu-id="b7404-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="b7404-146">Referencias</span><span class="sxs-lookup"><span data-stu-id="b7404-146">References:</span></span>

- [<span data-ttu-id="b7404-147">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="b7404-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="b7404-148">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="b7404-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="b7404-149">Datos adjuntos seguros ATP</span><span class="sxs-lookup"><span data-stu-id="b7404-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="b7404-150">Vínculos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="b7404-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="b7404-151">Documentos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="b7404-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
