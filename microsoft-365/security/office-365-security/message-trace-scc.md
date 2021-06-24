---
title: Seguimiento de mensajes en el Microsoft 365 Defender web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden usar el vínculo seguimiento de mensajes en el portal de Microsoft 365 Defender para averiguar qué sucedió con los mensajes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108132"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="1e17e-103">Seguimiento de mensajes en el Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="1e17e-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e17e-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="1e17e-104">**Applies to**</span></span>
- [<span data-ttu-id="1e17e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1e17e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1e17e-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1e17e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1e17e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e17e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1e17e-108">El seguimiento de mensajes en el portal Microsoft 365 Defender sigue los mensajes de correo electrónico a medida que se desplazan por la Exchange Online organización.</span><span class="sxs-lookup"><span data-stu-id="1e17e-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="1e17e-109">Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje.</span><span class="sxs-lookup"><span data-stu-id="1e17e-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="1e17e-110">También muestra qué acciones se realizaron en el mensaje antes de alcanzar su estado final.</span><span class="sxs-lookup"><span data-stu-id="1e17e-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="1e17e-111">Puede usar la información del seguimiento de mensajes para responder eficazmente a las preguntas del usuario sobre lo que ocurrió con los mensajes, solucionar problemas de flujo de correo y validar los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="1e17e-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="1e17e-112">El seguimiento de mensajes en el portal Microsoft 365 Defender es solo un paso a través del seguimiento de mensajes en el centro Exchange administración.</span><span class="sxs-lookup"><span data-stu-id="1e17e-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="1e17e-113">Para obtener más información, vea [Seguimiento de mensajes en el centro de administración Exchange moderna.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="1e17e-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e17e-114">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="1e17e-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1e17e-115">Debe ser miembro de los grupos de  roles **Administración** de  la **organización,** Administración de cumplimiento o Servicio de Exchange Online para usar el seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1e17e-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="1e17e-116">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="1e17e-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1e17e-117">**Notas:** La pertenencia al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e17e-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1e17e-118">Para más información, consulte [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1e17e-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="1e17e-119">El número máximo de mensajes que se muestran en los resultados de un seguimiento de mensajes depende del tipo de informe seleccionado (vea la sección Elegir tipo [de](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) informe para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="1e17e-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="1e17e-120">El cmdlet [Get-HistoricalSearch de](/powershell/module/exchange/get-historicalsearch) Exchange Online PowerShell o PowerShell independiente de EOP devuelve todos los mensajes de los resultados.</span><span class="sxs-lookup"><span data-stu-id="1e17e-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="1e17e-121">Seguimiento de mensajes abierto</span><span class="sxs-lookup"><span data-stu-id="1e17e-121">Open message trace</span></span>

<span data-ttu-id="1e17e-122">En el portal de Microsoft 365 Defender ( ), vaya a <https://security.microsoft.com> **Correo electrónico & colaboración Exchange** seguimiento de \> **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="1e17e-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="1e17e-123">O bien, para ir directamente a la página de seguimiento de mensajes, use <https://admin.exchange.microsoft.com/#/messagetrace> .</span><span class="sxs-lookup"><span data-stu-id="1e17e-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="1e17e-124">En este momento, se abre el seguimiento de mensajes en el EAC.</span><span class="sxs-lookup"><span data-stu-id="1e17e-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="1e17e-125">Para obtener más información, vea [Seguimiento de mensajes en el centro de administración Exchange moderna.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="1e17e-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
