---
title: Revisión de administrador para mensajes notificados
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Aprende a revisar los mensajes que se notifican y a enviar comentarios a los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 619cd35b6a60f0d50aa6c13e4cad2b8d7ae947a8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730981"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="1e530-103">Revisión de administrador para mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="1e530-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="1e530-104">La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="1e530-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1e530-105">Este documento se proporciona únicamente con fines de evaluación y exploración.</span><span class="sxs-lookup"><span data-stu-id="1e530-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="1e530-106">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="1e530-106">**Applies to**</span></span>
- [<span data-ttu-id="1e530-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1e530-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1e530-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e530-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1e530-109">En Microsoft 365 con Exchange Online buzones de correo y Microsoft Defender para Office 365, los administradores ahora pueden enviar mensajes con plantilla de vuelta a los usuarios finales después de revisar los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="1e530-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="1e530-110">Esto se puede personalizar para su organización y también en función del veredicto del administrador.</span><span class="sxs-lookup"><span data-stu-id="1e530-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="1e530-111">Esta característica está diseñada para enviar comentarios a los usuarios, pero no cambia los veredictos de los mensajes en el sistema.</span><span class="sxs-lookup"><span data-stu-id="1e530-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="1e530-112">Para ayudar a Microsoft a actualizar y mejorar sus filtros, deberá enviar mensajes para su análisis mediante [el envío de administrador.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="1e530-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="1e530-113">Solo podrá marcar y notificar a los usuarios los resultados de la revisión si el mensaje se notificó como [falsos positivos o falsos negativos](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="1e530-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e530-114">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="1e530-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1e530-115">Para modificar la configuración de envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="1e530-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
    - <span data-ttu-id="1e530-116">Administración de la organización o Administrador de seguridad en [el Centro de seguridad](permissions-microsoft-365-compliance-security.md).</span><span class="sxs-lookup"><span data-stu-id="1e530-116">Organization Management or Security Administrator in the [Security center](permissions-microsoft-365-compliance-security.md).</span></span>
    - <span data-ttu-id="1e530-117">Administración de la [organización en Exchange Online](/Exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="1e530-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="1e530-118">También necesitarás acceso a la Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e530-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="1e530-119">Si la cuenta que está intentando usar no tiene acceso Exchange Online PowerShell, recibirá un error que indica Especificar una dirección de correo electrónico en *su dominio*.</span><span class="sxs-lookup"><span data-stu-id="1e530-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="1e530-120">Para obtener más información acerca de cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="1e530-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
    - [<span data-ttu-id="1e530-121">Habilitar o deshabilitar el acceso a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e530-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
    - [<span data-ttu-id="1e530-122">Reglas de acceso de cliente en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1e530-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="1e530-123">Configurar los mensajes usados para notificar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="1e530-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="1e530-124">En el [centro Microsoft 365 seguridad,](../defender/overview-security-center.md)vaya a **Directivas &** Directivas de amenazas Configuración del \>  \> **mensaje notificado por el usuario.**</span><span class="sxs-lookup"><span data-stu-id="1e530-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="1e530-125">Si desea especificar el nombre para mostrar del remitente **Office 365,** active la casilla especificar una dirección de correo electrónico para usarla como remitente en la sección Notificaciones de correo electrónico para los **resultados** de la revisión de administrador y escriba el nombre que desea usar.</span><span class="sxs-lookup"><span data-stu-id="1e530-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="1e530-126">Esta es la dirección de correo electrónico que estará visible en Outlook y a la que se dirigirán las respuestas.</span><span class="sxs-lookup"><span data-stu-id="1e530-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="1e530-127">Si desea personalizar cualquiera de las plantillas, haga clic **en Personalizar notificación de correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="1e530-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="1e530-128">En este menú desplegable, solo podrá personalizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e530-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="1e530-129">Suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="1e530-129">Phishing</span></span>
    - <span data-ttu-id="1e530-130">Correo no deseado</span><span class="sxs-lookup"><span data-stu-id="1e530-130">Junk</span></span>
    - <span data-ttu-id="1e530-131">No se encontraron amenazas</span><span class="sxs-lookup"><span data-stu-id="1e530-131">No threats found</span></span>
    - <span data-ttu-id="1e530-132">Formación de sensibilización</span><span class="sxs-lookup"><span data-stu-id="1e530-132">Awareness training</span></span>
    - <span data-ttu-id="1e530-133">Pie de página</span><span class="sxs-lookup"><span data-stu-id="1e530-133">Footer</span></span>

4. <span data-ttu-id="1e530-134">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1e530-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="1e530-135">Para borrar estos valores, haga clic en **Descartar** en la página Envíos de usuario.</span><span class="sxs-lookup"><span data-stu-id="1e530-135">To clear these values, click **Discard** on the User submissions page.</span></span>
