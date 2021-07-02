---
title: Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a usar la directiva de entrega avanzada en Exchange Online Protection (EOP) para identificar mensajes que no deben filtrarse en escenarios compatibles específicos (simulaciones de suplantación de identidad de terceros y mensajes entregados a buzones de operaciones de seguridad (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256872"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="a5ece-103">Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="a5ece-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="a5ece-104">**Applies to**</span></span>
- [<span data-ttu-id="a5ece-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a5ece-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a5ece-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a5ece-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a5ece-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5ece-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="a5ece-108">La característica que se describe en este artículo está en Versión preliminar, no está disponible para todos y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="a5ece-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="a5ece-109">Para mantener la organización segura de forma [predeterminada,](secure-by-default.md)Exchange Online Protection (EOP) no permite listas seguras ni omitir el filtrado de mensajes identificados como malware o phishing de elevada confianza.</span><span class="sxs-lookup"><span data-stu-id="a5ece-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="a5ece-110">Sin embargo, hay escenarios específicos que requieren la entrega de mensajes sin filtrar.</span><span class="sxs-lookup"><span data-stu-id="a5ece-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="a5ece-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5ece-111">For example:</span></span>

- <span data-ttu-id="a5ece-112">**Simulaciones de suplantación** de identidad de terceros: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real impacte en su organización.</span><span class="sxs-lookup"><span data-stu-id="a5ece-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="a5ece-113">Buzones de operaciones de seguridad **(SecOps):** buzones dedicados que usan los equipos de seguridad para recopilar y analizar mensajes sin filtrar (tanto buenos como malos).</span><span class="sxs-lookup"><span data-stu-id="a5ece-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="a5ece-114">Use la directiva _de entrega avanzada_ en Microsoft 365 para evitar que estos mensajes en estos _escenarios específicos_ se filtren. <sup>\*</sup> La directiva de entrega avanzada garantiza que los mensajes en estos escenarios consigan los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="a5ece-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="a5ece-115">Los filtros de EOP y Microsoft Defender Office 365 realizar ninguna acción en estos mensajes.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5ece-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="a5ece-116">[La purga de hora cero (ZAP)](zero-hour-auto-purge.md) para correo no deseado y suplantación de identidad (phishing) no toma ninguna acción en estos mensajes.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5ece-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="a5ece-117">[Las alertas predeterminadas](alerts.md) del sistema no se desencadenan para estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="a5ece-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="a5ece-118">[AIR y la agrupación en clústeres en Defender para Office 365](office-365-air.md) omite estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="a5ece-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="a5ece-119">Específicamente para simulaciones de suplantación de identidad de terceros:</span><span class="sxs-lookup"><span data-stu-id="a5ece-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="a5ece-120">[Los envíos de](admin-submission.md) administrador generan una respuesta automática que indica que el mensaje forma parte de una campaña de simulación de suplantación de identidad (phishing) y no es una amenaza real.</span><span class="sxs-lookup"><span data-stu-id="a5ece-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="a5ece-121">Las alertas y AIR no se desencadenarán.</span><span class="sxs-lookup"><span data-stu-id="a5ece-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="a5ece-122">[Caja fuerte vínculos en Defender para Office 365](safe-links.md) no bloquea ni detona las direcciones URL identificadas específicamente en estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="a5ece-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="a5ece-123">[Caja fuerte datos adjuntos en Defender para Office 365](safe-attachments.md) no detonan datos adjuntos en estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="a5ece-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="a5ece-124"><sup>\*</sup> No puede omitir el filtrado de malware o ZAP para malware.</span><span class="sxs-lookup"><span data-stu-id="a5ece-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="a5ece-125">Los mensajes identificados por la directiva de entrega avanzada no son amenazas de seguridad, por lo que los mensajes se marcan como invalidaciones del sistema.</span><span class="sxs-lookup"><span data-stu-id="a5ece-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="a5ece-126">Los administradores pueden filtrar y analizar estas invalidaciones del sistema en las siguientes experiencias:</span><span class="sxs-lookup"><span data-stu-id="a5ece-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="a5ece-127">Explorador de amenazas/detecciones en tiempo real en Defender para Office 365 plan 2</span><span class="sxs-lookup"><span data-stu-id="a5ece-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="a5ece-128">La [entidad Email Page en el Explorador de amenazas/Detecciones en tiempo real](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="a5ece-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="a5ece-129">Informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="a5ece-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="a5ece-130">Búsqueda avanzada en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="a5ece-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="a5ece-131">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="a5ece-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a5ece-132">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="a5ece-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a5ece-133">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a5ece-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a5ece-134">Para ir directamente a la **página Entrega avanzada,** abra <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="a5ece-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="a5ece-135">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5ece-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a5ece-136">Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="a5ece-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a5ece-137">Para crear, modificar o quitar la configuración de la directiva de  entrega avanzada, debe ser miembro del grupo de  roles Administrador de seguridad en el **portal de Microsoft 365 Defender** y miembro del grupo de roles Administración de la organización en **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="a5ece-138">Para obtener acceso de solo lectura a la directiva de entrega avanzada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="a5ece-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a5ece-139">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a5ece-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a5ece-140">Agregar usuarios al rol de Azure Active Directory correspondiente proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5ece-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a5ece-141">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a5ece-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="a5ece-142">Usar el portal Microsoft 365 Defender para configurar buzones de SecOps en la directiva de entrega avanzada</span><span class="sxs-lookup"><span data-stu-id="a5ece-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="a5ece-143">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Reglas de amenazas sección \>  \>  Reglas de entrega \>  \> **avanzada**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="a5ece-144">En la **página Entrega avanzada,** compruebe que la pestaña buzón **de SecOps** está seleccionada y, a continuación, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5ece-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="a5ece-145">Haga ![ clic en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="a5ece-146">Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="a5ece-147">En el control desplegable Editar buzones de SecOps que se abre, escriba un buzón de Exchange Online existente que desee designar como buzón de **SecOps** siguiendo uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5ece-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="a5ece-148">Haga clic en el cuadro, deje que se resuelva la lista de buzones y, a continuación, seleccione el buzón.</span><span class="sxs-lookup"><span data-stu-id="a5ece-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="a5ece-149">Haga clic en el cuadro para empezar a escribir un identificador para el buzón (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.) y seleccione el buzón (nombre para mostrar) de los resultados.</span><span class="sxs-lookup"><span data-stu-id="a5ece-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="a5ece-150">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a5ece-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a5ece-151">Los grupos de distribución no están permitidos.</span><span class="sxs-lookup"><span data-stu-id="a5ece-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="a5ece-152">Para quitar un valor existente, haga clic en Quitar</span><span class="sxs-lookup"><span data-stu-id="a5ece-152">To remove an existing value, click remove</span></span> ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a5ece-154">junto al valor.</span><span class="sxs-lookup"><span data-stu-id="a5ece-154">next to the value.</span></span>

4. <span data-ttu-id="a5ece-155">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="a5ece-156">Las entradas de buzón de SecOps que configuró se muestran en la **pestaña Buzón de SecOps.** Para realizar cambios, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar** en la pestaña.</span><span class="sxs-lookup"><span data-stu-id="a5ece-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="a5ece-157">Use el portal Microsoft 365 Defender para configurar simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada</span><span class="sxs-lookup"><span data-stu-id="a5ece-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="a5ece-158">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Reglas de amenazas sección \>  \>  Reglas de entrega \>  \> **avanzada**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="a5ece-159">En la **página Entrega avanzada,** seleccione la pestaña **Simulación de suplantación** de identidad y, a continuación, realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="a5ece-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="a5ece-160">Haga ![ clic en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="a5ece-161">Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="a5ece-162">En el **control desplegable Editar simulación de suplantación** de identidad de terceros que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a5ece-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a5ece-163">**Dominio** de envío: expanda esta configuración y escriba al menos un dominio de dirección de correo electrónico (por ejemplo, contoso.com) haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro.</span><span class="sxs-lookup"><span data-stu-id="a5ece-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="a5ece-164">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a5ece-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a5ece-165">Puede agregar hasta 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="a5ece-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="a5ece-166">**Enviar IP:** expanda esta configuración y escriba al menos una dirección IPv4 válida haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro.</span><span class="sxs-lookup"><span data-stu-id="a5ece-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="a5ece-167">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a5ece-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="a5ece-168">Puede agregar hasta 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="a5ece-168">You can add up to 10 entries.</span></span> <span data-ttu-id="a5ece-169">Los valores admitidos son:</span><span class="sxs-lookup"><span data-stu-id="a5ece-169">Valid values are:</span></span>
     - <span data-ttu-id="a5ece-170">IP única: por ejemplo, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="a5ece-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="a5ece-171">Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="a5ece-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="a5ece-172">IP cidr: por ejemplo, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="a5ece-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="a5ece-173">Direcciones **URL** de simulación para permitir: expanda esta configuración y, opcionalmente, escriba direcciones URL específicas que forman parte de la campaña de simulación de suplantación de identidad que no se deben bloquear ni detonar haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro.</span><span class="sxs-lookup"><span data-stu-id="a5ece-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="a5ece-174">Puede agregar hasta 10 entradas.</span><span class="sxs-lookup"><span data-stu-id="a5ece-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="a5ece-175">Para quitar un valor existente, haga clic en Quitar</span><span class="sxs-lookup"><span data-stu-id="a5ece-175">To remove an existing value, click remove</span></span> ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a5ece-177">junto al valor.</span><span class="sxs-lookup"><span data-stu-id="a5ece-177">next to the value.</span></span>

4. <span data-ttu-id="a5ece-178">Cuando haya terminado, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5ece-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="a5ece-179">**Primera vez:** haga clic **en Agregar** y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="a5ece-180">**Editar existente:** haga clic **en Guardar** y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a5ece-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="a5ece-181">Las entradas de simulación de suplantación de identidad de terceros que configuró se muestran en la pestaña **Simulación de suplantación de** identidad. Para realizar cambios, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar** en la pestaña.</span><span class="sxs-lookup"><span data-stu-id="a5ece-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="a5ece-182">Escenarios adicionales que requieren la omisión de filtrado</span><span class="sxs-lookup"><span data-stu-id="a5ece-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="a5ece-183">Además de los dos escenarios con los que la directiva de entrega avanzada puede ayudarle, hay otros escenarios que pueden requerir omitir el filtrado:</span><span class="sxs-lookup"><span data-stu-id="a5ece-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="a5ece-184">**Filtros de terceros:** si el registro  MX de su dominio no apunta a Office 365 (los mensajes se enruta en otro lugar primero), [la](secure-by-default.md) seguridad de forma predeterminada no *está disponible*.</span><span class="sxs-lookup"><span data-stu-id="a5ece-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="a5ece-185">Si quieres agregar protección, tendrás que habilitar el filtrado mejorado para conectores (también conocido como *listado de omitir*).</span><span class="sxs-lookup"><span data-stu-id="a5ece-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="a5ece-186">Para obtener más información, vea [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span><span class="sxs-lookup"><span data-stu-id="a5ece-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="a5ece-187">Si no desea el filtrado mejorado para conectores, use reglas de flujo de correo (también conocidas como reglas de transporte) para omitir el filtrado de Microsoft para los mensajes que ya han sido evaluados por el filtrado de terceros.</span><span class="sxs-lookup"><span data-stu-id="a5ece-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="a5ece-188">Para obtener más información, vea [Usar reglas de flujo de correo para establecer el SCL en mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span><span class="sxs-lookup"><span data-stu-id="a5ece-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="a5ece-189">**Falsos positivos** en revisión: es posible que desee permitir temporalmente que determinados mensajes que Microsoft sigue analizando a través de [envíos](admin-submission.md) de administrador informen de mensajes buenos conocidos que se marcan incorrectamente como incorrectos para Microsoft (falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="a5ece-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="a5ece-190">Al igual que con todas las invalidaciones, se **_recomienda encarecidamente_** que estas asignaciones sean temporales.</span><span class="sxs-lookup"><span data-stu-id="a5ece-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="a5ece-191">Exchange Online Procedimientos de PowerShell para buzones de SecOps en la directiva de entrega avanzada</span><span class="sxs-lookup"><span data-stu-id="a5ece-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="a5ece-192">En Exchange Online PowerShell, los elementos básicos de los buzones de SecOps en la directiva de entrega avanzada son:</span><span class="sxs-lookup"><span data-stu-id="a5ece-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="a5ece-193">**La directiva de invalidación de SecOps:** controlada por los **\* cmdlets -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="a5ece-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="a5ece-194">**La regla de invalidación de SecOps**: Controlada por los **\* cmdlets -SecOpsOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="a5ece-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="a5ece-195">Este comportamiento tiene los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="a5ece-195">This behavior has the following results:</span></span>

- <span data-ttu-id="a5ece-196">Primero se crea la directiva y, a continuación, se crea la regla que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a5ece-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a5ece-197">Al quitar una directiva de PowerShell, también se quita la regla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="a5ece-198">Al quitar una regla de PowerShell, no se quita la directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="a5ece-199">Debe quitar la directiva correspondiente manualmente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="a5ece-200">Usar PowerShell para configurar buzones de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="a5ece-201">Configurar un buzón de SecOps en la directiva de entrega avanzada en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5ece-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a5ece-202">Cree la directiva de invalidación de SecOps.</span><span class="sxs-lookup"><span data-stu-id="a5ece-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="a5ece-203">Cree la regla de invalidación de SecOps que especifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a5ece-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="a5ece-204">Paso 1: Usar PowerShell para crear la directiva de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="a5ece-205">Para crear la directiva de invalidación de SecOps, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="a5ece-206">**Nota:** Independientemente del valor name que especifique, el nombre de la directiva será SecOpsOverridePolicy, por lo que también puede usar ese valor.</span><span class="sxs-lookup"><span data-stu-id="a5ece-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="a5ece-207">En este ejemplo se crea la directiva de buzón de SecOps.</span><span class="sxs-lookup"><span data-stu-id="a5ece-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="a5ece-208">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="a5ece-209">Paso 2: Usar PowerShell para crear la regla de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="a5ece-210">En este ejemplo se crea la regla de buzón de SecOps con la configuración especificada.</span><span class="sxs-lookup"><span data-stu-id="a5ece-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="a5ece-211">\*\*Nota:\*\*\*\*Independientemente del valor name que especifique, el nombre de la regla será SecOpsOverrideRule donde es un valor GUID único \<GUID\> \<GUID\> (por ejemplo, 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="a5ece-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="a5ece-212">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="a5ece-213">Usar PowerShell para ver la directiva de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="a5ece-214">En este ejemplo se devuelve información detallada sobre la única directiva de buzón de SecOps.</span><span class="sxs-lookup"><span data-stu-id="a5ece-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="a5ece-215">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="a5ece-216">Usar PowerShell para ver reglas de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="a5ece-217">En este ejemplo se devuelve información detallada acerca de las reglas de invalidación de SecOps.</span><span class="sxs-lookup"><span data-stu-id="a5ece-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="a5ece-218">Aunque el comando anterior debe devolver solo una regla, las reglas pendientes de eliminación también pueden incluirse en los resultados.</span><span class="sxs-lookup"><span data-stu-id="a5ece-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="a5ece-219">En este ejemplo se identifica la regla válida (una) y las reglas no válidas.</span><span class="sxs-lookup"><span data-stu-id="a5ece-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="a5ece-220">Después de identificar las reglas no válidas, puede quitarlas mediante el cmdlet **Remove-SecOpsOverrideRule,** tal como se describe [más adelante en este artículo](#use-powershell-to-remove-secops-override-rules).</span><span class="sxs-lookup"><span data-stu-id="a5ece-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="a5ece-221">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="a5ece-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="a5ece-222">Usar PowerShell para modificar la directiva de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="a5ece-223">Para modificar la directiva de invalidación de SecOps, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="a5ece-224">En este ejemplo se secops2@contoso.com a la directiva de invalidación de SecOps.</span><span class="sxs-lookup"><span data-stu-id="a5ece-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="a5ece-225">**Nota:** Si existe una regla de invalidación de SecOps asociada y válida, también se actualizarán las direcciones de correo electrónico de la regla.</span><span class="sxs-lookup"><span data-stu-id="a5ece-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="a5ece-226">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="a5ece-227">Usar PowerShell para modificar una regla de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="a5ece-228">El cmdlet **Set-SecOpsOverrideRule** no modifica las direcciones de correo electrónico de la regla de invalidación de SecOps.</span><span class="sxs-lookup"><span data-stu-id="a5ece-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="a5ece-229">Para modificar las direcciones de correo electrónico de la regla de invalidación de SecOps, use el cmdlet **Set-SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="a5ece-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="a5ece-230">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="a5ece-231">Usar PowerShell para quitar la directiva de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="a5ece-232">En este ejemplo se quita la directiva de buzón de SecOps y la regla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="a5ece-233">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="a5ece-234">Usar PowerShell para quitar reglas de invalidación de SecOps</span><span class="sxs-lookup"><span data-stu-id="a5ece-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="a5ece-235">Para quitar una regla de invalidación de SecOps, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="a5ece-236">En este ejemplo se quita la regla de invalidación de SecOps especificada.</span><span class="sxs-lookup"><span data-stu-id="a5ece-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="a5ece-237">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="a5ece-238">Exchange Online Procedimientos de PowerShell para simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada</span><span class="sxs-lookup"><span data-stu-id="a5ece-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="a5ece-239">En Exchange Online PowerShell, los elementos básicos de las simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada son:</span><span class="sxs-lookup"><span data-stu-id="a5ece-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="a5ece-240">**La directiva de invalidación de simulación de suplantación de** identidad : controlada por los **\* cmdlets -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="a5ece-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="a5ece-241">**La regla de invalidación de simulación de** suplantación de identidad : controlada por los **\* cmdlets -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="a5ece-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="a5ece-242">Este comportamiento tiene los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="a5ece-242">This behavior has the following results:</span></span>

- <span data-ttu-id="a5ece-243">Primero se crea la directiva y, a continuación, se crea la regla que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a5ece-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a5ece-244">Puede modificar la configuración de la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="a5ece-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="a5ece-245">Al quitar una directiva de PowerShell, también se quita la regla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="a5ece-246">Al quitar una regla de PowerShell, no se quita la directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="a5ece-247">Debe quitar la directiva correspondiente manualmente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="a5ece-248">Usar PowerShell para configurar simulaciones de suplantación de identidad de terceros</span><span class="sxs-lookup"><span data-stu-id="a5ece-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="a5ece-249">Configurar una simulación de suplantación de identidad de terceros en la directiva de entrega avanzada en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5ece-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a5ece-250">Crear la directiva de invalidación de simulación de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a5ece-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="a5ece-251">Cree la regla de invalidación de simulación de suplantación de identidad (phishing) que especifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a5ece-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="a5ece-252">Paso 1: Usar PowerShell para crear la directiva de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="a5ece-253">En este ejemplo se crea la directiva de invalidación de simulación de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a5ece-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="a5ece-254">**Nota:** Independientemente del valor name que especifique, el nombre de la directiva será PhishSimOverridePolicy, por lo que también puede usar ese valor.</span><span class="sxs-lookup"><span data-stu-id="a5ece-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="a5ece-255">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="a5ece-256">Paso 2: Usar PowerShell para crear la regla de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="a5ece-257">Utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="a5ece-258">Independientemente del valor name que especifique, el nombre de la regla será PhishSimOverrideRule donde es un valor GUID único \<GUID\> \<GUID\> (por ejemplo, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="a5ece-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="a5ece-259">Una entrada de dirección IP válida es uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a5ece-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="a5ece-260">IP única: por ejemplo, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="a5ece-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="a5ece-261">Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="a5ece-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="a5ece-262">IP cidr: por ejemplo, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="a5ece-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="a5ece-263">En este ejemplo se crea la regla de invalidación de simulación de suplantación de identidad con la configuración especificada.</span><span class="sxs-lookup"><span data-stu-id="a5ece-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="a5ece-264">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="a5ece-265">Usar PowerShell para ver la directiva de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="a5ece-266">En este ejemplo se devuelve información detallada sobre la única directiva de invalidación de simulación de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a5ece-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="a5ece-267">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="a5ece-268">Usar PowerShell para ver reglas de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="a5ece-269">En este ejemplo se devuelve información detallada acerca de las reglas de invalidación de simulación de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a5ece-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="a5ece-270">Aunque el comando anterior debe devolver solo una regla, las reglas pendientes de eliminación también pueden incluirse en los resultados.</span><span class="sxs-lookup"><span data-stu-id="a5ece-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="a5ece-271">En este ejemplo se identifica la regla válida (una) y las reglas no válidas.</span><span class="sxs-lookup"><span data-stu-id="a5ece-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="a5ece-272">Después de identificar las reglas no válidas, puede quitarlas mediante el cmdlet **Remove-PhisSimOverrideRule,** tal como se describe [más adelante en este artículo](#use-powershell-to-remove-phishing-simulation-override-rules).</span><span class="sxs-lookup"><span data-stu-id="a5ece-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="a5ece-273">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="a5ece-274">Usar PowerShell para modificar la directiva de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="a5ece-275">Para modificar la directiva de invalidación de simulación de suplantación de identidad,use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="a5ece-276">En este ejemplo se deshabilita la directiva de invalidación de simulación de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a5ece-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="a5ece-277">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="a5ece-278">Usar PowerShell para modificar una regla de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="a5ece-279">Para modificar la regla de invalidación de simulación de suplantación de identidad, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="a5ece-280">En este ejemplo se modifica la regla de invalidación de simulación de suplantación de identidad (phishing) especificada con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="a5ece-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="a5ece-281">Agregue la entrada de dominio blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="a5ece-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="a5ece-282">Quite la entrada de dirección IP 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="a5ece-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="a5ece-283">Tenga en cuenta que estos cambios no afectan a las entradas existentes.</span><span class="sxs-lookup"><span data-stu-id="a5ece-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="a5ece-284">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="a5ece-285">Usar PowerShell para quitar una directiva de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="a5ece-286">En este ejemplo se quita la directiva de invalidación de simulación de suplantación de identidad (phishing) y la regla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5ece-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="a5ece-287">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="a5ece-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="a5ece-288">Usar PowerShell para quitar reglas de invalidación de simulación de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a5ece-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="a5ece-289">Para quitar una regla de invalidación de simulación de suplantación de identidad,use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a5ece-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="a5ece-290">En este ejemplo se quita la regla de invalidación de simulación de suplantación de identidad especificada.</span><span class="sxs-lookup"><span data-stu-id="a5ece-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="a5ece-291">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="a5ece-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
