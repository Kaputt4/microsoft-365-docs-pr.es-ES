---
title: Confirmar una notificación de retención
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar eDiscovery avanzado para enviar y hacer un seguimiento de las notificaciones de retención legal a través del correo electrónico, así como supervisar el estado de las obligaciones.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034890"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="7f807-103">Confirmar una notificación de retención</span><span class="sxs-lookup"><span data-stu-id="7f807-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="7f807-104">Al responder a una solicitud o investigación reglamentaria, es posible que deba informar a los administradores de su obligación de conservar la información almacenada electrónicamente (ESI) y cualquier material que pueda ser relevante para un asunto legal activo o inminente.</span><span class="sxs-lookup"><span data-stu-id="7f807-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="7f807-105">Una vez enviado, los equipos legales deben saber que cada administrador ha recibido, leído, comprendido y aceptado seguir las instrucciones indicadas.</span><span class="sxs-lookup"><span data-stu-id="7f807-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="7f807-106">Para ayudar a reducir el tiempo, el costo y el esfuerzo de realizar un seguimiento con los administradores, eDiscovery avanzado le permite enviar y realizar un seguimiento de las notificaciones de retención legal a través del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7f807-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="7f807-107">Además de los avisos por correo electrónico, cada administrador tendrá acceso a un Portal de cumplimiento individualizado, lo que permite a los administradores mantenerse informados de los cambios en su estado de obligación.</span><span class="sxs-lookup"><span data-stu-id="7f807-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="7f807-108">Notificaciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7f807-108">Email notifications</span></span>

<span data-ttu-id="7f807-109">Después de que se haya emitido una notificación de retención legal, cada administrador recibirá un correo electrónico único y personalizado que contiene el aviso de retención legal definido e instrucciones agregadas.</span><span class="sxs-lookup"><span data-stu-id="7f807-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="7f807-110">Vea cómo puede usar el  [Editor](using-communications-editor.md) de comunicación integrado para permitir que los administradores confirmen su aviso o accedan a su Portal de cumplimiento directamente desde su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7f807-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="7f807-111">En función de la configuración de la notificación de retención legal, los administradores pueden recibir los siguientes avisos:</span><span class="sxs-lookup"><span data-stu-id="7f807-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="7f807-112">**Aviso de emisión:** El primer aviso enviado a su administrador.</span><span class="sxs-lookup"><span data-stu-id="7f807-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="7f807-113">Este aviso contendrá las instrucciones de emisión y el aviso de retención anexado al final del mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f807-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="7f807-114">**Aviso de aviso:** Si se habilita, se enviará un aviso a los administradores en función de la frecuencia y el intervalo especificados.</span><span class="sxs-lookup"><span data-stu-id="7f807-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="7f807-115">Los avisos se seguirán enviados hasta que el administrador haya reconocido su aviso o hasta que se agote el número de avisos.</span><span class="sxs-lookup"><span data-stu-id="7f807-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="7f807-116">**Aviso de escalación:** Si se habilita, se enviará un aviso de escalación al administrador y al administrador después de agotar los avisos de aviso.</span><span class="sxs-lookup"><span data-stu-id="7f807-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="7f807-117">El sistema enviará automáticamente avisos de escalación hasta que se haya completado el número especificado de escalaciones o hasta que el administrador confirme su notificación de retención.</span><span class="sxs-lookup"><span data-stu-id="7f807-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="7f807-118">**Aviso de reemisión:** Durante el transcurso de una investigación, si se actualiza el contenido del aviso de retención, el aviso actualizado se enviará automáticamente al administrador.</span><span class="sxs-lookup"><span data-stu-id="7f807-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="7f807-119">**Aviso de versión:** Cuando un administrador se libere del caso, se le enviará el aviso de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="7f807-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="7f807-120">Portal de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7f807-120">Compliance Portal</span></span>

<span data-ttu-id="7f807-121">Además de las notificaciones por correo electrónico, cada administrador tendrá acceso a un portal de cumplimiento único.</span><span class="sxs-lookup"><span data-stu-id="7f807-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="7f807-122">A través del portal, cada administrador puede ver, acceder y reconocer sus notificaciones de retención activas.</span><span class="sxs-lookup"><span data-stu-id="7f807-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portal de cumplimiento para un administrador](../media/CustodianPortal.jpg)
