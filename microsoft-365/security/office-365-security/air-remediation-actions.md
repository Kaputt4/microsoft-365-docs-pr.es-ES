---
title: Acciones de corrección en Office 365 de investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información sobre las acciones de corrección en la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261057"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="d1ab9-104">Acciones de corrección tras una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="d1ab9-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="d1ab9-105">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="d1ab9-105">Remediation actions</span></span>

<span data-ttu-id="d1ab9-106">[Capacidades automatizadas de investigación y respuesta](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) en Office 365 Advanced Threat Protection incluye ciertas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="d1ab9-107">Siempre que se ejecuta una investigación automatizada o se ha completado, normalmente verá una o más acciones de corrección que requieren la aprobación del equipo de operaciones de seguridad para continuar.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="d1ab9-108">En la tabla siguiente se resumen las acciones de corrección disponibles actualmente en la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="d1ab9-109">Acción</span><span class="sxs-lookup"><span data-stu-id="d1ab9-109">Action</span></span> | <span data-ttu-id="d1ab9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1ab9-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="d1ab9-111">Bloquear URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="d1ab9-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="d1ab9-112">Protéjase contra mensajes de correo electrónico y documentos que contienen direcciones URL malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="d1ab9-113">Esto permite el bloqueo de vínculos malintencionados y de todas las páginas web relacionadas a través de [vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) cuando el usuario hace clic en un vínculo de un archivo existente de Office o en un mensaje de correo electrónico anterior.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="d1ab9-114">Correo electrónico de eliminación de software</span><span class="sxs-lookup"><span data-stu-id="d1ab9-114">Soft delete email</span></span>  |<span data-ttu-id="d1ab9-115">Eliminar temporalmente mensajes de correo electrónico específicos del buzón de un usuario</span><span class="sxs-lookup"><span data-stu-id="d1ab9-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="d1ab9-116">Eliminación temporal de clústeres de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d1ab9-116">Soft delete email clusters</span></span>  |<span data-ttu-id="d1ab9-117">Eliminación temporal de mensajes de correo malintencionado que coinciden con una consulta de los buzones de todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="d1ab9-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="d1ab9-118">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="d1ab9-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="d1ab9-119">Quita la regla de reenvío del buzón de un usuario final específico.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="d1ab9-120">Aprobar (o rechazar) acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="d1ab9-120">Approve (or reject) pending actions</span></span>

![Página de acción de investigaciones de aire](../../media/air-investigationactionspage.png)

<span data-ttu-id="d1ab9-122">Mientras ve los [detalles de una investigación](air-view-investigation-results.md), puede aprobar o rechazar cualquier acción de corrección pendiente.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="d1ab9-123">Le recomendamos hacerlo tan pronto como sea posible para que las investigaciones automatizadas se completen.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1ab9-124">Es necesario disponer de los permisos adecuados para aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="d1ab9-125">Consulte [permisos necesarios para usar la funcionalidad de Air](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="d1ab9-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="d1ab9-126">Seleccione la ficha **acciones** .</span><span class="sxs-lookup"><span data-stu-id="d1ab9-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="d1ab9-127">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-127">Select an item in the list.</span></span> <span data-ttu-id="d1ab9-128">(Esto activa los botones aprobar y rechazar).</span><span class="sxs-lookup"><span data-stu-id="d1ab9-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="d1ab9-129">Revise la información disponible de los elementos seleccionados y, a continuación, apruebe o rechace las acciones.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="d1ab9-130">**APPROVE** permite que se inicie la corrección.</span><span class="sxs-lookup"><span data-stu-id="d1ab9-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="d1ab9-131">**Rechazar** no realiza ninguna acción adicional</span><span class="sxs-lookup"><span data-stu-id="d1ab9-131">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1ab9-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d1ab9-132">Next steps</span></span>

- [<span data-ttu-id="d1ab9-133">Información sobre la guía de seguridad de usuario comprometida</span><span class="sxs-lookup"><span data-stu-id="d1ab9-133">Learn about the compromised user security playbook</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [<span data-ttu-id="d1ab9-134">Ver los informes de ATP</span><span class="sxs-lookup"><span data-stu-id="d1ab9-134">View your ATP reports</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)