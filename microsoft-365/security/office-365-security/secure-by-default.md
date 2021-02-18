---
title: Proteger de forma predeterminada en Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Obtenga más información sobre la configuración segura de forma predeterminada en Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288518"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="6129b-103">Proteger de forma predeterminada en Office 365</span><span class="sxs-lookup"><span data-stu-id="6129b-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6129b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="6129b-104">**Applies to**</span></span>
- [<span data-ttu-id="6129b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6129b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6129b-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6129b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6129b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6129b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6129b-108">"Seguro de forma predeterminada" es un término que se usa para definir la configuración predeterminada más segura posible.</span><span class="sxs-lookup"><span data-stu-id="6129b-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="6129b-109">Sin embargo, la seguridad debe equilibrarse con la productividad.</span><span class="sxs-lookup"><span data-stu-id="6129b-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="6129b-110">Esto puede incluir el equilibrio entre:</span><span class="sxs-lookup"><span data-stu-id="6129b-110">This can include balancing across:</span></span>

- <span data-ttu-id="6129b-111">**Facilidad de** uso: la configuración no debe inquiete a la productividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="6129b-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="6129b-112">**Riesgo:** la seguridad puede bloquear actividades importantes.</span><span class="sxs-lookup"><span data-stu-id="6129b-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="6129b-113">**Configuración heredada:** es posible que algunas configuraciones de productos y características anteriores deban mantenerse por motivos empresariales, incluso si se mejora la configuración nueva y moderna.</span><span class="sxs-lookup"><span data-stu-id="6129b-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="6129b-114">Las organizaciones de Microsoft 365 con buzones en Exchange Online están protegidas por Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="6129b-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="6129b-115">Esta protección incluye:</span><span class="sxs-lookup"><span data-stu-id="6129b-115">This protection includes:</span></span>

- <span data-ttu-id="6129b-116">El correo electrónico con sospechoso de malware se pondrá automáticamente en cuarentena y se notificará a los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="6129b-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="6129b-117">Vea [Configurar directivas antimalware en EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="6129b-118">El correo electrónico identificado como suplantación de identidad de confianza alta se controlará de acuerdo con la acción de directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="6129b-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="6129b-119">Vea [Configurar directivas contra correo no deseado en EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6129b-120">Para obtener más información acerca de EOP, vea [información general sobre Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="6129b-121">Dado que Microsoft quiere mantener seguros nuestros clientes de forma predeterminada, algunos reemplazos de inquilinos no se aplican para malware o suplantación de identidad de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="6129b-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="6129b-122">Estos reemplazos incluyen:</span><span class="sxs-lookup"><span data-stu-id="6129b-122">These overrides include:</span></span>

- <span data-ttu-id="6129b-123">Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)</span><span class="sxs-lookup"><span data-stu-id="6129b-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="6129b-124">Remitentes seguros de Outlook</span><span class="sxs-lookup"><span data-stu-id="6129b-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="6129b-125">Lista de direcciones IP permitidos (filtrado de conexiones)</span><span class="sxs-lookup"><span data-stu-id="6129b-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="6129b-126">Puede encontrar más información sobre estos reemplazos en [Crear listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6129b-127">Estamos en el proceso de desuso de la acción Mover mensaje a la carpeta Correo no deseado para un veredicto de correo electrónico de **suplantación** de identidad de confianza alta en las directivas contra correo no deseado de EOP. </span><span class="sxs-lookup"><span data-stu-id="6129b-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="6129b-128">Las directivas contra correo no deseado que usan esta acción para mensajes de suplantación de identidad de alta confianza se convertirán en mensajes **de cuarentena.**</span><span class="sxs-lookup"><span data-stu-id="6129b-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="6129b-129">El **mensaje de redireccionamiento a la acción de dirección** de correo electrónico para mensajes de suplantación de identidad de alta confianza no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="6129b-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="6129b-130">De forma predeterminada, la seguridad no es una opción que se puede activado o desactivado, pero es la forma en que nuestro filtrado funciona de forma predeterminada para mantener mensajes potencialmente peligrosos o no deseados fuera de sus buzones.</span><span class="sxs-lookup"><span data-stu-id="6129b-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="6129b-131">Los mensajes de suplantación de identidad (phishing) de malware y de confianza alta deben ponerse en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="6129b-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="6129b-132">Solo los administradores pueden administrar los mensajes que se ponen en cuarentena como malware o phishing de confianza alta, y también pueden notificar falsos positivos a Microsoft desde allí.</span><span class="sxs-lookup"><span data-stu-id="6129b-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="6129b-133">Para obtener más información, vea Administrar mensajes y archivos en cuarentena [como administrador en EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="6129b-134">Más información sobre por qué lo estamos haciendo</span><span class="sxs-lookup"><span data-stu-id="6129b-134">More on why we're doing this</span></span>

<span data-ttu-id="6129b-135">De forma predeterminada, la razón de ser segura es: estamos llevando a través del mensaje la misma acción que realizaría si supo que el mensaje era malintencionado, incluso cuando una excepción configurada permitiría la entrega del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6129b-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="6129b-136">Este es el mismo enfoque que siempre hemos usado en malware y ahora estamos ampliando este mismo comportamiento a los mensajes de suplantación de identidad de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="6129b-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="6129b-137">Nuestros datos indican que un usuario tiene 30 veces más probabilidades de hacer clic en un vínculo malintencionado en los mensajes de la carpeta Correo no deseado frente a Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="6129b-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="6129b-138">Nuestros datos también indican que la tasa de falsos positivos (mensajes buenos marcados como falsos) para mensajes de suplantación de identidad de confianza alta es muy baja y los administradores pueden resolver los falsos positivos con envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="6129b-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="6129b-139">También determinamos que las listas de remitentes permitidos y dominios permitidos en las directivas contra correo no deseado y remitentes seguros en Outlook eran demasiado amplias y causaban más daño que bueno.</span><span class="sxs-lookup"><span data-stu-id="6129b-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="6129b-140">Dicho de otro modo: como servicio de seguridad, estamos actuando en su nombre para evitar que los usuarios se pongan en peligro.</span><span class="sxs-lookup"><span data-stu-id="6129b-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="6129b-141">Exceptions</span><span class="sxs-lookup"><span data-stu-id="6129b-141">Exceptions</span></span>

<span data-ttu-id="6129b-142">El único reemplazo que permite que los mensajes de suplantación de identidad de alta confianza omitan el filtrado son las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="6129b-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="6129b-143">Para usar reglas de flujo de correo para omitir el filtrado, vea Usar reglas de flujo de [correo para establecer el SCL en mensajes.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="6129b-144">Solo debe considerar el uso de invalidaciones en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="6129b-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="6129b-145">Simulaciones de suplantación de identidad: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real repercuta en su organización.</span><span class="sxs-lookup"><span data-stu-id="6129b-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="6129b-146">Buzones de seguridad/SecOps: buzones dedicados usados por los equipos de seguridad para obtener mensajes sin filtrar (tanto buenos como no).</span><span class="sxs-lookup"><span data-stu-id="6129b-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="6129b-147">Después, Teams puede revisar si contienen contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="6129b-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="6129b-148">Filtros de terceros: la seguridad de forma predeterminada no se aplica cuando el registro MX del dominio no apunta a Office 365.</span><span class="sxs-lookup"><span data-stu-id="6129b-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="6129b-149">Falsos positivos: es posible que desee permitir temporalmente ciertos mensajes que Microsoft sigue analizando a través de [envíos de administrador.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6129b-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="6129b-150">Al igual que con todas las invalidaciones, se recomienda que sean temporales.</span><span class="sxs-lookup"><span data-stu-id="6129b-150">As with all overrides, it is recommended that they are temporary.</span></span>
