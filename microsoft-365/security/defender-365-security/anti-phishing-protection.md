---
title: Protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las características de protección contra suplantación de identidad (phishing) en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073603"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="76cc3-103">Protección contra suplantación de identidad (phishing) en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76cc3-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="76cc3-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="76cc3-104">**Applies to**</span></span>
- [<span data-ttu-id="76cc3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="76cc3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="76cc3-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="76cc3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="76cc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76cc3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="76cc3-108">*El phishing* es un ataque de correo electrónico que intenta robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza.</span><span class="sxs-lookup"><span data-stu-id="76cc3-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="76cc3-109">Hay categorías específicas de phishing.</span><span class="sxs-lookup"><span data-stu-id="76cc3-109">There are specific categories of phishing.</span></span> <span data-ttu-id="76cc3-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76cc3-110">For example:</span></span>

- <span data-ttu-id="76cc3-111">**La suplantación** de identidad de lanza usa contenido centrado y personalizado que está específicamente adaptado a los destinatarios dirigidos (normalmente, después del reconocimiento de los destinatarios por parte del atacante).</span><span class="sxs-lookup"><span data-stu-id="76cc3-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="76cc3-112">**La caza de whaling** se dirige a ejecutivos u otros objetivos de alto valor dentro de una organización para obtener el máximo efecto.</span><span class="sxs-lookup"><span data-stu-id="76cc3-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="76cc3-113">El compromiso de correo electrónico empresarial **(BEC)** usa remitentes de confianza falsificados (responsables financieros, clientes, socios de confianza, etc.) para engañar a los destinatarios para que aprueben pagos, transfieran fondos o revelen datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="76cc3-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="76cc3-114">**Ransomware** que cifra los datos y exige el pago para descifrarlo casi siempre comienza en los mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="76cc3-114">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="76cc3-115">La protección contra la suplantación de identidad no puede ayudarle a descifrar archivos cifrados, pero puede ayudar a detectar los mensajes de suplantación de identidad inicial asociados con la campaña de ransomware.</span><span class="sxs-lookup"><span data-stu-id="76cc3-115">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="76cc3-116">Para obtener más información acerca de la recuperación de un ataque de ransomware, vea [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-116">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="76cc3-117">Con la creciente complejidad de los ataques, es incluso difícil para los usuarios capacitados identificar mensajes de suplantación de identidad sofisticados.</span><span class="sxs-lookup"><span data-stu-id="76cc3-117">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="76cc3-118">Afortunadamente, Exchange Online Protection (EOP) y las características adicionales de Microsoft Defender para Office 365 pueden ayudar.</span><span class="sxs-lookup"><span data-stu-id="76cc3-118">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="76cc3-119">Protección contra suplantación de identidad (phishing) en EOP</span><span class="sxs-lookup"><span data-stu-id="76cc3-119">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="76cc3-120">EOP (es decir, organizaciones de Microsoft 365 sin Microsoft Defender para Office 365) contiene características que pueden ayudar a proteger su organización de amenazas de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="76cc3-120">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="76cc3-121">**Inteligencia contra la suplantación de identidad**: revisa mensajes falsificados de remitentes en dominios internos y externos y permite o bloquea el acceso de los remitentes.</span><span class="sxs-lookup"><span data-stu-id="76cc3-121">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="76cc3-122">Para obtener más información, vea [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-122">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="76cc3-123">Directivas contra suplantación de identidad en **EOP:** activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y especificar la acción para remitentes suplantados bloqueados (pasar a la carpeta o cuarentena de correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="76cc3-123">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="76cc3-124">Para obtener más información, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-124">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="76cc3-125">Autenticación implícita de correo **electrónico:** EOP mejora las comprobaciones de autenticación de correo electrónico estándar para el correo electrónico entrante ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)) con reputación del remitente, historial de remitentes, historial de destinatarios, análisis de comportamiento y otras técnicas avanzadas para ayudar a identificar remitentes falsificados.</span><span class="sxs-lookup"><span data-stu-id="76cc3-125">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="76cc3-126">Para obtener más información, consulte [Autenticación de correo electrónico de Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-126">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="76cc3-127">Protección contra suplantación de identidad adicional en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="76cc3-127">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="76cc3-128">Microsoft Defender para Office 365 contiene características adicionales y avanzadas contra la suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="76cc3-128">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="76cc3-129">Directivas contra suplantación de identidad en **Microsoft Defender para Office 365:** crear nuevas directivas personalizadas, configurar opciones contra suplantación (proteger usuarios y dominios de suplantación), configuración de inteligencia de buzones de correo y umbrales de suplantación de identidad avanzada ajustables.</span><span class="sxs-lookup"><span data-stu-id="76cc3-129">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="76cc3-130">Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-130">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="76cc3-131">Para obtener más información acerca de las diferencias entre las directivas anti phishing en EOP y las directivas contra suplantación de identidad en Defender para Office 365, vea [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-131">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="76cc3-132">**Vistas de** campaña: aprendizaje automático y otras heurísticas identifican y analizan los mensajes implicados en ataques de suplantación de identidad coordinados contra todo el servicio y la organización.</span><span class="sxs-lookup"><span data-stu-id="76cc3-132">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="76cc3-133">Para obtener más información, vea [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-133">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="76cc3-134">**Simulador de ataque:** los administradores pueden crear mensajes de suplantación de identidad falsos y enviarlos a usuarios internos como una herramienta educativa.</span><span class="sxs-lookup"><span data-stu-id="76cc3-134">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="76cc3-135">Para obtener más información, vea [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-135">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="76cc3-136">Otros recursos contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="76cc3-136">Other anti-phishing resources</span></span>

- <span data-ttu-id="76cc3-137">Para los usuarios finales: [protéjase de esquemas de suplantación de identidad (phishing)](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)y otras formas de fraude en línea .</span><span class="sxs-lookup"><span data-stu-id="76cc3-137">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="76cc3-138">[Cómo Microsoft 365 valida la dirección De para evitar la suplantación de identidad](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="76cc3-138">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
