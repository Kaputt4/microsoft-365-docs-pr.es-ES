---
title: Seguro de forma predeterminada en Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Obtenga más información acerca de la configuración de seguridad de forma predeterminada en Exchange Online Protection (EOP)
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945335"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="acbaa-103">Seguro de forma predeterminada en Office 365</span><span class="sxs-lookup"><span data-stu-id="acbaa-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="acbaa-104">"Seguro de forma predeterminada" es un término que se usa para definir los valores predeterminados más seguros posible.</span><span class="sxs-lookup"><span data-stu-id="acbaa-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="acbaa-105">Sin embargo, la seguridad debe estar equilibrada con la productividad.</span><span class="sxs-lookup"><span data-stu-id="acbaa-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="acbaa-106">Esto puede incluir un equilibrio entre:</span><span class="sxs-lookup"><span data-stu-id="acbaa-106">This can include balancing across:</span></span>

- <span data-ttu-id="acbaa-107">Facilidad de uso: la configuración no debe obtener la productividad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="acbaa-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="acbaa-108">Riesgo: la seguridad puede bloquear actividades importantes.</span><span class="sxs-lookup"><span data-stu-id="acbaa-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="acbaa-109">Configuración heredada: es posible que algunas configuraciones de productos y características anteriores deban mantenerse por motivos empresariales, incluso si se han mejorado las opciones nuevas y modernas.</span><span class="sxs-lookup"><span data-stu-id="acbaa-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="acbaa-110">Microsoft 365 organizaciones con buzones de correo en Exchange online están protegidas por Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="acbaa-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="acbaa-111">Esta protección incluye:</span><span class="sxs-lookup"><span data-stu-id="acbaa-111">This protection includes:</span></span>

1. <span data-ttu-id="acbaa-112">El correo electrónico con el malware sospechoso se pondrá en cuarentena automáticamente y se notificará a los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="acbaa-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="acbaa-113">Vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="acbaa-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="acbaa-114">El correo electrónico de suplantación de identidad identificado como "alta confianza" se controlará de acuerdo con la acción contra la Directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="acbaa-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="acbaa-115">Consulte [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="acbaa-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="acbaa-116">Debido a que Microsoft desea mantener a nuestros clientes seguros de forma predeterminada, algunos invalidaciones de los inquilinos no se aplican a malware o phish de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="acbaa-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="acbaa-117">Estas invalidaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="acbaa-117">These overrides include:</span></span>

- <span data-ttu-id="acbaa-118">Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)</span><span class="sxs-lookup"><span data-stu-id="acbaa-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="acbaa-119">Remitentes seguros de Outlook</span><span class="sxs-lookup"><span data-stu-id="acbaa-119">Outlook Safe senders</span></span>
- <span data-ttu-id="acbaa-120">Lista de direcciones IP permitidas (filtrado de la conexión)</span><span class="sxs-lookup"><span data-stu-id="acbaa-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="acbaa-121">Puede encontrar más información sobre estas invalidaciones en [crear listas de remitentes seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="acbaa-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="acbaa-122">Seguro de forma predeterminada esta es una configuración que puede activarse o desactivarse, pero el modo en que nuestro filtrado funciona de forma predeterminada para conservar los mensajes potencialmente peligrosos o no deseados de los buzones.</span><span class="sxs-lookup"><span data-stu-id="acbaa-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="acbaa-123">El malware y el phish de confianza alta deben enviarse a cuarentena.</span><span class="sxs-lookup"><span data-stu-id="acbaa-123">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="acbaa-124">Solo los administradores pueden administrar mensajes que se pusieron en cuarentena como malware o una suplantación de identidad de confianza alta y también pueden informar de falsos positivos a Microsoft desde allí.</span><span class="sxs-lookup"><span data-stu-id="acbaa-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="acbaa-125">Para obtener más información, consulte [administrar mensajes en cuarentena y archivos como un administrador en EOP](manage-quarantined-messages-and-files.md) .</span><span class="sxs-lookup"><span data-stu-id="acbaa-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="acbaa-126">Exceptions</span><span class="sxs-lookup"><span data-stu-id="acbaa-126">Exceptions</span></span>

<span data-ttu-id="acbaa-127">Entre los únicos reemplazos que omiten todos los filtros se incluyen:</span><span class="sxs-lookup"><span data-stu-id="acbaa-127">The only overrides that will bypass all filters include:</span></span>

- <span data-ttu-id="acbaa-128">Reglas de transporte de Exchange (ETR)/mail reglas de flujo.</span><span class="sxs-lookup"><span data-stu-id="acbaa-128">Exchange Transport Rules (ETR)/mail flow rules.</span></span> <span data-ttu-id="acbaa-129">Use reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes en EOP.</span><span class="sxs-lookup"><span data-stu-id="acbaa-129">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="acbaa-130">Lista de permitidos/bloqueados de inquilino: administre direcciones URL y archivos en la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="acbaa-130">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="acbaa-131">Estos tipos de reemplazos son útiles para:</span><span class="sxs-lookup"><span data-stu-id="acbaa-131">These types of overrides are useful for:</span></span>

- <span data-ttu-id="acbaa-132">Simulaciones de phish: los ataques simulados pueden ayudarle a identificar a los usuarios vulnerables antes de que un ataque real afecte a su organización.</span><span class="sxs-lookup"><span data-stu-id="acbaa-132">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="acbaa-133">Buzones de seguridad/SecOps: buzones dedicados usados por los equipos de seguridad para obtener mensajes no filtrados (buenos y no válidos).</span><span class="sxs-lookup"><span data-stu-id="acbaa-133">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="acbaa-134">Los equipos pueden revisar para ver si contienen contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="acbaa-134">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="acbaa-135">Filtros de terceros: algunos proveedores de terceros recomiendan desactivar EOP (SCL =-1), ya que el filtro de terceros administrará el filtrado de correo.</span><span class="sxs-lookup"><span data-stu-id="acbaa-135">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="acbaa-136">Microsoft no recomienda desactivar EOP como EOP es necesario para defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbaa-136">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="acbaa-137">Falsos positivos: es posible que desee permitir determinados mensajes que Microsoft todavía está analizando mediante los [envíos de administración](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="acbaa-137">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="acbaa-138">Como con todas las invalidaciones, se recomienda que sean temporales.</span><span class="sxs-lookup"><span data-stu-id="acbaa-138">As with all overrides, it is recommended that they are temporary.</span></span>
