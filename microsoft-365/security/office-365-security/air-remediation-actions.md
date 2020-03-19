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
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836863"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="3ab4f-104">Acciones de corrección tras una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="3ab4f-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="3ab4f-105">Acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="3ab4f-105">Remediation actions</span></span>

<span data-ttu-id="3ab4f-106">La [funcionalidad de investigación y respuesta automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) en [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 incluyen determinadas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="3ab4f-107">Siempre que se ejecuta una investigación automatizada o se ha completado, normalmente verá una o más acciones de corrección que requieren la aprobación del equipo de operaciones de seguridad para continuar.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="3ab4f-108">En la tabla siguiente se resumen las acciones de corrección disponibles actualmente en ATP de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="3ab4f-109">Acción</span><span class="sxs-lookup"><span data-stu-id="3ab4f-109">Action</span></span> | <span data-ttu-id="3ab4f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ab4f-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="3ab4f-111">Bloquear URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="3ab4f-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="3ab4f-112">Protege contra mensajes de correo electrónico y documentos que contienen direcciones URL malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="3ab4f-113">Esto permite el bloqueo de vínculos malintencionados y de todas las páginas web relacionadas a través de [vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) cuando el usuario hace clic en un vínculo de un archivo existente de Office o en un mensaje de correo electrónico anterior.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="3ab4f-114">Correo electrónico de eliminación de software</span><span class="sxs-lookup"><span data-stu-id="3ab4f-114">Soft delete email</span></span>  |<span data-ttu-id="3ab4f-115">Eliminar de forma temporal los mensajes de correo electrónico específicos del buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="3ab4f-116">Un mensaje eliminado temporalmente se mueve a la carpeta elementos recuperables de un usuario y se conserva hasta que expira el período de retención de elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="3ab4f-117">Eliminación temporal de clústeres de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3ab4f-117">Soft delete email clusters</span></span>  |<span data-ttu-id="3ab4f-118">Eliminar de forma temporal los mensajes de correo malintencionado que coinciden con una consulta de todos los buzones de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="3ab4f-119">Los mensajes eliminados temporalmente se mueven a la carpeta de elementos recuperables de los usuarios y se conservan hasta que expira el período de retención de elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="3ab4f-120">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="3ab4f-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="3ab4f-121">Quita una regla de reenvío de un buzón de correo del usuario final específico.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="3ab4f-122">En Office 365 ATP, no se realizan automáticamente acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="3ab4f-123">Las acciones de corrección solo se realizan tras la aprobación del equipo de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="3ab4f-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="3ab4f-124">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="3ab4f-124">Next steps</span></span>

- [<span data-ttu-id="3ab4f-125">Ver acciones de corrección pendientes o realizadas tras una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="3ab4f-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="3ab4f-126">Detalles y resultados de una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="3ab4f-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)